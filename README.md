# 🧠 LLM Study — 대규모 언어모델 시대의 학습 자료 모음 (2023–2026)

[![Last updated](https://img.shields.io/badge/last%20updated-2026--07--29-0a7f5b?style=flat-square)](https://github.com/melocream/awesome-llm-study/commits/master)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC--BY--4.0-lightgrey.svg?style=flat-square)](LICENSE)

> 트랜스포머부터 GPT·Claude, 에이전트·MCP·RAG까지 — **LLM 시대를 스스로 공부하는 분들께 도움이 되고자** 직접 읽고, 보고, 검증한 자료만 모았습니다.
> 이 저장소의 모든 링크는 실제로 열어 보고 살아있는 것만 담았습니다. (죽은 링크·추측 URL 없음)

- 관리: 데이터가답이다(동원킴) · [@melocream](https://github.com/melocream)
- 만든 사람이 만드는 것: **[marblo.app](https://marblo.app)** — AI-native 팀을 위한 오케스트레이션 컨트롤 플레인
- 원칙: **권위 있는 1차 출처 우선**, 최신(2024–2026) 자료 우선, 한 줄 코멘트로 "왜 봐야 하는지"만 남깁니다.

---

## English summary

An opinionated Korean-first, source-verified map for learning LLMs: foundations, building models, agents and MCP, RAG, evaluation, and local serving. Start with the four-stage roadmap below; every resource is labelled with a suggested level and time investment. Contributions are welcome in Korean or English.

## 🗺️ 학습 로드맵

자료가 많은 것보다 **다음에 무엇을 할지 아는 것**이 중요합니다. 아래 순서대로 한 단계씩 끝내고, 관심 분야의 섹션으로 확장하세요.

| 단계                         | 목표                                       | 먼저 볼 자료                                                                                                                 | 권장 기간 |
| ---------------------------- | ------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------- | --------- |
| 1. 작동 원리 잡기            | 토큰·어텐션·다음 토큰 예측을 말로 설명한다 | [3Blue1Brown](#1-️-llm-발전사--기초), [Illustrated Transformer](#1-️-llm-발전사--기초)                                       | 1–2주     |
| 2. 직접 만들어 보기          | 작은 언어 모델을 학습·평가한다             | [Karpathy Zero to Hero](#2--강의-courses), [CS336](#2--강의-courses)                                                         | 3–6주     |
| 3. 제품으로 연결하기         | 프롬프트·RAG·툴 호출을 조합한다            | [에이전트·MCP](#3--에이전트--툴콜--mcp), [RAG](#6--rag-검색-증강-생성)                                                       | 2–4주     |
| 4. 운영 가능한 시스템 만들기 | 평가·서빙·비용·보안을 함께 설계한다        | [Evals](#9--평가--evals), [로컬 실행](#10-️-로컬-실행--서빙--양자화), [보안](#11-️-llm-보안), [비용](#12--비용--토큰-경제학) | 지속      |

`[입문]`, `[중급]`, `[심화]`는 사전지식 기준이고, 시간은 첫 회독·실습의 대략적인 투자량입니다.

## 목차

- [학습 로드맵](#️-학습-로드맵) · [발전사·기초](#1-️-llm-발전사--기초) · [강의](#2--강의-courses) · [에이전트·MCP](#3--에이전트--툴콜--mcp)
- [Claude Code](#4--claude-code--코딩-에이전트) · [프롬프트](#5-️-프롬프트--컨텍스트-엔지니어링) · [RAG](#6--rag-검색-증강-생성) · [정렬](#7--파인튜닝--rlhf--정렬-alignment)
- [핵심 논문](#8--핵심-논문-must-read-papers) · [평가·Evals](#9--평가--evals) · [로컬 실행](#10-️-로컬-실행--서빙--양자화) · [보안](#11-️-llm-보안) · [비용](#12--비용--토큰-경제학) · [멀티모달](#13-️-멀티모달) · [한국어 자료](#14--한국어-자료)

---

## 1. 🏗️ LLM 발전사 · 기초

> 트랜스포머 → GPT → instruction tuning → 현재까지, "안에서 무슨 일이 벌어지는가"를 그림과 애니메이션으로 이해하기.

- [입문 · 15–60분] [3Blue1Brown — Neural Networks 시리즈](https://www.3blue1brown.com/topics/neural-networks) · 신경망·어텐션을 수식이 아닌 직관으로 이해시키는 최고의 시각화 강의
- [입문 · 15–60분] [3Blue1Brown — Transformers, the tech behind LLMs (Ch.5)](https://www.youtube.com/watch?v=wjZofJX0v4M) · "LLM이 왜 트랜스포머인가"를 27분 애니메이션으로 완벽 설명
- [입문 · 15–60분] [Andrej Karpathy — Intro to Large Language Models (1시간)](https://www.youtube.com/watch?v=zjkBMFhNj_g) · LLM 전체 그림을 비전문가도 이해하게 그려주는 입문 명강
- [입문 · 15–60분] [Andrej Karpathy — Deep Dive into LLMs like ChatGPT](https://www.youtube.com/watch?v=7xTGNNLPyMI) · 사전학습→SFT→RLHF 전 과정을 3시간에 훑는 심화 강의
- [입문 · 15–60분] [The Illustrated Transformer — Jay Alammar](https://jalammar.github.io/illustrated-transformer/) · 트랜스포머 구조를 그림으로 뜯어보는 국민 필독 블로그
- [입문 · 15–60분] [The Illustrated GPT-2 — Jay Alammar](https://jalammar.github.io/illustrated-gpt2/) · 디코더-온리 언어모델이 토큰을 생성하는 원리를 시각화
- [입문 · 15–60분] [The Annotated Transformer — Harvard NLP](https://nlp.seas.harvard.edu/annotated-transformer/) · 원논문을 줄 단위 PyTorch 코드로 재현한 주석본
- [입문 · 15–60분] [LLM Visualization — bbycroft.net](https://bbycroft.net/llm) · GPT 추론을 행렬 단위로 3D 애니메이션으로 걸어보는 인터랙티브 시각화
- [입문 · 15–60분] [Generative AI exists because of the transformer — Financial Times](https://ig.ft.com/generative-ai/) · 스크롤형 인터랙티브로 배우는 생성형 AI의 작동 원리

## 2. 🎓 강의 (Courses)

> 밑바닥부터 직접 구현하며 배우는 정통 커리큘럼 위주.

- [중급 · 2–12시간] [Stanford CS224n — NLP with Deep Learning](https://web.stanford.edu/class/cs224n/) · NLP·언어모델의 정석 대학원 강의 (강의노트·슬라이드 공개)
- [중급 · 2–12시간] [↳ CS224n 강의 영상 (Spring 2024, YouTube)](https://www.youtube.com/playlist?list=PLoROMvodv4rOaMFbaqxPDoLWjDaRAdP9D) · Christopher Manning 교수의 전체 강의 23강을 공개한 Stanford Online 공식 재생목록
- [중급 · 2–12시간] [Stanford CS336 — Language Modeling from Scratch](https://stanford-cs336.github.io/spring2025/) · 데이터·토크나이저부터 학습·평가까지 "LLM을 처음부터" 만드는 2025 신설 강의
- [중급 · 2–12시간] [↳ CS336 강의 영상 (Spring 2025, YouTube)](https://www.youtube.com/playlist?list=PLoROMvodv4rOY23Y0BoGoBGgQ1zmU_MT_) · 위 강의의 전체 녹화본 17강 — 토크나이저·아키텍처·GPU·MoE까지 처음부터 쌓아 올리는 과정
- [중급 · 2–12시간] [Karpathy — Neural Networks: Zero to Hero](https://karpathy.ai/zero-to-hero.html) · micrograd→makemore→GPT까지 코드로 쌓아올리는 무료 강의 시리즈
- [중급 · 2–12시간] [karpathy/nanoGPT](https://github.com/karpathy/nanoGPT) · GPT를 ~300줄로 재현하는 가장 유명한 미니멀 학습용 구현체
- [중급 · 2–12시간] [karpathy/makemore](https://github.com/karpathy/makemore) · bigram→트랜스포머까지 언어모델을 단계별로 만드는 실습 저장소
- [중급 · 2–12시간] [Practical Deep Learning — fast.ai](https://course.fast.ai/) · 톱다운 방식으로 빠르게 실전 딥러닝에 진입하는 인기 강의
- [중급 · 2–12시간] [DeepLearning.AI — Short Courses](https://www.deeplearning.ai/short-courses/) · Andrew Ng 팀이 파트너사와 만든 1시간짜리 실전 LLM 단기 강좌 모음
- [중급 · 2–12시간] [Hugging Face — LLM Course](https://huggingface.co/learn/llm-course) · Transformers·토크나이저·파인튜닝을 실습으로 배우는 무료 공식 코스
- [중급 · 2–12시간] [Andrej Karpathy — YouTube 채널](https://www.youtube.com/@AndrejKarpathy) · 위 강의들의 원본 채널, LLM 학습 영상의 사실상 표준

## 3. 🤖 에이전트 · 툴콜 · MCP

> "모델이 스스로 도구를 쓰게" 만드는 패턴과, 그 표준이 된 MCP.

- [중급 · 20–90분] [Model Context Protocol — 공식 소개](https://modelcontextprotocol.io/docs/getting-started/intro) · LLM에 도구·데이터를 연결하는 개방형 표준 MCP의 출발점
- [중급 · 20–90분] [MCP Specification (2025-06-18)](https://modelcontextprotocol.io/specification/2025-06-18) · 프로토콜 스펙 원문 — 서버/클라이언트를 직접 만들 때 필독
- [중급 · 20–90분] [modelcontextprotocol — GitHub 조직](https://github.com/modelcontextprotocol) · SDK·레퍼런스 서버·스키마 등 MCP 생태계 소스 저장소
- [중급 · 20–90분] [Anthropic — Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents) · 워크플로우 vs 에이전트, 프롬프트 체이닝·라우팅·오케스트레이션 패턴 정리 (에이전트 설계 필독)
- [중급 · 20–90분] [Anthropic — Building agents with the Claude Agent SDK](https://claude.com/blog/building-agents-with-the-claude-agent-sdk) · 실제 프로덕션 에이전트를 SDK로 짜는 공식 가이드
- [중급 · 20–90분] [ReAct: Synergizing Reasoning and Acting (arXiv)](https://arxiv.org/abs/2210.03629) · 추론(Reason)과 행동(Act)을 번갈아 하는 에이전트 패턴의 원조 논문
- [중급 · 20–90분] [Toolformer: LMs Can Teach Themselves to Use Tools (arXiv)](https://arxiv.org/abs/2302.04761) · 모델이 스스로 API 호출을 학습하는 툴 사용의 대표 논문

## 4. 💻 Claude Code · 코딩 에이전트

> 터미널에서 사는 코딩 에이전트 — 공식 문서와 실전 베스트 프랙티스.

- [입문 · 15–45분] [Claude Code — Overview](https://code.claude.com/docs/en/overview) · Claude Code가 무엇이고 무엇을 할 수 있는지 공식 개요
- [입문 · 15–45분] [Claude Code — Quickstart](https://code.claude.com/docs/en/quickstart) · 설치부터 첫 작업까지 10분 온보딩 가이드
- [입문 · 15–45분] [Claude Code — Common Workflows](https://code.claude.com/docs/en/common-workflows) · 코드베이스 탐색·리팩터·테스트 등 실무 워크플로우 모음
- [입문 · 15–45분] [Claude Code — MCP 연결](https://code.claude.com/docs/en/mcp) · Claude Code에 외부 도구를 MCP로 붙이는 방법
- [입문 · 15–45분] [Claude Code — Best Practices (Anthropic Engineering)](https://code.claude.com/docs/en/best-practices) · CLAUDE.md·컨텍스트 관리 등 에이전틱 코딩을 잘 쓰는 노하우
- [입문 · 15–45분] [anthropics/claude-code — GitHub](https://github.com/anthropics/claude-code) · 이슈·릴리스·레퍼런스가 모이는 공식 저장소

## 5. ✍️ 프롬프트 · 컨텍스트 엔지니어링

> 잘 물어보는 법(Prompt)에서, 무엇을 컨텍스트 윈도우에 넣을지 설계하는 법(Context)으로.

- [입문 · 20–60분] [Anthropic — Prompt Engineering Overview](https://docs.claude.com/en/docs/build-with-claude/prompt-engineering/overview) · Claude 기준 프롬프트 기법 총정리 (공식)
- [입문 · 20–60분] [Anthropic — Interactive Prompt Engineering Tutorial](https://github.com/anthropics/prompt-eng-interactive-tutorial) · 9개 챕터 실습형 프롬프트 튜토리얼 (초급→고급)
- [입문 · 20–60분] [OpenAI — Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering) · GPT 계열 기준 프롬프트 작성 전략 공식 가이드
- [입문 · 20–60분] [Prompt Engineering Guide (DAIR.AI)](https://www.promptingguide.ai/) · 기법·논문·예제를 총망라한 커뮤니티 표준 레퍼런스
- [입문 · 20–60분] [Anthropic — Effective Context Engineering for AI Agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents) · 프롬프트 이후의 화두 "컨텍스트 엔지니어링"을 정의한 글
- [입문 · 20–60분] [OpenAI Cookbook](https://cookbook.openai.com/) · 실전 예제 코드로 배우는 프롬프트·툴콜·임베딩 레시피

## 6. 📚 RAG (검색 증강 생성)

> 모델의 지식 한계를 외부 검색으로 메우는 파이프라인 설계.

- [중급 · 30–120분] [RAG: Retrieval-Augmented Generation (원논문, arXiv)](https://arxiv.org/abs/2005.11401) · RAG라는 개념을 처음 제시한 2020년 원조 논문
- [중급 · 30–120분] [Retrieval-Augmented Generation for LLMs: A Survey (arXiv)](https://arxiv.org/abs/2312.10997) · Naive→Advanced→Modular RAG까지 전체 지형을 정리한 서베이
- [중급 · 30–120분] [Anthropic — Contextual Retrieval](https://www.anthropic.com/engineering/contextual-retrieval) · 청크에 문맥을 덧붙여 검색 정확도를 크게 올리는 실전 기법
- [중급 · 30–120분] [LangChain — Retrieval 문서](https://docs.langchain.com/oss/python/langchain/retrieval) · RAG 파이프라인을 코드로 구성하는 공식 가이드
- [중급 · 30–120분] [LlamaIndex — 공식 문서](https://docs.llamaindex.ai/) · 문서 인덱싱·쿼리에 특화된 RAG 프레임워크 레퍼런스
- [중급 · 30–120분] [Pinecone — Retrieval-Augmented Generation](https://www.pinecone.io/learn/retrieval-augmented-generation/) · 벡터DB 관점에서 RAG를 개념부터 실습까지 정리한 학습 글
- [중급 · 30–120분] [Hugging Face Cookbook — Simple RAG](https://huggingface.co/learn/cookbook/rag_zephyr_langchain) · 오픈모델(Zephyr)+LangChain으로 만드는 최소 RAG 예제

## 7. 🎯 파인튜닝 · RLHF · 정렬 (Alignment)

> 사전학습 모델을 "사람이 원하는 대로" 다듬는 방법 — SFT, RLHF, DPO, LoRA.

- [중급 · 30–90분] [InstructGPT: Training LMs to follow instructions (arXiv)](https://arxiv.org/abs/2203.02155) · RLHF로 지시를 따르게 만든, ChatGPT의 직계 조상 논문
- [중급 · 30–90분] [Illustrating RLHF — Hugging Face 블로그](https://huggingface.co/blog/rlhf) · RLHF 3단계(SFT·보상모델·PPO)를 그림으로 설명한 입문 글
- [중급 · 30–90분] [Constitutional AI: Harmlessness from AI Feedback (arXiv)](https://arxiv.org/abs/2212.08073) · 사람 대신 원칙(헌법)으로 정렬하는 Anthropic의 RLAIF 논문
- [중급 · 30–90분] [DPO: Direct Preference Optimization (arXiv)](https://arxiv.org/abs/2305.18290) · 보상모델·RL 없이 선호 데이터로 바로 정렬하는 방법
- [중급 · 30–90분] [LoRA: Low-Rank Adaptation (arXiv)](https://arxiv.org/abs/2106.09685) · 소수 파라미터만 학습해 저비용으로 파인튜닝하는 표준 기법
- [중급 · 30–90분] [QLoRA: Efficient Finetuning of Quantized LLMs (arXiv)](https://arxiv.org/abs/2305.14314) · 4-bit 양자화로 단일 GPU에서 대형모델 파인튜닝을 가능케 한 논문
- [중급 · 30–90분] [Hugging Face PEFT 문서](https://huggingface.co/docs/peft) · LoRA·QLoRA 등 파라미터 효율적 파인튜닝 공식 라이브러리
- [중급 · 30–90분] [Hugging Face TRL 문서](https://huggingface.co/docs/trl) · SFT·DPO·PPO를 코드로 돌리는 RLHF/정렬 학습 라이브러리

## 8. 📄 핵심 논문 (Must-Read Papers)

> LLM 시대를 만든 논문들. **모든 arXiv 링크는 abs 페이지를 직접 열어 논문 제목이 표기와 일치하는지 대조했습니다** (ID만 그럴듯하게 적힌 항목이 없도록).

### 랜드마크 (2017–2023)

- [심화 · 45–120분] [Attention Is All You Need (2017)](https://arxiv.org/abs/1706.03762) · 트랜스포머를 세상에 내놓은 모든 것의 시작
- [심화 · 45–120분] [Scaling Laws for Neural Language Models (2020)](https://arxiv.org/abs/2001.08361) · 모델·데이터·연산을 키우면 예측 가능하게 좋아진다는 스케일링 법칙
- [심화 · 45–120분] [GPT-3: Language Models are Few-Shot Learners (2020)](https://arxiv.org/abs/2005.14165) · 거대 모델의 few-shot in-context learning을 입증한 논문
- [심화 · 45–120분] [Chinchilla: Training Compute-Optimal LLMs (2022)](https://arxiv.org/abs/2203.15556) · 같은 연산이면 "더 많은 데이터"가 답이라는 컴퓨트-최적 학습
- [심화 · 45–120분] [Chain-of-Thought Prompting (2022)](https://arxiv.org/abs/2201.11903) · "단계별로 생각하라"로 추론 성능을 끌어올린 프롬프트 기법
- [심화 · 45–120분] [InstructGPT / RLHF (2022)](https://arxiv.org/abs/2203.02155) · 인간 피드백 강화학습으로 정렬한 대화형 LLM의 원형
- [심화 · 45–120분] [Self-Instruct (2022)](https://arxiv.org/abs/2212.10560) · 모델이 스스로 지시 데이터를 생성해 튜닝하는 방법
- [심화 · 45–120분] [Llama 2 (2023)](https://arxiv.org/abs/2307.09288) · 오픈 웨이트 LLM 대중화를 이끈 Meta의 기술 보고서
- [심화 · 45–120분] [ReAct (2023)](https://arxiv.org/abs/2210.03629) · 추론+행동 결합, LLM 에이전트의 개념적 토대
- [심화 · 45–120분] [GPT-4 Technical Report (2023)](https://arxiv.org/abs/2303.08774) · 멀티모달·시험 성능 등 GPT-4의 능력과 한계를 담은 보고서

### 2024–2026 프런티어 — MoE · 롱컨텍스트 · 추론 · SSM

> 지금 모델들이 왜 이렇게 생겼는지를 설명하는 네 갈래. 위 랜드마크를 읽은 뒤에 보세요.

**MoE (Mixture of Experts) — 파라미터는 키우되 계산은 아끼기**

- [심화 · 60–120분] [Mixtral of Experts (2024)](https://arxiv.org/abs/2401.04088) · sparse MoE가 성능과 추론 비용을 어떻게 함께 다루는지 보여 주는 실전형 기술 보고서
- [심화 · 90–150분] [DeepSeek-V3 Technical Report (2024)](https://arxiv.org/abs/2412.19437) · 671B MoE를 실제로 학습시킨 과정을 라우팅·로드밸런싱·학습 비용까지 공개한 보고서

**롱컨텍스트 — 컨텍스트 윈도우는 어떻게 늘어났고, 늘어난 만큼 쓸 수 있나**

- [심화 · 60–120분] [LongRoPE (2024)](https://arxiv.org/abs/2402.13753) · 위치 임베딩 확장으로 롱컨텍스트를 만드는 대표 접근; 긴 문서·에이전트 설계 전에 읽기 좋음
- [심화 · 60–120분] [Gemini 1.5 (2024)](https://arxiv.org/abs/2403.05530) · 100만 토큰 컨텍스트를 제품 규모로 끌어올린 기술 보고서
- [심화 · 45–90분] [RULER: What's the Real Context Size of Your Long-Context LMs? (2024)](https://arxiv.org/abs/2404.06654) · "광고된 컨텍스트 길이 ≠ 실제로 쓸 수 있는 길이"를 벤치마크로 보여 주는 논문; 롱컨텍스트를 믿기 전에 읽기

**Test-time compute · 추론 모델 — 학습이 아니라 추론에 연산을 더 쓰기**

- [심화 · 60–120분] [Scaling LLM Test-Time Compute Optimally (2024)](https://arxiv.org/abs/2408.03314) · 추론 시점에 연산을 더 쓰는 편이 파라미터를 키우는 것보다 유리해지는 조건을 정면으로 분석
- [심화 · 60–120분] [DeepSeek-R1 (2025)](https://arxiv.org/abs/2501.12948) · open reasoning model의 학습·증류 설계를 공개해 추론 모델을 실험하려는 사람에게 유용

**SSM — 어텐션 바깥의 계보**

- [심화 · 60–120분] [Mamba: Linear-Time Sequence Modeling with Selective State Spaces (2023)](https://arxiv.org/abs/2312.00752) · attention 밖의 SSM 계열이 왜 다시 주목받는지 이해하는 출발점
- [심화 · 90–150분] [Transformers are SSMs (Mamba-2, 2024)](https://arxiv.org/abs/2405.21060) · 트랜스포머와 SSM이 같은 구조의 두 얼굴임을 보이고 Mamba-2를 제시

## 9. ✅ 평가 · Evals

> 만든 모델·프롬프트·에이전트가 **정말 좋아졌는지** 재현 가능하게 확인하는 방법.

- [입문 · 30분] [EleutherAI LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness) · 공개 모델 벤치마크를 같은 조건에서 재현하는 가장 널리 쓰이는 평가 도구
- [입문 · 30–60분] [promptfoo](https://www.promptfoo.dev/docs/intro/) · 프롬프트·RAG·에이전트를 assertion과 red-team 케이스로 CI에서 검증하는 실무 도구
- [입문 · 20분] [LMSYS Chatbot Arena](https://lmarena.ai/) · 사람 선호 기반 리더보드가 모델 선택에 무엇을 말하고 무엇을 말하지 않는지 배운다
- [중급 · 60–120분] [SWE-bench](https://www.swebench.com/) · 실제 GitHub 이슈 해결 능력으로 코딩 에이전트를 평가하는 대표 벤치마크

## 10. 🖥️ 로컬 실행 · 서빙 · 양자화

> API 호출을 넘어 내 컴퓨터와 서버에서 모델을 돌리고, 속도·메모리·품질을 교환하는 법.

- [입문 · 30분] [Ollama](https://ollama.com/) · 가장 짧은 경로로 로컬 모델을 내려받아 API로 실행하는 시작점
- [중급 · 60–120분] [vLLM](https://docs.vllm.ai/) · PagedAttention과 continuous batching을 포함한 고성능 LLM 서빙의 표준 레퍼런스
- [중급 · 60–120분] [llama.cpp](https://github.com/ggml-org/llama.cpp) · CPU·Apple Silicon에서도 GGUF 양자화 모델을 이해하고 실행하는 핵심 프로젝트
- [중급 · 45–90분] [Hugging Face — Bitsandbytes quantization](https://huggingface.co/docs/transformers/quantization/bitsandbytes) · 8-bit/4-bit 양자화의 트레이드오프를 코드로 확인한다

## 11. 🛡️ LLM 보안

> 도구를 쓰고 데이터를 읽는 모델에서는 프롬프트 인젝션을 포함한 보안 설계가 기능의 일부입니다.

- [입문 · 30–60분] [OWASP Top 10 for LLM Applications](https://genai.owasp.org/llm-top-10/) · LLM 애플리케이션의 대표 위험과 완화책을 빠르게 훑는 기준선
- [중급 · 45–90분] [Anthropic — Mitigate jailbreaks and prompt injections](https://docs.claude.com/en/docs/test-and-evaluate/strengthen-guardrails/mitigate-jailbreaks) · 공격을 막는 단일 프롬프트가 아니라 계층형 방어가 필요한 이유를 배운다
- [중급 · 45–90분] [promptfoo red teaming](https://www.promptfoo.dev/docs/red-team/) · 인젝션과 데이터 유출 시나리오를 자동 테스트로 옮기는 실습 경로

## 12. 💸 비용 · 토큰 경제학

> 좋은 제품은 품질뿐 아니라 토큰·지연 시간·캐시·모델 선택 비용을 함께 관리합니다.

- [입문 · 20–40분] [OpenAI — Prompt caching](https://platform.openai.com/docs/guides/prompt-caching) · 반복되는 긴 컨텍스트 비용을 줄이는 캐시 설계의 출발점
- [중급 · 30–60분] [Anthropic — Token counting](https://docs.claude.com/en/docs/build-with-claude/token-counting) · 호출 전에 토큰을 측정해 예산·제한·UX를 통제하는 방법
- [중급 · 45–90분] [Google Cloud — AI/ML cost optimization](https://docs.cloud.google.com/architecture/framework/perspectives/ai-ml/cost-optimization) · 모델·인프라·운영 비용을 KPI와 함께 관리하는 Well-Architected 프레임워크

## 13. 🖼️ 멀티모달

> 텍스트만 다루던 LLM이 이미지·음성·문서를 이해하고 생성하는 흐름.

- [입문 · 30–60분] [OpenAI — Images and vision](https://platform.openai.com/docs/guides/images-vision) · 이미지 입력·생성 기능을 제품 흐름에 안전하게 붙이는 공식 가이드
- [중급 · 60–120분] [LLaVA: Large Language and Vision Assistant](https://arxiv.org/abs/2304.08485) · 비전 인코더와 언어 모델을 결합하는 멀티모달 assistant의 대표 논문
- [중급 · 45–90분] [Hugging Face — Multimodal task guides](https://huggingface.co/docs/transformers/tasks/vision) · 오픈 모델로 비전·문서 작업을 실험할 때의 실용적 출발점

## 14. 🇰🇷 한국어 자료

> 한국어로 깊게 파고들 수 있는, 지금도 살아있는 자료만.

- [입문 · 20–60분] [테디노트 (teddylee777) 블로그](https://teddylee777.github.io/) · LangChain·RAG·LLM 실전 예제가 가장 풍부한 한국어 기술 블로그
- [입문 · 20–60분] [테디노트 TeddyNote — YouTube](https://www.youtube.com/@teddynote) · LLM/LangChain을 한국어로 가장 꾸준히 다루는 채널
- [입문 · 20–60분] [teddylee777/langchain-kr](https://github.com/teddylee777/langchain-kr) · LangChain 공식 문서를 한국어로 재구성한 실습 튜토리얼 저장소
- [입문 · 20–60분] [ratsgo's NLPBOOK](https://ratsgo.github.io/nlpbook/) · 트랜스포머·BERT·GPT를 한국어로 깊이 있게 정리한 전자책
- [입문 · 20–60분] [가짜연구소 (Pseudo-Lab) — GitHub](https://github.com/Pseudo-Lab) · 국내 최대 오픈 AI 스터디 커뮤니티의 프로젝트·자료 모음
- [입문 · 20–60분] [모두를 위한 머신러닝/딥러닝 — 김성훈](https://hunkim.github.io/ml/) · 한국어 딥러닝 입문의 고전, 기초 개념 다지기용
- [입문 · 20–60분] [rickiepark/nlp-with-transformers](https://github.com/rickiepark/nlp-with-transformers) · 『트랜스포머를 활용한 자연어 처리』 한국어판 예제 코드
- [입문 · 20–60분] [혁펜하임 — AI & 딥러닝 강의 (YouTube)](https://www.youtube.com/@hyukppen) · 어텐션·트랜스포머 같은 딥러닝 이론을 수식까지 한국어로 차근차근 짚어 주는 강의 채널
- [중급 · 30–90분] [서울대 DSBA 연구실 (YouTube)](https://www.youtube.com/@dsba2979) · LLM·딥러닝 최신 논문을 한국어로 발표·해설하는 대학원 세미나 채널 (논문 읽기 훈련용)
- [입문 · 20–60분] [조코딩 JoCoding (YouTube)](https://www.youtube.com/@jocoding) · 비개발자·입문자가 LLM API로 AI 앱을 직접 만들어 보는 실전 채널

### 🎬 영상으로 감 잡기 (한국어)

- [입문 · 10–20분] [마블로 — 터미널 말고 보드에서 Claude Code 병렬 개발하기 (YouTube)](https://youtu.be/vsWPkl8hzq4) · 오케스트레이터가 여러 코딩 에이전트를 보드 위에서 병렬로 굴리는 한국어 실전 데모 (※ 이 저장소 관리자가 만드는 제품 [marblo.app](https://marblo.app))

---

## 📁 향후 저장소 구조

현재는 README를 검증된 인덱스로 유지합니다. 노트·실습이 실제로 쌓일 때만 아래 구조를 만듭니다.

<details>
<summary>확장 예정 구조 보기</summary>

```text
01-foundations/        # 개념 노트와 시각화
02-courses/            # 강의 수강 노트와 실습
03-agents-mcp/         # 툴콜·MCP 실험
06-rag/                # 검색 증강 생성 실습
08-papers/             # 논문 요약
```

</details>

---

> 🔗 잘못된 링크나 추가하면 좋을 자료가 있으면 이슈/PR 환영합니다.
> 기여 방법은 [CONTRIBUTING.md](CONTRIBUTING.md), 이용 조건은 [CC BY 4.0](LICENSE)을 참고하세요.
> Maintained by 데이터가답이다(동원킴) · [@melocream](https://github.com/melocream) · Built with [marblo.app](https://marblo.app)
