# Overview :smiling_face_with_three_hearts:

This is a **backend system** built using the [RESTful API](https://www.redhat.com/en/topics/api/what-is-a-rest-api) that lets users submit and internal teams search user feedback emails and content data.

## Languages/Frameworks In Use
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
  - [MongoDB Compass](https://docs.mongodb.com/compass/current/?_ga=2.9969713.546031619.1643937027-838649943.1643937027) to customize data fields in the form of documents.
  - [Postman](https://www.postman.com/product/what-is-postman/) that sends POST requests.
  - But to automate the testing process, I have implemented the Spring Boot Test template.
    - After each test has completed, the test data is cleaned up so we don't pollute our test database.

# Getting Down to Business... :woman_technologist:
## Features
- The data dashboard that's developed in Java (SpringMVC) is consisted of a **controller**, two models (or POJO classes) named **data value object** and **data access object**.
  - The data dashboard controller enables us to populate the database when a user sends a [POST request]
  - When a user submits a [POST request](https://en.wikipedia.org/wiki/POST_(HTTP)#:~:text=In%20computing%2C%20POST%20is%20a,submitting%20a%20completed%20web%20form.) on the frontend, for example, create a new account on a shopping website, and the payload is transmitted in the request body (@RequestBody) and stored in the database.
  - The data access object is implemented as an interfce so that it can be implemented in other classes, and has two functions: save, which stores data into our database in the form of a key-value pair, and find by ID, which returns the corresponding ID from the database.
- **Dependency Injection / Inversion of Control**
  - DI/IoC is a design pattern that is used to achieve **loose coupling** and **decoupling**.
  - The objects will not control themselves and their dependencies. Instead, an external container will control the creation of all objects and the management of their dependencies, so the object only needs to declare its dependencies without knowing the details (loose coupling).
  - The Java object managedby the IoC container is called the Bean, which is a Java class annotated by @Component.
- Using [MongoDB](https://www.mongodb.com/atlas/database), a JSON-like document database with JSON-like query, as our primary database
  - Why MongoDB over SQL? 
    - Data in MongoDB has a **flexible schema** while MySQL has a fixed schema. This flexibility enables this project (and many more) to adapt quick to fast changing feature requirement.
    - High availability and easier/simpler [horizontal scaling](https://www.mongodb.com/basics/horizontal-vs-vertical-scaling)/[sharding](https://www.mongodb.com/features/database-sharding-explained) solutions.
    - We are not dealing with critical information (i.e., transactions, customer info, ect.) in this project, and we are only performing collection of search of data, so there's no need for [ACID](https://www.mongodb.com/basics/acid-transactions) or lock, which are operations that ensure the database inconsistent after a series of operations which are more mature in SQL.
- **Inverted Index**
  - Implemented to record the mapping from stop words/noise to index.
  - The underlying data structure is a B+ tree.
- **Full-text search**
  - The search engine analyzes every single word/token in every stored document.
- **Elasticsearch**, a full-text search engine
  - Character filters
    -  A character filter receives the original text as a stream of characters and can transform the stream by adding, removing, or changing characters.
  - Tokenizer
    - A tokenizer receives a stream of characters, breaks it up into individual tokens (usually a stream of tokens), and outputs a stream of tokens.
  - Token filters
    - A token filter receives a stream of tokens and may add, remove, or change tokens.
      - A stop token filter removes common words (stop words) like the from the token stream.
      - A synonym token filter introduces synonyms into the token stream.
  - [The Edge N-Gram Algorithm](https://www.elastic.co/guide/en/elasticsearch/reference/current/analysis-edgengram-tokenizer.html)
    - This algorithm enables the autocompletion in my search engine by attempting to complete a word from user input based on the first letter, then the first two letters, then the first three letters, etc.
    - >The edge_ngram tokenizer first breaks text down into words whenever it encounters one of a list of specified characters, then it emits N-grams of each word where the start of the N-gram is anchored to the beginning of the word.
- The Relevance Algorithm: **Term Frequency/Inverse Document Frequency**
  - **Term frequency** is measured by how often a word appears in the field. Typically speaking, the more often, the *more* relevant.
  - **Inverse document frequency** is measured by how often a term appears in the index. Terms that appear in many documents have a *lower weight* than more-uncommon words. Therefore, the more often, the *less* relevant.
  - **Field-length norm** deals with the length of the field. The longer the field, the less likely the words in the field will be relevant. A term that appears in a short title field carries more weight than a term appearing in the long content field.

# Guides and Tutorials that I Found Useful :goggles:
- [Spring](https://spring.io/guides), and specifically [how to use Spring to build a RESTful web service](https://spring.io/guides/gs/rest-service/).
- [Ealstic](https://www.elastic.co/guide/index.html), great NLP search engine API's for fuzzy search and autocompletion.
