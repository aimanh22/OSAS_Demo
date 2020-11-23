# Online Sentiment Analysis System Demo

Sentiment analysis (also known as opinion mining or emotion AI) refers to natural language processing, text analysis, computational linguistics, and biometrics to systematically identify, extract, quantify, and study affective states and subjective information. Sentiment analysis is widely applied to the voice of the customer materials such as reviews and survey responses, online and social media, and healthcare materials for applications that range from marketing to customer service to clinical medicine. (Wikipedia)

## 1. Introduction

The on-line sentiment analysis system is a cloud based online microservice that takes text from users as an input, analyzes its emotions and reflects back the emotion to the user.  It also creates a text analyzer that contains all the text ever inputted to the system and shows the frequency of the positive, negative and neutral sentiments of all the texts inputted to the system.

Built on AWS cloud platform, this project demonstrates a brief but complete online sentiment analysis system structure. It provides two access methods - for both humans (website) and the program (command line). The project is also supported by AWS Lambda  which makes the system  serverless and scalable according to workload. Besides, use of Grafana and RDS provide a flexible and fast way to build a user-friendly data dashboard which can be used as a monitor of the system status. It can be used as a prototype for a machine learning online system in the future. 


## 2. The system architecture 

The whole system is based on the AWS cloud and uses Comprehend to judge the input corpus's sentiment.  It classifies corpus's sentiment into 3 classes: negative, neutral, and positive. People can access the system with two approaches: website for human access and REST API for program access. The static website is hosted on AWS S3 bucket, while the REST API is based on AWS Gateway. The website, too, relies on the REST API to find the input text's sentiment. Actually, the API Gateway is a unique interface of the system to receive the user's request. After receiving the request, the AWS Gateway relays the message to AWS Lambda for the next round of processes. AWS Lambda, which can run code for virtually any type of application or back-end service, is the system's core scheduler. It sends the client's request (the text) to AWS Comprehend, a natural language processing (NLP) service with machine learning, for sentiment analysis and then returns the result to clients through API Gateway.  Besides, the lambda stores the results in a relational database. In this demo, we use MySQL as the database to store the completed requests. By querying the database, we can visualize the requests with [Grafana](https://grafana.com/grafana/), which is hosted on an EC2 instance.   

![System Architectur](https://github.com/gamecicn/OSAS_Demo/blob/main/image/architecture.png)


## 3 Video

[Demo]
[PPT](https://www.youtube.com/watch?v=8BWzlhqQAg0&feature=youtu.be)

## 4 Presentation Document

[PPT is here](https://github.com/gamecicn/OSAS_Demo/blob/main/doc/Sentiment%20Analyzer.pptx)


## 5 Code

The src folder contains the code used for building the system. It contains code for the lamda fuunction and the website. 

Website Template Credits: https://templatemo.com/tm-525-the-town

## 5 Team Member 

aimanjawaid.haider@duke.edu, maobin.guo@duke.edu,  xinyi.pan@duke.edu, 


