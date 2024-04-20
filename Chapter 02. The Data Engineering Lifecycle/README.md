# Chapter 02. The Data Engineering Lifecycle
* This book emphasizes data lifecycle management over just focusing on specific data technologies.
* There are more and more data technologies with increasing ease of use.
* Data engineers will need to adapt to this changing landscape by thinking about the entire data lifecycle.
* The book will introduce the "data engineering lifecycle" as a framework and its underlying principles. 

## Table of Contents

* [What Is the Data Engineering Lifecycle?](#what-is-the-data-engineering-lifecycle)
* [Major Undercurrents Across the Data Engineering Lifecycle](#major-undercurrents-across-the-data-engineering-lifecycle)
* [Conclusion](#conclusion)
* [Additional Resources](#additional-resources)

### What Is the Data Engineering Lifecycle?
* The data engineering lifecycle has 5 stages: Generation, Storage, Ingestion, Transformation, and Serving data.
* Data is collected, stored, transformed, and finally presented to data users (analysts, scientists, engineers).
* Storage is considered foundational and interacts with all other stages.
* The lifecycle is not always linear and stages can overlap or repeat.
* Underlying principles (security, data management, etc.) are crucial throughout the entire process.
* Data engineering lifecycle is part of the bigger data lifecycle.
* Full data lifecycle follows data throughout its entire existence.
* Data engineering lifecycle focuses on the stages data engineers manage.
<p align="center">
  <img src="./resources/images/The data engineering lifecycle is a subset of the full data lifecycle.png" alt="The data engineering lifecycle is a subset of the full data lifecycle"/>
</p>

> **Understanding Source Systems**

* **What they are:** Systems that produce the raw data used in data engineering (examples: IoT devices, databases, message queues).
* **Key role of Data Engineers:** Understand how source systems function, how they generate data (frequency, format, etc.), and communicate with source system owners to stay informed of potential changes.
* **Challenges:** Data engineers must work with a vast array of different data sources.

**Types of Source Systems**

* **Traditional:** Application servers backed by a database (e.g., relational databases).
<p align="center">
  <img src="./resources/images/Source system example an application database.png" alt="Source system example: an application database"/>
</p>

* **Modern:** IoT swarms sending data to a central collection system.
<p align="center">
  <img src="./resources/images/Source system example an IoT swarm and message queue.png" alt="Source system example: an IoT swarm and message queue"/>
</p>

**Evaluating Source Systems: Key Questions**

* **Data Characteristics:** What generates the data (application, IoT devices, etc.)?
* **Persistence:**  Is the data stored long-term or is it temporary?
* **Generation Rate:** How much data is produced and at what frequency?
* **Consistency:** How reliable is the data (nulls, formatting issues, etc.)?
* **Errors:** How frequent are errors?
* **Duplicates/Late Data:** Are there duplicates or delayed data?
* **Schema:**  What's the data structure? Will data need to be joined across systems?
* **Schema Changes:** How are changes handled and communicated?
* **Extraction:** How often should the data be pulled?
* **Stateful Systems:** How are updates provided (snapshots or change data capture)?
* **Data Provider:** Who/what transmits the data? 
* **Performance Impact:** Does reading data affect the source system's performance?
* **Upstream Dependencies:** Are there other systems the source relies on?
* **Data Quality:** Are there checks in place to address late/missing data?

**Additional Notes**

* Data engineers must be aware of the unique aspects and potential limitations of each source system.
* Data schemas (schemaless vs. fixed schema) can evolve and pose challenges for data transformation. 


> **The Importance of Storage in Data Engineering**

* **Storage is fundamental:**  It underpins every stage of the data lifecycle (ingestion, transformation, serving).
* **Complexity:**  Modern architectures often use multiple storage solutions, and storage systems themselves may have complex capabilities.
* **Impactful choice:** Selecting the right storage directly impacts the efficiency and effectiveness of your data pipeline.

**Key Questions for Evaluating Storage Systems**

* **Performance:** Does it match the required read/write speeds and avoid bottlenecks?
* **Scalability:** Can it handle your current and anticipated future data volumes?
* **Compatibility:** Does it work well with your existing architecture? 
* **Data Access:** Can users retrieve data within their required timeframes?
* **Metadata:** Are you capturing metadata to aid in future discoverability and changes?
* **Query Patterns:** Does the storage system support the types of queries you'll need?
* **Schema Type:** Is the storage schema-agnostic, flexible, or strictly enforced?
* **Compliance, Governance:** How does it handle regulatory and data quality requirements?

**Data Temperatures**

* **Hot Data:** Frequently accessed, demands fast retrieval (think real-time user requests)
* **Lukewarm Data:** Accessed less often (weekly or monthly)
* **Cold Data:** Infrequently accessed, typically for archiving or compliance.

**Choosing Storage**

* **No one-size-fits-all:** The best storage solution depends on your specific use cases, data characteristics, and the key considerations listed above.
* **Trade-offs:**  Every storage technology has pros and cons.



> **Data Ingestion: The Essentials**

* **Understand your Source Systems:**  How the source produces data, its reliability, and potential issues are crucial to plan effectively. 
* **Data Destinations:** Consider where the data needs to go after ingestion, as this will dictate formatting, frequency, and storage needs.
* **Data Quality:** Assess if the data needs cleaning or transformation before use. If so, plan those steps.

**Batch vs. Streaming**

* **Batch:** Processes data in chunks, often on a schedule (e.g., daily). Simpler to implement, common for analytics.
* **Streaming:** Real-time or near real-time data processing.  More complex, but allows immediate action on incoming data.
* **Which to choose:**  
    * Does downstream processing truly need *immediate* data? 
    * Is the added complexity of streaming justified by the potential benefits?

**Push vs. Pull**

* **Push:** The source actively sends data to your system.
* **Pull:** Your system queries the source to get data.
* **It's often a mix:** Data may be pushed and pulled at different stages of your pipeline.

**Things to keep in mind:**

* Ingestion is a common bottleneck – plan for reliability and potential source system issues.
* Think about the end-use of the data. Can you reuse ingested data to avoid redundancy?
 

> **Data Transformation: Turning Raw Data into Insights**

* **Purpose:** Transforms raw ingested data into formats ready for analysis, reports, or machine learning. 
* **Key Tasks:**
    * Data Cleaning and type adjustments (strings to numbers, etc.)
    * Normalization and schema changes
    * Aggregation for reporting
    * Feature engineering for ML models

 **Questions to Consider**

* **Value:** Does the transformation add clear business value?
* **Simplicity:** Can the transformation logic be kept simple and isolated for easy maintenance? 
* **Business Logic:** How are you incorporating core business rules into the transformation?

**Batch vs. Streaming Transformation**

* **Batch:** Processes data in chunks, often scheduled. Popular and widely used.
* **Streaming:** Transforms data as it arrives (real-time or near real-time). Gaining popularity for its speed advantage.

**Transformation Best Practices**

* **Transformations aren't limited to one stage:** They can happen during ingestion, storage, or within dedicated pipelines.
* **Data modeling is key:** Applying business logic creates valuable insight for end-users.
* **Feature engineering for ML:**  Close collaboration between data engineers and data scientists is crucial. 


> **Data Serving: Getting Value from Your Data**

* **Focus on Actionable Insights**: The whole point of data engineering is to enable use cases that drive business results. Prioritize projects with clear goals.
* **Key Areas of Data Serving:**
    * **Analytics:** Providing insights on past and current business performance.
       * **Self-Service is the Goal:** Work towards democratizing data access.
    * **Machine Learning (ML):**  Applying advanced techniques for prediction and automation. 
         * **Data Quality is Crucial:** Garbage in, garbage out applies strongly to ML.
    * **Reverse ETL:** Pushing insights and model results back into operational systems to enhance their capabilities.

**Types of Analytics**

<p align="center">
  <img src="./resources/images/Types of analytics.png" alt="Types of analytics"/>
</p>

* **Business Intelligence (BI):**  Understand historical and current business state. Key for reporting and strategic decision-making.
* **Operational Analytics:** Real-time or near real-time insights for immediate action (think inventory management, system health monitoring) 
* **Embedded Analytics:** Integrate data insights directly into customer-facing products or services. 
     * **Security Emphasis:**  Tenant isolation and data access controls are absolutely critical.

**Machine Learning Considerations**

* **Collaborate with ML teams:** Understand data quality needs, model use-cases, and ensure tools are well-integrated.
* **Feature Stores:**  Consider these for streamlining feature engineering for ML. 
* **Start with strong analytics:** Build a robust data foundation before venturing into complex ML projects.

**Reverse ETL**

* **A Growing Need:** Enables pushing analytics insights and model outputs back into business systems (marketing platforms, CRMs, etc.)
* **Tools are emerging:**  Solutions like Hightouch and Census specialize in this area.
<p align="center">
  <img src="./resources/images/Reverse ETL.png" alt="Reverse ETL"/>
</p>

### Major Undercurrents Across the Data Engineering Lifecycle
<p align="center">
  <img src="./resources/images/The major undercurrents of data engineering.png" alt="The major undercurrents of data engineering"/>
</p>

> **Security: The Foundation of Data Engineering**

* **Top Priority:**  Data security is non-negotiable.  Neglecting it leads to serious consequences.
* **Principle of Least Privilege:** Grant users and systems the absolute minimum access they need to function. This is essential for preventing accidents and breaches.
* **Security is Everyone's Job:** Educate your entire team to create a security-conscious company culture. 
* **Data Protection:** Secure data across its entire lifespan:
    * At rest: Encryption, masking, obfuscation
    * In transit: Encryption
    * Access: Strict controls, minimizing exposure time
 
**Data Engineer Responsibilities**

* **Be a Security Expert:**  Become deeply knowledgeable about security best practices on-premises and in the cloud.
* **Master IAM:** Understand how to manage user identities, roles, policies, and network security.
* **Encryption:** Know the appropriate encryption techniques and when to apply them.


> **Data Management: Treating Data as a Valuable Asset**

* **Why it matters:**  Data is no longer just a technical concern. Managing data well maximizes its value for the entire organization. 
* **Key Areas for Data Engineers:**

    * **Governance:** 
        * **Discoverability:** Metadata and data catalogs make data easy to find and understand.
        * **Security & Accountability:** Clear access controls, and knowing who's responsible for data quality.
    * **Data Quality:** Ensuring data is accurate, complete, and timely – critical for trust.
    * **Modeling:** Designing data structures for optimal use in analytics and ML.
    * **Lineage:**  Tracking data's journey for troubleshooting, compliance, and understanding changes.
    * **Integration:** Systems must "talk" to each other – data engineers make this happen. 
    * **Lifecycle Management:**  Archiving and deletion when needed, considering both costs and legal requirements.
    * **Ethics & Privacy:** Protect sensitive data, and use  data responsibly, especially regarding user rights.

**Data Engineer's Role**

* **Proactive Approach:**  Build systems with these principles in mind, not as an afterthought.
* **Tool Expertise:** Become proficient in data catalogs, metadata management, and lineage tracking tools.
* **Collaboration:** Work closely with those responsible for business definitions and data privacy regulations.


> **What is DataOps?**

* **DataOps = Agility + Quality:**  It borrows from DevOps and manufacturing to help data teams deliver reliable, high-quality data products quickly. 
* **Not just Tech:** DataOps starts with a culture of collaboration, rapid improvement cycles, and open communication within the data team and across the entire company. 

**The Three Pillars of DataOps**

1. **Automation** 
   * **Goal:** Reduce manual work, increase consistency.
   * **Tools:** Workflow orchestrators (Airflow, Dagster), CI/CD for data pipelines,  configuration as code. 
   * **Evolve with your Team:** Start simple (cron), then move to orchestrators, and later explore advanced tools as your needs grow.

2. **Observability & Monitoring**
   * **Know When Things Break** Proactively monitor data quality, system health, and model performance.
   * **Think like a developer:**  Use practices like Data Observability Driven Development (DODD) for proactive issue detection.

3. **Incident Response**
   * **Fix Fast, Learn Faster:**  When issues happen (and they will!), fix them quickly, and use them as opportunities to prevent future issues.
   * **Build Trust:** Communicate openly and honestly about incidents. Proactively identify problems before users find them.

**How Data Engineers Can Embrace DataOps**

* **If starting from scratch:** Build these principles into your foundation, it'll be easier this way!
* **Existing Projects:** Start by adding monitoring, then move to automation and incident response.
* **Mature Organization:** Collaborate with existing DataOps teams to further enhance data workflows.


> **Data Architecture**

* **It's about Strategy:** A blueprint for how your data systems will support the evolving needs of the business.
* **Data Engineer's Role:** 
    * Understand what the business wants to do with their data.
    * Design systems to collect and serve that data, balancing cost and ease of operation
    * Collaborate with data architects (if your organization has them)

**Orchestration**

* **The Conductor of Your Data Pipeline:**  Orchestration tools coordinate complex data jobs, making sure they run on time and in the right order.
* **More than Scheduling:**   
    * Tracks job dependencies (think of a flow chart) 
    * Can handle various run frequencies (daily, hourly, etc.)
    * Monitors jobs, sends alerts, and allows you to track history.
* **It's Evolving:** 
    * Airflow is popular, but newer tools like Prefect and Dagster offer improvements.
    * Streaming data processing is challenging, but modern tools are making it easier.


> **Software Engineering is Still Essential**

* **Abstraction Doesn't Mean No Code:** Core data processing still requires coding skills (Spark, SQL etc.). Know how to test your code properly.
* **Contribute or Create:** Get involved in open source data tools – fix what you use, build what you need. But research if something already exists before building!
* **Streaming Challenges:** Real-time data processing is inherently tricky. Learn to manage complex joins, windowing functions, and choose the right streaming tools.
* **Infrastructure as Code (IaC):**  Automate the setup and management of your data infrastructure for consistency and speed.
* **Pipelines as Code:**  Modern orchestration tools (Airflow, Prefect, Dagster) let you define your entire data flow using code. 

**General Problem-Solving:**

* **Custom Solutions:**  You WILL encounter situations where existing tools fall short. Be ready to write custom code, work with APIs, and handle those unique challenges.


### Conclusion
**The Big Picture of Data Engineering**

* **It's Not Just Tech:** Tools are important, but the best data engineers focus on the full lifecycle of data, and how to maximize its value for the business.
* **The Data Engineering Lifecycle:** A framework to organize your work:
    * Generation
    * Storage 
    * Ingestion
    * Transformation 
    * Serving 
* **The Undercurrents:**  Key areas that impact success across the entire lifecycle:
    * Security
    * Data Management
    * DataOps
    * Data Architecture
    * Orchestration
    * Software Engineering  

**Your Goals as a Data Engineer**

* **Maximize ROI:**  Deliver solutions that create real business value while controlling costs. 
* **Reduce Risk:**  Ensure data security and quality with proactive safeguards.
* **Unlock Data Power:** Make data more accessible, useful and reliable for everyone.

**Next Steps**

* **Dive into Chapters 3+:** if you're ready to design good data architectures and choose the right tools. 
* **Part II:**  Provides in-depth exploration of each stage of the data engineering lifecycle.

### Additional Resources
* [Reverse ETL](https://www.youtube.com/watch?v=G_aq03cSa8Y)
