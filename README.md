# Hello World! I am Krishanavatar Gurjar 👋

Senior Software Engineer · AI/ML & IDP Systems · Technical Lead @ [Infrrd.ai](https://www.infrrd.ai/)

<br>

```python
class AboutMe():
  def __init__(self):
    self.name        = "Krishanavatar Gurjar"
    self.username    = "krishanavatar"
    self.location    = "India"
    self.email       = "krishanavatargurjar@gmail.com"
    self.current_org = "https://www.infrrd.ai/"
    self.experience  = "8+ years"
    self.focus       = ["Multi-LLM Orchestration", "IDP", "AI/ML Pipelines", "Microservices"]
    self.open_to     = ["On-site", "Remote"]

  def __str__(self):
    return self.name

if __name__ == '__main__':
    me = AboutMe()
    print(me.__dict__)
```

<hr>

### What I Build

<details>
<summary>🐍 Python — Multi-LLM Orchestration Layer</summary>

```python
# Switch LLM providers via config — no code changes needed
class LLMOrchestrator:
    PROVIDERS = {
        "openai":  OpenAIClient,
        "gemini":  GeminiClient,
        "claude":  ClaudeClient,
    }

    def __init__(self, config: dict):
        provider = config["llm"]["provider"]
        self.client = self.PROVIDERS[provider](config)

    def extract(self, document: bytes, schema: dict) -> dict:
        prompt = build_extraction_prompt(document, schema)
        return self.client.complete(prompt)
```

</details>

<details>
<summary>☕ Java — Spring Boot IDP Microservice</summary>

```java
// Event-driven document processor — RabbitMQ → OCR → LLM → result store
@Service
public class DocumentProcessor {

    @RabbitListener(queues = "${queue.documents}")
    public void process(DocumentEvent event) {
        byte[]   raw = ocrService.extract(event.getFileUrl());
        JsonNode out = llmService.structure(raw, event.getSchema());
        resultStore.save(event.getDocId(), out);
    }
}
```

</details>

<details>
<summary>🐍 Python — NTP Pipeline (100% confidence extraction)</summary>

```python
# No-Touch Processing — human review only when confidence < threshold
def process_document(doc_path: str, schema: dict) -> ExtractionResult:
    raw_text  = ocr_engine.extract(doc_path)
    entities  = ner_model.predict(raw_text)
    result    = llm_extractor.structure(entities, schema)

    if result.confidence >= 1.0:
        return result.auto_approve()   # no human in the loop
    return result.queue_for_review()
```

</details>

<hr>

## Technologies & Tools

### AI / ML & LLMs

<p>
<div style="word-spacing: 15px">
    <img src="https://img.shields.io/badge/Generative%20AI-FF6B6B?style=for-the-badge&logo=openai&logoColor=white" alt="Generative AI">
    <img src="https://img.shields.io/badge/Multi--LLM%20Orchestration-4ECDC4?style=for-the-badge&logo=openai&logoColor=white" alt="Multi-LLM Orchestration">
    <img src="https://img.shields.io/badge/LLM%20Integration-95E1D3?style=for-the-badge&logo=brain&logoColor=white" alt="LLM Integration">
    <img src="https://img.shields.io/badge/Intelligent%20Document%20Processing-AA96DA?style=for-the-badge&logo=files&logoColor=white" alt="IDP">
    <img src="https://img.shields.io/badge/OCR%20%26%20Image%20Processing-FFD93D?style=for-the-badge&logo=opencv&logoColor=black" alt="OCR & Image Processing">
    <img src="https://img.shields.io/badge/YOLO%2FDarknet-6BCB77?style=for-the-badge&logo=yolo&logoColor=white" alt="YOLO/Darknet">
    <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white" alt="TensorFlow">
    <img src="https://img.shields.io/badge/spaCy%20NER-09A3D5?style=for-the-badge&logo=spacy&logoColor=white" alt="spaCy NER">
    <img src="https://img.shields.io/badge/Prompt%20Engineering-F38181?style=for-the-badge&logo=text&logoColor=white" alt="Prompt Engineering">
    <img src="https://img.shields.io/badge/LLM%20Cost%20Optimization-6BCB77?style=for-the-badge&logo=optimization&logoColor=white" alt="LLM Cost Optimization">
</div>
</p>

### Backend & Cloud

<p>
<div style="word-spacing: 15px">
    <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
    <img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java">
    <img src="https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white" alt="Flask">
    <img src="https://img.shields.io/badge/Spring%20Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white" alt="Spring Boot">
    <img src="https://img.shields.io/badge/AWS%20Lambda-FF9900?style=for-the-badge&logo=awslambda&logoColor=white" alt="AWS Lambda">
    <img src="https://img.shields.io/badge/AWS%20EC2-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white" alt="AWS EC2">
    <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker">
    <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white" alt="Kubernetes">
    <img src="https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB">
    <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white" alt="MySQL">
    <img src="https://img.shields.io/badge/Elasticsearch-005571?style=for-the-badge&logo=elasticsearch&logoColor=white" alt="Elasticsearch">
    <img src="https://img.shields.io/badge/RabbitMQ-FF6600?style=for-the-badge&logo=rabbitmq&logoColor=white" alt="RabbitMQ">
    <img src="https://img.shields.io/badge/REST%20API-FF6B6B?style=for-the-badge&logo=api&logoColor=white" alt="REST API">
    <img src="https://img.shields.io/badge/Microservices-FF6B9D?style=for-the-badge&logo=microservices&logoColor=white" alt="Microservices">
</div>
</p>

### DevOps & Observability

<p>
<div style="word-spacing: 15px">
    <img src="https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=jenkins&logoColor=white" alt="Jenkins">
    <img src="https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white" alt="Grafana">
    <img src="https://img.shields.io/badge/Kibana-005571?style=for-the-badge&logo=kibana&logoColor=white" alt="Kibana">
    <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git">
    <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Linux">
    <img src="https://img.shields.io/badge/Jira-0052CC?style=for-the-badge&logo=jira&logoColor=white" alt="Jira">
    <img src="https://img.shields.io/badge/Confluence-172B4D?style=for-the-badge&logo=confluence&logoColor=white" alt="Confluence">
    <img src="https://img.shields.io/badge/Claude%20Code-CC785C?style=for-the-badge&logo=anthropic&logoColor=white" alt="Claude Code">
    <img src="https://img.shields.io/badge/Cursor-000000?style=for-the-badge&logo=cursor&logoColor=white" alt="Cursor">
</div>
</p>

### Leadership & Strategy

<p>
<div style="word-spacing: 15px">
    <img src="https://img.shields.io/badge/Technical%20Leadership-FF6B6B?style=for-the-badge&logo=leadership&logoColor=white" alt="Technical Leadership">
    <img src="https://img.shields.io/badge/Team%20Mentorship-4ECDC4?style=for-the-badge&logo=mentorship&logoColor=white" alt="Team Mentorship">
    <img src="https://img.shields.io/badge/HLD%20%2F%20LLD-95E1D3?style=for-the-badge&logo=design&logoColor=white" alt="HLD/LLD">
    <img src="https://img.shields.io/badge/Client%20Delivery-AA96DA?style=for-the-badge&logo=delivery&logoColor=white" alt="Client Delivery">
    <img src="https://img.shields.io/badge/Cost%20Optimization-6BCB77?style=for-the-badge&logo=optimization&logoColor=white" alt="Cost Optimization">
    <img src="https://img.shields.io/badge/Stakeholder%20Communication-FFD93D?style=for-the-badge&logo=communication&logoColor=black" alt="Stakeholder Communication">
</div>
</p>

<hr>

### Key Achievements

| Achievement | Impact |
| :--- | :--- |
| **No-Touch Processing (NTP)** | 100% confidence automated extraction → **40% billing growth** for Infrrd.ai |
| **Multi-LLM Orchestration Framework** | Production-ready config-driven switching between ChatGPT, Gemini & Claude |
| **On-site Client Delivery — USA** | Delivered 2 months ahead of schedule, enabling early revenue generation |
| **End-to-End ML Ownership** | Built YOLO + NER pipelines from dataset → training → production inference |
| **Team Leadership** | Led 3–5 engineer teams across product and client delivery tracks |

<hr>

### Current Focus & Aspirations

- ✍️ Writing about AI/ML, IDP, and LLM orchestration on [krishanavatar.github.io](https://krishanavatar.github.io)
- 🤖 Building production-grade multi-LLM systems for enterprise document intelligence
- 📦 Open-sourcing tools from 8+ years of IDP/AI engineering
- 🎓 Deepening expertise in agentic AI frameworks and cost-efficient inference

<hr>

### Fun Facts & Quotes

> "The best code is the code you don't have to write." — *Every engineer after their third refactor*
>
> "Shipping 2 months early isn't luck — it's ruthless scope clarity and a team that trusts each other."
>
> `confidence_score >= 1.0` — *When your NTP pipeline finally hits 100%*

<hr>

### Connect with Me

<p style="word-spacing: 20px">
    <a href="https://www.linkedin.com/in/krishanavatar-gurjar">
        <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn">
    </a>
    <a href="https://github.com/krishanavatar">
        <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
    </a>
    <a href="https://krishanavatar.github.io">
        <img src="https://img.shields.io/badge/Blog-FF5722?style=for-the-badge&logo=blogger&logoColor=white" alt="Blog">
    </a>
    <a href="mailto:krishanavatargurjar@gmail.com">
        <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email">
    </a>
</p>

<hr>

<div align="center">
    <img src="https://komarev.com/ghpvc/?username=krishanavatar&color=blueviolet&style=flat-square" alt="Profile views" />
</div>

<div align="center">
    <img height="180em" src="https://github-readme-stats.vercel.app/api?username=krishanavatar&show_icons=true&theme=radical&hide_border=true&bg_color=0D1117&include_all_commits=true&count_private=true" alt="GitHub Stats" />
    <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=krishanavatar&layout=compact&langs_count=8&theme=radical&hide_border=true&bg_color=0D1117" alt="Top Languages" />
</div>


