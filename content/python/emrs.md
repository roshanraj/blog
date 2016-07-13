+++
date = "2016-07-14T01:30:32+05:30"
title = "Superfast Rest API with flask"
header = "RR Blog"
slug = "flask-rest-starter"
tags = [ "python", "flask", "Rest api"]

categories = [
 
  "python",
  "flask",
  "rest api"
]

+++


# Using Flask for blazing fast Rest API development
### Directory structure


    .
    |
    ├── utils
    ├── handlers
    |   └──  todo.py
    ├── models
    |   └──  todo.py
    └── main.py

* main.py - holds route and flask application initialization.
* handlers - This directory holds handlers for different routes.
* models - holds different data models. 

### Quick Start 
* python main.py
* server will start on port 5000

# Two routes defined in the sample
### /todo 
##### metod (Post)
![Alt text](/images/post.png "Post")
##### metod (get)
![Alt text](/images/get.png "Get")

    
### /todo/<todo id>
##### metod (Get)
![Alt text](/images/withid.png "Get")
##### metod (Put)
![Alt text](/images/put.png "Put")


