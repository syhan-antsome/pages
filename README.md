# 📚 GitHub Pages 문서 저장소

이 저장소는 **GitHub Pages**를 활용하여 개발 관련 문서들을 웹에서 쉽게 조회할 수 있도록 구성된 문서 호스팅 공간입니다.

## 🌐 접속 URL

**메인 페이지**: https://syhan-antsome.github.io/pages/

## 📋 문서 목록

현재 저장소에는 다음과 같은 문서들이 포함되어 있습니다:

### 1. 🏠 [메인 페이지](https://syhan-antsome.github.io/pages/)
- **파일**: `index.html`
- **설명**: 모든 문서로 쉽게 이동할 수 있는 네비게이션 페이지
- **특징**: 반응형 디자인, 호버 효과, 모바일 친화적

### 2. 👋 [Hello](https://syhan-antsome.github.io/pages/hello.html)
- **파일**: `hello.html`
- **설명**: 간단한 인사 페이지

### 3. 🔧 [DX Service Build and Modify](https://syhan-antsome.github.io/pages/dxservice_build_and_modify.html)
- **파일**: `dxservice_build_and_modify.html`
- **설명**: DX 서비스 빌드 및 수정 가이드
- **특징**: KaTeX 수식, Mermaid 다이어그램 지원

### 4. ⚙️ [서비스생성가이드](https://syhan-antsome.github.io/pages/service_mng.html)
- **파일**: `service_mng.html`
- **설명**: 서비스 생성 및 관리 가이드

### 5. 🔐 [소셜 로그인 시스템 가이드](https://syhan-antsome.github.io/pages/소셜로그인_절차_도식화.html)
- **파일**: `소셜로그인_절차_도식화.html`
- **설명**: Google, 카카오, 네이버 소셜 로그인 구현 가이드
- **특징**: 상세한 플로우 다이어그램, API 스펙, 코드 예제 포함

## 🚀 사용법

### 1. 문서 조회
브라우저에서 https://syhan-antsome.github.io/pages/ 에 접속하여 원하는 문서를 클릭합니다.

### 2. 직접 URL 접근
각 문서에 직접 접근할 수도 있습니다:
```
https://syhan-antsome.github.io/pages/{파일명}.html
```

### 3. 새 문서 추가 방법

#### Step 1: HTML 문서 작성
새로운 HTML 문서를 작성하여 이 저장소에 추가합니다.

#### Step 2: index.html 업데이트
`index.html` 파일을 열고 문서 목록에 새 항목을 추가합니다:

```html
<li class="document-item">
    <a href="새문서.html" class="document-link">
        <div class="document-title">📝 새 문서 제목</div>
        <div class="document-desc">새 문서에 대한 설명</div>
    </a>
</li>
```

#### Step 3: Git 커밋 및 푸시
```bash
git add .
git commit -m "Add new document: 새문서"
git push
```

#### Step 4: GitHub Pages 반영 확인
1-2분 후 https://syhan-antsome.github.io/pages/ 에서 새 문서를 확인할 수 있습니다.

## 📁 파일 구조

```
pages/
├── README.md                          # 이 파일
├── LICENSE                            # 라이선스 파일
├── index.html                         # 메인 네비게이션 페이지
├── hello.html                         # Hello 페이지
├── dxservice_build_and_modify.html    # DX 서비스 가이드
├── dxservice_build_and_modify.md      # DX 서비스 가이드 (마크다운 원본)
├── service_mng.html                   # 서비스 생성 가이드
└── 소셜로그인_절차_도식화.html          # 소셜 로그인 가이드
```

## 🎨 디자인 특징

### index.html 페이지
- **반응형 디자인**: 다양한 화면 크기에 최적화
- **모던 UI**: 깔끔하고 직관적인 인터페이스
- **호버 효과**: 마우스 오버 시 시각적 피드백
- **이모지 활용**: 각 문서의 성격을 직관적으로 표현

### 개별 문서들
- **수식 지원**: KaTeX를 활용한 수학 수식 렌더링
- **다이어그램**: Mermaid를 활용한 플로우차트 및 시퀀스 다이어그램
- **코드 하이라이팅**: 다양한 프로그래밍 언어 구문 강조
- **반응형 레이아웃**: 모바일 및 태블릿 친화적 디자인

## 🔧 기술 스택

- **호스팅**: GitHub Pages
- **스타일링**: CSS3 (Flexbox, Grid)
- **수식**: [KaTeX](https://katex.org/)
- **다이어그램**: [Mermaid](https://mermaid.js.org/)
- **코드 하이라이팅**: highlight.js
- **아이콘**: Unicode Emoji

## 📝 작성 가이드라인

### HTML 문서 작성 시 권장사항

1. **메타 태그 포함**
```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>문서 제목</title>
```

2. **외부 라이브러리 활용**
```html
<!-- 수식 지원 -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex/dist/katex.min.css">

<!-- 다이어그램 지원 -->
<script type="module">
  import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
  mermaid.initialize({ startOnLoad: true });
</script>
```

3. **접근성 고려**
- 시맨틱 HTML 사용
- 적절한 헤딩 구조
- alt 텍스트 포함

## 🚀 GitHub Pages 설정

이 저장소는 GitHub Pages가 다음과 같이 설정되어 있습니다:

- **Source**: Deploy from a branch
- **Branch**: main
- **Folder**: / (root)
- **Custom domain**: 없음 (기본 github.io 도메인 사용)

## 📄 라이선스

이 프로젝트는 라이선스가 적용되어 있습니다. 자세한 내용은 [LICENSE](LICENSE) 파일을 참조하세요.

## 🤝 기여 방법

1. **이슈 제기**: 문서 오류나 개선 사항이 있으면 Issues에서 알려주세요
2. **직접 수정**: Fork → 수정 → Pull Request
3. **새 문서 제안**: 새로운 문서 아이디어가 있으면 Issues에서 제안해주세요

## 📞 문의

문서나 저장소에 대한 문의사항이 있으시면 GitHub Issues를 통해 연락해주세요.

---

**✨ 이 저장소는 개발 지식을 공유하고 문서화하여 누구나 쉽게 접근할 수 있도록 하는 것을 목표로 합니다.**