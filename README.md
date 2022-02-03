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

# Getting Down to Business...:woman_technologist:
## Features
- The data dashboard that's developed in Java (SpringMVC) is consisted of a **controller**, two models (or POJO classes) named **data value object** and **data access object**.
  - The data dashboard controller enables us to populate the database when a user sends a [POST request](https://en.wikipedia.org/wiki/POST_(HTTP)#:~:text=In%20computing%2C%20POST%20is%20a,submitting%20a%20completed%20web%20form.) on the frontend, for example, create a new account on a shopping website, and the payload is transmitted in the request body (@RequestBody) and stored in the database.
  - The data access object is implemented as an interfce so that it can be implemented in other classes, and has two functions: save, which stores data into our database in the form of a key-value pair, and find by ID, which returns the corresponding ID from the database.
