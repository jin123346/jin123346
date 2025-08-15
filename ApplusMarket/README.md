# 📱 ApplusMarket – Electronics Secondhand Marketplace

ApplusMarket is a mobile-first platform tailored for buying and selling used electronic products.  
It features secure authentication, real-time crawling from official sources, live chat, and payment capabilities.  
Developed using Spring Boot and Flutter with a focus on reliability, performance, and scalability.

---

## 🚀 Tech Stack

| Layer        | Technology |
|--------------|------------|
| **Frontend** | Flutter (Dart), Riverpod, Dio |
| **Backend**  | Java, Spring Boot, Spring Security, JWT |
| **Database** | MySQL (relational), MongoDB (chat logs) |
| **Infra**    | AWS EC2, Docker, Nginx, systemd |
| **Others**   | Redis, Kafka, Jsoup, GitHub Actions (CI/CD) |

---

## 🔐 Authentication & Authorization

- **JWT-based access and refresh token** system
- Passwords encrypted with **BCrypt**
- Role-based login: Buyer / Seller / Admin
- Social login supported (Google)

---

## ✨ Key Features

### 🛒 Product Management
- Product registration, modification, and deletion
- Multiple image uploads and product option combinations
- Category filtering and keyword-based search

### 🔍 Real-Time Crawling
- Scheduled crawling from **Samsung official used-trade site**
- Uses **Kafka** for distributed messaging
- Auto product posting upon crawl data collection

### 💬 Real-Time Chat System
- Chat implemented with WebSocket and Redis
- Chat history stored in MongoDB
- Unread message count, image sharing, and chat log persistence

### 💳 Payment & Orders
- Buyer-seller payment flow
- Order history, delivery management, and cancellation handling
- Payment result monitoring and update logic

---

## 🛠️ DevOps & Deployment

- **Blue-Green Deployment** using systemd and Nginx
- CI/CD via **GitHub Actions**
- Docker-based deployment for environment consistency
- Spring profiles and log separation by log level

---

## 📂 Project Structure

```bash
applusmarket/
├── frontend/               # Flutter app (Buyer/Seller mode)
├── backend/
│   ├── modules/            # User, Product, Payment, Chat, Crawl, Auth
│   ├── config/             # Security, Redis, Kafka
│   └── docs/               # API documentation via Spring REST Docs
└── infra/
    ├── nginx/
    ├── docker-compose.yml
    └── systemd/
 ```   
📎 Documentation & Links
🔗 Frontend Repository

🔗 Backend Repository

📄 Live Demo

📚 API Docs (REST Docs)

🙋‍♀️ My Role
Designed backend architecture and implemented core services

Built real-time crawling system using Kafka & Jsoup

Developed secure JWT-based login & user role management

Deployed CI/CD pipeline using GitHub Actions + systemd

Integrated Redis-based chat system with MongoDB persistence

📝 Results & Takeaways
Delivered key features in 1 week under tight deadlines

Strengthened debugging and troubleshooting skills during crawling failure cases

Realized the value of ownership and persistence

Gained hands-on experience in cloud deployment & real-time systems

📬 Contact
Ha Jinhee (하진희)
Email: hajhi7899@gmail.com
GitHub: github.com/your-username
