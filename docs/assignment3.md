## Assignment 3: Materials and Methods 

```mermaid
graph TD
    %% --- Style Definitions ---
    %% Node Styles
    classDef purpleTheme fill:#9370DB,stroke:#8A2BE2,stroke-width:2px,color:#fff
    classDef pinkTheme fill:#DB7093,stroke:#C71585,stroke-width:2px,color:#fff

    %% Subgraph Container Style (Lavender)
    style S1 fill:#E6E6FA,stroke:#B57EDC,stroke-width:2px
    style S2 fill:#E6E6FA,stroke:#B57EDC,stroke-width:2px
    style S3 fill:#E6E6FA,stroke:#B57EDC,stroke-width:2px
    style S4 fill:#E6E6FA,stroke:#B57EDC,stroke-width:2px

    %% --- Chart Structure ---
    %% Subgraphs now have an ID (S1, S2, etc.) and a Title in quotes
    subgraph S1 ["Research Input & Core Problem"]
        A["Problem: How to optimize LLM workflows for research?"]
    end

    subgraph S2 ["Core Engine & Integrations"]
        B[LLM-Powered Research Tool]
        C["PostgreSQL Database (Structured Data)"]
        D["Weaviate (Text Mining / Vector Search)"]
        
        B -- "MCP Connection" --> C
        B -- "MCP Connection" --> D
    end
    
    subgraph S3 ["Methodologies & Outputs"]
        E[Enhanced Database Interaction]
        F[Pattern Recognition in Large Datasets]
        G[Collaborative Research Documentation]
        H[Vibe Code Methodologies]
    end

    subgraph S4 ["Ultimate Goal"]
        I[Revolutionized Academic Inquiry & Discovery]
    end
    
    %% --- Flow Logic ---
    A --> B
    C --> E
    D --> F
    H --> G
    
    E --> I
    F --> I
    G --> I

    %% --- Apply Node Styles ---
    class A,E,F,G,H,I pinkTheme
    class B,C,D purpleTheme
```

