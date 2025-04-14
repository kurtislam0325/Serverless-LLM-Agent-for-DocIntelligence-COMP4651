# Serverless-LLM-Agent-for-DocIntelligence-COMP4651

# 🧠 Serverless LLM Agent for Document Intelligence (AWS-based)

## 📌 Overview

This project implements a **serverless document intelligence pipeline** on AWS that leverages **Large Language Models (LLMs)** to analyze and summarize user-uploaded documents. The application is built entirely with AWS services, following best practices for scalability, cost-efficiency, and maintainability.

## 🚀 Features

- Upload `.pdf`, `.txt`, or `.docx` files to S3
- Automatically trigger processing via AWS Lambda
- Extract content from the uploaded file
- Send text to a hosted LLM (Amazon Bedrock or HuggingFace)
- Store the generated summary in DynamoDB or S3
- Optional: Query results via an API Gateway endpoint

---

## 🧱 Architecture

```plaintext
User → S3 Upload → Lambda Trigger → LLM Inference → DynamoDB/S3 → (Optional) API Gateway → User
```

## 🛠️ AWS Services Used

| Component         | AWS Service              | Description                              |
|------------------|--------------------------|------------------------------------------|
| File Upload       | Amazon S3                | Stores uploaded documents                |
| Processing Logic  | AWS Lambda               | Parses and forwards content to LLM       |
| Inference Model   | Amazon Bedrock / HF API  | Summarizes or analyzes document content  |
| Result Storage    | DynamoDB / S3            | Saves extracted summaries and metadata   |
| Result Access     | API Gateway (optional)   | Provides REST API for data retrieval     |
| Monitoring        | CloudWatch               | Logs and system monitoring               |
| Security          | IAM                      | Access control between AWS components    |

---

## 📦 Project Structure

.
├── lambda/
│   ├── handler.py              # Main Lambda function logic
│   ├── llm_inference.py        # Integration with LLM (e.g., Bedrock or HuggingFace)
│   └── utils.py                # Helper functions for parsing and formatting
├── templates/
│   └── api_response_template.json
├── README.md
└── requirements.txt


---

## 🗓️ Project Timeline

| Week | Task |
|------|------|
| 1-2  | S3 + Lambda trigger setup |
| 3-4  | Document parsing + LLM integration |
| 5-6  | DynamoDB or S3 output and API Gateway |
| 7-8  | Logging, IAM security, cost monitoring |
| 9    | Final testing and documentation |

---

## 🔐 IAM Permissions (Example)

- Lambda:
  - `s3:GetObject`
  - `dynamodb:PutItem`
  - `logs:*`
- S3:
  - Trigger for `s3:ObjectCreated:*`
- Optional: API Gateway secured with IAM or key

---

## 📊 Cost Estimation

- **S3**: Storage + PUT/GET operations
- **Lambda**: Execution time × memory size
- **LLM API**: Token-based usage (e.g., Bedrock or HF)
- **DynamoDB**: Read/Write request units
- **API Gateway**: Per request pricing

---

## 💡 Future Enhancements

- Frontend dashboard (e.g., React + Amplify Hosting)
- OCR support (Amazon Textract or Tesseract)
- Support different LLM tasks: Q&A, entity extraction
- Modular workflow using AWS Step Functions

---

## 📚 References

- [Amazon S3](https://docs.aws.amazon.com/s3/)
- [AWS Lambda](https://docs.aws.amazon.com/lambda/)
- [Amazon Bedrock](https://aws.amazon.com/bedrock/)
- [HuggingFace Inference API](https://huggingface.co/inference-api)
- [AWS CloudWatch](https://docs.aws.amazon.com/cloudwatch/)
- [AWS DynamoDB](https://docs.aws.amazon.com/dynamodb/)
- [API Gateway](https://docs.aws.amazon.com/apigateway/)

---

## 🤝 Acknowledgments

This project is developed for the Cloud Computing course, demonstrating the integration of modern serverless architectures and AI technologies.



