# Overview :smiling_face_with_three_hearts:

This is a **backend system** built using the [RESTful API](https://www.redhat.com/en/topics/api/what-is-a-rest-api) that lets users submit and internal teams search user feedback emails and content data.

## Languages / Frameworks that were implemented
- [x] Java
- [x] [Spring Boot](https://github.com/spring-projects)
- [x] Spring Data
- [x] MangoDB
- [x] [Elasticsearch](https://www.elastic.co/guide/en/elasticsearch/reference/current/elasticsearch-intro.html), a distributed, full-text search engine developed in Java!

## Why did I create this project?
- [x] I was able to increase the performance of email and content text seach by **#30%** by creating index in MongoDB and full-text indexing documents in Elasticsearch.
- [x] I refactored API request parameters with page numbers and page size. ~~Who doesn't wanna know how many more pages you have to read through until what you are looking for pops out?~~
- [x] I improved Elasticseach full-text search result relevance of user feedback data by analyzing feedback text fields with tokenization and token filters of lower case, stop words, stemming, and edge N-gram, sorted by [TF/IDF](https://monkeylearn.com/blog/what-is-tf-idf/) relevance.
    3. Improved Elasticsearch full-text search result relevance of user feedback data by analyzing feedback text fields with tokenization and token filters of lower case, stop word, stemming and edge N-gram, sorted by TF/IDF relevance
    4. Integrated Cabana tool with Elasticsearch for internal teams to explore and visualize
    5. Set up Swagger RESTful API Documentation to improve communication efficiency
    6. Implemented unit tests and achieved line coverage > 90% using Spring Boot Test
