---
title: Quick walkthrough of creating an API with Spring Boot.
---
Prerequisite: Make sure you have Java 11 and maven installed.

Head over to _start.spring.io_ and create a starter project. Add these three dependency from the Add Dependency tab on right pane.

**JPA** : JAVA Persistence API
**H2** : In memory relational database.
**Spring Web** : Uses Apache Tomcat as default embedded container.

Click on Generate at the bottom to download the zipped folder. Extract it and open it in IntelliJ or any other favourite editor of your choice.

Your pom.xml with dependencies should look like below.

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/49iof8y308haovzmkwav.png)

Just three dependencies that we added from the website. Simple and clean.

At this point we can run the service and it'll start the tomcat but it won't be very useful to us since we haven't defined any endpoints.

So let’s jump into the action and start creating classes. I'll start from bottom-up i.e. creating classes that are closer to the database and then move up to utilize those classes.

**1. Model layer**

The first thing I like to think about is the object that I want to store in the database. In this post I am using **Video** object. A video can contain a title and a description.

Let's create a class named Video.java.

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/d0i0u5u5g7g2p8ehvv1d.png)

Here is the quick summary of the annotations used in the class.

_@Id_ : Annotation tells that the field is a primary key.
_@GeneratedValue_ : JPA will take care of auto generating this value for us. We don't need to manually send it with the object.
_@Entity_ : Represents that the POJO can be persisted in the database.


**2. Repository layer**

Remember JPA that we added while generating the project. It exposes many methods that can be utilized to interact with the database. Methods like save(), findAll(), delete for regular CRUD operations.

No more hassle of constructing JDBC queries.👍

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/047a0a26c1h2qqkx935j.png)

@Repository : Helps Spring Boot to scan the repository layer.

**3. Controller/ Resource layer**

Layer that expose object from data to the outside world and brings days from outside world.

In other words, it is where we define GET, POST and other REST mappings to create API endpoints.

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ctycpukv7vzhny452pih.png)

@RestController : Signifies that the class is a controller class and contains REST endpoints. 


That's it. 🎉🎉

Now you are ready to run the service. Look for the class ending with Application in your project. It should contain main method. 

You can simply run the main method that will scan all the components based on the annotations that we have supplied and bootup the service.

If everything went well, you should be able to see tomcat running at port 8080. Fireup postman and go to http://localhost:8080 and GET, POST a Video object.

This is a very basic and simple implementation of creating an API with Spring Boot. There are many features of SB that comes out of the box which I will write about in the next few posts.

If you like to walk through video tutorial rather I have a Spring Boot playlist on YouTube 👉 [Spring Boot Tutorial Series](https://www.youtube.com/channel/UC7Ze67ISJCgtHZBXCYcBLIg)

I post daily about programming. You can find me 👇

[Youtube](https://studio.youtube.com/channel/UC7Ze67ISJCgtHZBXCYcBLIg) | [Twitter](https://twitter.com/S_AWDESH) | [Instagram](https://www.instagram.com/awdeshcodes/)

Let’s learn together 💪💪

Happy Coding 💻