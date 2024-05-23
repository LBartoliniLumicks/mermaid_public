flowchart LR
        %% LABELS 
        ROOT((("Alpha\nVerification")))
        
        OPEN(fa:fa-expand\nOpen Points \n& Key Deliverables)
        TESTS(fa:fa-circle-question\nTests)
        INSTRUMENT(fa:fa-gear\nInstrument)
        FMEA(fa:fa-triangle-exclamation\nFMEA)
        META(Meta)
        REQS(fa:fa-crosshairs\nRequirements)
        ASSAY("fa:fa-flask \nAssay")
        SAT("fa:fa-house\n Site Acceptance Test")
        
        WF_PROTOCOLS(WF Protocols)
        LHS_RECIPES(LHS Recipes)
        TEST_VERIF(Verification)
        OPEN_TIMELINE(Timeline View)
        OPEN_DETAILS(Open Point Details)
        OPEN_CLOSED("Closed Points (Decisions)")
        TEST_LEARN(Learning)
        HW_MODULES(HW Modules)
        IMPROV_LIST(Improvement List for Beta)
        SYSTEM_CHANGELOG(Systems Change-log)
        MINUTES(fa:fa-note-sticky\nMeeting Notes)
        KNOWLEDGE_LIB(fa:fa-bookmark\nKnowledge Library)
        ISSUES(fa:fa-circle-xmark\nIssue tracking)
        MINUTES_CORE(Core Team)
        SOP(Standard Operating Protocols)
        ASSAY_VERIF(Assay Verification experiments)
        CONCEPTUAL_STEPS(Conceptual Steps)
        CELL_LINES(Cell Lines)
        ELEMENTARY_STEPS("Elementary (machine) steps")
        MINUTES_LEARN(Learning Events)
        LEARNING_GROUPS(Learning groups)
    
        %% LINKS
        ROOT ===> ASSAY
        ROOT ===> OPEN
        ROOT ===> TESTS
        ROOT ===> SAT
        ROOT ===> REQS
        ROOT ===> META
        ROOT ===> FMEA
        ROOT ===> INSTRUMENT
    
        subgraph Assay
        ASSAY --> SOP
        ASSAY --> ASSAY_VERIF
        ASSAY --> CONCEPTUAL_STEPS
        ASSAY_VERIF --> CELL_LINES
        SOP ---> WF_PROTOCOLS
        WF_PROTOCOLS --> ML_PREP(ML Prep.\Protocol)
        WF_PROTOCOLS --> EC_PREP(EC Prep.\nProtocol)
        SOP --> LHS_RECIPES
        CONCEPTUAL_STEPS --> ELEMENTARY_STEPS
        end
    
        subgraph Tests
        TESTS --> TEST_LEARN
        TESTS --> TEST_VERIF
        SAT -.->|includes| TEST_VERIF
        end
        
        subgraph Other
        REQS -.-|define| TEST_VERIF
        META --> KNOWLEDGE_LIB
        META --> ISSUES
        META --> LEARNING_GROUPS -.- MINUTES_LEARN
        META --> MINUTES
        MINUTES --> MINUTES_LEARN
        MINUTES --> MINUTES_CORE
        FMEA
        end
    
        subgraph Open_points
        OPEN --> OPEN_TIMELINE
        OPEN --> OPEN_DETAILS
        OPEN -->|when `closed`\nlisted in| OPEN_CLOSED
        end
    
        subgraph Instrument
        INSTRUMENT --> IMPROV_LIST
        INSTRUMENT --> SYSTEM_CHANGELOG
        INSTRUMENT --> HW_MODULES
        end
        
    
    classDef default stroke:#000000, fill:#FFFFFF;
    
    classDef commonStyle stroke:#000000,fill:#e0ecf4,stroke-width:4px;
    class ASSAY,OPEN,SAT,TESTS,INSTRUMENT,FMEA,MINUTES,REQS,KNOWLEDGE_LIB,ISSUES,SOP,ASSAY_VERIF,CONCEPTUAL_STEPS commonStyle;
    
    classDef rootStyle stroke:#4d004b, fill:#bfd3e6,stroke-width:3px,font-size:20px,font-weight:bold;
    class ROOT rootStyle;
    
    classDef subgraphStyle stroke:#969696, fill:#f3f3f3;
    class Instrument,Open_points,Assay,Other,Tests subgraphStyle;
    
    click ROOT href "https://coda.io/d/_dsmgymC2yEv/START-HERE-Alpha-Verification_suDTz"
    
    click SOP href "https://coda.io/d/_dsmgymC2yEv/SOP-Experiment-Baseline_suGTp"
    click ASSAY href "https://coda.io/d/_dsmgymC2yEv/Assay-Workflow_suz9C"
    click ASSAY_VERIF href "https://coda.io/d/_dsmgymC2yEv/Assay-verification-experiments_suoJU"
    click CELL_LINES href "https://coda.io/d/_dsmgymC2yEv/Cell-lines-for-Alpha-verification_suuzh"
    click CONCEPTUAL_STEPS href "https://coda.io/d/_dsmgymC2yEv/Baseline-DOP-Development-Operating-Procedure_suVaC"
    click ELEMENTARY_STEPS href "https://coda.io/d/_dsmgymC2yEv/Chronological-full-workflow_suBve"

    
    click OPEN_TIMELINE href "https://coda.io/d/_dsmgymC2yEv/Key-Deliverables-and-Open-Points_suWHg"
    click OPEN_CLOSED href "https://coda.io/d/_dsmgymC2yEv/Decisions_suvG8"
    
    click SAT href "https://coda.io/d/_dsmgymC2yEv/Site-Acceptance-Test_suYNl"
    
    click FMEA href "https://coda.io/d/_dsmgymC2yEv/FMEA-Concerns_suhFH"
    
    click KNOWLEDGE_LIB href "https://coda.io/d/_dsmgymC2yEv/Knowledge-Library_suyOD"
    
    click INSTRUMENT href "https://coda.io/d/_dsmgymC2yEv/Instrument_suk0a"
    click IMPROV_LIST href "https://coda.io/d/_dsmgymC2yEv/Improvement-List_su3kx"
    click SYSTEM_CHANGELOG href "https://coda.io/d/_dsmgymC2yEv/System-Change-Log_suiSW"
    click HW_MODULES href "https://coda.io/d/_dsmgymC2yEv/HW-modules_sunsp"
    click MINUTES_LEARN href "https://coda.io/d/_dsmgymC2yEv/Learning-Events-Notes_suzQd"
    click MINUTES_CORE href "https://coda.io/d/_dsmgymC2yEv/Core-Team-Notes_suBjv"