# Simple Library App 


**<br/>Integrate from my previous [Java Springboot app](https://github.com/eggOnion/library_BookLoaningSystem/blob/main/README.md)** 
_<br/>Now running on Docker 🙌_


## What this app does?

An library book loaning system app to showcase Java on Springboot with Postgres to demostrate the RDBMS (Relational Database Management System). 

***

## What is Docker?

It is a software platform that allows you to build, test & deploy your application easily. When Docker runs, it packed your app into units called containers. It then pull informations from your `Dockerfile` and `docker-compose.yml` file to include the libraries, system tools & database so that your application can run on Docker.

The best of all is that **NO INSTALLATION** and **NO SETUPS** of other software is needed. All you need is to install `Docker Desktop` and sign-in.

**Here's the link [download Docker Desktop](https://www.docker.com/products/docker-desktop/)**

***

## How to run

Ensure that you already have a Docker Desktop installed on your system.

1. Clone this project.
2. Run `docker compose up` on you WSL terminal.
```
docker compose up
```
3. It takes around 5-8mins to build the app. Depending on your speed.
4. That's all. It's done!
<br/>

![dockercomposeup](https://github.com/eggOnion/SimpleLibrary_onDocker/blob/main/imageSource/DockerComposeUp.png?raw=true)


<br/>If any codes/contents were modified, then use the --build flag:
```
docker compose up --build
```

***

## How to use the app

### Ensure that `docker compose up` runs successfully.


**<br/>1. Access the endpoint using `thunder-client` or `Postman`.**
```
http://localhost:8080/learners
```
```
http://localhost:8080/books
```

---

**2. Perform Authentication**
<br/>

![Authentication](https://github.com/eggOnion/SimpleLibrary_onDocker/blob/main/imageSource/authentication.png?raw=true)
<br/>

**Username: user**
**<br/>Password: password**

---

**3. Once authenticated, you should see the contents in both the endpoints.**
<br/>

![View_Learners&Books](https://github.com/eggOnion/SimpleLibrary_onDocker/blob/main/imageSource/viewLearners_Books.png?raw=true)

**!! Pls note that your `id value` might varies from mine. Not to worry.**

---

**4. CREATE a new Learner & Book**

**<br/>Run the JSON code below. You should see the `201` return code if successful.**

![CREATE_Learners](https://github.com/eggOnion/SimpleLibrary_onDocker/blob/main/imageSource/addLearner.png?raw=true)

`Select POST and enter the URL:`
```
http://localhost:8080/learners
```
```
{
    "firstName": "Helen",
    "lastName": "Wick",
    "email": "helenwick@continental.com",
    "contact_num": "99123456",
    "loanPeriod": []
}
```
<br/>

![CREATE_Books](https://github.com/eggOnion/SimpleLibrary_onDocker/blob/main/imageSource/addBook.png?raw=true)
<br/>
`Select POST and enter the URL:`
```
http://localhost:8080/books
```
```
{
    "title": "Rich Dad Poor Dad",
    "author": "Robert Kiyosaki",
    "genre": "Personal Finance",
    "quantity": 4,
    "availability": true,
    "loanPeriod": []
}
```

---

### Check out the results!

![View_addedLearners](https://github.com/eggOnion/SimpleLibrary_onDocker/blob/main/imageSource/viewAddedLearner.png?raw=true)
<br/>

![View_addedBooks](https://github.com/eggOnion/SimpleLibrary_onDocker/blob/main/imageSource/viewAddedBook.png?raw=true)

---

**5. UPDATE a Learner & Book**

**<br/>Now that we learnt how to `CREATE`. It's time for `UPDATE.`**
**<br/>Run the JSON code below. You should see the `200` return code if successful.**

![updateLearner](https://github.com/eggOnion/SimpleLibrary_onDocker/blob/main/imageSource/updateLearner.png?raw=true)

`Select PUT and enter the URL:`
```
http://localhost:8080/learners/37
```
```
{
    "firstName": "Bowery",
    "lastName": "King",
    "email": "boweryking@continental.com",
    "contact_num": "99912345",
    "loanPeriod": []
}
```
<br/>

![updateBooks](https://github.com/eggOnion/SimpleLibrary_onDocker/blob/main/imageSource/updateBookpng.png?raw=true)

`Select PUT and enter the URL:`
```
http://localhost:8080/books/37
```
```
{
    "title": "The Return of the King",
    "author": "J. R. R. Tolkien",
    "genre": "Fantasy",
    "quantity": 3,
    "availability": true,
    "loanPeriod": []
}
```

---

**6. DELETE a Learner & Book**

**<br/>No need to input JSON content when deleting.**
**<br/>You should see the `204` return code if successful.**

![deleteLearner](https://github.com/eggOnion/SimpleLibrary_onDocker/blob/main/imageSource/deleteLearner.png?raw=true)
<br/>
`Select DELETE and enter the URL:`
```
http://localhost:8080/learners/37
```
<br/>

![deleteBooks](https://github.com/eggOnion/SimpleLibrary_onDocker/blob/main/imageSource/deleteBook.png?raw=true)
<br/>
`Select DELETE and enter the URL:`
```
http://localhost:8080/books/37
```

***

## References

[Docker](https://aws.amazon.com/docker/#:~:text=Docker%20is%20a%20software%20platform,tools%2C%20code%2C%20and%20runtime.)