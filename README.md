# Clean Eye 🔍

**AI가 한국 직장인 페르소나가 되어 처음 화면을 처음 보는 사람처럼 평가합니다.** <br> 
서비스를 오래 보고 고민하면 어느 순간부터는 화면이 익숙해져서 "처음 보는 사람은 어떻게 느낄까?"를 상상하기가 점점 어려워집니다.
그래서 한 번쯤은 처음 보는 사람의 시선으로 화면을 살펴볼 수 있는 도구가 있으면 좋겠다는 생각으로 만들었습니다!
<br> 
<br> 


## 어떻게 평가하나요?

평가는 석사 시절 자주 활용했던, HCI(Human-Computer Interaction) 분야에서 많이 사용하는 Think-Aloud 방식을 참고했습니다.
페르소나는 화면을 보면서 자연스럽게 이런 순서로 생각합니다.<br> 
👀 가장 먼저 무엇이 보이는지?<br> 
💭 이 화면이 무엇을 하는 곳이라고 이해하는지?<br> 
👉 다음에 무엇을 누를 것 같은지?<br> 
📝 마지막으로 화면을 어떻게 정리하는지?<br> 
단순히 "좋다, 나쁘다"보다 왜 그렇게 생각했는지를 보는 데 초점을 맞췄습니다.
<br> 
<br> 



## 어떤 데이터를 사용하나요?

한국 직장인 페르소나(NVIDIA Nemotron-Personas-Korea)를 기반으로 평가합니다.
평가에는 20~60대의 다양한 한국 직장인 페르소나가 참여합니다.
개발자나 디자이너처럼 화면을 많이 보는 직군보다는 일반적인 회사원(사무원, 관리자, 은행원, HR 등) 관점을 최대한 반영하려고 했습니다.<br> 
그래서 보통은 **"이 화면을 처음 보는 일반 직장인도 이해할 수 있을까?"** 를 확인하는 용도로 사용하면 좋습니다.
<br> 
<br> 




### 예시. AI 자동 요약
<img width="454" height="379" alt="AI 자동 요약" src="https://github.com/user-attachments/assets/13ba9273-9f86-418c-a4a1-cbf4f3a49153" /> <br>
<br> 위의 예시 화면에 대한 페르소나의 평가는 아래와 같습니다.<br> 

<img width="512" height="551" alt="페르소나 평가" src="https://github.com/user-attachments/assets/7f1fd695-9202-4ee7-86b1-7dc8421790fa" />

<img width="511" height="503" alt="종합 의견" src="https://github.com/user-attachments/assets/621eeecc-0154-47e1-a333-ed5d3f4277c4" />



## 설치
1. `clean-eye` 폴더를 Claude Code의 `~/.claude/skills`에 복사합니다.
2. Claude Code를 다시 실행합니다.
3. `/clean-eye` 명령을 사용할 수 있습니다.
<br> 
<br> 


CC BY 4.0 — [LICENSE.md](./LICENSE.md) 참고
