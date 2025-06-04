ZAHY FILMS - Video Streaming Platform
Overview
ZAHY FILMS is an innovative video streaming platform developed as a final year project by students at the Université Chouaib Doukkali, Ecole Nationale des Sciences Appliquées d'El Jadida (ENSAJ). The platform is built using a microservices architecture to provide a scalable, modular, and user-centric solution for streaming on-demand video content. It offers features such as personalized recommendations, user interactions (likes, comments, favorites), and robust administrative tools for content and user management.
This project was completed by:

Asmae LAHLOU
Zineb TAGHTI
Hafsa SABROU
Younes AMERGA

Supervised by Prof. Chafik BAIDADA and evaluated by a jury including Prof. Hajar LAZAR during the 2024/2025 academic year.

Features
User Features

Account Management: User registration, authentication, and profile management.
Video Streaming: Access to a catalog of videos with free and premium content based on subscription levels.
Interaction: Like, dislike, and comment on videos, with the ability to reply to comments.
Personalized Recommendations: Video suggestions based on viewing history, favorites, and sentiment analysis of comments.
Favorites and History: Save favorite videos and track viewing history.
Notifications: Receive alerts for new videos and comment interactions.
ChatBot (CineBot): An integrated conversational assistant to answer queries about movies (e.g., genres, actors, release year).

Admin Features

Content Management: Upload, edit, and delete videos with metadata (title, description, genres, etc.).
User Management: View and manage user accounts, including subscription details.
Subscription Management: Create, modify, or delete subscription plans.
Dashboard: Centralized interface for monitoring platform statistics and managing resources.


Architecture
ZAHY FILMS is built on a microservices architecture with a three-tier MVC pattern, ensuring scalability, modularity, and maintainability. The system is composed of the following components:
Microservices

User Service: Manages user accounts, authentication (via Spring Security), and subscriptions. Stores data in MySQL.
Video Service: Handles video upload, storage, and streaming. Uses MinIO for object storage.
Comment Service: Manages user interactions (likes, dislikes, comments). Stores data in MongoDB.
Recommendation Service: Provides personalized video suggestions using Flask-based algorithms analyzing viewing history, favorites, and comment sentiment.
Notification Service: Sends asynchronous notifications via RabbitMQ and tests emails using Mailtrap.

Additional Components

API Gateway: Centralizes client requests and routes them to appropriate microservices.
Service Registry (Eureka Server): Enables dynamic service discovery and load balancing.
Botpress Chatbot: Enhances user experience with real-time assistance.
PayPal Integration: Facilitates secure online payments for subscriptions.

Data Storage

MySQL: Stores structured data (user accounts, subscriptions).
MongoDB: Manages semi-structured data (comments, metadata).
MinIO: Stores video files with S3-compatible object storage.

Communication

Synchronous: HTTP requests for direct interactions.
Asynchronous: RabbitMQ for non-blocking operations like notifications.

Frontend

Built with Angular, TypeScript, HTML, and CSS for a responsive and dynamic user interface.

Backend

Developed using Java, Spring Boot, and Spring Security for secure and scalable services.
Flask (Python) for the recommendation service API.


Technologies Used
Development Tools

IntelliJ IDEA: Backend development IDE.
VS Code: Frontend and general code editing.
Postman: API testing and debugging.
LaTeX: Documentation and report generation.
SonarQube: Static code analysis for quality assurance.

Languages and Frameworks

Java: Backend development with Spring Boot and Spring Security.
TypeScript: Frontend development with Angular.
Python: Recommendation service with Flask.
HTML/CSS: Interface structure and styling.

Databases and Storage

MySQL: Relational database for user and subscription data.
MongoDB: NoSQL database for comments and metadata.
MinIO: Object storage for video files.

External Services

PayPal: Secure payment processing.
Botpress: Chatbot for user assistance.
Mailtrap: Email testing for notifications.
RabbitMQ: Asynchronous messaging between microservices.
Eureka Server: Service discovery and load balancing.


Project Structure
The project is organized into sprints, each focusing on specific features:

Sprint 1: Accounts and Subscriptions

User registration, login, and profile management.
Subscription plans and PayPal payment integration.
Admin dashboard for user and subscription management.


Sprint 2: Video Management

Video upload, storage, and streaming.
Search and browse videos by genre.
User history and favorites functionality.


Sprint 3: Likes and Comments

Commenting and replying to comments.
Liking/disliking videos and comments.


Sprint 4: Personalized Recommendations

Recommendations based on viewing history, favorites, and comment sentiment analysis.
Flask-based recommendation algorithm.


Sprint 5: Notifications

Notifications for new video uploads and comment interactions.
Integration with RabbitMQ and Mailtrap.




Installation and Setup
Prerequisites

Node.js (for Angular frontend)
Java JDK 17 (for Spring Boot backend)
Python 3.8+ (for Flask recommendation service)
MySQL and MongoDB (for databases)
MinIO (for video storage)
RabbitMQ (for messaging)
Docker (optional, for containerized deployment)
PayPal Developer Account (for payment integration)
Mailtrap Account (for email testing)

Setup Instructions

Clone the Repository
git clone https://github.com/Younessamg/PFA_II_ZAHY_Films.git
cd zahy-films


Backend Setup (Spring Boot)

Navigate to the backend directory:cd backend


Configure application.properties with database credentials, MinIO, RabbitMQ, and PayPal settings.
Build and run:./mvnw clean install
./mvnw spring-boot:run




Frontend Setup (Angular)

Navigate to the frontend directory:cd frontend


Install dependencies:npm install


Run the Angular app:ng serve




Recommendation Service (Flask)

Navigate to the recommendation service directory:cd recommendation-service


Install dependencies:pip install -r requirements.txt


Run the Flask server:python app.py




Database Setup

Set up MySQL and MongoDB instances.
Import the provided schema (schema.sql) for MySQL.
Configure MinIO for video storage.


External Services

Set up RabbitMQ and configure exchanges/queues.
Create a Mailtrap account and update notification service settings.
Configure PayPal sandbox credentials for payment testing.
Integrate Botpress for the CineBot chatbot.


Run the Application

Ensure all microservices (User, Video, Comment, Recommendation, Notification) are running.
Access the application at http://localhost:4200 (default Angular port).




Testing
The project follows a test pyramid approach:

Unit Tests: Validate individual components (e.g., user creation, video upload, recommendation algorithms).
Integration Tests: Verify interactions between microservices (e.g., authentication-to-video access, comment-to-recommendation).
End-to-End Tests: Simulate complete user journeys (e.g., registration, subscription, video streaming, commenting).
Code Quality: Analyzed using SonarQube to ensure maintainability and reliability.

To run tests:
# Backend tests (Spring Boot)
cd backend
./mvnw test

# Frontend tests (Angular)
cd frontend
ng test

# Recommendation service tests (Flask)
cd recommendation-service
pytest


Future Improvements

Performance Optimization: Enhance platform responsiveness based on user feedback.
Recommendation Algorithm: Improve accuracy with advanced machine learning techniques.
Live Streaming: Add support for real-time streaming capabilities.
Content Partnerships: Expand the video catalog through collaborations with content creators.
Notification Enhancements: Strengthen notification delivery with production-ready email services.


Contributing
Contributions are welcome! Please follow these steps:

Fork the repository.
Create a new branch (git checkout -b feature/your-feature).
Commit your changes (git commit -m "Add your feature").
Push to the branch (git push origin feature/your-feature).
Open a Pull Request.


License
This project is licensed under the MIT License. See the LICENSE file for details.

Acknowledgments
We express our gratitude to:

Prof. Chafik BAIDADA for his guidance and support.
Prof. Hajar LAZAR for evaluating the project.
All ENSAJ professors for their valuable teachings that contributed to the success of this project.


