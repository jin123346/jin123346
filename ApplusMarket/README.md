# 📱 ApplusMarket – Electronics Secondhand Marketplace

[🔗 GitHub - Flutter](https://github.com/jin123346/APPlusMarket_Flutter)  
[🔗 GitHub - Spring Boot API Server](https://github.com/jin123346/APPlusMarket_BE)  
[📐 Figma UI Design](https://www.figma.com/design/HVSt9yLxX4gawgyWRo98tb/1%EC%A1%B0-App-%ED%99%94%EB%A9%B4%EC%84%A4%EA%B3%84?node-id=0-1)  
[📚 API Docs](http://ec2-3-35-170-26.ap-northeast-2.compute.amazonaws.com/docs/index.html)

---

## 📌 Overview

> A mobile-based secondhand electronics marketplace powered by Spring Boot (REST API) and Flutter.  
> Implements real-time crawling using Kafka, secure login with JWT, WebSocket-based chat, and Blue-Green zero-downtime deployment.

| Duration | Team | Stack |
|---|---|---|
| Jan – Mar 2025 | 3 Members (Fullstack) | Spring Boot, Flutter, Kafka, MongoDB, WebSocket |

📷 **Preview**  
<img width="864" height="1845" alt="image (6)" src="https://github.com/user-attachments/assets/af86ab4a-4eb0-4dbe-9a0a-5a599fdd5649" />

---

## 🛠️ Tech Stack

### Backend
- Spring Boot 3, Spring Security, JWT, MyBatis, QueryDSL, Redis, Kafka, MongoDB  
- CI/CD: GitHub Actions + EC2 + Docker + systemd + Nginx

### Frontend
- Flutter (Dart), Riverpod, Dio, WebView, WebSocket (STOMP)

📊 Architecture Overview  
<img src="./assets/architecture.png" width="700"/>

---

## 🔐 Main Features

### 1. 🔐 JWT Authentication
- Access & Refresh token system
- OAuth2.0 social login (Google)
- Role-based access control (Admin/Seller/Buyer)

**Code Snippet: JWT Filter**
```java
protected void doFilterInternal(...) {
  String token = resolveToken(request);
  if (tokenProvider.validateToken(token)) {
      Authentication auth = tokenProvider.getAuthentication(token);
      SecurityContextHolder.getContext().setAuthentication(auth);
  }
  filterChain.doFilter(request, response);
}
```

---

### 2. 🔍 Real-time Crawling & Search

- Crawling Samsung official site using Jsoup + WebClient  
- Kafka-based async architecture  
- MongoDB for structured data storage  
- Redis for crawl-status deduplication

📷 Example Flow  
<img width="1378" height="601" alt="image (7)" src="https://github.com/user-attachments/assets/97d9e3ab-cdc3-418a-944a-e1efb18313fd" />

<img width="1065" height="242" alt="image (2)" src="https://github.com/user-attachments/assets/0c2bf7eb-291a-49c3-94f3-7db27ed50c7b" />

**Code Snippet: Kafka Producer**
```java
public void sendSearchRequest(String keyword) {
    SearchRequestDto dto = new SearchRequestDto(keyword);
    kafkaTemplate.send("crawler-search-topic", dto);
}
```
---

### 3. 🚀 Blue-Green Deployment

- CI/CD pipeline with GitHub Actions  
- systemd-based service switch with port tracking  
- Nginx route management for zero-downtime

**Blue-Green Logic Flow**  
<img width="821" height="630" alt="image (3)" src="https://github.com/user-attachments/assets/d660ce21-c103-4ed9-8bd0-0d2a9a3b3f90" />
![New Port 8081 Up](https://github.com/user-attachments/assets/b51097ee-47aa-4c67-8cb9-7e065cde2300)

---

## 🧪 Performance Optimization

- Crawling latency reduced by 50% (from ~8s → ~2s)  
- MongoDB Upsert + bulkWrite() → minimized duplication  
- DB load reduced 40% via Redis + async Kafka

📊 Result:  
✅ Fast response  
✅ Efficient memory use  
✅ Real-time UX  

---

## 👩‍💻 My Contribution

| Area | Description |
|------|-------------|
| Backend | Core architecture, Kafka, crawling, chat, auth |
| DevOps | CI/CD, systemd, Nginx, Blue-Green |
| Frontend | Flutter: profile mgmt, product UI, WebSocket |
| Documentation | API Docs (Spring REST Docs), code convention |

---

## 🧠 Key Learnings

- 🛠 Built a full CI/CD pipeline with system-level deployment  
- 🔁 Refactored sync crawling into event-based async structure  
- 📡 Designed real-time price alert system  
- 🤝 Standardized API structure for team collaboration

---

## 📎 Screenshots
> 로그인화면

![image](https://github.com/user-attachments/assets/bfe243bc-43aa-4a98-89f6-5549b6c143b2)

> 회원가입화면

 ![image](https://github.com/user-attachments/assets/1cbfe47d-b420-446d-b752-19bb3dd147ef)

> 상품 화면

![image](https://github.com/user-attachments/assets/f6cd84a0-333b-4f62-bf28-c15d1b990804)


> 채팅화면

![image](https://github.com/user-attachments/assets/4ce803ca-fca1-4f3c-9d93-cc9209a30f47)


> 마이페이지화면

![image](https://github.com/user-attachments/assets/4629a8d1-a603-4297-b894-daab5275c662)
![image](https://github.com/user-attachments/assets/b907027d-125a-451e-be36-e132f49fc2c6)
![image](https://github.com/user-attachments/assets/196116f3-5711-491c-bc79-798f2d38b604)

---

## 🧾 Dependencies

📦 Backend (Spring Boot)
```text
- spring-boot-starter-web
- spring-security
- spring-data-redis
- spring-kafka
- spring-data-mongodb
- jsoup, selenium
- GitHub Actions, systemd
```

📱 Frontend (Flutter)
```text
- riverpod, dio, jwt_decoder
- web_socket_client, stomp_dart_client
- shared_preferences, secure_storage
```

---

## 📬 Contact

> **Ha Jinhee**  
> 📧 hajhi7899@gmail.com  
> 🌐 GitHub: [jin123346](https://github.com/jin123346)

