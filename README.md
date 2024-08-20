# RIMATE
Find the right roommate
### RIMATE is a Roommate Matching System

#### **Overview**
This documentation outlines the proposed system for matching roommates based on personal preferences to ensure compatibility and satisfaction for all parties involved. The system is designed to ease the stress of finding a suitable roommate by eliminating the element of luck and replacing it with a structured, data-driven approach.

#### **Process Flow**
1. **Room Seeker's Information Collection:**
   - The individual seeking a room (referred to as "room seeker") will be required to provide their personal details, which include:
     - Latest ID
     - Confirmation slip of the room reservation

2. **Preference Form:**
   - The room seeker fills out a form detailing their preferences regarding various lifestyle factors, which include:
     - **Sleep Schedule:** Early bird or night owl
     - **Cleanliness:** Levels of tidiness expected
     - **Cooking:** Frequency and type of cooking (e.g., shared meals or independent)
     - **Alcohol Consumption:** Whether they drink and their comfort level with alcohol consumption by others
     - **Noise Levels:** Tolerance to noise and preferred quiet times
     - **Socializing:** Frequency of hosting guests or participating in social activities
     - **Guest Policy:** Preferences for having guests over, including overnight stays

3. **Matching Process:**
   - The system will compare the room seeker's preferences against those of available roommates who have filled out a similar form. 
   - Using an algorithm, the system will calculate a compatibility score and present the room seeker with three roommate options that best match their preferences.

#### **Impact of the System**
The system is designed to:
- **Help Relieve Stress:** By providing a structured and reliable process for finding compatible roommates, it reduces the anxiety associated with finding the right living partner.
- **Reduce Search Time:** The system expedites the roommate-finding process, making it faster and more efficient.
- **Support Room Seekers in Zambia:** Specifically, it aims to assist people residing in Zambia to find roommates and accommodations easily and effectively.

#### **Review System**
- The system will include a review feature where previous roommates can provide feedback on their experiences, further assisting future users in making informed decisions.

#### **Problem Statement**
- **Problem:** Finding a suitable roommate can be challenging due to differences in lifestyles and expectations, which often results in conflicts.
- **Solution:** The proposed system will streamline the process of finding a compatible roommate by matching individuals based on detailed preferences, thereby eliminating the random element of luck.

#### **Feature Highlight: Roommate Matching**
- **Rationale:** The core feature of the system is its ability to find the "right roommate" for users, ensuring that individuals are paired with others who share similar habits and expectations.

#### **Accommodation Sections**
- The system will cater to two sections of accommodation:
  - **On-Campus Accommodation:** Housing provided within the university or college campus.
  - **Off-Campus Accommodation:** Housing provided outside the campus premises.

### Technology Documentation for RIMATE a Roommate Matching System

#### **Overview**
This Part provides details of the technology stack, architecture, and key components of the Roommate Matching System. The system is designed to efficiently match individuals with compatible roommates based on their preferences, utilizing a robust backend, mobile-friendly frontend, and intelligent matching algorithms.

#### **Technology Stack**

1. **Frontend:**
   - **React Native:** A popular framework for building cross-platform mobile applications using JavaScript. React Native is chosen for its ability to develop native apps for both iOS and Android from a single codebase.
   - **Redux:** For state management, allowing predictable state updates and better management of application state across different components.
   - **Axios:** A promise-based HTTP client for making API requests from the mobile app to the backend.

2. **Backend:**
   - **Flask:** A lightweight Python web framework used to create the RESTful API that serves as the backbone of the application. Flask is chosen for its simplicity and flexibility, making it ideal for rapid development.
   - **MongoDB:** A NoSQL database used for storing user data, preferences, and other dynamic information. MongoDB's flexible schema is well-suited for handling the varied data types involved in the roommate matching process.
   - **Redis:** An in-memory data structure store, used for caching and speeding up data retrieval, reducing the load on MongoDB, and ensuring fast response times for frequently accessed data.

3. **Matching Algorithm:**
   - **Python (Pandas, Scikit-learn):** Used for developing and running the roommate matching algorithm. Pandas is utilized for data manipulation, while Scikit-learn provides tools for implementing and optimizing the matching algorithm.
   - **Algorithm Type:** A recommendation system that uses collaborative filtering or a weighted scoring system based on the preferences provided by users.

4. **Authentication & Security:**
   - **JWT (JSON Web Tokens):** Used for user authentication and maintaining sessions. JWT allows secure transmission of user credentials between the mobile app and backend.
   - **Bcrypt:** A password-hashing function used to securely store user passwords in the database.

5. **Hosting & Deployment:**
   - **Heroku/AWS/GCP:** For hosting the Flask backend, providing scalability, security, and ease of deployment.
   - **MongoDB Atlas:** A cloud-hosted MongoDB service for secure and scalable database management.
   - **Redis Cloud:** A managed Redis service for caching, ensuring high availability and persistence.
   - **Nginx:** A web server used as a reverse proxy and load balancer to improve the performance and reliability of the application.

6. **APIs & Integrations:**
   - **RESTful API:** The backend provides RESTful endpoints for handling user authentication, preference submission, matching results, and reviews.
   - **Third-Party API Integration:** Potential integration with external APIs for additional features, such as real-time messaging or geolocation services for off-campus accommodation.

7. **Version Control & Collaboration:**
   - **Git & GitHub:** For version control and collaborative development. GitHub Actions could be used for continuous integration and deployment (CI/CD) pipelines.
   - **Jira/Trello:** For project management, tracking development progress, and managing tasks within the team.

8. **Testing:**
   - **Jest & Enzyme:** For unit and integration testing of the React Native components.
   - **Pytest:** For testing the Flask API endpoints, ensuring reliability and robustness.
   - **Postman:** For manual API testing to ensure that the endpoints behave as expected.

#### **System Architecture**

1. **Client-Server Architecture:**
   - **Client Side:** The mobile application is built using React Native, which interacts with the backend via RESTful API calls. The app handles user input, displays matched roommates, and collects reviews.
   - **Server Side:** The backend, built with Flask, handles API requests, processes user data, runs the matching algorithm, and communicates with the MongoDB and Redis databases.

2. **Database Design:**
   - **User Collection:** Stores user data, including personal details, hashed passwords, and authentication tokens.
   - **Preferences Collection:** Contains user preferences, such as sleep schedule, cleanliness, noise levels, etc., used by the matching algorithm.
   - **Matches Collection:** Stores the results of the matching process, including the compatibility score and selected roommates.
   - **Reviews Collection:** Keeps user feedback on previous roommates for future reference in the matching process.

3. **Data Flow:**
   - **User Interaction:** The user fills out the preference form on the mobile app, which is then sent to the backend via an API call.
   - **Data Processing:** The backend receives the data, stores it in MongoDB, and triggers the matching algorithm.
   - **Caching with Redis:** Frequently accessed data, such as user preferences and match results, is cached in Redis to reduce latency and improve performance.
   - **Matching Process:** The algorithm processes the user’s data, compares it with other users' preferences, and calculates compatibility scores.
   - **Results Delivery:** The backend sends the matched roommates and their scores back to the mobile app, where the user can view their options.

4. **Scalability:**
   - **Horizontal Scaling:** The system can scale horizontally by adding more servers to handle increased traffic.
   - **Database Scaling:** MongoDB Atlas and Redis Cloud offer built-in tools for scaling the database and cache as the user base grows.

5. **Security Measures:**
   - **Data Encryption:** All sensitive data, including user credentials and preferences, are encrypted in transit using SSL/TLS.
   - **Access Control:** Role-based access control (RBAC) is implemented to ensure that only authorized users can access specific features or data.
   - **Regular Audits:** The system undergoes regular security audits to identify and mitigate potential vulnerabilities.

#### **Deployment Strategy**

1. **Staging Environment:**
   - A staging environment will be set up to mirror the production environment, allowing for thorough testing before deploying any new features or updates.

2. **Continuous Integration/Continuous Deployment (CI/CD):**
   - Automated pipelines will be set up using GitHub Actions to ensure that every code change is tested and deployed with minimal manual intervention.

3. **Monitoring & Logging:**
   - **New Relic/Datadog:** For monitoring application performance and identifying bottlenecks.
   - **Log Management:** Centralized logging using tools like ELK Stack (Elasticsearch, Logstash, Kibana) for tracking and analyzing system logs.

#### **Future Enhancements**

1. **Advanced Machine Learning Integration:**
   - Explore machine learning models to enhance the roommate matching algorithm by incorporating predictive analytics based on user behavior and historical data.

2. **Real-Time Communication:**
   - Implement a real-time chat feature using WebSockets or third-party services like Firebase to allow potential roommates to communicate before finalizing their selection.

3. **Geolocation Services:**
   - Integrate geolocation APIs to help users find nearby off-campus accommodation based on their preferences.

4. **AI-Based Matching Optimization:**
   - Investigate the use of AI for dynamically optimizing the matching algorithm based on real-time feedback and changing preferences.
---
## System Infrastructure

### **1. Frontend Components (React Native)**
   - **1.1 User Authentication Screens**
     - Login Screen
     - Signup Screen
     - Password Reset Screen
   - **1.2 User Profile & Preferences**
     - Profile Setup Screen
     - Preferences Form Screen
   - **1.3 Roommate Matching**
     - Matching Results Screen
     - Roommate Profile Details Screen
     - Filtering & Sorting Options
   - **1.4 Notifications & Messages**
     - Notifications Screen
     - Real-Time Chat Screen (optional)
   - **1.5 Reviews & Feedback**
     - Review Submission Screen
     - View Roommate Reviews Screen
   - **1.6 Additional Screens**
     - Home/Dashboard Screen
     - Settings Screen
     - Help/Support Screen

### **2. Backend Components (Flask)**
   - **2.1 Authentication & User Management**
     - User Registration Endpoint
     - Login/Logout Endpoint
     - Password Reset Endpoint
     - Token Management (JWT)
   - **2.2 Profile & Preferences Management**
     - User Profile Endpoint
     - Preferences Submission Endpoint
     - Update Profile/Preferences Endpoint
   - **2.3 Roommate Matching**
     - Matching Algorithm Execution
     - Matching Results Endpoint
     - Matching History Retrieval
   - **2.4 Messaging & Notifications (optional)**
     - Message Sending/Receiving Endpoint
     - Notification Service Endpoint
   - **2.5 Reviews & Ratings**
     - Submit Review Endpoint
     - Fetch Reviews Endpoint
   - **2.6 Admin & Analytics (optional)**
     - Admin Dashboard API
     - Analytics Data Retrieval Endpoint

### **3. Database Components (MongoDB)**
   - **3.1 User Collection**
     - Stores user details (username, email, hashed password, etc.)
   - **3.2 Preferences Collection**
     - Stores user preferences related to living habits
   - **3.3 Matches Collection**
     - Stores matching results and compatibility scores
   - **3.4 Reviews Collection**
     - Stores reviews and ratings of past roommates
   - **3.5 Messages Collection (optional)**
     - Stores messages between users (if chat is implemented)
   - **3.6 Notifications Collection (optional)**
     - Stores notifications sent to users

### **4. Caching Components (Redis)**
   - **4.1 User Session Cache**
     - Caches active user sessions to reduce load on the database
   - **4.2 Frequently Accessed Data**
     - Caches frequently accessed user profiles and preferences
   - **4.3 Matching Results Cache**
     - Caches recent matching results to improve retrieval speed

### **5. Infrastructure Components**
   - **5.1 Hosting & Deployment**
     - Flask Backend Hosting (e.g., Heroku, AWS, GCP)
     - MongoDB Atlas for Database Hosting
     - Redis Cloud for Caching
   - **5.2 Continuous Integration/Continuous Deployment (CI/CD)**
     - GitHub Actions for automated testing and deployment
     - Staging Environment for pre-production testing
   - **5.3 Monitoring & Logging**
     - Application Performance Monitoring (e.g., New Relic, Datadog)
     - Centralized Logging System (e.g., ELK Stack)

### **6. Miscellaneous Components**
   - **6.1 Third-Party Integrations**
     - Geolocation API (optional)
     - Real-Time Messaging Service (e.g., Firebase) (optional)
   - **6.2 DevOps & Management**
     - GitHub for Version Control
     - Jira/Trello for Project Management

### **Summary of Components**
1. **Frontend Components:** 12 key screens/components
2. **Backend Components:** 12 API endpoints/services
3. **Database Components:** 6 collections
4. **Caching Components:** 3 caches
5. **Infrastructure Components:** 7 elements
6. **Miscellaneous Components:** 3 integrations and tools

---

**Total Components:** 43 (excluding optional components)
