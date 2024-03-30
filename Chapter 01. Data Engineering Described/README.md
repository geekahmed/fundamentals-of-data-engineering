# Chapter 01. Data Engineering Described
This chapter explores the rise of data engineering, its role in supporting data science, and the skills and collaborations data engineers possess.

## Table of Contents

* [What Is Data Engineering?](#what-is-data-engineering)
* [Data Engineering Skills and Activities](#data-engineering-skills-and-activities)
* [Data Engineers Inside an Organization](#data-engineers-inside-an-organization)
* [Conclusion](#conclusion)
* [Additional Resources](#additional-resources)

### What Is Data Engineering?
* **Data engineering** is the development, implementation, and maintenance of systems and processes that take in raw data and produce high-quality, consistent information that supports downstream use cases, such as analysis and machine learning.
* **Data engineering** is the **intersection** of security, data management, DataOps, data architecture, orchestration, and software engineering.
* A **data engineer** manages the data engineering lifecycle, beginning with getting data from source systems and ending with serving data for use cases, such as analysis or machine learning.

<p align="center">
  <img src="./resources/images/The%20data%20engineering%20lifecycle.png" alt="The data engineering lifecycle"/>
</p>

* The data engineering lifecycle shifts the conversation away from technology and toward the data itself and the end goals that it must serve.
* The stages of the data engineering lifecycle are as follows:
    * Generation
    * Storage
    * Ingestion
    * Transformation
    * Serving
* Early Days (1980s-2000s):
    *  Data warehousing emerged with data warehouse engineers building tools for BI and reporting.
    * The rise of the internet created new data challenges for web companies.
* Birth of Modern Data Engineering (2000s):
    * Big data era began with the need to handle massive datasets.
    * Open source tools like Hadoop and cloud platforms like AWS became foundational.
    * Big data engineers focused on managing complex big data frameworks.
* The 2010s: Big Data Engineering Matures
    * Big data became a buzzword, but managing the tools was complex and expensive.
    * Trend shifted towards simplification and abstraction of big data tools.
* The 2020s: Engineering for the Data Lifecycle
    * Focus moved from big data to data engineering for the entire data lifecycle.
    * Data engineers became data lifecycle engineers, managing security, data management, and orchestration.
    * Emphasis shifted from "biggest data" to data quality, governance, and compliance.
* Data engineering and data science are separate but complementary fields.
* Data engineers provide the clean, usable data (upstream) that data scientists analyze and turn into insights (downstream).
* Data engineers build the foundation for data science success by handling data gathering, cleaning, and processing.
<p align="center">
  <img src="./resources/images/A data engineer gets data and provides value from the data.png" alt="A data engineer gets data and provides value from the data"/>
</p>

### Data Engineering Skills and Activities
* Data engineers need a broad skillset: data security, management, architecture, software engineering, and understanding the data lifecycle. They juggle various aspects to optimize cost, agility, scalability, and more.
* Today's data tools simplify workflows, allowing data engineers to focus on best-of-breed services and agile architectures.
* Data engineers typically don't build ML models, reports, or dashboards but should have a working understanding of these areas.
* Data engineering is a new field with no formal training yet.
* People come from various backgrounds and need to be self-motivated learners.
* This book provides a foundation for the knowledge and skills needed to be a data engineer.
* Prior experience in data-related fields (software engineering, data analysis) eases transitioning.
* Core knowledge for data engineers:
    * Data management best practices
    * Various data tools and their trade-offs
    * Software engineering principles
* Data engineers consider:
    * Needs of data consumers (analysts, scientists)
    * Broader impact of data within the organization
*  **Communication:** Be able to explain technical concepts to both technical and non-technical audiences. Understand the organization's structure and dynamics.
 *  **Business Acumen:** Understand how to define project scope based on business needs.  See the impact of data & technology decisions on the business.
 *  **Agile/DevOps/DataOps:** Grasp the cultural aspects of these practices, not just the technical side. They require buy-in from the whole organization.
 *  **Cost Management:** Focus on delivering value while minimizing costs. Optimize for time-to-value, total cost of ownership, and opportunity cost. Monitor costs to avoid surprises.
 *  **Continuous Learning:** Stay updated on the ever-changing data field. Learn to filter trends and identify what's truly relevant. Focus on honing both foundational knowledge and new skills.
 *  **Big Picture Thinking:** Understand how your work contributes to the organization's overall goals. Focus on maximizing business value.
 *  **Technical Skills**
    *  **Architecture:** Design cost-effective, high-performance data architectures using pre-built or custom components. Align architectures with the data engineering lifecycle (Generation, Storage, Ingestion, Transformation, Serving).
    *  **Software Engineering:**  Write production-grade code. Leverage best practices and be comfortable diving into codebases for specific needs. 
    *  **Programming Languages:**
        * Primary: SQL (most common for databases/data lakes), Python (glue between components, popular in data tools), JVM languages (Java/Scala, good for performance and lower-level features in open source frameworks)
        * Secondary: bash (command-line interface for Linux, improves productivity with scripting) - substitute PowerShell for Windows
* **SQL Proficiency is Key for Data Engineers**
    * Despite challenges from big data era, SQL remains essential for data engineering due to its:
        * Declarative nature
        * Ability to handle massive data volumes (with tools like Spark SQL)
        * Broad framework and streaming support
    * Modern SQL can handle complex data structures (JSON) and integrates well with data management tools (dbt).
* **Beyond SQL: Choosing the Right Tool**
    * While powerful, SQL isn't always the best option. Data engineers should be flexible and:
        * Recognize limitations (e.g., avoid complex text processing in SQL)
        * Choose alternative languages (e.g., Spark for NLP tasks)
* **Secondary Programming Languages**
    * Proficiency in additional languages may be required based on company or specific tools:
        * R, JavaScript, Go, Rust, C/C++, C#, Julia
        * Examples: JavaScript for cloud data warehouses, C# for Microsoft Azure
* Staying sharp in data engineering:
    * Focus on fundamentals: understand core concepts that won't change.
    * Stay current: follow new developments and how they fit in the data lifecycle.
* Data Engineering Roles: Type A vs. Type B
  * Type A (Abstraction): Uses pre-built tools and services, focuses on keeping data architecture simple. 
  * Type B (Build): Builds custom data tools and systems, focuses on scalability and competitive advantage.
  * Type A is common across data maturity stages, B is common in later stages or for unique use cases. 
  * A and B engineers may coexist or a single person may develop both skillsets over time.

### Data Engineers Inside an Organization
### Conclusion
### Additional Resources
* How Data Engineering Works? https://youtu.be/qWru-b6m030