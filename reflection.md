# Reflection:

**Which parts of the design you feel most confident about, and which parts you are least sure about.**

Working on this project allowed me to explore the design and implementation of a cloud-based patient intake and triage system in depth. I feel the most confident about the overall workflow and architecture design. Structuring a web-based intake form, integrating cloud storage for images, and designing a structured database for triage and patient information felt straightforward and realistic. Using serverless compute, with Cloud Run and Cloud Functions, for the triage logic and background processes provides flexibility, scalability, and cost-efficiency for a small prototype. The data flow feels well-organized. Walking through the patient journey, from submitting the form, to processing symptoms, to staff viewing triage results, helped me confirm that each service has a clear purpose.

At the same time, there were also areas where I felt less confident about. I don't feel confident about the triage computation. Although I structured it logically to return “urgent”, “moderate", or “routine, creating medically reliable triage logic is much more complicated and would require real clinical guidance or validated models. I also feel some uncertainty about how deep and detailed the IAM and networking configuration needs to be in a real clinical deployment. Concepts like least-privilege roles are straightforward, but implementing granular permissions, VPC connectors, and firewall restrictions can get complex. Another area is Cloud SQL performance at scale. It works well for this design, but when it comes to large patient volume, scaling it would require more planning than what this assignment asked for.

**At least one alternative architecture you considered and why you did not choose it.**

One alternative architecture I considered was building this system on Microsoft Azure instead of Google Cloud. Azure offers similar managed services. For example, Azure App Service for hosting applications, Azure Functions for serverless compute, and Azure SQL Database for relational storage. However, I feel that I am more experienced in Google Cloud Platform since I've been using it for multiple of the previous assignments. I like the format of Google Cloud when creating a virtual machine more than Azure.


**If you had 4–8 more weeks and unlimited credits, what next steps you would implement.**

If I had more time and unlimited credits, I would focus on adding predictive analytics, like patient risk scoring and real-time notification systems for the staff. I would like to add AI models to create a more intelligent symptom analyzer. These models will always need human oversight, especially when AI or codes are used to make decisions on patients. I think I would also plan on integrating FHIR APIs to exchange data with EHR systems since healthcare has a lot of problems with interoperability. I would also do more research to implement more security to ensure the data is safe and secured.
