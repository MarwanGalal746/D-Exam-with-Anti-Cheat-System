<div align="center">
  <br>
  <h1>D-Exam with Anti Cheat System</h1>
</div>

## Table of contents

- [**Summary**](#summary)
- [**Functional requirements**](#functional-requirements)
- [**Non-functional requirements**](#non-functional-requirements)
- [**System architecture**](#system-architecture)
- [**Stakeholders**](#stakeholders)
- [**Use cases diagram**](#use-cases-diagram)
- [**Class diagram**](#class-diagram)
  - [**User service**](#user-service)
  - [**Course service**](#course-service)
  - [**Exam service**](#exam-service)

- [**ERD**](#erd)
  - [**User service**](#user-service)
  - [**Course service**](#course-service)
  - [**Exam service**](#exam-service)


## Summary

With the current world pandemic everyone is moving towards online exams as it’s much safer for the students, with that said, our project aims to have a reliable exams system that prevent students from cheating. Our system will give teachers the ability to create their own exams and provide them to their students. The system will have an efficient anti-cheat system with uncommon cheating detection techniques that aims to achieve equality and fairness. It will not be limited to Multiple-Choice Questions only and will have different types of questions so that the grading system will not be restricted only to the final answer with an auto correction for some types of questions.

##  Functional requirements

- **Signing Up and Registration**
  - Role (Student or Teacher).
  - Email Verification.
- **Logging In**
  - Email Verification.
  - Credentials Validation.
  - Reset Password.
- **User Profile**
- **Course**
  - Access code.
  - Create/delete a course by teacher.
  - Join/leave course by students.
  - Remove students by teachers.
- **Exam**
  - Create/delete/update an exam by teacher.
  - Take exam by student.
  - Auto-correction for MCQ questions.
- **Board**
  - See all registered courses for students.
  - See all created courses for teachers.
  - See all upcoming exams.
  - Check your previous exam results.
- **Anti-Cheat**
  - **Face Authentication**: User will have to verify his identity before entering the exam by scanning his face through the laptop’s camera and comparing it with his existing profile picture on the system, it will continue with him through the session by either taking multiple screenshots at different time or only when the system detects a change that needs a confirmation. 
  - **Eye Tracking**: User will have to look at some objects on the screen to determine the dimensions of the screen then the system will detect any suspicious behavior from the user (looking at his phone/book/another screen). The system will not always take an immediate action but will be there different scenarios for this.
  - **Restricting Device Usage**: User will not be able to normally use the device till he finishes the exam. OS services and applications will be suspended. 

##  Non functional requirements

- **Robustness**: The system is robust and handle invalid user unusual input and
  situations without crashing (Invalid picture input, email regex, etc).
- **Usability**: Interface should be simple, convenient and easy for teachers and students
  to learn and use it efficiently. User should only need 1 or 2 clicks to reach his
  destination.
- **Security**: Preventing unauthorized access to the database and code injection
  techniques such as SQL injection. Verifying user whenever he logs in from another
  device.
- **Performance and Scalability**: Considering the large number of students in each
  level of education, the response time must be within 800ms and page loading should
  not take more than 3 seconds.
- **Compatibility**: Anti-Cheat must be compatible with the different modern browsers.
- **Reliability**: The system should not fail during any stage of examination process
  from authentication to taking the exam.

##  

##  System architecture

![](System%20architecture/system-architecture.jpg)

##  Stakeholders

- **Teacher**: Possess the professional knowledge to lead create course(s) for students
  that will include exam(s), those exam(s) questions will be created by the teacher as
  well as their answers. 
- **Student**: Participates in the process by joining those courses that are created by the
  teachers as well as taking the exams that are assigned to him by those teachers in
  those courses.
- **Developer**: Designs the system that includes the interaction between the teachers
  and students through the courses as well as the exams.

##  Use cases diagram

![](Use%20cases%20diagram/Use-cases.drawio.png)

##  Class diagram

### User service

![](./Class%20diagram/user-service-cd.png)

### Course service

![](./Class%20diagram/course-service-cd.png)

### Exam service

![](./Class%20diagram/exam-service-cd.png)

### Tools services

![](./Class%20diagram/tools-services-cd.png)





##  ERD

### User service

![](./ERD/user-service-db.png)

### Course service

![](./ERD/course-service-db.png)

### Exam service

![](./ERD/exam-service-db.png)

We created three databases communicate with each others using a message broker because of we use microservices architecture as shown in the [System architecture](#System-architecture). but to make the reader relates about the relations between the three databases using foreign keys, we put the ERD of the database if we used a shared database.

![](./ERD/shared-db.png)
