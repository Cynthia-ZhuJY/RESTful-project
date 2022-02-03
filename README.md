# Overview :smiling_face_with_three_hearts:

This is a backend system built using the [RESTful API] (https://www.redhat.com/en/topics/api/what-is-a-rest-api) that lets users submit and internal teams search user feedback.
    1. Developed the RESTful backend system to let users submit and let internal teams to search user feedback emails and content data using Java, Spring Boot, Spring Data, MongoDB and Elasticsearch
    2. Increased email and content text search API’s performance by 30% by creating index in MongoDB and full-text indexing documents in Elasticsearch, also refactoring API request parameters with page number and page size
    3. Improved Elasticsearch full-text search result relevance of user feedback data by analyzing feedback text fields with tokenization and token filters of lower case, stop word, stemming and edge N-gram, sorted by TF/IDF relevance
    4. Integrated Cabana tool with Elasticsearch for internal teams to explore and visualize
    5. Set up Swagger RESTful API Documentation to improve communication efficiency
    6. Implemented unit tests and achieved line coverage > 90% using Spring Boot Test
