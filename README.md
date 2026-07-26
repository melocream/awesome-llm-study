# 🧠 LLM Study — 대규모 언어모델 시대의 학습 자료 모음 (2023–2026)

> 트랜스포머부터 GPT·Claude, 에이전트·MCP·RAG까지 — **LLM 시대를 스스로 공부하는 분들께 도움이 되고자** 직접 읽고, 보고, 검증한 자료만 모았습니다.
> 이 저장소의 모든 링크는 실제로 열어 보고 살아있는 것만 담았습니다. (죽은 링크·추측 URL 없음)

- 관리: [@melocream](https://github.com/melocream)
- 만든 사람이 만드는 것: **[marblo.app](https://marblo.app)** — AI-native 팀을 위한 오케스트레이션 컨트롤 플레인
- 원칙: **권위 있는 1차 출처 우선**, 최신(2024–2026) 자료 우선, 한 줄 코멘트로 "왜 봐야 하는지"만 남깁니다.
- 참고한 형식: [teddylee777/machine-learning](https://github.com/teddylee777/machine-learning) 의 카테고리 + 한 줄 코멘트 스타일

---

## 📁 저장소 폴더 구조 (성장 시 제안)

```
llm-study/
├── README.md                  # 지금 이 문서 (전체 인덱스)
├── 01-foundations/            # LLM 발전사·기초 (개념·시각화)
│   └── notes/                 # 트랜스포머·어텐션 정리 노트
├── 02-courses/                # 강의 수강 노트 & 실습 코드
│   ├── cs224n/
│   ├── cs336/
│   └── karpathy-zero-to-hero/
├── 03-agents-mcp/             # 에이전트·툴콜·MCP 실험
│   └── mcp-servers/           # 직접 만든 MCP 서버 예제
├── 04-claude-code/            # Claude Code·코딩 에이전트 워크플로우
├── 05-prompting/              # 프롬프트·컨텍스트 엔지니어링
│   └── templates/
├── 06-rag/                    # RAG 파이프라인 실습
├── 07-finetuning-alignment/   # 파인튜닝·RLHF·정렬
│   └── experiments/
├── 08-papers/                 # 핵심 논문 요약 (arXiv)
│   └── summaries/
└── 09-korean/                 # 한국어 자료 & 번역 정리
```

---

## 1. 🏗️ LLM 발전사 · 기초

> 트랜스포머 → GPT → instruction tuning → 현재까지, "안에서 무슨 일이 벌어지는가"를 그림과 애니메이션으로 이해하기.

- [3Blue1Brown — Neural Networks 시리즈](https://www.3blue1brown.com/topics/neural-networks) · 신경망·어텐션을 수식이 아닌 직관으로 이해시키는 최고의 시각화 강의
- [3Blue1Brown — Transformers, the tech behind LLMs (Ch.5)](https://www.youtube.com/watch?v=wjZofJX0v4M) · "LLM이 왜 트랜스포머인가"를 27분 애니메이션으로 완벽 설명
- [Andrej Karpathy — Intro to Large Language Models (1시간)](https://www.youtube.com/watch?v=zjkBMFhNj_g) · LLM 전체 그림을 비전문가도 이해하게 그려주는 입문 명강
- [Andrej Karpathy — Deep Dive into LLMs like ChatGPT](https://www.youtube.com/watch?v=7xTGNNLPyMI) · 사전학습→SFT→RLHF 전 과정을 3시간에 훑는 심화 강의
- [The Illustrated Transformer — Jay Alammar](https://jalammar.github.io/illustrated-transformer/) · 트랜스포머 구조를 그림으로 뜯어보는 국민 필독 블로그
- [The Illustrated GPT-2 — Jay Alammar](https://jalammar.github.io/illustrated-gpt2/) · 디코더-온리 언어모델이 토큰을 생성하는 원리를 시각화
- [The Annotated Transformer — Harvard NLP](https://nlp.seas.harvard.edu/annotated-transformer/) · 원논문을 줄 단위 PyTorch 코드로 재현한 주석본
- [LLM Visualization — bbycroft.net](https://bbycroft.net/llm) · GPT 추론을 행렬 단위로 3D 애니메이션으로 걸어보는 인터랙티브 시각화
- [Generative AI exists because of the transformer — Financial Times](https://ig.ft.com/generative-ai/) · 스크롤형 인터랙티브로 배우는 생성형 AI의 작동 원리

## 2. 🎓 강의 (Courses)

> 밑바닥부터 직접 구현하며 배우는 정통 커리큘럼 위주.

- [Stanford CS224n — NLP with Deep Learning](https://web.stanford.edu/class/cs224n/) · NLP·언어모델의 정석 대학원 강의 (강의노트·슬라이드 공개)
- [Stanford CS336 — Language Modeling from Scratch](https://stanford-cs336.github.io/spring2025/) · 데이터·토크나이저부터 학습·평가까지 "LLM을 처음부터" 만드는 2025 신설 강의
- [Karpathy — Neural Networks: Zero to Hero](https://karpathy.ai/zero-to-hero.html) · micrograd→makemore→GPT까지 코드로 쌓아올리는 무료 강의 시리즈
- [karpathy/nanoGPT](https://github.com/karpathy/nanoGPT) · GPT를 ~300줄로 재현하는 가장 유명한 미니멀 학습용 구현체
- [karpathy/makemore](https://github.com/karpathy/makemore) · bigram→트랜스포머까지 언어모델을 단계별로 만드는 실습 저장소
- [Practical Deep Learning — fast.ai](https://course.fast.ai/) · 톱다운 방식으로 빠르게 실전 딥러닝에 진입하는 인기 강의
- [DeepLearning.AI — Short Courses](https://www.deeplearning.ai/short-courses/) · Andrew Ng 팀이 파트너사와 만든 1시간짜리 실전 LLM 단기 강좌 모음
- [Hugging Face — LLM Course](https://huggingface.co/learn/llm-course) · Transformers·토크나이저·파인튜닝을 실습으로 배우는 무료 공식 코스
- [Andrej Karpathy — YouTube 채널](https://www.youtube.com/@AndrejKarpathy) · 위 강의들의 원본 채널, LLM 학습 영상의 사실상 표준

## 3. 🤖 에이전트 · 툴콜 · MCP

> "모델이 스스로 도구를 쓰게" 만드는 패턴과, 그 표준이 된 MCP.

- [Model Context Protocol — 공식 소개](https://modelcontextprotocol.io/docs/getting-started/intro) · LLM에 도구·데이터를 연결하는 개방형 표준 MCP의 출발점
- [MCP Specification (2025-06-18)](https://modelcontextprotocol.io/specification/2025-06-18) · 프로토콜 스펙 원문 — 서버/클라이언트를 직접 만들 때 필독
- [modelcontextprotocol — GitHub 조직](https://github.com/modelcontextprotocol) · SDK·레퍼런스 서버·스키마 등 MCP 생태계 소스 저장소
- [Anthropic — Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents) · 워크플로우 vs 에이전트, 프롬프트 체이닝·라우팅·오케스트레이션 패턴 정리 (에이전트 설계 필독)
- [Anthropic — Building agents with the Claude Agent SDK](https://claude.com/blog/building-agents-with-the-claude-agent-sdk) · 실제 프로덕션 에이전트를 SDK로 짜는 공식 가이드
- [ReAct: Synergizing Reasoning and Acting (arXiv)](https://arxiv.org/abs/2210.03629) · 추론(Reason)과 행동(Act)을 번갈아 하는 에이전트 패턴의 원조 논문
- [Toolformer: LMs Can Teach Themselves to Use Tools (arXiv)](https://arxiv.org/abs/2302.04761) · 모델이 스스로 API 호출을 학습하는 툴 사용의 대표 논문

## 4. 💻 Claude Code · 코딩 에이전트

> 터미널에서 사는 코딩 에이전트 — 공식 문서와 실전 베스트 프랙티스.

- [Claude Code — Overview](https://code.claude.com/docs/en/overview) · Claude Code가 무엇이고 무엇을 할 수 있는지 공식 개요
- [Claude Code — Quickstart](https://code.claude.com/docs/en/quickstart) · 설치부터 첫 작업까지 10분 온보딩 가이드
- [Claude Code — Common Workflows](https://code.claude.com/docs/en/common-workflows) · 코드베이스 탐색·리팩터·테스트 등 실무 워크플로우 모음
- [Claude Code — MCP 연결](https://code.claude.com/docs/en/mcp) · Claude Code에 외부 도구를 MCP로 붙이는 방법
- [Claude Code — Best Practices (Anthropic Engineering)](https://code.claude.com/docs/en/best-practices) · CLAUDE.md·컨텍스트 관리 등 에이전틱 코딩을 잘 쓰는 노하우
- [anthropics/claude-code — GitHub](https://github.com/anthropics/claude-code) · 이슈·릴리스·레퍼런스가 모이는 공식 저장소

## 5. ✍️ 프롬프트 · 컨텍스트 엔지니어링

> 잘 물어보는 법(Prompt)에서, 무엇을 컨텍스트 윈도우에 넣을지 설계하는 법(Context)으로.

- [Anthropic — Prompt Engineering Overview](https://docs.claude.com/en/docs/build-with-claude/prompt-engineering/overview) · Claude 기준 프롬프트 기법 총정리 (공식)
- [Anthropic — Interactive Prompt Engineering Tutorial](https://github.com/anthropics/prompt-eng-interactive-tutorial) · 9개 챕터 실습형 프롬프트 튜토리얼 (초급→고급)
- [OpenAI — Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering) · GPT 계열 기준 프롬프트 작성 전략 공식 가이드
- [Prompt Engineering Guide (DAIR.AI)](https://www.promptingguide.ai/) · 기법·논문·예제를 총망라한 커뮤니티 표준 레퍼런스
- [Anthropic — Effective Context Engineering for AI Agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents) · 프롬프트 이후의 화두 "컨텍스트 엔지니어링"을 정의한 글
- [OpenAI Cookbook](https://cookbook.openai.com/) · 실전 예제 코드로 배우는 프롬프트·툴콜·임베딩 레시피

## 6. 📚 RAG (검색 증강 생성)

> 모델의 지식 한계를 외부 검색으로 메우는 파이프라인 설계.

- [RAG: Retrieval-Augmented Generation (원논문, arXiv)](https://arxiv.org/abs/2005.11401) · RAG라는 개념을 처음 제시한 2020년 원조 논문
- [Retrieval-Augmented Generation for LLMs: A Survey (arXiv)](https://arxiv.org/abs/2312.10997) · Naive→Advanced→Modular RAG까지 전체 지형을 정리한 서베이
- [Anthropic — Contextual Retrieval](https://www.anthropic.com/engineering/contextual-retrieval) · 청크에 문맥을 덧붙여 검색 정확도를 크게 올리는 실전 기법
- [LangChain — Retrieval 문서](https://docs.langchain.com/oss/python/langchain/retrieval) · RAG 파이프라인을 코드로 구성하는 공식 가이드
- [LlamaIndex — 공식 문서](https://docs.llamaindex.ai/) · 문서 인덱싱·쿼리에 특화된 RAG 프레임워크 레퍼런스
- [Pinecone — Retrieval-Augmented Generation](https://www.pinecone.io/learn/retrieval-augmented-generation/) · 벡터DB 관점에서 RAG를 개념부터 실습까지 정리한 학습 글
- [Hugging Face Cookbook — Simple RAG](https://huggingface.co/learn/cookbook/rag_zephyr_langchain) · 오픈모델(Zephyr)+LangChain으로 만드는 최소 RAG 예제

## 7. 🎯 파인튜닝 · RLHF · 정렬 (Alignment)

> 사전학습 모델을 "사람이 원하는 대로" 다듬는 방법 — SFT, RLHF, DPO, LoRA.

- [InstructGPT: Training LMs to follow instructions (arXiv)](https://arxiv.org/abs/2203.02155) · RLHF로 지시를 따르게 만든, ChatGPT의 직계 조상 논문
- [Illustrating RLHF — Hugging Face 블로그](https://huggingface.co/blog/rlhf) · RLHF 3단계(SFT·보상모델·PPO)를 그림으로 설명한 입문 글
- [Constitutional AI: Harmlessness from AI Feedback (arXiv)](https://arxiv.org/abs/2212.08073) · 사람 대신 원칙(헌법)으로 정렬하는 Anthropic의 RLAIF 논문
- [DPO: Direct Preference Optimization (arXiv)](https://arxiv.org/abs/2305.18290) · 보상모델·RL 없이 선호 데이터로 바로 정렬하는 방법
- [LoRA: Low-Rank Adaptation (arXiv)](https://arxiv.org/abs/2106.09685) · 소수 파라미터만 학습해 저비용으로 파인튜닝하는 표준 기법
- [QLoRA: Efficient Finetuning of Quantized LLMs (arXiv)](https://arxiv.org/abs/2305.14314) · 4-bit 양자화로 단일 GPU에서 대형모델 파인튜닝을 가능케 한 논문
- [Hugging Face PEFT 문서](https://huggingface.co/docs/peft) · LoRA·QLoRA 등 파라미터 효율적 파인튜닝 공식 라이브러리
- [Hugging Face TRL 문서](https://huggingface.co/docs/trl) · SFT·DPO·PPO를 코드로 돌리는 RLHF/정렬 학습 라이브러리

## 8. 📄 핵심 논문 (Must-Read Papers)

> LLM 시대를 만든 랜드마크 논문 — arXiv 링크는 전부 실재 확인함.

- [Attention Is All You Need (2017)](https://arxiv.org/abs/1706.03762) · 트랜스포머를 세상에 내놓은 모든 것의 시작
- [Scaling Laws for Neural Language Models (2020)](https://arxiv.org/abs/2001.08361) · 모델·데이터·연산을 키우면 예측 가능하게 좋아진다는 스케일링 법칙
- [GPT-3: Language Models are Few-Shot Learners (2020)](https://arxiv.org/abs/2005.14165) · 거대 모델의 few-shot in-context learning을 입증한 논문
- [Chinchilla: Training Compute-Optimal LLMs (2022)](https://arxiv.org/abs/2203.15556) · 같은 연산이면 "더 많은 데이터"가 답이라는 컴퓨트-최적 학습
- [Chain-of-Thought Prompting (2022)](https://arxiv.org/abs/2201.11903) · "단계별로 생각하라"로 추론 성능을 끌어올린 프롬프트 기법
- [InstructGPT / RLHF (2022)](https://arxiv.org/abs/2203.02155) · 인간 피드백 강화학습으로 정렬한 대화형 LLM의 원형
- [Self-Instruct (2022)](https://arxiv.org/abs/2212.10560) · 모델이 스스로 지시 데이터를 생성해 튜닝하는 방법
- [Llama 2 (2023)](https://arxiv.org/abs/2307.09288) · 오픈 웨이트 LLM 대중화를 이끈 Meta의 기술 보고서
- [ReAct (2023)](https://arxiv.org/abs/2210.03629) · 추론+행동 결합, LLM 에이전트의 개념적 토대
- [GPT-4 Technical Report (2023)](https://arxiv.org/abs/2303.08774) · 멀티모달·시험 성능 등 GPT-4의 능력과 한계를 담은 보고서

## 9. 🇰🇷 한국어 자료

> 한국어로 깊게 파고들 수 있는, 지금도 살아있는 자료만.

- [테디노트 (teddylee777) 블로그](https://teddylee777.github.io/) · LangChain·RAG·LLM 실전 예제가 가장 풍부한 한국어 기술 블로그
- [테디노트 TeddyNote — YouTube](https://www.youtube.com/@teddynote) · LLM/LangChain을 한국어로 가장 꾸준히 다루는 채널
- [teddylee777/langchain-kr](https://github.com/teddylee777/langchain-kr) · LangChain 공식 문서를 한국어로 재구성한 실습 튜토리얼 저장소
- [ratsgo's NLPBOOK](https://ratsgo.github.io/nlpbook/) · 트랜스포머·BERT·GPT를 한국어로 깊이 있게 정리한 전자책
- [가짜연구소 (Pseudo-Lab) — GitHub](https://github.com/Pseudo-Lab) · 국내 최대 오픈 AI 스터디 커뮤니티의 프로젝트·자료 모음
- [모두를 위한 머신러닝/딥러닝 — 김성훈](https://hunkim.github.io/ml/) · 한국어 딥러닝 입문의 고전, 기초 개념 다지기용
- [rickiepark/nlp-with-transformers](https://github.com/rickiepark/nlp-with-transformers) · 『트랜스포머를 활용한 자연어 처리』 한국어판 예제 코드

---

> 🔗 잘못된 링크나 추가하면 좋을 자료가 있으면 이슈/PR 환영합니다.
> Maintained by [@melocream](https://github.com/melocream) · Built with [marblo.app](https://marblo.app)
