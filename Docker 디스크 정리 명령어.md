## 🧹 Docker 디스크 정리 명령어

### 1️⃣ 현재 디스크 사용량 확인

```bash
# Docker가 사용 중인 디스크 확인
docker system df

# 상세 정보
docker system df -v
```

### 2️⃣ 안전한 정리 (사용하지 않는 것만)

```bash
# 사용하지 않는 모든 것 정리 (안전, 추천)
docker system prune -a

# 볼륨까지 포함해서 정리 (주의!)
docker system prune -a --volumes

# 빌드 캐시만 정리
docker builder prune -a
```

### 3️⃣ 개별 정리

```bash
# 1. 중지된 컨테이너 모두 삭제
docker container prune

# 2. 사용하지 않는 이미지 삭제
docker image prune -a

# 3. 사용하지 않는 볼륨 삭제 (주의!)
docker volume prune

# 4. 사용하지 않는 네트워크 삭제
docker network prune

# 5. 빌드 캐시 삭제
docker builder prune
```

### 4️⃣ 강력한 정리 (모든 것 삭제)

```bash
# ⚠️ 경고: 실행 중인 컨테이너 제외하고 모두 삭제
docker system prune -a -f --volumes

# 모든 컨테이너 중지 후 삭제
docker stop $(docker ps -aq)
docker rm $(docker ps -aq)

# 모든 이미지 삭제
docker rmi $(docker images -q)

# 모든 볼륨 삭제 (데이터베이스 데이터도 삭제됨!)
docker volume rm $(docker volume ls -q)
```

## 🎯 추천하는 정리 순서 (개발 서버)

```bash
# 1. 현재 상태 확인
docker system df

# 2. 서비스 중지 (필요시)
docker-compose -f docker-compose.full.yml down

# 3. 안전하게 정리 (대화형)
docker system prune -a

# 입력 프롬프트가 나오면 'y' 입력
# WARNING! This will remove:
#   - all stopped containers
#   - all networks not used by at least one container
#   - all images without at least one container associated to them
#   - all build cache
# Are you sure you want to continue? [y/N] y

# 4. 결과 확인
docker system df

# 5. 서비스 재시작
docker-compose -f docker-compose.full.yml up -d
```

## 📊 각 항목별 공간 확보 효과

```bash
# Images (가장 많은 공간 차지)
docker image prune -a
# 예상: 5-20GB 확보

# Build cache (두 번째로 많음)
docker builder prune -a
# 예상: 2-10GB 확보

# Containers (적은 편)
docker container prune
# 예상: 100MB-1GB

# Volumes (데이터베이스 포함, 주의!)
docker volume prune
# 예상: 1-5GB (하지만 데이터 손실 가능)
```

## 💾 디스크 공간 추가 확보

```bash
# 1. 시스템 전체 디스크 확인
df -h

# 2. Docker가 차지하는 정확한 크기
du -sh /var/lib/docker

# 3. 로그 파일 정리
find /var/lib/docker/containers/ -name "*.log" -exec truncate -s 0 {} \;

# 4. 오래된 빌드 아티팩트 삭제
cd /root/akc-b2c
./gradlew clean
rm -rf ~/.gradle/caches/
```

## 🔧 즉시 실행할 명령어 (안전)

```bash
# 한 줄로 정리 (대화형 확인 있음)
docker system prune -a && docker builder prune -a

# 확인 없이 바로 정리 (-f 플래그)
docker system prune -a -f && docker builder prune -a -f
```

## ⚠️ 주의사항

1. **`docker volume prune`은 조심!**
   - MySQL 데이터가 볼륨에 있다면 데이터베이스가 초기화됩니다
   - 백업 후 실행하세요

2. **실행 중인 서비스는 영향 없음**
   - `prune` 명령어는 사용 중인 리소스는 삭제하지 않습니다

3. **정리 후 재빌드 필요**
   - 이미지를 삭제하면 다음 `docker-compose up` 시 다시 빌드됩니다

먼저 `docker system df`로 확인하고, `docker system prune -a`를 실행해보세요! 결과를 알려주시면 추가 조치를 알려드리겠습니다. 🚀