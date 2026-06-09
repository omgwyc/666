graph TD
    %% 样式定义
    classDef pain fill:#ffcccc,stroke:#cc0000,stroke-width:2px;
    classDef goal fill:#ccffcc,stroke:#008800,stroke-width:2px;
    classDef data fill:#cce5ff,stroke:#0044cc,stroke-width:2px;
    classDef science fill:#fff2cc,stroke:#ccaa00,stroke-width:2px;
    classDef tech fill:#e6ccff,stroke:#6600cc,stroke-width:2px;
    classDef task fill:#d9ead3,stroke:#38761d,stroke-width:2px;
    classDef output fill:#f9cb9c,stroke:#b45f06,stroke-width:2px;

    %% 顶层：现实痛点
    Pain["公路交通设施监测痛点"]:::pain
    PainSub1["监测手段单一"]
    PainSub2["数据融合能力不足"]
    PainSub3["病害识别精度有限"]
    PainSub4["风险预警能力不强"]
    Pain --> PainSub1 & PainSub2 & PainSub3 & PainSub4

    %% 第二层：总目标
    Goal["构建多模态时空数据融合的<br>公路交通设施智能监控技术体系"]:::goal
    PainSub1 & PainSub2 & PainSub3 & PainSub4 --> Goal

    %% 数据源
    DataSource["多源数据输入"]:::data
    DataSource -.- Sat["VHR卫星影像"]
    DataSource -.- Video["地面视频流"]
    DataSource -.- GNSS["北斗+GLONASS"]
    DataSource -.- IMU["移动IMU传感器"]

    %% 科学问题
    subgraph Science ["三大关键科学问题"]
        S1["科学问题1：<br>异构数据时空基准统一<br>与多尺度协同表征"]:::science
        S2["科学问题2：<br>病害多模态、多尺度特征映射<br>与跨尺度关联"]:::science
        S3["科学问题3：<br>动态交通场景下<br>风险演化与预测"]:::science
    end

    %% 关键技术问题
    subgraph Tech ["四大关键技术问题"]
        T1["技术1：<br>亚像素级/厘米级联合配准"]:::tech
        T2["技术2：<br>混合神经网络架构设计"]:::tech
        T3["技术3：<br>北斗/GLONASS/IMU<br>复杂环境高精度定位"]:::tech
        T4["技术4：<br>小样本与不平衡学习"]:::tech
    end

    %% 研究任务
    subgraph Tasks ["四大研究任务"]
        Task1["任务1：<br>异质数据时空融合<br>与协同表征"]:::task
        Task2["任务2：<br>病害缺陷精准提取<br>与变化检测"]:::task
        Task3["任务3：<br>事故风险预测<br>与异常行为识别"]:::task
        Task4["任务4：<br>平台研发<br>与精准测绘"]:::task
    end

    %% 任务与科学问题、技术问题的映射
    Task1 --> S1
    Task1 --> T1 & T2
    Task2 --> S2
    Task2 --> T2 & T4
    Task3 --> S3
    Task3 --> T3 & T4
    Task4 --> T3

    %% 数据源到任务1
    DataSource --> Task1

    %% 任务之间的流程关系
    Task1 --> Task2
    Task2 --> Task3
    Task1 & Task2 & Task3 --> Task4

    %% 最终输出
    Output["最终成果"]:::output
    OutputSub1["智能监控原型平台"]
    OutputSub2["车道级风险预警地图"]
    OutputSub3["中俄试点验证报告"]
    OutputSub4["混合神经网络模型库"]
    Task4 --> Output
    Output --> OutputSub1 & OutputSub2 & OutputSub3 & OutputSub4

    %% 反馈循环（虚线）
    Task2 -.->|"病害反馈优化融合"| Task1
    Task3 -.->|"风险反馈优化配准"| Task1
