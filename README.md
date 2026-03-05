## Hi, I'm Béla 👋
### **Solutions Architect | Senior Java Developer | Former Oracle DBA**
![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white) ![Spring](https://img.shields.io/badge/spring-%236DB33F.svg?style=for-the-badge&logo=spring&logoColor=white) ![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white) ![GitLab](https://img.shields.io/badge/gitlab-%23181717.svg?style=for-the-badge&logo=gitlab&logoColor=white) ![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white) ![Oracle](https://img.shields.io/badge/Oracle-F80000?style=for-the-badge&logo=oracle&logoColor=white) ![Redis](https://img.shields.io/badge/redis-%23DD0031.svg?style=for-the-badge&logo=redis&logoColor=white) ![Elasticsearch](https://img.shields.io/badge/elasticsearch-%230377CC.svg?style=for-the-badge&logo=elasticsearch&logoColor=white) ![Next JS](https://img.shields.io/badge/Next-black?style=for-the-badge&logo=next.js&logoColor=white) ![NPM](https://img.shields.io/badge/NPM-%23CB3837.svg?style=for-the-badge&logo=npm&logoColor=white) ![Google Cloud](https://img.shields.io/badge/GoogleCloud-%234285F4.svg?style=for-the-badge&logo=google-cloud&logoColor=white) ![Azure](https://img.shields.io/badge/azure-%230072C6.svg?style=for-the-badge&logo=microsoftazure&logoColor=white) ![Thymeleaf](https://img.shields.io/badge/Thymeleaf-%23005C0F.svg?style=for-the-badge&logo=Thymeleaf&logoColor=white) ![TailwindCSS](https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white) ![Kubernetes](https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=for-the-badge&logo=kubernetes&logoColor=white) ![Jira](https://img.shields.io/badge/jira-%230A0FFF.svg?style=for-the-badge&logo=jira&logoColor=white) ![Maven](https://img.shields.io/badge/apachemaven-C71A36.svg?style=for-the-badge&logo=apachemaven&logoColor=white) ![GitHub Copilot](https://img.shields.io/badge/github_copilot-8957E5?style=for-the-badge&logo=github-copilot&logoColor=white) ![Ollama](https://img.shields.io/badge/ollama-%23000000.svg?style=for-the-badge&logo=ollama&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/github%20actions-%232671E5.svg?style=for-the-badge&logo=githubactions&logoColor=white) ![TeamCity](https://img.shields.io/badge/teamcity-000000.svg?style=for-the-badge&logo=teamcity&logoColor=white) ![Jenkins](https://img.shields.io/badge/jenkins-%232C5263.svg?style=for-the-badge&logo=jenkins&logoColor=white) ![SonarQube](https://img.shields.io/badge/SonarQube-black?style=for-the-badge&logo=sonarqube&logoColor=4E9BCD) ![TOGAF](https://img.shields.io/badge/TOGAF-005C94?style=for-the-badge&logo=The-Open-Group&logoColor=white) ![Scrum](https://img.shields.io/badge/Scrum-0288D1?style=for-the-badge&logo=scrumdotorg&logoColor=white) ![Agile](https://img.shields.io/badge/Agile-4CAF50?style=for-the-badge&logo=agile&logoColor=white) ![ISO](https://img.shields.io/badge/ISO%20Standards-555555?style=for-the-badge&logo=iso&logoColor=white)

I build enterprise-grade systems where **high-performance code** meets **bulletproof data architecture**. With over a decade of experience—ranging from managing 1,000+ production systems to architecting cloud-native Java microservices—I bridge the gap between complex backend logic and robust infrastructure.


## 🏗️ My Ideal Enterprise Stack
This architecture represents my "gold standard" for a secure, scalable, and observable production environment. It reflects my philosophy: **Security by design, data integrity by default, and total observability**.

```mermaid
graph TD
    %% Global Settings
    direction TB

    subgraph Edge [Global Edge]
        CF[Cloudflare WAF / CDN]
    end

    subgraph K8s_Cluster [Kubernetes Cluster]
        direction TB
        GW[API Gateway]
        
        subgraph App_Layer [Compute Layer]
            direction LR
            NEXT[Next.js SSR]
            SB[Spring Boot API]
        end

        subgraph Security [Security]
            HV{{HashiCorp Vault}}
        end

        subgraph Obs [Elastic Observability]
            APM[Elastic APM Server]
            ES[(Elasticsearch)]
            KIB[Kibana Dashboard]
            APM --- ES --- KIB
        end

        R[(Redis Cache)]
    end

    subgraph Persistence [Data Layer]
        direction LR
        subgraph Postgres_Stack [Operational]
            E[(Postgres)]
            PBR[[pgBackRest]]
        end

        subgraph Oracle_Stack [Analytical / BI]
            F[(Oracle DB)]
            RMAN[[RMAN]]
        end
    end

    %% Flow logic
    CF ===> GW ===> NEXT ===> SB
    
    %% Security & Data
    SB -.-> HV
    SB <---> R
    SB ===>|JDBC w/ Vault| E
    SB ===>|JDBC w/ Vault| F
    E ===>|ETL| F

    %% Full Stack Monitoring (APM & Beats)
    NEXT & SB & GW -.->|Traces/Logs| APM
    R & E & F -.->|Metrics/Logs| ES
    HV -.->|Audit Logs| ES

    %% Styling
    style CF fill:#f38020,color:#fff
    style NEXT fill:#000,color:#fff
    style SB fill:#6db33f,color:#fff
    style ES fill:#005a9e,color:#fff
    style APM fill:#005a9e,color:#fff
    style KIB fill:#005a9e,color:#fff
    style HV fill:#000,color:#fff,stroke:#ffd700
    style K8s_Cluster fill:#f0f4f8,stroke:#326ce5
```

## 🛠️ Core Competencies

### Architectural Strategy
- Distributed Systems: Designing microservices with Spring Boot and Kubernetes, ensuring high availability and seamless communication via API Gateways.
- Data Engineering: Expert-level database design, moving from transactional (OLTP) to analytical (OLAP) via custom ETL processes and Snowflake schemas wether it is based on PostgreSQL or ORACLE, means no problem.

### Security & Performance
- Secret Management: Implementing HashiCorp Vault for dynamic database credential rotation and zero-trust security.
- Observability: Full-stack monitoring using the Elastic (ELK) Stack and APM for distributed tracing across services.
- Caching: Optimizing application throughput with Redis to reduce database contention and latency.

### Coding & Framework Expertise
- **Spring Ecosystem**: Extensive experience with Spring Boot, Spring Security, Spring Data, and Spring Cloud for building resilient, cloud-native applications.
- **Database Migrations**: Expert use of Flyway for version-controlled, automated database schema changes, ensuring parity across Dev, Test, and Prod.
- **Modern Java**: Proficient in leveraging the latest Java features to write clean, maintainable, and high-performance code.
- **NextJS**: well, here I have to tell, I am not the UI expert. Yet, I can manage myself comfortably among divs and buttons... 🤿

### Observability (ELK Stack)
- **Full-Stack Monitoring**: Implementing Elastic APM for distributed tracing across Next.js and Spring Boot.
- **Visualization & Insights**: Creating advanced Kibana dashboards to monitor system health, audit logs, and business metrics in real-time.

### CI/CD & DevOps Automation
- **Automated Security**: Integrating Snyk into the pipeline for real-time vulnerability scanning of dependencies and container images.
- **Code Quality & Governance**: Leveraging SonarQube / SonarCloud to enforce high standards through static code analysis, identifying technical debt and security hotspots.
- **Orchestration**: Proficient in GitHub Actions, TeamCity, and Jenkins for managing complex build and deployment lifecycles. And once I saw a Bamboo deployment... 🎍😄

A pipeline with which I could live with, would look something like:
```mermaid
graph LR
    subgraph Dev [Development]
        A[Code Commit] --> B[Push to GitHub]
    end

    subgraph CI [Continuous Integration]
        direction TB
        B --> C[Maven Build]
        C --> D{Unit Tests}
        
        D -- Pass --> E[SonarCloud Scan]
        D -- Fail --> X[Pipeline Failed]
        
        E --> F{Quality Gate}
        F -- Pass --> G[Snyk Security Scan]
        F -- Fail --> X
        
        G --> H{Vulnerability Gate}
        H -- Pass --> I[Dockerize & Tag]
        H -- Fail --> X
    end

    subgraph CD [Continuous Deployment]
        direction TB
        I --> J[Push to Registry]
        J --> K[K8s Rolling Update]
        K --> L[Post-Deploy Tests]
    end

    %% Styling
    style X fill:#ff9999,stroke:#333
    style E fill:#f3702a,color:#fff
    style G fill:#4c4a73,color:#fff
    style I fill:#2496ed,color:#fff
    style K fill:#326ce5,color:#fff
    style F stroke-width:4px,stroke-dasharray: 5 5
    style H stroke-width:4px,stroke-dasharray: 5 5
```

### The DBA Heritage
- **Disaster Recovery**: Implementing professional-grade backup strategies using pgBackRest for Postgres and RMAN for Oracle.
- **Tuning**: Deep performance tuning of Oracle 10g-21c RAC environments, including High Availability (Data Guard) ASM and Grid Control, with similar mindset when it comes to open source: hands on experience with PostgreSQL since version 10.
- **Stored procedures, JSON, custom data types, XML**: yes, we need to talk about these, eventho everyone would get rid of them, at a certain point, they somehow appear in the database :eyes:. If done with right, they **CAN** be part of a performant production environment. Imho key is to document them properly, and use them with caution. Been there, done that :godmode:

### Methodologies & Standards
- **Enterprise Architecture (TOGAF)**: Applying the ADM (Architecture Development Method) to align IT strategy with business goals, ensuring scalable and modular system evolution.
- **Compliance & Quality (ISO)**: Experienced in architecting systems that adhere to ISO standards (such as **ISO 27001** for security or **ISO 9001** for quality management), critical for Luxembourg's financial and regulatory environments.
- **Agile & Scrum**: Deeply rooted in Agile mindsets. I advocate for **Scrum frameworks** to drive iterative development, ensuring rapid feedback loops and high-quality deliverables in hybrid and cross-functional teams.

### Experience Highlights
- **Solutions Architect**: Currently leading the evolution of energy market auction platforms and data exchange API-s in Luxembourg.
- **Senior Java Developer**: Specialist in the Spring ecosystem (Boot, Data, Security, Cloud).
- **Database Administrator**: Supported 1000+ production RAC databases across EMEA, focusing on 24/7 uptime and extreme performance tuning.

### Education
- BSc Software Information Technology
- Oracle Database 11g: SQL Fundamentals I
- Oracle Database 11g: Administration I
- Oracle Database 11g: Administration II
- Upgrade to Oracle Database 12c
- Kubernetes for App Developers (LFD459)
- Certified Kubernetes Application Developer
- TOGAF® Enterprise Architecture Foundation
- Currently chasing AZ-204 Developing Solutions for Microsoft Azure certificates

## 🕹️ Outside the IDE
While my professional life is spent at the computer, I like to spend even more time close to it 😲... I’m a dedicated gamer who enjoys the tactical side of play. It’s my favorite way to reset, while having fun with my friends online. My other hobbies are cycling, hiking with my family and friends, or reading a good book, well or even a bad one 😄, and discuss it later with someone.
  
## 📫 Let's Connect
I'm always interested in discussing complex system design, Kubernetes orchestration, or the future of Java, in the growing shade of the mighty AI :robot:, **our field of work is changing**. Changing ever since I stepped onto this path a decade ago, and will be doing exactly that in the future. But in the end, isn't this the very reason why it is so interesting :fire:?

[![LinkedIn](https://img.shields.io/badge/LinkedIn-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/b%C3%A9la-vanek-83523b54/)
