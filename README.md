# study.langgraph
### 에이전트 프레임워크 종류
- CrewAI
  - `LangChain`으로 구축된 프레임워크
  - Agent, Tool, Task. Process, Crew로 구성
  - LangChain과 결합 용이, 멀티에이전트 아키텍처 최적화
- AutoGen
  - MS에서 구축한 멀티 에이전트 대화 시스템 구축 프레임워크
  - 사용자 대신하는 UserProxyAgent, 이를 보조하는 AssistantAgent 등 존재
  - 여러 에이전트 간의 `대화` 자체에 집중
- Langgraph
  - LangChain 생태계에서 구축된 그래프 방식의 프레임워크, Low-Level 접근
  - 에이전트-에이전트, 에이전트-도구 간의 흐름을 상세히 정의하므로 Controllability 높음
 
### LLM 프레임워크 생태계:언어별 적합성
```mermaid
graph TB
    %% 메인 노드 정의
    LC["Langchain 🔗<br/><small>기본 LLM 통합 프레임워크</small><br/><small>👍 Python</small>"]
    LG["LangGraph 🌐<br/><small>다중 에이전트 시스템</small><br/><small>👍 Python</small>"]
    SK["Semantic Kernel 🧠<br/><small>기본 LLM 통합 프레임워크</small><br/><small>👍 C#/.NET</small>"]
    AG["AutoGen 🤖<br/><small>다중 에이전트 시스템</small><br/><small>👍 Python</small>"]
    
    %% 하위 카테고리
    PY["Python 생태계 🐍"]
    DN["C#/.NET 생태계 ⚡"]
    
    %% 연결 관계
    LC --> LG
    SK --> AG
    
    %% 언어별 그룹화
    PY -.-> LC
    PY -.-> LG
    PY -.-> AG
    DN -.-> SK
    
    %% 스타일링
    classDef python fill:#3776AB,color:white,stroke:#2D5F8A,stroke-width:2px
    classDef dotnet fill:#512BD4,color:white,stroke:#3E1FA3,stroke-width:2px
    classDef base fill:#f9f9f9,stroke:#ccc,stroke-width:1px
    
    class LC,LG,AG python
    class SK dotnet
    class PY python
    class DN dotnet
```

