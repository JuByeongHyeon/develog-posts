# 어도비 딥브러쉬 / 핸즈온 / 커스텀 필터 직접 써 본 후기, 되는 것과 안 되는 것

> 디벨로그에서 쓴 글 · 2026-11-13
>
> https://develog.develrocket.com/@wnqudgus1234/adobe-labs-deep-brush-hands-on-test

**한눈에 보기 (2026년 11월 13일 테스트 기준)**

- 딥브러쉬: 벽 그림자 위에 칠하기, 티셔츠에 글자 넣기는 **잘 됐습니다.** 조명을 바꾸면 몸의 명암은 바뀌었지만 벽 그림자는 그대로였고, 사람 뒤로만 칠하기는 이 사진에서는 안 됐습니다
- 핸즈온: 소파를 잡아 늘이니 약 30초 뒤 후보 3장이 나왔습니다. 다만 **내 사진 업로드는 지원하지 않아** 어도비 예시 사진만 쓸 수 있습니다
- 커스텀 필터: 물건 하나를 바꾸는 도구가 아니라 **사진 전체에 거는 필터를 만드는 도구**였습니다. 필터와 슬라이더 이름까지 적어 요청하니 프롬프트 한 번으로 만들어졌습니다
- 횟수: 딥브러쉬는 사진을 올릴 때, 핸즈온은 Refresh(생성)를 누를 때 하루 5회에서 1회씩 줄었습니다. 커스텀 필터는 입장 화면에 "생성 크레딧을 쓰지 않는다"고 적혀 있습니다

[지난 글](https://develog.develrocket.com/@wnqudgus1234/adobe-max-2026-sneaks-deep-brush)에서 어도비 맥스(Adobe MAX) 2026 스닉스(Sneaks)에서 공개된 연구 기능 10개를 소개했습니다. 이번 글에서는 그중 지금 바로 써 볼 수 있는 딥브러쉬, 핸즈온과 포토샵 실험 기능 커스텀 필터를 직접 테스트한 결과를 정리합니다.

테스트에는 AI로 만든 가상 인물 사진(콘크리트 벽 앞, 흰 티셔츠, 머그컵)을 썼습니다. 실제 인물이 아닙니다.

## 1. 써 보기 전에 알아 둘 것

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1794533000309-c5j3wm/p01-playground.jpg)

*이미지: Adobe Labs Playground 첫 화면*

세 도구 모두 [Adobe Labs Playground](https://labs.adobe.com/playground)에서 들어갈 수 있습니다. 입장 화면에 적힌 조건은 다음과 같습니다.

- **개인 Adobe 계정**으로 로그인해야 합니다
- 결과물은 **개인 / 비상업 용도**로만 쓰고 공유할 수 있습니다 (SNS 포함)
- 베타 약관이 적용되며, 기능이 언제든 바뀌거나 사라질 수 있습니다


| 도구     | 주소                                                                                | 내 사진 올리기   | 횟수                     |
| :----- | :-------------------------------------------------------------------------------- | :--------: | :--------------------- |
| 딥브러쉬   | [projectdeepbrush.adobelabs.com](https://projectdeepbrush.adobelabs.com/)         | O          | 사진 올릴 때 1회 (하루 5회)     |
| 핸즈온    | [projecthandson.adobelabs.com](https://projecthandson.adobelabs.com/)             | X (예시 사진만) | Refresh 1번에 1회 (하루 5회) |
| 커스텀 필터 | [projectcustomfilters.adobelabs.com](https://projectcustomfilters.adobelabs.com/) | O          | 입장 화면 기준 크레딧 안 씀       |


딥브러쉬와 핸즈온 입장 화면 기준으로, 하루 5회는 매일 오전 9시(한국 시각)에 다시 채워집니다. 커스텀 필터는 테스트할 때 포토샵 주소(try-filters.photoshop.adobe.com)로 열렸고, 화면 위에 포토샵 체험판 버튼("Start free trial")이 있었습니다.

## 2. 딥브러쉬 (Project Deep Brush): 그림자를 따라 칠해집니다

### 사용법

1. 사진을 올립니다 (이때 1회 차감)
2. "Getting your photo ready"(사진 준비) 과정이 끝날 때까지 기다립니다
3. 왼쪽 도구에서 붓, 글자(Text), 오른쪽에서 조명(Lights)을 골라 칠합니다

칠하기, 글자, 조명은 몇 번을 해도 횟수가 줄지 않았습니다.

### 테스트 1. 벽 그림자 위에 칠하기: 됐습니다

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1794533000366-yjx9w1/p02-db-shadow.jpg)

*이미지: 직접 테스트한 화면 (Adobe Labs Project Deep Brush)*

사진 오른쪽 벽(사람 그림자가 진 쪽)에 주황색으로 세로줄을 그었습니다. 머리와 어깨 그림자가 **페인트 위에 그대로 진하게 남고**, 콘크리트 결도 비쳐 보였습니다. 시연 영상에서 본 "붓이 사진 안으로 들어간다"는 느낌이 그대로 났습니다.

### 테스트 2. 티셔츠에 글자 넣기: 됐습니다

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1794533000372-68p8km/p04-db-text.jpg)

*이미지: 직접 테스트한 화면 (Adobe Labs Project Deep Brush). 글자 위 세로 막대는 편집 화면의 글자 위치 손잡이입니다.*

글자 도구로 "HELLO"를 넣었습니다. 글자가 **티셔츠 주름의 음영을 그대로 받고**, 첫 글자 "H"는 소매 쪽으로 꺾여 붙었습니다. 옷에 로고를 넣은 모습을 미리 보는 데 써 볼 만합니다.

### 테스트 3. 조명 방향 바꾸기: 몸의 명암만 바뀌었습니다

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1794533000350-69ty6m/p03-db-light.jpg)

*이미지: 직접 테스트한 화면 (Adobe Labs Project Deep Brush). 글자 위 세로 막대는 편집 화면의 글자 위치 손잡이입니다.*

조명(Lights)을 오른쪽에서 비추도록 바꿨습니다.

- 얼굴, 컵, 청바지, 스툴의 밝고 어두운 부분이 바뀌고, 칠해 둔 페인트와 테스트 2에서 넣은 글자까지 빛을 받았습니다
- 빛 색을 파랗게 바꾸니 얼굴과 스툴에 푸른 기운이 돌았습니다
- 다만 이번 테스트에서는 **벽에 진 사람 그림자가 그대로**였습니다. 빛 방향을 바꿔도 그림자가 반대쪽으로 옮겨 가지 않았습니다

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1794533001320-b8wb51/p03b-db-light-ui-v2.jpg)

*이미지: 조명 설정 화면 (Adobe Labs Project Deep Brush)*

### 테스트 4. 사람 뒤로만 칠하기: 이 사진에서는 안 됐습니다

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1794533000377-7ttl8m/p05-db-mask.jpg)

*이미지: 직접 테스트한 화면 (Adobe Labs Project Deep Brush)*

가로줄을 그어서 사람 뒤 벽에만 칠해지게 하고 싶었습니다. 붓 옵션의 마스킹 값(Color, Distance 등)을 여러 값으로 바꿔 봤지만 줄이 셔츠 위에도 칠해졌습니다. 사람이 벽에 붙어 서 있어 사람과 벽의 거리 차이가 작은 사진이라 그럴 수 있습니다.

> 붓 옵션은 설정(톱니) => "Show context bar"를 Always로 바꾸면 화면 아래에 크기 / 단단함 / 투명도 / 마스킹 막대가 나옵니다.

## 3. 핸즈온 (Project Hands On): 손으로 잡아 늘이면 AI가 다시 그립니다

핸즈온은 11월 13일 기준 **내 사진 업로드를 지원하지 않았습니다.** 화면 어디에도 업로드 버튼이 없고, 어도비가 준비한 예시 사진(향수병, 소파, 사람 등 9장)만 고를 수 있습니다. 그래서 소파 예시로 테스트했습니다.  
[핸즈온](https://labs.adobe.com/sneaks/hands-on)

### 사용법

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1794533000357-03e3nr/p07-ho-menu.jpg)

*이미지: 직접 테스트한 화면, 어도비 예시 사진 (Adobe Labs Project Hands On)*

소파를 누르면 AI가 소파를 알아보고 조절 메뉴를 띄웠습니다. 왼팔 / 오른팔 곡선, 등받이 모양, 길이, 지우기가 나왔습니다.

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1794533001295-ojd51r/p08-ho-drag.jpg)

*이미지: 직접 테스트한 화면, 어도비 예시 사진 (Adobe Labs Project Hands On)*

"Couch length"(소파 길이)를 고르면 양쪽에 손잡이가 생깁니다. 오른쪽 손잡이를 끌어 소파를 길게 늘였습니다.

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1794533001301-depzqc/p09-ho-cands.jpg)

*이미지: 직접 테스트한 화면, 어도비 예시 사진 (Adobe Labs Project Hands On)*

Refresh를 누르니 약 30초 뒤 후보 3장이 나왔습니다. 마음에 드는 것을 고르고 Apply를 누르면 적용됩니다. **Refresh 1번에 하루 5회 중 1회**가 줄었습니다.

### 결과: 됐습니다

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1794533001315-4xxidd/p10-ho-before-after.jpg)

*이미지: 직접 테스트한 화면, 어도비 예시 사진 (Adobe Labs Project Hands On)*

쿠션, 단추, 다리까지 자연스럽게 늘어났습니다. 늘어난 소파는 오른쪽 스탠드와 작은 탁자 뒤쪽까지 이어져, 오른쪽 팔걸이 일부가 탁자에 가려졌습니다. "소파를 더 길게 해 줘"라고 프롬프트를 쓰는 대신, 얼마나 늘릴지를 손으로 정한다는 점이 다릅니다.

## 4. 커스텀 필터 (Project Custom Filters): 물건 바꾸기가 아니라 필터 만들기

커스텀 필터는 스닉스 10개에는 들어가지 않은 포토샵 실험 기능입니다. 오른쪽 AI 어시스턴트 창에 원하는 효과를 적으면 슬라이더가 달린 필터를 만들어 줍니다.

### 첫 시도: 물건 바꾸기를 요청하니 선택하라는 안내가 나왔습니다

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1794533001310-m8gbms/p11-cf-first-try.jpg)

*이미지: 직접 테스트한 화면 (Adobe Labs Project Custom Filters)*

처음에는 "티셔츠를 파란색으로 만들어 주고, 머그컵을 맥주로 바꿔 줄래?"라고 요청했습니다. 머그컵은 바뀌지 않아서 "티셔츠만 바꿔 줘"로 줄였더니, AI가 이렇게 답했습니다.

> 티셔츠만 바꾸려면 이미지에서 티셔츠 부분을 **더블클릭해 선택**해야 하고, 전체에 필터를 적용하면 배경과 피부까지 함께 파랗게 변한다.

커스텀 필터는 **사진 속 물건을 다른 물건으로 바꾸는 도구가 아니라**, 사진 전체(또는 고른 부분)의 색과 분위기를 바꾸는 필터를 만드는 도구였습니다. 티셔츠를 더블클릭해 고르는 방법은 이번에 해 보지 않았습니다.

### 두 번째 시도: 사진 전체 필터로 요청하니 만들어졌습니다

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1794533002013-vtp46l/p12-cf-screen-v2.jpg)

*이미지: 직접 테스트한 화면 (Adobe Labs Project Custom Filters)*

이번에는 필터 자체를 요청했습니다.

> Create a warm vintage film filter with film grain and a soft orange light leak from the left. Give me sliders for grain amount, warmth, and light leak strength.  
> (따뜻한 빈티지 필름 필터를 만들어 줘. 필름 입자와 왼쪽에서 들어오는 주황색 빛 번짐을 넣고, 입자 / 따뜻함 / 빛 번짐 세기 슬라이더를 만들어 줘)

약 30초 뒤 왼쪽에 **"Vintage Film Warmth"** 필터와 슬라이더 3개(Grain / Warmth / Leak)가 생겼습니다.

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1794533001304-mql3kt/p13-cf-compare.jpg)

*이미지: 직접 테스트한 화면 (Adobe Labs Project Custom Filters)*

기본값만으로도 사진이 따뜻한 필름 느낌으로 바뀌었고, Warmth와 Leak를 끝까지 올리니 전체가 노래지면서 왼쪽에서 빛이 번졌습니다. 사진 전체에 거는 필터로 요청하고 슬라이더 이름까지 적으니, 프롬프트 한 번으로 필터가 만들어졌습니다.

## 5. 한 줄 정리


| 도구     | 된 것                  | 안 된 것 (이번 테스트)                         | 참고                      | 횟수                 |
| :----- | :------------------- | :------------------------------------- | :---------------------- | :----------------- |
| 딥브러쉬   | 그림자 위에 칠하기, 옷에 글자 넣기 | 사람 뒤로만 칠하기 (이 사진에서), 조명 바꿀 때 벽 그림자 옮기기 | -                       | 사진 올릴 때 1회         |
| 핸즈온    | 소파 길이 늘이기 (후보 3장)    | -                                      | 내 사진 업로드 미지원 (11/13 기준) | Refresh 1번에 1회     |
| 커스텀 필터 | 말로 필터 + 슬라이더 만들기     | -                                      | 물건 바꾸기는 이 도구의 용도가 아님    | 크레딧 안 씀 (입장 화면 기준) |


세 도구 모두 아직 연구 단계의 미리보기(베타)라 결과가 매번 같지는 않을 수 있습니다. 그래도 "그림자를 따라 칠하는 붓"과 "손으로 잡아 늘이는 편집"은 지금 써 봐도 충분히 신기한 수준이었습니다.

## 자주 묻는 질문

**Q. 딥브러쉬, 핸즈온은 무료인가요?**  
A. 2026년 11월 13일 기준 Adobe Labs Playground에서 개인 Adobe 계정으로 무료로 써 볼 수 있습니다. 입장 화면 안내 기준 하루 5회까지 생성할 수 있고, 매일 오전 9시(한국 시각)에 다시 채워집니다.

**Q. 핸즈온에 내 사진을 올릴 수 있나요?**  
A. 2026년 11월 13일 기준으로는 업로드를 지원하지 않습니다. 어도비가 준비한 예시 사진 9장 중에서 골라 써야 합니다. 딥브러쉬와 커스텀 필터는 내 사진을 올릴 수 있습니다.

**Q. 딥브러쉬는 어떤 동작에서 횟수가 줄어드나요?**  
A. 테스트에서는 사진을 올릴 때 1회 줄었습니다. 올린 사진에 붓으로 칠하거나 글자를 넣거나 조명을 바꾸는 것은 횟수가 줄지 않았습니다.

**Q. 커스텀 필터로 사진 속 물건을 바꿀 수 있나요?**  
A. 테스트에서 머그컵을 맥주로 바꾸는 요청은 되지 않았습니다. 커스텀 필터는 물건을 바꾸는 도구가 아니라 사진의 색과 분위기를 바꾸는 필터를 만드는 도구이고, 특정 부분만 바꾸려면 그 부분을 더블클릭해 선택해야 한다고 AI 어시스턴트가 안내했습니다.

**Q. 만든 결과물을 상업적으로 써도 되나요?**  
A. 입장 화면 안내에 따르면 결과물은 개인 / 비상업 용도로만 쓰고 공유할 수 있습니다.

## 출처

- [Adobe Labs Playground](https://labs.adobe.com/playground)
- [Adobe Labs: Project Deep Brush](https://labs.adobe.com/sneaks/deep-brush)
- [Adobe Labs: Project Hands On](https://labs.adobe.com/sneaks/hands-on)
- [Adobe Blog: Adobe MAX 2026 Sneaks](https://blog.adobe.com/en/publish/2026/11/11/adobe-max-sneaks)
- [지난 글: 어도비 맥스 2026 스닉스 10개 정리](https://develog.develrocket.com/@wnqudgus1234/adobe-max-2026-sneaks-deep-brush)

---

*이 글은 어도비와 관련 없이 작성했으며, 어도비로부터 대가를 받지 않았습니다. 글 속 결과물은 Adobe Labs 미리보기(베타)로 만들었고, 화면 캡처와 예시 이미지의 저작권은 Adobe에 있습니다. 테스트 사진 속 인물은 AI로 만든 가상 인물입니다. Adobe, Adobe Labs, Photoshop, Adobe MAX는 Adobe의 상표입니다.*
