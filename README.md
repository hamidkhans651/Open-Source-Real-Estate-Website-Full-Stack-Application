# College-assignments

REAL ESTATE WEBSITE 
Teaching Program Microservice

Schema:
Program: (id, title, description, prerequisite) 
PROPERTIES: (id, propertyId, title, short_description)

API Endpoints:
Program Management

`POST /programs/create: Creates a new property.`
`PUT /programs/{programId}/update: Updates a property details.`
`DELETE /programs/{programId}/delete: Deletes a program.`
`GET /programs/list: Retrieves a list of all properties.`
API : Get All PROPERTIES
Endpoint: api.property.com/program/all
Method: GET
Description: Retrieves a list of all properties available in the system.
Request:
No request body is required for this API as it retrieves all properties.

Successful Response:

{
    "status": "success",
    "programs": [
        {
            "ProgramId": "P001",
            "Title": "PROPERTY DETAIlS",
            "Description": "Showing all details of property to user"
            "Prerequisites": "None"
        },
        {
            "ProgramId": "P002",
            "Title": "Further Process of sell & Buy",
            "Description": "An  focused on applied Generative AI techniques.",
            "Prerequisites": "None"
        }
    ]
}

Failed Response:
{
    "status": "error",
    "message": "No programs currently available."
}


API : Get Specific Program
Endpoint: api.panaversity.com/program/{id}
Method: GET
Description: Retrieves details about a specific program.
Request:
{ 
    "ProgramId": "P001"
}
Successful Response:
{
    "status": "success",
    "ProgramId": "P001",
    "Title": "Cloud Native Modern Python Program",
    "Description": "A comprehensive program covering all aspects of Cloud Native Modern Python Programming.",
    "ShortDescription": "A comprehensive program covering all aspects of Cloud Native Modern Python Programming.",
    "Prerequisites": "None",
    "Courses": [
        {
            "CourseId": "C001",
            "Title": "Modern Python Program",
            "Description": "This course provides an in-depth understanding of modern Python programming techniques.",
            "ShortDescription": "Modern Python Program"
        },
        {
            "CourseId": "C002",
            "Title": "Cloud Native",
            "Description": "This course covers cloud-native concepts and practices.",
            "ShortDescription": "Cloud Native"
        }
    ]
}
Failed Response:
{
    "status": "error",
    "message": "Program not found for the provided ProgramId."
}

API : Create New Program
Endpoint: api.panaversity.com/program/create
Method: POST
Description: Creates a new program with the specified details.
Request:
{
    "title": "Modern Python Program",
    "description": "Cover all aspects of modern Python.",
    "prerequisite": "None"
}

Successful Response:
{
    "status": "success",
    "ProgramId": "P003",
    "message": "Program created successfully."
}
Failed Response:
{
    "status": "error",
    "message": "Invalid input data. Please check the required fields."
}
API : Update Program
Endpoint: api.panaversity.com/program/update/{id}
Method: PUT
Description: Updates the details of an existing program identified by its id.
Request:
{
    "id": "P001"
}
{
    "title": "Modern Python Program",
    "description": "Generative AI approaches to modern Python programming",
    "prerequisite": "Basic Python knowledge"
}
Successful Response:
{
    "status": "success",
    "program": {
        "id": "P001",
        "title": "Modern Python Program",
        "description": "Generative AI approaches to modern Python programming",
        "prerequisite": "Basic Python knowledge"
    },
    "message": "Program updated successfully."
}
Failed Response: (Not Found )
{
    "status": "error",
    "message": "Program not found for the provided ID."
}
Failed Response: (Invalid Input )
{
    "status": "error",
    "message": "Invalid input data. Please check the required fields."
}

API :  Delete Program
Endpoint: api.panaversity.com/program/delete/{id}
Method: DELETE
Description:Deletes an existing program identified by its id.
Request:
No request body needed; Id is passed as a URL parameter
Successful Response:
{
    "status": "success",
    "message": "Program deleted successfully."
}
Failed Response:
{
    "status": "error",
    "message": "Program not found for the provided ID."
}


Course Management
POST /programs/{programId}/courses/create: Creates a new course within a program.
PUT /courses/{courseId}/update: Updates an existing course's details.
DELETE /courses/{courseId}/delete: Deletes a course.
GET /programs/{programId}/courses: Retrieves a list of courses within a program.
GET /courses/{courseId}/details: Fetches detailed information about a specific course, including its Table of Contents.

API: Retrieve a List of Courses within a Program
Endpoint: api.panaversity.com/programs/{programId}/courses
Method: GET
Successful Response:
{
    "status": "success",
    "programId": "P001",
    "courses": [
        {
            "id": "C001",
            "title": "",
            "short_description": "A course on advanced concepts in Python programming."
        },
        {
            "id": "C002",
            "title": "Cloud Native Development",
            "short_description": "A course focused on cloud-native development practices."
        }
        // Additional courses would be listed here
    ]
}
Failed Response:
{
    "status": "error",
    "message": "Program not found for the provided Program ID."
}
API : Get All Courses

Endpoint: api.panaversity.com/courses/all
Method: GET
Description: Retrieves a list of all courses available in the system.
Request:
No request body is required for this API as it retrieves all courses.
Successful Response:
{
    "Courses": [
        {
            "CourseId": "C001",
            "Title": "Generative AI",
            "Description": "This course covers the fundamentals of Generative AI.",
            "ShortDescription": "Generative AI Overview"
            "ProgramId": "P001"
        },
        {
            "CourseId": "C002",
            "Title": "Cloud Native AI",
            "Description": "This course focuses on cloud-native approaches to AI.",
            "ShortDescription": "Cloud Native AI Overview"
            "ProgramId": "P002"
        }
        // Additional courses would be listed here
    ]
}
Failed Response:
{
    "status": "error",
    "message": "No courses currently available."
}

Description: Retrieves a list of all courses available in the system.
Request:
No request body is required for this API as it retrieves all courses.
API : Get Specific Course
Endpoint: api.panaversity.com/course/{id}
Method: GET
Description: Retrieves details about a specific course identified by its id.
Request:
{ 
    "CourdeId": "C001"
}
Successful Response:
{
    "status": "success",
    "course": {
        "id": "C001",
        "programId": "P001",
        "title": "Advanced Python Programming",
        "short_description": "A course on advanced concepts in Python programming."
    }
}
Failed Response:
{
    "status": "error",
    "message": "Course not found for the provided ID."
}

API : Create New Course
Endpoint: api.panaversity.com//programs/{programId}/courses/create
Method: POST
Description: Creates a new course associated with a specific program identified by programId.
Request:
{
    "programId": "P001",
    "title": "Learn Kubernetes",
    "short_description": "A course on advanced concepts in Kubernetes ."
}

Successful Response:
{
    "status": "success",
    "course": {
        "id": "C003",
        "programId": "P001",
        "title": "Advanced Python Programming",
        "short_description": "A course on advanced concepts in Python programming."
    },
    "message": "Course created successfully."
}

Failed Response:
{
    "status": "error",
    "message": "Program not found for the provided Program ID."
}
Failed Response:
{
    "status": "error",
    "message": "Invalid input data. Please check the required fields."
}

API : Update Course
Endpoint: api.panaversity.com/course/update/{id}
Method: PUT
Description: Updates the details of an existing course identified by its id.
Request:
{
    "id": "C001"
}
{
    "title": "Applied Generative AI",
    "short_description": "It covers all the fundamentals of Applied Generative AI.",
    "programId": "P001"
}

Successful Response:
{
    "status": "success",
    "course": {
        "id": "C001",
        "programId": "P001",
        "title": "Applied Generative AI",
        "short_description": "It covers all the fundamentals of Applied Generative AI..",
    },
    "message": "Course updated successfully."
}

Failed Response:
{
    "status": "error",
    "message": "Course not found for the provided ID."
}
Failed Response:
{
    "status": "error",
    "message": "Invalid input data. Please check the required fields."
}

API :  Delete Course
Endpoint: api.panaversity.com/course/delete/{id}
Method: DELETE
Description: Deletes an existing course identified by its id.
Request:
No request body needed; Id is passed as a URL parameter
Successful Response:
{
    "status": "success",
    "message": "Course deleted successfully."
}
Failed Response:
{
    "status": "error",
    "message": "Course not found for the provided ID."
}


Course Content Microservice
Schema:
Module: (id, courseId, title, description)
Lesson: (id, moduleId, title, contentUrl, duration)

API Endpoints:
Module Management
POST /courses/{courseId}/modules: Creates a new module for a course.
GET /courses/{courseId}/modules: Retrieves all modules for a course.
PUT /modules/{moduleId}: Updates a specific module.
DELETE /modules/{moduleId}: Deletes a specific module.
API : Get All Modules For A Courses
Endpoint:  api.panaversity.com/courses/{courseId}/modules
Method: GET
Description: Retrieves all modules associated with a specific course identified by courseId
Request:
The courseId is passed as a path parameter in the URL, so no request body is required.
Successful Response:
{
    "status": "success",
    "courseId": "C001",
    "modules": [
        {
            "id": "M001",
            "title": "Chat GPT",
            "description": "This module covers the creation of Chat GPT"
        },
        {
            "id": "M002",
            "title": "Prompt Engineering",
            "description": "This module explores the principles of Prompt Engineering."
        }
        // Additional modules would be listed here
    ]
}
Failed Response:
{
    "status": "error",
    "message": "Course not found for the provided Course ID."
}
API : Create New Module for a Course
Endpoint:  api.panaversity.com/courses/{courseId}/modules
Method: GET
Description: Retrieves all modules associated with a specific course identified by courseId
Request:
{
    "title": "Open Assistant API",
    "description": "This module provides a comprehensive guide on how to create and integrate an Open Assistant API."
}

Successful Response:
{
    "status": "success",
    "module": {
        "id": "M003",
        "courseId": "C001",
        "title": "Open Assistant API",
        "description": "This module provides a comprehensive guide on how to create and integrate an Open Assistant API."
    },
    "message": "Module created successfully."
}

Failed Response:
{
    "status": "error",
    "message": "Course not found for the provided Course ID."
}

Failed Response:
{
    "status": "error",
    "message": "Invalid input data. Please check the required fields."
}
API : Update Specific Module
Endpoint: api.panaversity.com/module/update/{id}
Method: PUT
Description: Updates the details of an existing module identified by its id
Request:
{
    "title": "AI Agents",
    "description": "This module provides an in-depth look at AI agents, their architecture, and implementation strategies."
}
Successful Response:
{
    "status": "success",
    "module": {
        "id": "M002",
        "courseId": "C001",
        "title": "AI Agents",
        "description": "This module provides an in-depth look at AI agents, their architecture, and implementation strategies."
    },
    "message": "Module updated successfully."
}
Failed Response:
{
    "status": "error",
    "message": "Module not found for the provided ID."
}

Failed Response:
{
    "status": "error",
    "message": "Invalid input data. Please check the required fields."
}
API :  Delete Specific Module
Endpoint: api.panaversity.com/modules/{id}
Method: DELETE
Description: Deletes an existing module identified by its id
Request:
No request body is required since the id of the module to be deleted is passed as a path parameter in the URL.
Successful Response:
{
    "status": "success",
    "message": "Module deleted successfully."
}
Failed Response:
{
    "status": "error",
    "message": "Module not found for the provided ID."
}


Lesson Management
POST /modules/{moduleId}/lessons: Adds a new lesson to a module.
GET /modules/{moduleId}/lessons: Retrieves all lessons for a module.
PUT /lessons/{lessonId}: Updates specific lesson details.
DELETE /lessons/{lessonId}: Deletes a specific lesson.
API : Get All Lessons For A Courses
Endpoint: api.panaversity.com/modules/{moduleId}/lessons
Method: GET
Description: Retrieves all lessons associated with a specific module identified by moduleId.
Request:
The moduleId is passed as a path parameter in the URL, so no request body is required.
Successful Response:
{
    "status": "success",
    "moduleId": "M001",
    "lessons": [
        {
            "id": "L001",
            "title": "FastAPI in Container",
            "contentUrl": "https://github.com/panaversity/fastapi-in-container ",
            "duration": “3 weeks” 
        },
        {
            "id": "L002",
            "title": "Deploying FastAPI with Docker",
            "contentUrl": "https://github.com/panaversity/deploy-fastapi-docker ",
            "duration": “4 weeks”
        }
        // Additional lessons would be listed here
    ]
}
Failed Response:
{
    "status": "error",
    "message": "Module not found for the provided Module ID."
}
API : Add New Lesson to a Module
Endpoint: api.panaversity.com/modules/{moduleId}/lessons
Method: GET
Description: Adds a new lesson to a specific module identified by moduleId.
Request:
{
    "title": "Modern Generative AI Applications",
    "contentUrl": "https://github.com/panaversity/modern-generative-ai-applications ",
    "duration": “Three weeks”
}

{
    "status": "success",
    "lesson": {
        "id": "L005",
        "moduleId": "M001",
        "title": "Modern Generative AI Applications",
        "contentUrl": "https://example.com/modern-generative-ai-applications",
        "duration": "40 minutes"
    },
    "message": "Lesson added successfully."
}

Successful Response:
{
    "status": "error",
    "message": "Module not found for the provided Module ID."
}

Failed Response:
{
    "status": "error",
    "message": "Invalid input data. Please check the required fields."
}
API : Update Specific Lesson
Endpoint: api.panaversity.com/lessons/{lessonId}
Method: PUT
Description:  Updates the details of a specific lesson identified by its lessonId.
Request:
{
    "title": "Improve LLM Accuracy",
    "contentUrl": "https://github.com/panaversity/improve-llm-accuracy",
    "duration": “Two weeks”
}

Successful Response:
{
    "status": "success",
    "lesson": {
        "id": "L005",
        "moduleId": "M001",
        "title": "Improve LLM Accuracy",
        "contentUrl": "https://github.com/panaversity/improve-llm-accuracy",
        "duration": "Two weeks"
    },
    "message": "Lesson updated successfully."
}

Failed Response:
{
    "status": "error",
    "message": "Lesson not found for the provided Lesson ID."
}

Failed Response:
{
    "status": "error",
    "message": "Invalid input data. Please check the required fields."
}
API :  Delete Specific Lesson
Endpoint: api.panaversity.com/lesson/{id}
Method: DELETE
Description: Deletes a specific lesson identified by its lessonId.
Request:
No request body is required since the lessonId of the lesson to be deleted is passed as a path parameter in the URL.
Successful Response:
{
    "status": "success",
    "message": "Lesson deleted successfully."
}
Failed Response:
{
    "status": "error",
    "message": "Lesson not found for the provided Lesson ID."
}



Instructor Microservice
Schema:
id: Unique identifier for the instructor.
name: Name of the instructor.
email: Email address of the instructor.
assignedCourses: List of courses assigned to the instructor.
API Endpoints:
Base URL: api.panaversity.com
POST /instructors/login: Instructor login and authentication.
GET /instructors/{instructorId}/classes: Lists all classes taught by the instructor.
GET /instructors/{instructorId}/students: Retrieves students assigned to the instructor.

Examples:
POST  api.panaversity.com/instructors/login
Request:
{
    "email": "hamid@example.com",
    "password": "strongpassword123"
}

Successful Response:
{
    "status": "success",
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
    "instructor": {
        "id": "instructor123",
        "name": "Hamid Ali",
        "email": "hamid@example.com",
        "assignedCourses": ["101", "102"]
    }
}

Failed Response (Invalid Credentials):
{
    "status": "error",
    "message": "Invalid email or password"
}
GET  api.panaversity.com/instructors/{instructorId}/classes
Request: (No request body needed; instructorId is passed as a URL parameter)
Successful Response:
{
    "status": "success",
    "classes": [
        {
            "classId": "class001",
            "courseId": "101",
            "courseTitle": "Introduction to Generative AI",
            "term": "Fall 2024",
            "meetingTimes": "Mon, Wed, Fri - 10:00 AM to 11:00 AM"
        },
        {
            "classId": "class002",
            "courseId": "102",
            "courseTitle": "Deep Learning for Generative AI",
            "term": "Spring 2025",
            "meetingTimes": "Tue, Thu - 2:00 PM to 3:30 PM"
        }
    ]
}
Failed Response (Instructor Not Found):
{
    "status": "error",
    "message": "Instructor not found"
}
GET  /instructors/{instructorId}/students
Request: (No request body needed; instructorId is passed as a URL parameter)
Successful Response:
{
    "status": "success",
    "students": [
        {
            "studentId": "student001",
            "name": "Ahmed Aslam",
            "email": "ahmed.aslam@example.com",
            "courseId": "101",
            "courseTitle": "Introduction to Generative AI"
        },
        {
            "studentId": "student002",
            "name": "Sara Khan",
            "email": "sara.khan@example.com",
            "courseId": "102",
            "courseTitle": "Deep Learning for Generative AI"
        }
    ]
}

Failed Response (Instructor Not Found):
{
    "status": "error",
    "message": "Instructor not found"
}


Student Microservice
Schema:
student_id: Unique identifier for the student.
password: The student's password.
name: Name of the student.
email: Email address of the student.
mobile_number: The student's mobile phone number.
city: The city where the student resides.
country: The country where the student resides.
API Endpoints:
Base URL: api.panaversity.com
POST /student/login: Handles student login and validates credentials.
GET /student/details: Fetches student details.
Example:
POST /student/login
Request:
{
    "student_id": "12345",
    "password": "mysecretpassword"
}

Successful Response:
{
    "status": "success",
    "student": {
        "student_id": "12345",
        "name": "Ahmed Aslam",
        "email": "ahmed@gmail.com",
        "mobile_number": "03008255555",
        "city": "Karachi",
        "country": "Pakistan"
    },
    "message": "Login successful"
}

Failed Response (Invalid Credentials):
{
    "status": "error",
    "message": "Invalid student ID or password"
}

Failed Response (Account Locked):
{
    "status": "error",
    "message": "Account is locked due to multiple unsuccessful login attempts. Please contact support."
}

GET /student/d
