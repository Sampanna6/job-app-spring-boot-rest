# Job App - Spring Boot REST API

A REST API for managing job postings, built with Spring Boot, Spring Data JPA (Hibernate) and PostgreSQL. Built as a learning project while following the Telusko Spring Boot course, and tested with Postman.

## Tech stack
- Java 17 or later
- Spring Boot (Web MVC, Spring Data JPA)
- Hibernate
- PostgreSQL
- Maven and Lombok
- Postman (API testing)

## Features
- Create, view, update and delete job postings
- Search job postings by keyword (matches the profile or description; the search is case-sensitive)
- Load sample data with one request

## API endpoints
| Method | URL | What it does |
|---|---|---|
| GET | /load | Loads 5 sample job posts |
| GET | /jobPosts | Returns all job posts |
| GET | /jobPost/{postId} | Returns one job post |
| GET | /jobPost/keyword/{keyword} | Searches job posts by keyword |
| POST | /jobPost | Adds a job post (JSON body) |
| PUT | /jobPost | Updates a job post (JSON body) |
| DELETE | /jobPost/{postId} | Deletes a job post |

Sample request body for POST and PUT:



```json
{
  "postId": 6,
  "postProfile": "Backend Developer",
  "postDesc": "Experience with Spring Boot and REST APIs",
  "reqExperience": 2,
  "postTechStack": ["Java", "Spring Boot", "SQL"]
}
```

## How to run
1. Install Java 17 or later and PostgreSQL.
2. Create a PostgreSQL database. The project expects one named `telusko1` on `localhost:5432`, user `postgres`. Change these in `src/main/resources/application.properties` if yours differ.
3. Set an environment variable `DB_PASSWORD` to your PostgreSQL password.
4. Run `SpringBootRestApplication` from IntelliJ.
5. In Postman, send `GET http://localhost:8080/load` once, then `GET http://localhost:8080/jobPosts`.