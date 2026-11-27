# [develog] MCP 기능 수정했어요!

> 디벨로그에서 쓴 글 · 2026-11-24
>
> https://develog.develrocket.com/@wnqudgus1234/develog-mcp-기능-수정했어요

> **요약**
>
> - Claude Code로 디벨로그 MCP를 연결하면 "403 Forbidden"이 뜨던 문제를 고쳤어요.
> - 설정의 [Claude에 연결] 버튼으로 연결하는 Claude(웹, 앱)는 처음부터 잘 됐어요.
> - Claude Code 연결 명령도 바꿨어요. 이제 어느 폴더에서 열어도 디벨로그가 보여요.
> - 문제를 찾게 도와주신 muchan님, 감사합니다!

[MCP 기능이 나왔어요! 를 통해서 다시 한 번 연결해보세요!](https://develog.develrocket.com/@wnqudgus1234/develog-mcp-%EA%B8%B0%EB%8A%A5%EC%9D%B4-%EB%82%98%EC%99%94%EC%96%B4%EC%9A%94)

---

## 이제 MCP로 글 써 보세요

연결해 두면 이런 부탁을 할 수 있어요.

- "내 지난 글 읽고, 안 겹치는 다음 글 주제 5개 추천해 줘."
- "이번 주에 쓴 글 읽고, 공부한 것 목록으로 정리해 줘."
- "내 글 중에 하나 골라서 퀴즈 5개 내 줘."
- "내 글 읽고 자기소개서 초안 써 줘."

마지막 건 제가 직접 해 봤어요. ([Develog MCP를 활용하여 이력서/자기소개서 작성 후기](https://develog.develrocket.com/@wnqudgus1234/%EB%94%94%EB%B2%A8%EB%A1%9C%EA%B7%B8-mcp-%EA%B5%AC%ED%98%84-%ED%9B%84-%ED%99%9C%EC%9A%A9-%ED%9B%84%EA%B8%B0))

## Claude Code는 이 명령으로 연결해요

Claude Code 연결 명령에 `--scope user`를 더했어요.

전에는 명령을 입력한 폴더에서만 디벨로그가 보였어요.  
다른 프로젝트 폴더에서 Claude Code를 열면 디벨로그가 없었죠.  
이제는 어느 폴더에서 열어도 보여요.

새 명령이에요. 설정 > 연결의 MCP 카드에도 바뀌어 있어요.

```bash
claude mcp add --transport http --scope user develog https://develog.develrocket.com/api/mcp

```

그다음 Claude Code에서 `/mcp`를 열고 develog를 골라 인증하면 돼요.

이미 예전 명령으로 연결해 둔 분은, 그때 연결한 폴더에서 아래 두 줄을 입력하고 다시 인증해 주세요.

```bash
claude mcp remove develog -s local
claude mcp add --transport http --scope user develog https://develog.develrocket.com/api/mcp

```

---

## MCP 잘 쓰고 계신가요?

11월 20일에 MCP 기능을 열었어요.  
AI 앱에서 디벨로그에 쓴 내 글을 찾아 읽는 기능이에요. ([MCP 기능이 나왔어요!](https://develog.develrocket.com/@wnqudgus1234/develog-mcp-%EA%B8%B0%EB%8A%A5%EC%9D%B4-%EB%82%98%EC%99%94%EC%96%B4%EC%9A%94))

벌써 써 보고 후기를 남겨 주신 분도 있어요.  
저도 이 기능으로 이력서와 자기소개서 초안을 만들어 봤고요.

## 작은 문제가 있었어요

그런데 Claude Code로 연결하면 허락 화면 대신 이 글자만 뜨는 문제가 있었어요.

```
403 Forbidden

```

"들어올 수 없어요"라는 뜻이에요.  
허락 화면까지 가지도 못하고 막힌 거예요.

## 무슨 일이었냐면요

AI 앱을 디벨로그에 연결할 때는 이런 일이 일어나요.

1. AI 앱이 디벨로그에 부탁해요. "연결하고 싶어요. 허락이 끝나면 열쇠를 여기로 보내 주세요."
2. 내가 디벨로그 허락 화면에서 [허락]을 눌러요.
3. 디벨로그가 그 "여기"로 열쇠를 보내요. AI 앱은 이 열쇠로 내 글을 읽어요.

문제는 1번의 "여기"였어요. 앱마다 적어 보내는 곳이 달라요.

- Claude(웹, 앱): claude.ai — 인터넷에 있는 주소
- Claude Code: localhost — 내 컴퓨터

## localhost가 뭐냐면요

localhost는 "지금 이 컴퓨터"라는 뜻이에요.

Claude Code는 claude.ai 같은 웹사이트가 아니에요. 내 노트북 안에서 돌아요.  
그래서 "열쇠는 이 컴퓨터로 보내 주세요"라는 뜻으로 localhost를 적어 보내요.  
내 노트북이 읽으면 내 노트북이고, 디벨로그 서버가 읽으면 디벨로그 서버 자신이에요.

## 그래서 안 됐던 거예요

디벨로그 서버 앞에는 방화벽이 있어요.  
수상한 요청을 서버에 닿기 전에 걸러 내는 경비실 같은 곳이에요.

나쁜 사람들이 쓰는 수법 중에 이런 게 있어요.  
서버에 localhost 주소를 슬쩍 건네서, 서버가 자기 안쪽(관리 화면이나 비밀 정보)을 열어 보게 만드는 거예요.  
서버한테 localhost는 "나 자신"이니까요.

그래서 방화벽은 요청 안에 localhost 주소가 보이면 일단 막아요.  
Claude Code가 보낸 "열쇠는 localhost로 보내 주세요"도 이 모양이라 막혔어요.

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1795486984976-65mseb/2-before.png)

사실 디벨로그는 그 주소를 직접 열지 않아요.  
브라우저에게 "허락 끝났으니 여기로 돌아가세요"라고 알려 주기만 해요.  
방화벽이 오해한겁니다.

## 이 버튼은 잘 됐어요

설정 > 연결의 **[Claude에 연결]** 버튼은 처음부터 잘 됐어요.  
Claude(웹, 앱)는 돌아갈 곳이 claude.ai라서 방화벽이 그냥 통과시켰거든요.

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1795486985377-84tbgk/1-claude-button.png)

## 이게 안 됐어요

같은 카드 아래쪽, **Claude Code 명령**으로 연결하는 길이 막혀 있었어요.

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1795486985083-ky1p94/3-old-command.png)

지금은 고쳤어요.

방화벽에서 MCP 연결에 쓰는 길 세 곳만 예외로 뺐어요.

- 허락 화면을 여는 길
- [허락] 버튼
- 열쇠를 받는 길

나머지 길은 지금도 방화벽이 그대로 지켜요.

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1795486985439-bfw3md/4-after.png)

403을 보고 그냥 넘어가셨다면 지금 다시 해 보세요.

## 도와주신 muchan님, 감사합니다!

muchan님이 후기에 "403 Forbidden이 나왔다"고 남겨 주신 덕분에 이 문제를 찾고 고칠 수 있었어요.  
지난 글을 읽혀서 다음 글 주제를 추천받는 모습도 보여 주셨어요.

👉 [muchan님 후기: 디벨로그 mcp 사용 후기](https://develog.develrocket.com/@muchan/%EB%81%84%EC%A0%81%EB%81%84%EC%A0%81-%EB%94%94%EB%B2%A8%EB%A1%9C%EA%B7%B8-mcp-%EC%82%AC%EC%9A%A9-%ED%9B%84%EA%B8%B0)

---

아직 BETA예요.  
써 보다가 막히는 곳이 있으면 댓글로 알려 주세요.
