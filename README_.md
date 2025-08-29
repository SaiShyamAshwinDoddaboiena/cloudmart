# 🚀 CloudMart Customer Support Assistant  

![Node.js](https://img.shields.io/badge/node-%3E%3D16-green?logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/express-4.x-lightgrey?logo=express&logoColor=white)
![React](https://img.shields.io/badge/react-18.x-blue?logo=react&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-DynamoDB-orange?logo=amazon-aws&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-AssistantAPI-412991?logo=openai&logoColor=white)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)
[![Build Status](https://img.shields.io/github/actions/workflow/status/your-username/cloudmart-ai-assistant/ci.yml?branch=main)](https://github.com/your-username/cloudmart-ai-assistant/actions)

An **AI-powered assistant** that goes beyond traditional chatbots by integrating directly with backend services. Powered by **OpenAI’s Assistant API with Function Calling** and **AWS Bedrock**, it can understand intent, trigger backend operations, and automate tasks such as **order management** and **product handling**.  

---

## ✨ Key Features
- **AI-Driven Actions**: Understands intent and executes real operations (e.g., cancel orders).  
- **Seamless Backend Integration**: Works with Node.js/Express services and DynamoDB.  
- **Multi-Agent Support**: Uses OpenAI Assistants and AWS Bedrock agents.  
- **Scalable & Extensible**: Add new tools and workflows easily.  

---

## ⚙️ Architecture Overview  

Example: **Canceling an Order (`CM-7890`)**  

1. **Frontend (React - `CustomerSupportPage.jsx`)**  
   - Captures user request → sends to backend API.  

2. **Backend (Node.js + Express)**  
   - Routes request → `aiService.js`.  

3. **AI Service (`aiService.js`)**  
   - Sends message to OpenAI thread.  
   - Detects intent → calls appropriate tool (e.g., `cancel_order`).  

4. **OpenAI API**  
   - Determines action required → triggers tool call.  

5. **Order Service (`orderService.js`)**  
   - Business logic + DynamoDB updates.  

6. **Database (DynamoDB)**  
   - Stores order and product records.  

7. **Final Response**  
   - AI generates confirmation message → shown to user.  

---

## 🛠️ Setup & Installation  

### Prerequisites  
- Node.js (LTS recommended)  
- npm  
- AWS CLI (configured for DynamoDB & Bedrock)  

### Installation  
```bash
git clone https://github.com/your-username/cloudmart-ai-assistant.git
cd cloudmart-ai-assistant
npm install
```

### Configuration  
Create `.env` in backend root:  
```env
PORT=5000
OPENAI_API_KEY=your_openai_api_key_here
OPENAI_ASSISTANT_ID=your_openai_assistant_id_here
AWS_REGION=your_aws_region_here
AWS_ACCESS_KEY_ID=your_aws_access_key_id_here
AWS_SECRET_ACCESS_KEY=your_aws_secret_access_key_here
BEDROCK_AGENT_ID=your_bedrock_agent_id_here
BEDROCK_AGENT_ALIAS_ID=your_bedrock_agent_alias_id_here
```

### Database Setup (DynamoDB)  
- **Orders Table**: `cloudmart-orders`  
- **Products Table**: `cloudmart-products`  

Run helper script (if available):  
```js
populateProductsTable();
```

### Running the Application  
```bash
npm start   # start backend (http://localhost:5000)
```
Start frontend (React app) separately.  

---

## 📡 API Endpoints  

### AI Endpoints  
- `POST /api/ai/start` → Start OpenAI thread.  
- `POST /api/ai/message` → Send message to AI, get response.  
- `POST /api/ai/bedrock/start` → Start Bedrock conversation.  
- `POST /api/ai/bedrock/message` → Chat with Bedrock agent.  

### Order Endpoints  
- `POST /api/orders` → Create order  
- `GET /api/orders` → Get all orders  
- `GET /api/orders/user?email={email}` → Get orders by user email  
- `GET /api/orders/:id` → Get order by ID  
- `PUT /api/orders/:id` → Update order  
- `DELETE /api/orders/:id` → Delete order  

### Product Endpoints  
- `GET /api/products` → Get all products  
- `GET /api/products/:id` → Get product by ID  
- `POST /api/products` → Create product  
- `PUT /api/products/:id` → Update product  
- `DELETE /api/products/:id` → Delete product  

---

## 🧰 Tech Stack  
- **Backend**: Node.js, Express.js  
- **AI**: OpenAI Assistant API, AWS Bedrock  
- **Database**: AWS DynamoDB  
- **Frontend**: React  
- **Utilities**: dotenv, uuid, AWS SDKs  

---

## 🔮 Roadmap  
- ✅ Enhanced order workflows (shipping, delivery)  
- 🔜 AI-driven product recommendations  
- 🔜 Customer authentication & profiles  
- 🔜 Multi-language support  

---

## 🤝 Contributing  
We welcome contributions! See `CONTRIBUTING.md` for guidelines.  

---

## 📄 License  
MIT License – see `LICENSE` file.  
