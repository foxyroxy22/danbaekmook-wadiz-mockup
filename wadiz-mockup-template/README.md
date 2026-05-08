# 🛒 와디즈 상세페이지 목업 템플릿

클라이언트에게 보여줄 와디즈 펀딩 상세페이지 목업을 빠르게 만들 수 있는 HTML 템플릿입니다.  
새 상품이 생길 때마다 이미지와 텍스트만 교체해서 바로 사용할 수 있어요.

**🔗 라이브 데모:** `https://[foxyroxy22].github.io/wadiz-mockup-template/`

---

## 📁 폴더 구조

```
wadiz-mockup-template/
│
├── index.html                  ← 메인 목업 파일 (여기서 모든 수정)
│
├── images/
│   ├── thumbnails/             ← 상단 슬라이더 이미지 (7장)
│   │   ├── thumb-01.jpg
│   │   ├── thumb-02.jpg
│   │   ├── thumb-03.jpg
│   │   ├── thumb-04.jpg
│   │   ├── thumb-05.jpg
│   │   ├── thumb-06.jpg
│   │   └── thumb-07.jpg
│   │
│   └── detail/                 ← 상세페이지 본문 이미지 (기본 20장, 필요 시 html 코드 복사하여 사용)
│       ├── detail-01.jpg
│       ├── detail-02.jpg
│       ├── detail-03.jpg
│       ├── ...
│       └── detail-20.jpg
│
└── README.md
```

---

## 🚀 새 상품 목업 만드는 방법

### STEP 1 — 이미지 준비 & 저장

#### 썸네일 이미지 (슬라이더용, 최대 7장)

- **저장 위치:** `images/thumbnails/` 폴더
- **파일명:** `thumb-01.jpg` ~ `thumb-07.jpg` 순서대로
- **권장 사이즈:** `750 × 450px` (5:3 비율)
- **형식:** JPG 또는 PNG 또는 GIF

```
images/thumbnails/thumb-01.jpg  ← 첫 번째 슬라이드 (가장 중요한 이미지)
images/thumbnails/thumb-02.jpg
...
```

#### 상세페이지 이미지 (본문용, 기본 20장)

- **저장 위치:** `images/detail/` 폴더
- **파일명:** `detail-01.jpg` ~ `detail-20.jpg` 순서대로
- **권장 너비:** `740px` (세로 길이 자유)
- **형식:** JPG 또는 PNG 또는 GIF

```
images/detail/detail-01.jpg  ← 첫 번째 상세 이미지 (오프닝)
images/detail/detail-02.jpg
...
```

> 💡 이미지가 7장 미만이라면 없는 번호는 `src=""` 그대로 두면 플레이스홀더가 표시됩니다.

---

### STEP 2 — index.html 열어서 내용 수정

메모장, VS Code, 어떤 에디터로든 `index.html`을 열고 아래 항목들을 찾아서 수정하세요.  
`Ctrl+F`로 검색하면 빠르게 찾을 수 있어요.

---

#### ① 썸네일 이미지 경로 연결

검색어: `썸네일 이미지 7장 src만 교체`

```html
<!-- 이렇게 생긴 부분을 찾아서 src에 경로를 넣으세요 -->
<div class="thumb-slide active">
  <img src="images/thumbnails/thumb-01.jpg" alt="썸네일1" />
</div>
<div class="thumb-slide">
  <img src="images/thumbnails/thumb-02.jpg" alt="썸네일2" />
</div>
<!-- ... thumb-07까지 동일하게 -->
```

---

#### ② 상세페이지 이미지 경로 연결

검색어: `상세페이지 이미지 20장`

```html
<!-- 이렇게 생긴 img 태그 20개를 찾아서 src에 경로를 넣으세요 -->
<img
  class="story-img-item"
  src="images/detail/detail-01.jpg"
  alt="상세페이지 이미지 01"
/>
<img
  class="story-img-item"
  src="images/detail/detail-02.jpg"
  alt="상세페이지 이미지 02"
/>
<!-- ... 최대 20개 -->
```

---

#### ③ 브랜드명 & 제품명

검색어: `BAROSSOK`

```html
<!-- 브랜드명 -->
<div class="sb-brand-name">BAROSSOK</div>
← 브랜드명으로 교체

<!-- 제품 제목 -->
<div class="sb-title">
  [단백질 6g] 탱글한 식물성 단백묵, 와사비간장 소스 포함!<br />by BAROSSOK
  (바로쏙)
</div>
← 제품명으로 교체
```

---

#### ④ 펀딩 달성률 & 서포터 수 & 남은 기간

검색어: `달성률`

```html
<div class="sb-funding-rate">219<span>%</span></div>
← 달성률 숫자 교체

<div class="sb-progress-bar" style="width: 219%"></div>
← 동일하게 교체 (100% 초과 시 자동으로 꽉 참)

<div class="sb-stat-num">219%</div>
← 달성률
<div class="sb-stat-num">142명</div>
← 서포터 수
<div class="sb-stat-num">12일</div>
← 남은 기간
```

---

#### ⑤ 가격

검색어: `sb-price`

```html
<div class="sb-price-original">15,000원</div>
← 정가 (없으면 삭제)
<div class="sb-price">
  <span class="sb-price-discount">20%</span> ← 할인율 12,000<span
    class="sb-price-unit"
    >원~</span
  >
  ← 최저 시작 가격
</div>
```

---

#### ⑥ 리워드 옵션

검색어: `sb-option`

```html
<div class="sb-option selected">
  <div class="sb-option-badge">인기</div>
  ← 뱃지 (없으면 줄 삭제)
  <div class="sb-option-name">오리지널 단백묵 2팩</div>
  ← 옵션명
  <div class="sb-option-desc">오리지널 맛 × 2개<br />와사비간장 소스 포함</div>
  ← 옵션 설명
  <div class="sb-option-price">12,000원</div>
  ← 옵션 가격
</div>
```

- 옵션이 더 필요하면 `<div class="sb-option">...</div>` 블록을 복사해서 추가
- 옵션이 적으면 블록 삭제

---

#### ⑦ AI 스토리 요약 (썸네일 아래 박스)

검색어: `ai-summary-item`

```html
<div class="ai-summary-item">
  <div class="emoji">🧊</div>
  <div class="ai-summary-item-body">
    <strong>핵심 포인트 제목</strong>
    <span>한 줄 설명</span>
  </div>
</div>
```

- 항목 3개 권장, 이모지와 텍스트 자유롭게 수정

---

#### ⑧ 배송 안내

검색어: `sb-delivery`

```html
<div class="sb-delivery">
  <strong>📦 배송 안내</strong><br />
  아이스박스 + 아이스팩 동봉<br />
  금요일 10시 이후 주문 → 화요일 발송<br />
  신선식품 특성상 단순변심 반품 불가
</div>
```

---

#### ⑨ 카테고리 / 브레드크럼

검색어: `건강식품`

```html
<div class="breadcrumb">
  <a href="#">홈</a> <span>›</span> <a href="#">푸드·음료</a> <span>›</span> ←
  카테고리로 교체 <a href="#">건강식품</a> <span>›</span> ← 서브카테고리로 교체
  <span style="color:#555;">BAROSSOK 단백묵</span> ← 제품명으로 교체
</div>
```

---

## 🌐 GitHub Pages로 배포하기

한 번만 설정해두면 이후엔 이미지 올리고 push만 해도 URL이 자동 업데이트돼요.

### 처음 설정 (1회만)

1. **GitHub에서 새 레포지토리 생성**
   - 이름: `wadiz-mockup-template` (또는 원하는 이름)
   - Public으로 설정 (Pages 무료 사용 위해)

2. **파일 업로드**

   ```bash
   git init
   git add .
   git commit -m "첫 번째 목업 템플릿"
   git remote add origin https://github.com/[유저명]/wadiz-mockup-template.git
   git push -u origin main
   ```

3. **GitHub Pages 활성화**
   - 레포지토리 → `Settings` → 왼쪽 메뉴 `Pages`
   - Source: `Deploy from a branch`
   - Branch: `main` / `/ (root)` 선택 → **Save**
   - 몇 분 뒤 `https://[유저명].github.io/wadiz-mockup-template/` URL 생성 완료!

### 새 상품 목업할 때마다

```bash
# 1. 이미지 교체 (images 폴더에 새 이미지 저장)
# 2. index.html 텍스트 수정
# 3. GitHub에 push

git add .
git commit -m "새 상품명 목업"
git push
```

→ 1~2분 후 URL 자동 반영 ✅

---

## 💡 팁

| 상황                           | 해결법                                                     |
| ------------------------------ | ---------------------------------------------------------- |
| 이미지가 7장보다 적을 때       | 없는 thumb-xx.jpg는 `src=""` 그대로 두면 플레이스홀더 표시 |
| 상세 이미지가 20장보다 적을 때 | 남은 `<img>` 태그는 `src=""` 그대로 두거나 줄 삭제         |
| 옵션이 2개일 때                | `sb-option` 블록 1개 삭제                                  |
| 클라이언트에게 공유할 때       | GitHub Pages URL 그대로 전달 (로그인 불필요)               |
| 목업 여러 개 관리하고 싶을 때  | `index.html`을 `상품명.html`로 복사해서 각각 수정          |

---

## 📝 수정 체크리스트

새 상품 목업 시 이것만 체크하세요:

- [ ] `images/thumbnails/` 에 thumb-01~07.jpg 저장
- [ ] `images/detail/` 에 detail-01~20.jpg 저장
- [ ] 썸네일 `<img src="">` 경로 연결 (7개)
- [ ] 상세 `<img src="">` 경로 연결
- [ ] 브랜드명 & 제품명 수정
- [ ] 달성률 & 서포터 수 & 남은 기간 수정
- [ ] 가격 & 할인율 수정
- [ ] 리워드 옵션 수정
- [ ] AI 스토리 요약 3줄 수정
- [ ] 배송 안내 수정
- [ ] `git push` → URL 확인

---

_Made with ❤️ for Wadiz mockup presentations_
