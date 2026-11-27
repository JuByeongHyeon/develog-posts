# [develog] MCP 기능이 나왔어요!

> 디벨로그에서 쓴 글 · 2026-11-20
>
> https://develog.develrocket.com/@wnqudgus1234/develog-mcp-기능이-나왔어요

> **요약**
>
> - 이제 내 AI 앱에서 디벨로그에 쓴 내 글을 찾아 읽을 수 있어요.
> - Claude, ChatGPT, Claude Code, Codex에서 연결돼요.
> - 읽기만 해요. 발행한 내 글만 보이고, 임시저장 글과 다른 사람 글은 안 보여요.
> - 설정 > 연결에서 연결하고, 언제든 끊을 수 있어요.

AI 앱이 디벨로그에서 내 글을 찾아 읽고, 그걸 바탕으로 답해요.

이번에 나온 MCP 연결 덕분이에요.
MCP는 AI 앱이 다른 서비스에 있는 내 데이터를 꺼내 쓰게 해 주는 연결 표준이에요.
AI 앱을 디벨로그에 한 번 연결해 두면, 대화하다가 언제든 내 글을 불러올 수 있어요.

## 만들게 된 계기

디벨로그에 글을 쓰는 건 나중에 다시 읽고 정리하기 위해서예요.  
그렇게 정리한 기록으로 어딘가에 나를 증명해야 할 때가 와요.

수강생도 있고, 여러 직무와 진로를 준비하는 분도 있어요.  
누구에게든 쌓인 기록은 곧 포트폴리오고 자기소개서예요.

그런데 지금은 내 글을 하나하나 열어 보면서 고치고 정리해야 해요.  
글이 쌓일수록 이 일이 점점 커져요.

그래서 그 일을 내 AI 앱이 대신할 수 있게 연결을 열었어요.

자기소개서를 쓰다 보면 예전에 쓴 글을 다시 찾게 돼요.  
한 달 동안 뭘 공부했는지 돌아보고 싶을 때도 있고요.

이제 AI 앱한테 부탁하면 돼요.

> "디벨로그에 쓴 글 중에 정보처리기사 공부한 글 찾아 줘."
>
> "그 글들 읽고 자기소개서 '성장 과정' 초안 써 줘."

## 할 수 있는 것, 없는 것

AI 앱이 디벨로그에서 하는 일은 찾기와 읽기뿐이에요.

- **내 글 찾기**: 검색어나 기간으로 내 글을 찾아요. 제목, 요약, 본문, 태그에서 찾고 최신 글부터 20개씩 보여 줘요.
- **내 글 읽기**: 찾은 글의 본문을 읽어요.

안 보이는 것도 있어요.

- 임시저장 글은 안 보여요. 발행한 글만 보여요.
- 다른 사람 글은 안 보여요.
- 글을 쓰거나 고치거나 지우지 못해요.

## 쓸 수 있는 AI 앱

- Claude
- ChatGPT
- Claude Code
- Codex

Gemini CLI도 연결돼요.
다만 Google이 2026년 6월 18일부터 무료 개인 계정과 Google AI Pro/Ultra 계정에서 Gemini CLI 지원을 끝냈어요.
유료 API 키나 회사 라이선스로 쓰는 분만 해당돼요.

이 밖의 앱은 아직 연결되지 않아요.

## 연결하는 법

설정 > 연결로 가 보세요. 메뉴에 BETA 표시가 붙어 있어요.
MCP 카드에 앱별 연결 방법이 있어요.

### Claude

**1.** MCP 카드에서 **[Claude에 연결]**을 눌러요.

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1795131490397-d7j4sc/1-mcp-card.png)

**2.** Claude의 "커스텀 커넥터 추가" 창이 열려요. 이름(디벨로그)과 주소가 이미 채워져 있어요.  

연결 대상이 develog.develrocket.com인지 보고 **[계속]**을 눌러요.

<img src="https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1795131490403-olijwn/2-add-dialog.png" alt="" width="715" height="447">

**3.** 몇 초 확인한 뒤 다음 화면이 떠요. "감지됨"으로 골라진 설정은 그대로 두고, 맨 아래 **[추가]**를 눌러요.

<img src="https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1795131490408-l5dbkd/3-add-button.png" alt="" width="567" height="928">

**4.** "디벨로그: 아직 연결되지 않았습니다"가 보이면 **[연결]**을 눌러요.

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1795131490423-3lqoa9/3b-claude-connect.png)

**5.** 디벨로그 허락 화면이 뜨면 **[허락]**을 눌러요. 무엇을 보고 누르면 되는지는 아래 "허락 화면"에 적어 두었어요.

**6.** Claude로 돌아오면 연결이 끝나요. 도구에 "내 글 찾기", "내 글 읽기"가 보여요.

Claude 무료 요금제는 사용자 지정 커넥터를 1개까지 추가할 수 있어요.
Team, Enterprise 요금제는 조직 관리자만 추가할 수 있어요.

### ChatGPT

ChatGPT는 연결 주소를 직접 넣어요. MCP 카드의 연결 주소가 이거예요.

```
https://develog.develrocket.com/api/mcp

```

1. MCP 카드에서 연결 주소를 복사해요.
2. ChatGPT에서 MCP 서버를 직접 추가하는 메뉴를 열어요. (Plugins 화면 [+] > Add custom MCP server)
3. 복사한 주소를 붙여 넣고 추가해요.
4. 디벨로그 허락 화면이 뜨면 **[허락]**을 눌러요.

ChatGPT는 요금제에 따라 이 메뉴가 안 보일 수 있어요.

### 터미널에서 쓰는 앱

Claude Code, Codex는 명령을 붙여 넣으면 돼요.

Claude Code는 MCP 카드에 있는 명령을 복사해요.

```bash
claude mcp add --transport http develog https://develog.develrocket.com/api/mcp

```

그다음 Claude Code 안에서 `/mcp`를 열고 develog를 골라 인증하면 브라우저에 허락 화면이 떠요.

Codex는 두 줄이에요. 두 번째 줄에서 허락 화면이 떠요.

```bash
codex mcp add develog --url https://develog.develrocket.com/api/mcp
codex mcp login develog

```

Gemini CLI는 이렇게 추가하고, Gemini CLI 안에서 `/mcp auth develog`를 입력해요. 위에 쓴 계정 조건이 있어요.

```bash
gemini mcp add --transport http develog https://develog.develrocket.com/api/mcp

```

### 허락 화면

어느 앱이든 마지막엔 디벨로그 허락 화면이 떠요.

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1795131490435-fgwxb2/4-consent.png)

[허락]을 누르기 전에 두 군데만 봐 주세요.

- **돌아갈 곳**: 내가 연결하려는 앱이 맞나요? Claude면 claude.ai, ChatGPT면 chatgpt.com처럼 그 앱 주소가 보여요. Claude Code처럼 내 컴퓨터에서 도는 앱은 localhost나 127.0.0.1로 보여요.
- **연결될 계정**: 내 디벨로그 계정이 맞나요?

내가 직접 시작한 연결이 아니라면 **[거절]**을 눌러 주세요.

## 이렇게 써 보세요

- "지난달에 쓴 글 중에 일본어 공부한 글만 찾아 줘."
- "이번 주에 쓴 글 읽고 공부한 것 목록으로 만들어 줘."
- "디벨로그 글 중에 포트폴리오에 넣을 만한 거 5개 골라 줘. 이유도 한 줄씩."
- "내 독서 기록 글로 자기소개서 '지원 동기' 초안 써 줘."

## 끊고 싶을 때

설정 > 연결 아래쪽 "연결된 AI 앱"에 연결한 앱이 보여요.
연결한 날과 마지막으로 쓴 때도 나와요.

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1795131625349-31tc9z/5-connected-apps.png)

**[연결 끊기]**를 누르면 그 앱은 더 이상 내 글을 읽을 수 없어요.
이미 대화로 가져간 내용은 AI 앱에 남아 있을 수 있어요.
AI 앱 쪽에 남은 커넥터는 그 앱 설정에서 지우면 돼요.

## 자주 묻는 질문

### Q. 글쓰기 기능은 없나요?

아직은 없어요. 지금은 읽기만 돼요.  
BETA라서 먼저 읽기부터 열었어요.

글쓰기도 중요하지만, 글을 작성하는 행위의 본질은 디벨로그에서 직접 작성하는 데 있다고 봅니다.  
여러분들이 감사하게도 열심히 써 주시거든요!

해서! 다양한 방면으로 어떤 도구를 내놓을지 고민하고 있습니다.

### Q. 다른 AI 앱에 연결했는데 안 돼요

지금은 Claude, Claude Code, ChatGPT, Codex, Gemini CLI만 연결돼요.

[허락]을 누르면 디벨로그는 AI 앱에 "열쇠"를 보내요. 이 열쇠가 있어야 AI 앱이 내 글을 읽을 수 있어요.  
그래서 열쇠를 보낼 곳을 미리 확인한 앱 주소로만 정해 뒀어요. 모르는 곳으로 열쇠가 새어 나가지 않게요.  
목록에 없는 앱으로 연결하면 디벨로그에 "연결할 수 없어요" 화면이 떠요.

써 보고 싶은 앱이 있으면 댓글로 알려 주세요.

### Q. Gemini 앱(웹, 모바일)은 안 되나요?

지금은 안 돼요.  
Gemini 앱에서 MCP 서버를 직접 연결하는 기능은 아직 미국, 영어 설정 같은 조건이 붙어 있어서 이번에는 넣지 않았어요.

### Q. 다른 사람이 내 글을 자기 AI 앱으로 꺼내 볼 수 있나요?

아니요. 허락 화면에서 확인한 내 계정의 글만, 내가 허락한 AI 앱에서만 보여요.  
남이 보내 준 링크로 허락 화면이 떴다면 [거절]을 눌러 주세요. 내가 직접 시작한 연결만 허락하면 돼요.

---

아직 BETA예요.
써 보다가 불편한 점이나 있었으면 하는 기능이 있으면 댓글로 알려 주세요.
