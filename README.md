<div align="center">
  <br>
  <h1>D-Exam with Anti Cheat System</h1>
</div>

## Table of contents

- [**Summary**](#summary)
- [**Features**](#features)
- [**System architecture**](#system-architecture)
- [**Stakeholders**](#stakeholders)
- [**Functional requirements**](#functional-requirements)
- [**Use cases diagram**](#use-cases-diagram)
- [**ERD**](#erd)
  - [**User service**](#user-service)
  - [**Course service**](#Course-service)
  - [**Exam service**](#Exam-service)


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

##  System architecture

![](System%20architecture/system-architecture.png)

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

##  ERD

### User service

![](./ERD/user-service-db.png)

### Course service

![](./ERD/course-service-db.png)

### Exam service

![](./ERD/exam-service-db.png)

We created three databases communicate with each others using a message broker because of we use microservices architecture as shown in the [System architecture](#System-architecture). but to make the reader relates about the relations between the three databases using foreign keys, we put the ERD of the database if we used a shared database.

![](./ERD/shared-db.png)
