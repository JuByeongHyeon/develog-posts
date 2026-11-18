# Claude Code 코드 모드 켜는 법, 켜고 끄고 비교해 봤다

> 디벨로그에서 쓴 글 · 2026-11-18
>
> https://develog.develrocket.com/@wnqudgus1234/claude-code-코드-모드-켜고-끄고-비교해-봤다

> **화장실이 급하다면**
>
> - Claude Code에는 도구를 하나씩 안 부르고, 코드로 한 번에 돌리는 "코드 모드"가 있다.
> - 아직 실험 기능이다. 2.1.323부터 들어 있고, 기본은 꺼져 있다.
> - 코드 모드를 킨것과 안 킨것을 비교해보았다.  
> => 파일 30개를 하나씩 보는 일은 80초가 20초가 됐다(한 번 잰 값).
> - 켜는 게 귀찮으면 Claude한테 "코드 모드 켜 줘"라고 시키면 된다.

---

# Claude Code 코드 모드, 켜고 끄고 비교해 봤다

하루가 멀다 하고 AI 소식이 나온다.  
새 모델, 새 플랫폼, 새 기능.  
너무 많다.

어느 정도냐면, 쇼츠를 넘기다 보면 10개 중 한두 개는 이런 소식이다. 내 체감으로는 그렇다.

그래서 피곤하다. 안 따라가면 뒤처질 것 같다. 그런데 매일 쏟아지는 걸 언제 다 깔아 보고 써 보니...ㅜ

그래서 오늘은 새로 설치할 게 아니라, Claude Code에 들어 있는 기능 하나를 가져와 보았다.  
앤트로픽에서 얘기하기론, 아직 실험 기능이라고 해서 기본적으로 적용은 되어있지 않다.

---

## 시작은 단순하다.

> Claude Code 쓰다 보면 화면에 Read, Edit, Write 너무 많이 뜬다. 이게....뭐지?

Read, Read, Read, Edit, Edit. 파일 30개를 보라고 하면 진짜 30번을 하나씩 읽는다.

![](https://data.develog.develrocket.com/upload/develog/wnqudgus1234/1794963791008-2tkdpm/___________2026-11-18_______9.40.22.png)

근데 이게 다 호출이다.

Read 한 번, Edit 한 번이 전부 Claude가 도구를 부르는 일이다.  
부를 때마다 결과를 받아서 다시 읽고, 다음에 뭘 할지 생각한다. 그게 다 토큰이고, 토큰은 곧 비용이다.

평소에 인지는 했었지만 별생각 없이 넘겼다. 뇌를 빼면서 화면에 Read가 줄줄이 지나가는 걸 보다가 문득 생각이 났다.

=> 왜 한 번에 안 읽지?  
=> 30번 부를 걸 한 번으로 줄일 수 있지 않나?

찾아보니 있었다.

---

## 코드 모드라는 게 있었다

Claude Code 2.1.323부터 "Code Mode"(코드 모드)가 들어와 있었다.

도구를 하나씩 부르지 않고, Claude가 JavaScript를 짜서 한 번에 돌린다.  
30개 읽기, 고르기, 고치기를 코드 한 덩어리로 처리하고, 코드가 돌려준 값만 읽는다.

걍 한 줄로 말하면, 읽고 쓰는 과정을 한 번에 처리하는 코드를 짜서 실행시킨단다.

공식 문서에는 이렇게 적혀 있다.

> "Claude writes a piece of JavaScript that makes the tool calls, and Claude Code runs that code in your session" 
>
> (Claude는 도구 호출을 수행하는 JavaScript 코드를 작성하고, Claude Code는 사용자의 세션 내에서 해당 코드를 실행합니다.)

## 아직 실험 기능이다

기본은 꺼져 있다. 직접 켜야 한다. 문서에도 언제든 바뀌거나 빠질 수 있다고 써 있다.

켜는 건 환경 변수 하나다.

```bash
CLAUDE_CODE_EXPERIMENTAL_CODE_MODE=1 claude

```

처음 켜면 확인 창이 뜬다. 기본 선택이 "No, start without it"이라서 그냥 엔터 치면 안 켜진다.  
"Yes, turn on Code Mode"로 내려서 골라야 한다.  
켜지면 화면 위에 "Code Mode (experimental) is on"이 뜬다.

걸리는 것도 좀 있다.

- 터미널에서만 된다. VS Code 패널이나 데스크톱 앱에선 안 된단다.
- 켜 두면 크롬 조작(Claude in Chrome)이랑 원격 조종(Remote Control)은 못 쓴다. => 이런...
- 코드 하나가 10분 넘게 걸리면 멈춘다. 권한 물어볼 때 대답이 늦어도 그 시간에 들어간다.
- 버전이 맞아도 계정에 따라 아직 안 열렸을 수 있단다.
- 회사에서 Bedrock 같은 클라우드를 거쳐 쓰고 있으면 안 된다.

코드 안에서 돌린 명령도 원래 걸어 둔 권한 규칙을 똑같이 탄다.  
딱 하나, auto 모드에선 코드를 돌리기 전에 한 번만 검사한단다. 돌리면서 바뀌는 값까지는 못 본다고.

## 켜고 끄고 비교해 봤다

진짜 줄어드나 궁금해서 직접 해 봤다.

작은 JS 프로젝트(파일 30개)를 똑같이 두 개 만들었다. 하나는 코드 모드를 끄고, 하나는 켜고 같은 일을 시켰다. |  
Claude Code 2.1.327, 모델은 Opus 5.5다.

첫 번째는 함수 이름 하나를 30개 파일에서 바꾸는 일.

<table><colgroup><col width="135"><col width="178"><col width="136"></colgroup><tr><th align="left" width="135"><p></p></th><th align="right" width="178"><p>끔</p></th><th align="right" width="136"><p>켬</p></th></tr><tr><td align="left"><p>모델 호출</p></td><td align="right"><p>4번</p></td><td align="right"><p>4번</p></td></tr><tr><td align="left"><p>입력 토큰</p></td><td align="right"><p>277,003</p></td><td align="right"><p>166,937</p></td></tr><tr><td align="left"><p>시간</p></td><td align="right"><p>14.8초</p></td><td align="right"><p>14.0초</p></td></tr></table>

호출 횟수는 똑같았다. 끈 쪽도 Claude가 알아서 명령 한 줄로 30개를 한 번에 바꿔 버렸다.

근데? => 토큰은 40% 덜 썼다.  
차이는 시작할 때 받는 도구 목록 같다.  
끈 쪽은 도구를 잔뜩 들고 시작했고(내 컴퓨터엔 붙여 둔 게 많다), 켠 쪽은 거의 "코드 실행" 하나만 들고 시작했다.

두 번째는 파일 30개를 하나씩 보고 함수 개수를 표로 만드는 일. 함수가 3개인 파일엔 주석도 달라고 했다.


|           | 끔       | 켬       |
| :-------- | ------: | ------: |
| 모델 호출     | 8번      | 5번      |
| 모델이 부른 도구 | 43번     | 4번      |
| 입력 토큰     | 598,267 | 216,948 |
| 시간        | 80.3초   | 20.0초   |


여기서는 차이가 컸다. 끈 쪽은 30번 읽고 9번 고쳤다. 화면에 파일 이름이 1번부터 30번까지 줄줄이 지나갔다.

켠 쪽은 이런 코드를 짰다.

```js
// 파일 30개를 한꺼번에 읽기
const files = (await $`find src -type f | sort`.text()).trim().split('\n');
const contents = {};
await Promise.all(files.map(async f => { contents[f] = await file(f).text(); }));

// 함수가 3개인 파일에만 주석 넣기
for (const r of three) {
  await write(r.f, '// TODO: split\n' + contents[r.f]);
}

```

토큰은 64%, 시간은 75% 줄었다.  
=> 시간이 줄어든게 나는 임팩트가 크다고 느꼈다.  
=> 토큰은 플렉스하면 되더라도 시간이 줄고 성능이 똑같다....라고 느꼈기에 동시에 더 많은 일을 할 수 있게되는 것.

근데 코드 모드를 켠 쪽도 파일 30개 내용을 한 번에 다 돌려받았다는 거다.  
=> **"결과만 본다"가 내용을 안 본다는 뜻은 아니었다.**  
=> 줄어든 건 하나씩 오가는 왕복이다.

한 번씩만 잰 값이라는 건 감안해야 한다. 끈 상태로 두 번 돌렸을 땐 1% 차이였다(첫 번째 작업). 켠 상태는 반복하지 않았다. 내 컴퓨터는 MCP 서버가 많이 붙어 있어서 도구 목록 차이가 유독 컸을 수도 있다. 토큰에는 캐시에서 다시 읽은 양도 섞여 있다. 토큰이 64% 줄었다고 요금이 64% 주는 건 아니다.

## 돌아다니는 숫자는 조심

코드 모드 소개 글에 37%, 98.7%, 81% 같은 숫자가 자주 보인다. 셋 다 Claude Code 코드 모드에서 잰 숫자가 아니다.

- 37%: Claude API의 Python 기능(PTC)에서 잰 숫자다(Anthropic).
- 98.7%: Anthropic 블로그의 예시다. 어떻게 쟀는지는 안 적혀 있다.
- 81%: MCP Night 행사에서 Cloudflare가 보인 데모다(WorkOS 정리). 일정 1개짜리 데모는 32%였다.

Claude Code 공식 문서에는 숫자가 아예 없다.

이 방식 자체는 새로운 얘기는 아니다.

> "도구를 AI 앞에 다 펼치지 말고 코드로 불러라."

Cloudflare가 2025년 9월, Anthropic이 11월, Goose가 12월에 먼저 이 얘기를 했다.  
Claude Code에는 아예 코드 모드로 만들어서 도입한 모양이다.

---

## 이것도 머리 아프면 그냥 Claude한테 시키면 된다

환경 변수가 귀찮으면 Claude Code한테 "코드 모드 켜 줘. 사용자 설정에 넣어 줘"라고 시키면 된다. 사용자 설정 파일(`~/.claude/settings.json`)에 들어가야 한다. 프로젝트 설정 파일에 넣으면 무시된다.

대신 바로 켜지진 않는다. Claude Code를 껐다 다시 켜야 한다. 처음 뜨는 창에서 Yes도 골라야 한다.

써 보니 파일 여러 개를 하나씩 봐야 하는 일엔 확실히 빨랐다.  
Anthropic도 도구 하나만 부르거나 중간 결과를 다 보고 판단해야 할 땐 이득이 적다고 했다.

아직 실험 기능이다. 궁금하면 한번 켜 보는 정도면 될 것 같다.

---

## 출처

- Claude Code 문서, Code Mode: [https://code.claude.com/docs/en/code-mode](https://code.claude.com/docs/en/code-mode)
- Anthropic 엔지니어링 블로그, 2025-11-04 "Code execution with MCP": [https://www.anthropic.com/engineering/code-execution-with-mcp](https://www.anthropic.com/engineering/code-execution-with-mcp)
- Anthropic 엔지니어링 블로그, 2025-11-24 "Introducing advanced tool use": [https://www.anthropic.com/engineering/advanced-tool-use](https://www.anthropic.com/engineering/advanced-tool-use)
- Claude API 문서, Programmatic tool calling: [https://platform.claude.com/docs/en/agents-and-tools/tool-use/programmatic-tool-calling](https://platform.claude.com/docs/en/agents-and-tools/tool-use/programmatic-tool-calling)
- Cloudflare 블로그, 2025-09-26 "Code Mode: the better way to use MCP": [https://blog.cloudflare.com/code-mode/](https://blog.cloudflare.com/code-mode/)
- WorkOS, 2025-12-11 MCP Night Cloudflare 데모 정리: [https://workos.com/blog/cloudflare-code-mode-cuts-token-usage-by-81](https://workos.com/blog/cloudflare-code-mode-cuts-token-usage-by-81)
- Goose 블로그, 2025-12-21 "Code Mode Doesn't Replace MCP": [https://goose-docs.ai/blog/2025/12/21/code-mode-doesnt-replace-mcp/](https://goose-docs.ai/blog/2025/12/21/code-mode-doesnt-replace-mcp/)

&nbsp;
