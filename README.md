# Overview :smiling_face_with_three_hearts:

This is a **backend system** built using the [RESTful API](https://www.redhat.com/en/topics/api/what-is-a-rest-api) that lets users submit and internal teams search user feedback emails and content data.

## Languages / Frameworks that were implemented
- [x] Java
- [x] [Spring Boot](https://github.com/spring-projects)
- [x] Spring Data
- [x] MangoDB
- [x] [Elasticsearch](https://www.elastic.co/guide/en/elasticsearch/reference/current/elasticsearch-intro.html), a distributed, full-text search engine developed in Java!

## Why is this project kinda a big deal (personally)?
- [x] I was able to increase the performance of email and content text seach by **30%** by creating index in MongoDB and full-text indexing documents in Elasticsearch.
- [x] I refactored API request parameters with page numbers and page size. ~~Who doesn't wanna know how many more pages you have to read through until what you are looking for pops out?~~
- [x] I improved Elasticseach full-text search result relevance of user feedback data by analyzing feedback text fields with **tokenization** and **token filters** of lower case, stop words, stemming, and edge N-gram, sorted by **[TF/IDF](https://monkeylearn.com/blog/what-is-tf-idf/) relevance**.
- [x] I integrated **[Kibana](https://www.elastic.co/kibana/)** with Elasticsearch for internal teams to explore and visualize. ~~Because we all love beautiful graphs!~~
- [x] I wrote Swagger RESTful API documentation to improve  communication efficiency. 
- [x] To complete this project, I implemented unit tests and the line coverage was able to achieve **> 90%** using **Spring Boot Test**.
  - [MongoDB Compass](https://docs.mongodb.com/compass/current/?_ga=2.9969713.546031619.1643937027-838649943.1643937027) to customize data fields
  - [Postman](https://www.postman.com/product/what-is-postman/) that sends POST requests

# Getting Down to Business...:woman_technologist:
## Features
- The data dashboard that's developed in Java (SpringMVC) is consisted of a **controller**, two models (or POJO classes) named **data value object** and **data access object**.
  - The data dashboard controller enables us to populate the database when a user sends a [POST request](https://en.wikipedia.org/wiki/POST_(HTTP)#:~:text=In%20computing%2C%20POST%20is%20a,submitting%20a%20completed%20web%20form.) on the frontend, for example, create a new account on a shopping website, and the payload is transmitted in the request body (@RequestBody) and stored in the database.
  - The data access object is implemented as an interfce so that it can be implemented in other classes, and has two functions: save, which stores data into our database in the form of a key-value pair, and find by ID, which returns the corresponding ID from the database.
- **Dependency Injection / Inversion of Control**
  - DI/IoC is a design pattern that is used to achieve **loose coupling** and **decoupling**.
  - The objects will not control themselves and their dependencies. Instead, an external container will control the creation of all objects and the management of their dependencies, so the object only needs to declare its dependencies without knowing the details (loose coupling).
  - The Java object managedby the IoC container is called the Bean, which is a Java class annotated by @Component.

# Guides and Tutorials that I Found Useful
- [Spring](https://spring.io/guides), and specifically [how to use Spring to build a RESTful web service](https://spring.io/guides/gs/rest-service/).
