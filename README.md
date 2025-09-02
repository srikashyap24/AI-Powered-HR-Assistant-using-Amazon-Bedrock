# AI-Powered HR Assistant using Amazon Bedrock

## Project Overview
The **AI-Powered HR Assistant** is a conversational AI system designed to streamline employee interactions with Human Resources. Using **Amazon Bedrock**, the system can answer employee queries regarding benefits, leaves, company policies, and work-related matters. It also allows employees to **submit requests directly** into a centralized database for efficient processing.

---

## Key Features

### 1. Conversational AI Agents
- Built using **Amazon Bedrock** to act as HR agents.  
- Provides natural language responses to employee queries such as:  
  - Leave policies and balances  
  - Employee benefits  
  - Working guidelines and company policies  

**Screenshot:**  
<img src="agent.py"/>

### 2. Retrieval-Augmented Generation (RAG)
- Integrated **Amazon Bedrock Knowledge Bases** to store HR documents and historical records.  
- Ensures AI responses are **accurate and grounded in company data**, reducing misinformation.  

**Screenshot:**  
![Knowledge Base Search](screenshots/knowledge_base_search.png)

### 3. Centralized Data Storage
- **Amazon S3** is used to store all HR-related documents (PDFs, spreadsheets, policy docs).  

### 4. Actionable Requests via Action Groups
- Employees can submit:  
  - **Leave requests**  
  - **Benefits requests**  
- Requests are handled via AWS Lambda functions triggered by Action Groups.
- Lambda functions process the submitted data and store it in Amazon DynamoDB.  

**Screenshot:**  
![Leave Request Submission](screenshots/leave_request.png)

### 5. Workflow Automation & Security
- **AWS Lambda functions** handle incoming requests and update DynamoDB.  
- **IAM roles** ensure secure, role-based access to sensitive HR data.  

---

## Architecture
**Screenshot of Architecture Diagram:**  
![Architecture](screenshots/architecture_diagram.png)

1. Employee interacts with the **AI agent** via a chat interface.  
2. The agent queries the **Bedrock Knowledge Base** for relevant HR policies.  
3. For actionable requests (leave/benefits), the **Action Groups** trigger a Lambda function.  
4. Lambda function stores the request in **DynamoDB** and confirms submission.  
5. Optional: **OpenSearch** can be integrated for advanced search across HR records.  

---

## Tech Stack
- **Amazon Bedrock** – AI agents for natural language processing  
- **Bedrock Knowledge Bases** – Storage and retrieval of HR documents  
- **Amazon S3** – Centralized data storage  
- **Amazon DynamoDB** – Storing leave and benefits requests  
- **AWS Lambda** – Serverless processing of action requests  
- **IAM** – Secure access control  

---

## Benefits
- Provides **quick and consistent responses** to employee queries.  
- Allows **direct submission** of HR requests, reducing manual work.  
- Ensures **data-driven decision-making** with centralized storage of HR records.  
- Fully **scalable and secure**, leveraging AWS managed services.  

---

## Future Enhancements
- Integrate **OpenSearch** for advanced semantic search across all HR documents.  
- Add **analytics dashboards** using **Amazon QuickSight** to monitor trends in employee requests.  
- Implement **multi-language support** to cater to a global workforce.  
