📊 Server Capacity Planning & Peak Load Forecasting
📌 Project Overview
As server node traffic scales, preventing resource exhaustion is critical to maintaining high availability. This project establishes an automated capacity planning model using Apache Kafka load metrics to forecast CPU utilization across a distributed server cluster.

The core objective is to identify potential capacity breaches before they happen—specifically targeting any server node projected to cross the 85% critical CPU threshold—and visualizing these insights in an interactive operational dashboard for infrastructure teams.

🎯 Business Value & Impact
Proactive Outage Prevention: Shifted infrastructure monitoring from reactive to proactive by predicting threshold breaches days in advance.

Data-Driven Scaling: Provided empirical justification for load balancing and resource allocation based on historical utilization trends.

Operational Visibility: Centralized complex cluster metrics into a single, highly readable executive dashboard.

🛠️ Technical Methodology
Phase 1: Data Extraction & Transformation
Processed raw telemetry data (kafka_load_metrics) tracking daily CPU utilization percentages and active users across 5 distinct server nodes.

Cleaned unstructured timestamps and resolved data type inconsistencies using Text-to-Columns parsing to ensure chronological accuracy for time-series modeling.

Phase 2: Predictive Forecasting
Isolated historical utilization trends to build a capacity projection model.

Utilized the FORECAST.LINEAR algorithm to map future peak loads.

Successfully identified a critical trajectory on Node 3, predicting an exact date when the server would exceed the 85% safe operating capacity limit.

Phase 3: Dashboard & Visualization (Tableau)
Engineered an operational Tableau dashboard to monitor cluster health:

Time-Series Analysis: Mapped maximum CPU utilization over time, segmented by Node ID.

Automated Alerting: Implemented a hardcoded 85% reference line to visually flag capacity breaches.

Interactive Filtering: Enabled dynamic isolation of specific server nodes for granular inspection.

<img width="1000" height="800" alt="Dashboard 1" src="https://github.com/user-attachments/assets/62afe755-790f-4891-92a1-1f7cb8787f83" />

🚀 Future Scope
To further scale this infrastructure monitoring tool, future iterations will include:

Migrating the raw CSV data pipeline into a PostgreSQL relational database.

Writing a Python automation script to query the database and trigger real-time email alerts when nodes cross the 85% threshold.

Containerizing the data processing pipeline using Docker for seamless deployment.


📸 Dashboard Preview
(Insert the high-quality image of your final Tableau dashboard here using ![Tableau Dashboard](path/to/image.png))
