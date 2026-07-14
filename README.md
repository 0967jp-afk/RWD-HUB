# RWD-HUB
start-up project
flowchart TD
    title[("RWD-Hub: Платформа RWD/RWE")]
    title -.-> Sources

    subgraph Sources ["Источники данных"]
        direction TB
        MIS1[MIS #1<br/>ЭМК/МИС]
        MIS2[MIS #2<br/>ЭМК/МИС]
        MIS3[MIS ... N<br/>ЭМК/МИС]
        LAB[Лабораторные<br/>системы]
        PHARM[Аптечные<br/>системы]
    end

    Sources --> Adapters

    subgraph Adapters ["Универсальные API-адаптеры"]
        direction TB
        ADAPI["Коннекторы к разным МИС<br/>(REST, SOAP, DB)"]
    end

    Adapters --> Standardization

    subgraph Standardization ["Слой стандартизации данных"]
        direction TB
        STD["FHIR Ru Core /<br/>OMOP CDM"]
    end

    Standardization --> Quality

    subgraph Quality ["Data Quality Guardian"]
        direction TB
        DQG["Контроль качества<br/>в реальном времени<br/>(полнота, непротиворечивость)"]
    end

    Quality --> Security

    subgraph Security ["Обезличивание и безопасность"]
        direction TB
        SEC["152-ФЗ, обезличивание,<br/>локализация данных"]
    end

    Security --> Federated

    subgraph Federated ["Федеративное обучение ИИ"]
        direction TB
        FL["Обучение моделей<br/>без передачи сырых данных"]
    end

    Federated --> Analytics

    subgraph Analytics ["Аналитика и RWE-модули"]
        direction TB
        ANA["Отчёты, метрики,<br/>пациентские регистры"]
    end

    Analytics --> Clients

    subgraph Clients ["Клиенты"]
        direction TB
        PHARMA[Фармкомпании]
        INSUR[Страховые /<br/>Регуляторы]
        RES[Исследователи /<br/>Университеты]
    end

    style title fill:#2b2b2b,color:#fff,stroke:#2b2b2b
    style Sources fill:#f5f5f5,stroke:#333,stroke-width:2px
    style Adapters fill:#e6f3ff,stroke:#0078d4,stroke-width:2px
    style Standardization fill:#e6f3ff,stroke:#0078d4,stroke-width:2px
    style Quality fill:#e6f9e6,stroke:#107c10,stroke-width:2px
    style Security fill:#fff4e6,stroke:#ffaa00,stroke-width:2px
    style Federated fill:#fff4e6,stroke:#ffaa00,stroke-width:2px
    style Analytics fill:#f0f6ff,stroke:#005a9e,stroke-width:2px
    style Clients fill:#f5f5f5,stroke:#333,stroke-width:2px
