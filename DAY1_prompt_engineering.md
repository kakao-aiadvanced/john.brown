프롬프트 태스크로 multiuser-conversation 전용 챗봇을 만들었습니다.

# 초기 프롬프트
```
너는 두 사람 이상의 메신저 대화를 바탕으로 그들이 필요한 정보를 제공하고, 한사람 이상의 글을 공감하는 표현을 해야해

아래가 그 메신저 내용이야
<conversation>
{{CONVERSATION}}
</conversation>
```

# antrhopic 생성 프롬프트
초기 프롬프트 입력시 자동 생성된 프롬프트
```
You are an AI assistant tasked with analyzing a messenger conversation between multiple people and answering a question about it. Your goal is to provide an accurate answer while also showing empathy and mentioning the names of the people involved in the conversation.

Here is the conversation transcript:
<conversation>
{{CONVERSATION}}
</conversation>

Question you need to answer is in the conversation.

To complete this task, follow these steps:

1. Carefully read through the entire conversation transcript.
2. Identify the key participants in the conversation and take note of their names.
3. Analyze the content of the messages to understand the context and main topics discussed.
4. Focus on the information relevant to answering the given question.
5. Formulate a clear and concise answer to the question based on the conversation.
6. While crafting your response, make sure to:
   a. Mention at least one names of the people involved in the conversation.
   b. Show empathy by acknowledging the emotions or experiences expressed by the participants.
   c. Use a friendly and supportive tone throughout your answer.

Present your final response in the following format:
<answer>
[Your answer to the question, incorporating names and showing empathy]
</answer>

Remember to be respectful, supportive, and accurate in your response while maintaining a conversational tone. Response in Korean.
```

# 생성 및 비교
<img width="1715" alt="image" src="https://github.com/user-attachments/assets/6f414aac-9262-472e-a1b0-817e7269ab5e">


# 마음에 들었던 비교
### 과제
```
A: 친구들아, 이번 주말에 뭐하지?
B: 나는 아직 계획 없어. 뭐 재밌는 거 있나?
C: 우리 캠핑 가는 거 어때? 날씨도 좋다던데
A: 오, 캠핑 좋네! 근데 나 캠핑 장비가 없는데...
B: 나도 없어. 렌트할 수 있나?
C: 응, 요즘 캠핑 용품 렌탈 서비스가 많아. 내가 알아볼게
A: 고마워 C야. 근데 캠핑장은 어디로 갈까?
B: 서울에서 너무 멀지 않은 곳으로 가자. 운전하기 힘들어
C: 가평 어때? 강가에 있는 캠핑장이 있던데
A: 좋아 보이네! 근데 밤에 좀 춥지 않을까?
B: 맞아, 10월이라 밤에는 쌀쌀할 것 같아
C: 걱정 마, 내가 난로도 렌트할게. 그리고 따뜻한 음식도 준비하면 되잖아
A: C가 진짜 캠핑 고수네! 우리 이번 주말 캠핑 어떻게 준비하면 좋을까?
```
### 응답
제가 만든 프롬프트의 응답: 
```
네, 이 대화를 바탕으로 필요한 정보를 제공하고 공감 표현을 해보겠습니다.

친구들의 캠핑 계획에 대해 정말 설레는 것 같아요! C님이 정말 캠핑에 대해 잘 아시는 것 같네요. 캠핑을 준비하는 데 몇 가지 도움이 될 만한 정보를 드릴게요:

1. 캠핑 장비 렌탈: 요즘에는 다양한 캠핑 용품 렌탈 서비스가 있어요. 텐트, 침낭, 의자, 테이블 등 기본적인 장비를 빌릴 수 있습니다.

2. 가평 캠핑장: 서울에서 가까운 가평은 인기 있는 캠핑 장소예요. 북한강 주변에 여러 캠핑장이 있어 선택의 폭이 넓답니다.

3. 날씨 대비: 10월은 일교차가 큰 편이에요. C님이 말씀하신 대로 난로를 준비하는 것이 좋겠어요. 따뜻한 옷도 꼭 챙기세요!

4. 음식 준비: 캠핑의 즐거움 중 하나는 바로 음식이죠. 미리 양념해간 고기나 간편하게 끓일 수 있는 찌개 재료 등을 준비하면 좋아요.

5. 안전 용품: 구급상자, 랜턴, 보조 배터리 등 안전 용품도 잊지 마세요.

A님이 걱정하신 것처럼 밤에 추울 수 있지만, C님의 아이디어대로 따뜻한 음식과 난로가 있다면 충분히 극복할 수 있을 거예요. 다들 이번 주말 캠핑을 정말 기대하고 계신 것 같아 보기 좋네요. 즐거운 시간 보내세요!
```

클로드가 만든 프롬프트의 응답: 
```
<answer>
친구들의 캠핑 계획을 위해 다음과 같이 준비하면 좋을 것 같아요:

1. C가 제안한 대로 캠핑 용품 렌탈 서비스를 이용해 필요한 장비를 빌리세요. 텐트, 침낭, 매트 등 기본 장비와 함께 난로도 꼭 준비하면 좋겠어요.

2. 가평으로 장소를 정했으니 미리 캠핑장을 예약하세요. 강가에 있는 캠핑장이라 경치도 좋을 것 같아요.

3. B가 걱정한 대로 밤에 추울 수 있으니 따뜻한 옷과 담요를 꼭 챙기세요.

4. C의 제안처럼 따뜻한 음식을 준비하세요. 캠핑용 버너와 조리 도구도 필요할 거예요.

5. 안전을 위해 구급상자와 손전등도 잊지 마세요.

6. 즐거운 시간을 위해 간단한 게임이나 책 등 여가 활동 준비물도 챙기면 좋겠어요.

7. A가 캠핑 경험이 없어 보이니, 서로 도와가며 준비하고 즐기는 게 어떨까요?

친구들과 함께하는 첫 캠핑이라 설레겠어요. 서로 협력하며 준비하면 더욱 즐거운 경험이 될 거예요. 좋은 추억 만들고 오세요!
</answer>
```

클로드 프롬프트의 응답이 <answer>로 잘 래핑되어 있고, 대화에서 언급되지 않았던 부분들이 잘 담겨 있음.

# 프롬프트 압축 기법
결과상 너무 압축되기는 했으나, 핵심이 담기긴한거같아 토큰 절약에는 효과적일 것으로 추정됨
<img width="1655" alt="image" src="https://github.com/user-attachments/assets/681a2ea4-2ece-4864-adc3-80e8c7947d95">

