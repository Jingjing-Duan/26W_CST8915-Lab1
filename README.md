# CST8915 Lab 1: Algonquin Pet Store on Azure VM

**Student Name**: Jingjing Duan  
**Student ID**: 041159829  
**Course**: CST8915 Full-stack Cloud-native Development  
**Semester**: Winter 2026  

---

## Demo Video

🎥 **Watch Demo Video**:  
youtube.com/watch?v=t5C37ASPgf8&feature=youtu.be

The demo video shows the full application running on an Azure Virtual Machine, including the Store Front, Product Service, Order Service, and RabbitMQ.

---

## Technical Explanations

### Order Service (Node.js)
The Order Service is responsible for handling customer orders. When a user places an order from the Store Front, the request is sent to the Order Service. This service receives the order data and sends it to RabbitMQ so the order can be processed asynchronously.
The Order Service is built using Node.js because it works well with asynchronous operations and network requests. In the microservices architecture, this service does not directly communicate with other services. Instead, it uses RabbitMQ to send messages, which helps keep the system loosely coupled and easier to scale.


---

### Product Service (Rust)
The Product Service provides product information for the application. It exposes a REST API that allows the Store Front to request a list of products and display them to users on the homepage.
This service is written in Rust using the Warp framework. Rust was chosen because it is fast and reliable, and it helps prevent common memory-related errors. In the microservices architecture, the Product Service runs independently and communicates with the Store Front through HTTP requests.

---

### Store Front (Vue.js)
The Store Front is the user interface of the application. It allows users to browse products, add items to a cart, and place orders. It acts as the main interaction point between the user and the backend services.
The Store Front is built using Vue.js, which makes it easier to build interactive web applications. It communicates with the Product Service to retrieve product data and sends order requests to the Order Service using REST APIs. This separation allows the frontend and backend to be developed and managed independently.

---

## Challenges and Learnings (Optional)

During this lab, I learned how to deploy and connect multiple microservices on an Azure Virtual Machine. One of the main challenges was configuring network ports and ensuring services could communicate correctly. This lab helped me better understand service decoupling, message queues, and real-world cloud deployment workflows.

---

## Acknowledgments

RabbitMQ Documentation  
Azure Documentation  
Course lecture materials
