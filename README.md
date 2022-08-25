
## MVC paradigm

MVC is a design pattern meant to break the code of an application into 3 main components: Model, View, and Controller. 

 It is **not** an engine, an npm package, a framework, or a language. It's just a way of organizing your code to make it easier to read, debug, scale, and work in teams. That's it. You could say it's just a useful folder structure for your code. 

If you break your code into different pieces and then put the puzzle together keeping in mind a specific and consistent order, the code will work the same way, and it will be written in the same way too. The only difference with the current way you write your code is how you organize it in different pieces.

### Model

The Model component is the code that deals with the database. Requests, updates and manipulates the data coming to and from our database. In our case, it's the code we use to manipulate MongoDB or Mongoose, but it applies to any kind of database.

### View

The View component is the code that deals with the UI of our application. We use EJS as our templating engine, but the final result is the HTML the user consumes. It's not limited to EJS though, we can use React, Handlebars and many other tools that render our visual interface.

### Controller

The Controller component includes every piece of code that interconnect the Model and the View components. It gets the request from the Router and hands it to the correspondent element and/or it gets the already processed information and takes it from the Model to the View.

## Understanding MVC

So we have the 100Devs building and we all live there.

Anytime someone has a question it goes like this:

1. They go to a board at the lobby and put up a request[^1] post the question (CLIENT[^2] and ROUTER[^3])
2. YOU see there's a question, read it and think "who can solve this specific issue?" (CONTROLLER [^4])
3. Once you've thought about the right person for the job, you hand the question to them
	- If it's info about a new content/tool to learn, you go to Leon for streaming (VIEWS [^5]) 
	- If it's a question about last class or content already taught by Leon, you go to the Stream Team -Shoutout to the Stream Team- (VIEWS [^6])
	- If it's a question about Discord/100Devs Community, you go to Blaw -Shoutout to Blaw- and then Blaw goes to the 100Devs knowledge DB (Discord Server),  and comes back with an answer (DATABASE[^7] MODEL[^8])
4. Whatever the answer is, you receive it again from the VIEWS engine or from the MODEL and get it to the Board (the CLIENT).

### Notes:

- Why a building?
	
	Because in a building everyone has their own office/apartment and work independently from each other towards a common goal (MODULES[^9]).
	
	Since our Agency is based on a fancy building (I mean, we do have members/MODULES working for FAANG, Nasa, etc.) it has an inner courier service, like a concierge kind of situation.
	
	Their job is to move packages from door to door. That means whenever the CONTROLLER wants to hand out a task, or a task is completed and a VIEW engine or the MODEL wants to give it back to the CONTROLLER, they just have to put the package at their own doorstep (out on the hallway)[^10] . Then the concierge takes the package to the appropriate CONTROLLER's doorstep and the CONTROLLER takes it in[^11] and so on and so forth.

## Databases

### I thought this was MVC, why databases?

Well MVC is, as we've already established, an "Organizational Architecture". It's one of many, but it's one of the most commonly used to structure the Backend of an application.

One of the most recurrent responsibilities of the Backend is the storage and manipulation of the clients' data. Databases are an integral part of a Backend and, in consequence, any organizational architecture striving for success and durability in the Backend world, has to gracefully deal with databases.

### Types of Databases

There are MANY types of databases, like MANY! (No, for real.) You can go ahead and check out [This video](https://youtu.be/W2Z7fbCLSTw) on the different types of databases there are. It's crazy.

However, there are two that are the most used in the industry. SQL and NO-SQL.

We've gotten to know MongoDB by now and it's pretty amazing. It's fast, it's scalable, it's got Mongo Atlas and, most importantly for us, it's pretty damn easy to use if you already know JavaScript. Besides, since this isn't a "learn to code" program, but a "get a job as SWE" program, it's more than appropriate.

That being said, as everything else, MongoDB has its issues. 

The fact that it doesn't need models or schemas (insert "What are those? gif") makes it very flexible... Like really flexible... Dangerously flexible... Ok, it can get pretty terrible. Enforcing required fields, type verification and all around consistency; although desired in a database, it's pretty hard to get with MongoDB alone.

Each type of database has its advantages and disadvantages, one of the advantages SQL databases have over NO-SQL is Object Modelling.

### Object Modeling

Imagine you could set your age in a database both as number or as a string (21 or "21"). The mechanism necessary to increment that age next year would be different for those who decided to use strings and those who decided to use numbers. Not so practical/scalable, isn't it?

Now imagine your password is a special date. If you pass it as a number instead of a string, someone could be able to increment that number and mess up your whole access to Netflix. Now you have to text your ex and admit you've been freeloading their Netflix account to watch The Sandman (or Betty La Fea if you're from Latin America, let's be real) and nobody wants that. 

(No, but fr, nobody wants that. Don't text your ex)

So in order to preserve your databases' integrity and scalability (and your dignity -or what's left of it anyways-) you need some sort of Modeling for your data, you need Schemas, you need to have your own Netflix account and move on. (Seriously, plenty of fish in the sea).

Object Modelling is one way to manipulate or *model* your data based on Object-Oriented Programming, and since you're a beast on OOP, this is the way to go. 

Once we can manipulate our data using OOP principles, the next tool that helps organizing a database are schemas.

### Schema

Schemas are basically templates for your data. Each entry's format can be controlled through schemas but we'll focus mainly on two aspects of each entry for now: Type (String, Number, Date, etc.) and Conditions (required field, for example).

Now that we know how useful it would be to model our data through schemas, don't you wish there was some tool that would help you control and manage the data you store in our database?...

Enter Mongoose.

### Mongoose

The Mongoose JS slogan is: "Elegant [mongodb](https://www.mongodb.com/) object modeling for [node.js](https://nodejs.org/en/)", and its self-description on their website is: "Mongoose provides a straight-forward, schema-based solution to model your application data."

That's why it's so useful, it takes charge of data-structuring business for us. 

Of course there are dozens of videos, tutorials and courses on Mongoose specifically, but this is not about that and our practical perspective will be using Leon's code as Legos. So don't worry too much about it for now. 

Let's go back to MVC.

## Code Examples of MVC

You can check [this video](https://youtu.be/pCvZtjoRq1I)

You can (and should) check [this 100Devs app](https://github.com/100devs/todo-mvc-auth-local). We will consider this app as a template for MVC. 

## MVC Strategies I Would Recommend

### To Understand It
-  Refactor old code
	1. Comment EVERY part of your code and clearly identify each section (Break your code into pieces)
	2. Ask yourself how many "pieces" of your code could be used as a module
	3. Identify each piece as it fitting the Model, View or Controller category
	4. Put the corresponding piece of code in another file (under the appropriate category folder)
	5. Export it using modules.export (for NodeJS)
	6. Import the piece into your original code and see the magic work
- Start new projects trying to keep MVC organization in mind
- Just be a baddie

### To Use It In Projects
1. Use the 100Devs template
2. Use the 100Devs template
3. Make peace with the fact that using templates is not a bad thing
4. Remember that all of those "real developers" out there use templates so using templates doesn't make you any less of a Software Engineer

___ 
[^1]: **Read** (get info/question). **Create** (post answer/info). **Update** (put answer/info). **Dee-lay-tay** (delete answer/info/mistake).
[^2]: The **person** with the question is the **Client**. They make the **request**.
[^3]: The **board** is the **Router**. It **"listens"** to the request first.
[^4]: **You** are the **Controller**. You **handle** the request the Router gave you and **choose** how to proceed.
[^5]: **Leon** is a **Views** engine. He doesn't need to access the DB because he's the GOAT and already knows the answer. He just **spits** out the facts, I mean, the **processed info**.
[^6]: The **Stream Team** are **Views** engines, They don't access the Database because they don't necessarily know the answer, but they'll **process** it via trial and error along with the client.
[^7]: Considering the **Discord Server** as our community's main way of answer a question, you could say it's our knowledge **Database**. 
[^8]: If **Blaw** is the one Super-Mod with the superpower to manipulate our DB's structure and information, you could say Blaw is the **Model**.
[^9]: Referring to the **module system** for organizing/breaking up our code in separate parts.
[^10]: They **Export** their task/functionality out of their apartment.
[^11]: The Controller **Requires** the task/functionality and the Concierge brings it into their apartment.
