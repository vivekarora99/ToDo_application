# ToDo_application 

OBJECTIVE-
Design and implement a todo application(Backend APIs Only).
1. The user should be able to create/read/update/delete todos. (CRUD)
2. The user should be able to search an existing todo by title/date/priority/state
3. The  user should be able to prioritize the todos

I used Java,Spring Boot for this problem.

a)Assumptions made:-
I assume that following softwares are installed :
   i)JDK 1.8 or later version
  ii)Postman 7.36.0
  iii)PostgreSQL 13.1
  
b)Approach to the solution: 
Since we were given a choice between nodejs or java and i did not have any expreince with nodejs.I thought better to create backnd api's in java using 
spring boot.So i followed tutorial from javabrains to create back-end API's.
So i created a class called Todo which will have attributes id,state,title,priority,data etc.Then i created a diffrent layers so that code is more readeable
and understandable. For Todo i have a controller,service and repository layer.Repository used CrudRepository from JPA to map tables to Class Todo.
Service layer contains the business logic.Controller has all the end points needed for Create,Read,Update and delete Todo in the system.

Following are the created methods :-

endpoint = "/todos" - Method = "GET" -- will give all the todos in the system
endpoint = "/todo/{id}" - Method = "GET" -- will todo with id specified
endpoint = "/todos" - Method = "POST" -- will save the todo passed in the request
endpoint = "/todo/{id}" - Method = "PUT" -- will update the todo passed in request and given the id
endPoint = "/todo/{id}" - Method = "DELETE" - will delete the id specified

Repository has id as String and Todo is saved.When controller calls GET method then we used findAll and findById methods of reposiroty to get the todos.
Also while adding new todo when POST is called or while updating as well save method of repository was used.Similary DELETE used deleteById to delete from 
repo.
 
c)DB schema
Todo:-
|id| |title| |data| |state| |priority|

d)Steps to run application : 

1. Go to todo folder  target/todo-0.0.1-SNAPSHOT.jar
2. run following command in cmd prompt 
	java -jar todo-0.0.1-SNAPSHOT.jar
3. Now after it is succussfull you can use post man to call GET,PUT,POST,DELETE request
