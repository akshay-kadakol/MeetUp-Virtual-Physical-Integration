# MeetUp-Virtual-Physical-Integration

This project presents a conceptual system designed to bridge the divide between virtual and real-world social connections. It enhances the way individuals interact by enabling seamless transitions between online relationships and offline meetups, fostering deeper personal and professional engagement.

---

## 🚀 Project Overview

In the modern digital era, most individuals maintain separate online and offline social circles, leading to missed opportunities for building meaningful relationships. 

This project introduces an integrated platform that:

✅ Recommends offline events based on user interests and online activities  
✅ Allows users to invite online friends to real-world events  
✅ Enables users to invite offline friends to virtual events via SMS or Email  
✅ Collects feedback after events to refine future recommendations  
✅ Prioritizes data privacy and secure information management  

---

## 🎯 Objectives

- Seamlessly integrate virtual preferences with physical interactions  
- Provide event recommendations personalized to user profiles  
- Strengthen social bonds by promoting meaningful offline and online connections  
- Securely handle user data and continuously improve recommendations based on feedback  

---

## 🛠️ Key Features

- Personalized offline event suggestions  
- Ability to invite online friends/followers to in-person meetups  
- Invite offline friends to virtual activities using SMS or Email  
- Feedback collection for improving recommendation algorithms  
- User-friendly system design with emphasis on privacy and security  

---

## 📁 Project Structure

- MeetUp-Virtual-Physical-Integration/
   - README.md
   - MeetUp_Project_Report.pdf
   - Diagrams/
   - Design/


---

## 🗂️ System Diagrams

Visual representations of the system's design and workflows:

### BPMN - Offline Event Process  
![BPMN Offline](https://github.com/user-attachments/assets/bba8c1a4-1abe-4373-9b00-7a5efbf3d944)

### BPMN - Online Event Process  
![BPMN Online](https://github.com/user-attachments/assets/ae31aad6-481f-4557-b4f9-6f6dc7b19bf1)

### Context Diagram  
![Context Diagram](https://github.com/user-attachments/assets/ea5b40f0-86b2-4244-ab84-ffac4ec357c9)

### Use Case Diagram  
![Use Case Diagram](https://github.com/user-attachments/assets/d01fabbf-3fb5-4050-b8c2-ab0763a1d609)

### Class Diagram (Without Methods)  
![Class Diagram No Methods](https://github.com/user-attachments/assets/00a1b60d-a6b1-4b4c-83da-d2adfd99df6f)

### Class Diagram (With Methods)  
![Class Diagram With Methods](https://github.com/user-attachments/assets/f6728617-ecd9-4c04-9d38-2f73c9c3a707)

### Sequence Diagram - Offline Interaction  
![Sequence Offline](https://github.com/user-attachments/assets/b15fa239-9456-468a-adea-86c9e3d97b6f)

### Sequence Diagram - Online Interaction  
![Sequence Online](https://github.com/user-attachments/assets/d82603e5-2b34-41c3-8e7d-cd914c1a3add)

### Entity Relationship Diagram (ERD)  
![ER Diagram](https://github.com/user-attachments/assets/f0687cfc-d5fe-4904-8234-6015bfb21999)

---

## 📐 System Design Documentation

The `/Design` folder includes:

- `Functional_Specifications.md` – System functionalities & user stories
- # Functional Specifications

- The user should be able to register into the application by entering all details.
- Users should be able to log in with valid credentials provided during signup.
- Users must set their preferences (event categories, locations, interests) for accurate event recommendations.
- The system should analyze preferences and generate personalized event recommendations from the database.
- The user should be able to finalize participation in an event.
- The system should generate event invitations for online and offline friends.
- Users can invite offline friends via SMS or Email and share event links with online friends on social media.
- After participating in events, the system should collect user feedback (ratings and comments).
- The recommendation algorithm must be refined based on collected feedback to improve future suggestions.


- `Class_Methods.md` – Method logic for each system class
- # Class Responsibilities and Methods

## SignUp Class
Method: userSignUp(email, password)
- Registers user if email is unique
- Returns success or error message

## Login Class
Method: userLogin(email, password)
- Authenticates user credentials
- Provides system access or error feedback

## Preferences Class
Method: getPreferences(userID, preferenceList)
- Stores and updates user event preferences

## Events Class
Method: getEvents(profile, preferences)
- Analyzes preferences and generates event recommendations

## Invitation Class
Method: generateInvitation(userID, eventID, email, phone)
- Sends invitations to offline friends via Email/SMS

## Feedback Class
Method: submitFeedback(userID, feedbackText)
- Stores user feedback to refine recommendations

- # System Constraints

- Users must provide FirstName and LastName during registration
- Login requires non-null Email and Password fields
- Preferences must be set before recommendations are generated
- Events require EventName, Date, Time, and Location to be stored
- Invitations cannot be sent without valid Email or Phone for offline users
- Feedback cannot be submitted with empty fields
- Event invitations require both online (social media) and offline (SMS/Email) options

 
- `Sequence_Logic.md` – Event interaction process logic
- # Sequence Logic for Major Scenarios

## Scenario: Meet Online Friends in an Offline Event
1. User receives personalized offline event recommendations
2. User finalizes participation in an event
3. System generates a shareable event invitation
4. User shares invitation via social media for online friends
5. User invites offline friends via SMS or Email

## Scenario: Meet Offline Friends in an Online Event
1. User receives virtual event recommendations
2. User chooses to invite offline friends via SMS or Email
3. Offline friends join the virtual event
4. System collects feedback after the event

# Software Design - Method Details

## Method: userSignUp(email, password)
- Checks if user already exists
- Registers new user if email is unique
- Returns confirmation or error

<img width="106" alt="image" src="https://github.com/user-attachments/assets/08167dcc-9e62-448e-9d96-27b32f0219a8" />                 <img width="103" alt="image" src="https://github.com/user-attachments/assets/9d4e648d-9d92-4a02-952a-668b9d574b99" />

## Method: userLogin(email, password)
- Retrieves stored password for provided email
- Authenticates credentials
- Returns login success or failure message

- 
<img width="114" alt="image" src="https://github.com/user-attachments/assets/330b7c94-0e99-4d93-8508-055b104bda92" />           <img width="114" alt="image" src="https://github.com/user-attachments/assets/3e8cc322-0e5b-4663-a658-aac496714b16" />                <img width="109" alt="image" src="https://github.com/user-attachments/assets/e5992931-5e01-4c90-9fcb-5e0555a84bc3" />




## Method: getPreferences(userID, preferenceList)
- Validates preferences
- Saves user preferences to the database
- Confirms success or error
               <img width="82" alt="image" src="https://github.com/user-attachments/assets/c34d801b-786c-4b08-a1c8-15d5b80d397b" />

## Method: getEvents(profile, preferences)
- Analyzes user preferences
- Retrieves matching events from the database
- Displays personalized event list
  <img width="109" alt="image" src="https://github.com/user-attachments/assets/54c2bb69-fcd9-4d2a-a6f3-d0d882d3ce08" />                 <img width="82" alt="image" src="https://github.com/user-attachments/assets/39a44a3f-1a68-4182-ba06-8035faae6969" />



## Method: generateInvitation(userID, eventID, email, phone)
- Validates Email and Phone
- Sends event invitation via Email/SMS
- Confirms successful invitation
-   <img width="82" alt="image" src="https://github.com/user-attachments/assets/36049a6d-43d4-4c78-84b6-16513583388c" />                     <img width="84" alt="image" src="https://github.com/user-attachments/assets/eb994050-b0a3-461f-9335-c3d26a0b3759" />                     <img width="84" alt="image" src="https://github.com/user-attachments/assets/5c6269ab-482c-4b0e-8f6d-0be2b91cc563" />               <img width="83" alt="image" src="https://github.com/user-attachments/assets/94d67743-cfed-4b17-92db-b346f89ccd3a" />

               



## Method: submitFeedback(userID, feedbackText)
- Stores user feedback in the database
- Updates recommendation algorithm based on feedback
          <img width="85" alt="image" src="https://github.com/user-attachments/assets/2bd2e583-be27-4901-b652-6f5a533b095a" />

---

## 💻 Technologies & Tools

| Area               | Tools/Concepts                       |
|--------------------|--------------------------------------|
| Process Modeling   | BPMN, UML Diagrams                  |
| System Design      | Class, Use Case, Sequence Diagrams  |
| Database Design    | Relational Model, SQL Concepts      |
| Documentation      | Markdown, Technical Specifications  |

---

## 👨‍💻 My Role & Contributions

I individually designed and documented the system, including:

✔ Requirement analysis and solution conceptualization  
✔ BPMN and UML modeling for system design  
✔ Database design with ER modeling and constraints  
✔ Functional specifications and method logic development  
✔ End-to-end technical documentation  

---

## 📌 Project Status

✅ Academic project completed as part of System Analysis & Project Management coursework  
💡 Future work includes developing a working software prototype with frontend and backend integration  

---

## 🎯 Learning Outcomes

- Strengthened skills in system analysis, process modeling, and design thinking  
- Applied theoretical concepts to real-world technical solutions  
- Developed comprehensive documentation to communicate technical designs effectively  

---

## 📢 Acknowledgment

This project was developed to demonstrate system analysis and project management capabilities within an academic setting.

---



