## Emils #100DaysOfCode

Här skriver jag om min framgångar och motgångar i att lära mig webbutveckling. Jag följer en kurs som heter The Complete Web Developer in 2019: Zero to Mastery från Udemy. Idén är att jag ska klara av att programmera 100 dagar i sträck. Vi får se hur det går.

Here, I write of my successes and struggles in learning web development. I'm taking a course called The Complete Web Developer in 2019: Zero to Mastery from Udemy. The idea is that I'm going to code for 100 days in a row. We'll see how it goes. The first 39 days of the journal is in Swedish.

---

---

#### Day 83: 4:00 // pretty-dashboard continued

Did a lot of work on the pretty-dashboard app today!

I wanted a way for the user to set their own position and name, so I added a little settings button with a dropdown menu. That was definitely easier said than done, and it took quite some time of researching bootstrap docs to get it like I wanted. It was fun to add the functions, because it made the project less static.

I encountered a problem when adding the "Update" button, which took the user entries, and sent them to a function to get new weather data. The problem was that I had to click twice in order for it to update. It seemed that the problem was when using setState and directly afterwards trying to update the weather data (which relied one the updated state) the state hadn't had time to update.

```js
onSubmitUpdate = (lat, long, name) => {
    if (lat && long) {
      this.setState({ lat: lat, long: long });
      this.updateWeatherData();
      ...
```

updateWeatherData used `this.state.lat` and `this.state.long` to get the weather, but as I mentioned, didn't get the latest state. I fixed it by sending lat and long directly to the updateWeatherData-function and removing them as state altogether.

I also played with the design a bit, and made the center text responsive, which was fun

---

#### Day 82: 1:00 // navbar

Started on the navbar today. Using React Bootstrap for pretty components. Struggled for a while to get it to work though, until I realized I hadn't included the CSS for the Bootstrap. Duh...

---

#### Day 81: 1:00 // isinfo

Home from Africa! I had a great trip, but as mentioned earlier, I didn't bring a laptop so I've been learning Python with the help of an app the last couple of days. Since I didn't really have internet, I wrote the journal posts in my phone, and I'm uploading them now.

Feels crazy that it's less than three weeks to go of the 100 day challenge. I'm super excited to take something big on and eventually work together with a team.

Today, I started reviving an old web app I thought of years ago - isinfo (ice info). It's basically a forum where users who ice skate can post reports about ice conditions at lakes, so you can get information and inspiration about where to go. I'm gonna build it in React, and I'm still in the planning phase - what I'm wondering about is whether I should use some sort of boilerplate layout or build everything from scratch. I'm leaning towards scratch.

The basic functionalities I'm thinking the website should have is a navigation bar, a way of signing in and out, a way to post new report and to search/browse reports.

---

#### Day 80: 1:00 // functional programming

Today, I studied functional programming. I've done it in Scheme earlier but it was good with some repetition. The idea behind functional programming is the use of functions and importantly, higher order functions that except functions as arguments. We usually strive to create pure functions, that have no side effects and always return the same output given the same input.

A lambda function is an anonymous function, especially useful in higher order functions.

---

#### Day 79: 1:00 // lists, tuples, dictionaries

SoloLearn continued. Today I learned about lists, tuples and dictionaries. Dictionaries use key-value pairs, like "name": "Emil", while lists are just what they sounds like, lists. Lists can be change, so they are mutable. Tuples are similar to lists, except faster, and the difference is that they are immutable.

---

#### Day 78: 1:00 // exceptions, read/write files

SoloLearn python course continued. Today I learned about exceptions and files. Exceptions are what happen when something goes wrong in the code. You do a try - except block, which is the equivalent of try - catch in JavaScript.

One thing that was interesting was the assert function - you basically assert that something is true, and if it's not, it raises an error. Great for checking for example input types in the beginning of a function, or the output at the end. I don't know if JavaScript has it?

You can read, write and spend to files in python as well - nothing too fancy. Don't forget to close the file after you're done.

---

#### Day 77: 0:40 // functions and modules

I kept on learning in the SoloLearn app today, with python. It strikes me how much python looks like pseudoprogramming: things just look exactly like you expect them to, and it is an intuitive syntax. Today, the focus was on functions and modules - you can import standard libraries that come with python, and you can also install third party ones.

---

#### Day 76: 1:00 // Marrakech + github troubles

Today, I flew to Morocco for vacation. I didn't bring my laptop, so I knew coding was gonna be a bit of an issue.

I've started learning python through an app called SoloLearn. The content is surprisingly good and it's a great replacement for something like looking at Facebook. Today, I leaned about how control structures, like if, while and for work in python.

I can't do commits to the github repo from the phone, so I'm doing local journal entries for now.

edit: turns out I can actually do commits.

---

#### Day 75/100: 1:00 // Unsplash API success!

So, I succeeded in doing what I was thinking of yesterday - I got the "Generate New Background"-button to work, by changing from getting a random wallpaper image from URL to getting it as an API call. I created a function called `onGenerateBackground` which made the fetch and was used both in the componentDidMount as well as the generate background-button.

I got a little too excited though, and used up my hourly rate of API calls. Oops.

(25 days to go. Woop woop!)

 ![Day 75](./screenshots/75.png?raw=true)

---

#### Day 74/100: 2:00 // Documentation + generate new background

I recently realized I haven't done much documentation so far. I looked over my github repo and it was quite poorly commented, so I added descriptions to all projects, and I aim to add more comments in my code as well.

I continued working on the pretty-dashboard app (renamed from pretty-new-tab) and I attempted adding the google calendar API, thinking it wouldn't be too hard. Turns out it was. There's a lot of bureaucracy in getting permission to use the calendar API, such as having a valid website address (localhost didn't cut it) so I kinda abandoned that idea. Then I wanted to add a "Generate new background"-button to the app, but encountered a problem. Since I access the random photo with a url, `https://source.unsplash.com/1600x900/?wallpaper`, it's a new one every time I refresh, but there's no real way to get it to re-render unfortunately - because the core url doesn't change, only what you get redirected to.

So I still think I can do it, but I'll have to use the Unsplash API instead, as I intented from start.

---

#### Day 73/100: 1:30 // Unsplash API + problems

I succeeded in displaying a random wallpaper image each time pretty-new-tab is rendered, which was very cool. I tried researching how to have the API key local so I don't push it to github, but I didn't quite figure it out.

However, I ran into a problem: I just assumed that chrome supported custom URLs when pressing new tab, but it turns out it doesn't... Which kinda sucks. So I had to download an addon for chrome that lets me do that. Not optimal, though. I'm pretty pleased with the loading time though! It's like two seconds or so.

Also, I added the weather symbol:

 ![Day 73](./screenshots/73.png?raw=true)

---

#### Day 72/100: 2:00 // weather API

Man, today was a lot of fun!!

I continued on the pretty-new-tab app, and I started really playing around with the weather API. You can get a ton of interesting data from it, like temperature, wind speed, type of precipitation and even weather symbol! So I did a switch case to display precipitation category (rain, snow, drizzle etc...) along with displaying temp and wind speed. I'm thinking of putting together a bunch of weather symbols to display and use that data as well. Would be really cool. I also did some more positioning and it went surprisingly well, just using flex box.

I think the next part will be to randomize background image with the Unsplash API...

Here's a preview:

![Day 72](./screenshots/72.png?raw=true)

---

#### Day 71/100: 3:00 // pretty-new-tab

Today, I walked into the wild. Or rather stumbled, maybe. I decided to start building a little useful app for myself, called pretty-new-tab. The idea is that it shows up whenever I open a new tab in the browser, and displays current time, a nice little message, my calendar events and the weather. Like a dashboard.

I use React to build it. I researched getting the weather from the SMHI API, and I actually got it to work! Which was really cool. I struggled for longer than I'd like to admit with getting a background image in place. There, I plan on using the Unsplash API (a website with a bunch of free, cool photos) to generate a random wallpaper. Lastly, I plan on integrating Google Calendar with their API, which will be interesting.

---

#### Day 70/100: 2:00 // Beginning of end/end of beginning?

Today marks day 70 on the 100 day calendar, and 100% on the Udemy Web Development course. It feels great to have gone through the whole thing, and I'm proud I've gotten this far. Thirty days to go on the challenge, which I think will be a breeze.

I've gone from knowing the very basics of HTML, CSS and JavaScript, to feel pretty confident in all of them, in addition to learning the frameworks and libraries of React, Node, NPM, Express, Redux and PostgreSQL. The learning process has been so much more than just learning how to build a website, because it's all of these things surrounding it - like learning Git, understanding how to think like a web developer, knowing where to find good information, how to read documentation, and just getting an understanding of the web development world.

It feels like I've just scratched the surface, and there's much more to learn. This course has introduced a lot of concepts of modern web development and I'm glad I've gotten to try these things out, but I think it's now that the real learning begins. Following along a course feels safe and easy, and I think that what awaits me now are all those hours of debugging, making errors, figuring out how to solve problems that arise, and just building an intuition and getting things into muscle memory.

I'm super excited to spend the rest of these 30 days on the challenge (and beyond) with building bigger projects of my own, and to further develop my skills.

![Day 70](https://udemy-certificate.s3.amazonaws.com/image/UC-378VSL9W.jpg)

---

#### Day 69/100: 1:00 // robofriends Redux

Short post today - I more or less finished the robofriends with Redux implemented. I added an asynchronous API request of the robots which was a little tricky when using Redux. I used middleware called thunk, which basically listened for asynchronous calls from actions, and then handled them accordingly. It wasn't very easy to understand. I'll review the code tomorrow and make sure I understood everything.

I have two more videos before finishing the web dev course :)

Here's the app: https://github.com/emilerik/robofriends-redux

---

#### Day 68/100: 2:00 // Redux cont.

For practicing Redux, I went back to the robofriends app, I'm about to implement Redux for state management instead of vanilla React. I started by creating an action (which is an object), setSearchField, which takes text as argument and has the attributes type and payload, like so:

```js
export const setSearchField = text => ({
  type: "CHANGE_SEARCH_FIELD",
  payload: text
});
```

After that, I created the reducer searchRobots, which takes a state and an action as arguments. This is the pure function that handles the actions taken by the user. A snippet of code:

```js
export const searchRobots = (state = initialState, action = {}) => {
  switch (action.type) {
    case CHANGE_SEARCH_FIELD:
      return Object.assign({}, state, { searchField: action.payload });
    default:
      return state;
  }
};
```

After that, I created the store, which has the "rootReducer", basically all the reducers mashed into one.

The components that are called containers are the smart components, that subscribe to any changes made in Redux, in order to update the props (in this case, the App component).

By the way, I just applied for a hackathon in Stockholm on April 27th - which is like a week after I finish the 100 days. That'd be cool!

---

#### Day 67/100: 1:30 // Redux!

I got started with Redux today! The problem that Redux attempts to solve is this: when you're building an app, especially if it's big, all these components and their children and their children's children have states, and when a state is updated, things kinda trickle up and down, and it can get messy.

Redux is a library which does state management, by taking state out of components and putting them in the same place - and letting components just handle props. (Although you can still use state in React with Redux) Its benefits can be summarized as:

- Good for large apps with a lot of states
- Useful when sharing data between containers
- State management is predictable, through these principles: 1. Single source of truth 2. State is read only 3. Changes are made with pure functions

Before, using something like jQuery, you had action -> make changes. Everything a user did when interacting with a website triggered a change, which might trigger another change and so on. With Redux, you have action -> reducer -> store -> make changes. From what I understand, the reducer is something like a pure function that reacts to an action, then updates the store, which contains all the information of how the website should look. Then, React looks at this and renders the View. Something like that.

---

#### Day 66/100: 1:30 // ..aaaand we're live!

Deployed the front end on Heroku today as well! So now we have the full app living in the cloud.

There are still lots of things that can be improved upon and expanded, but I'm still proud of it - it's a React app built from scratch with (some) design, a cool API function, a server, a database, and proper password validation.

I'm thinking the next step is to keep fixing some unwanted features, improve the design and make it look better in mobile devices. It definitely some sort of error message when user input in incorrect. One thing I also noticed is that it's slow when using it online - I guess that's the price of free hosting.

By the way, I actually reached the end of the Udemy course. The only thing I have left is a part of Redux, which I waited with - after that I'm 100% finished.

Lo and behold: http://fare-facial-recognition.herokuapp.com/

---

#### Day 65/100: 2:00 // Deployed! (or halfway...)

I deployed the fare app on Heroku today!

I spent some time adjusting all the end points and URLs to be compatible with Heroku, and got a bunch of bugs along the way. I was able to fix them though, and then went through the installation process, which was (surprisingly) smooth. So far, I've deployed the server and database, but not the front end though. Will probably do it through github.

It was very cool when I was able to register and sign in a user, knowing that half of the app was hosted on some computer, somewhere in the world! Still have some bugs that I have to deal with, like the fact that it doesn't increment entry count.

---

#### Day 64/100: 1:00 // security review

Today I did a security review of the facial recognition app.

The idea is that you want layers of security - you don't want to accept incorrect user input at the front end, but if it does get through, you want to make sure the back end handles it safely as well. So I added a few controls at the server, like checking that any input wasn't empty.

Another problem was that the API key for the facial recognition was sent in the header of the request, which is bad news. It means that the user can access my API key. So instead, the authorization was moved to the back end, and the API request was sent from the server. Got some weird bug which fixed itself.

---

#### Day 63/100: 2:00 // cleaning up

I still have a couple of bugs and improvements that I'm trying to fix on the app.

Today's concept: **dependency injection.** Example: when you're splitting a big file into smaller separate ones with clear, defined functions, you might run into the problem that a sub file needs dependencies from the main file. Like, register.js need the variable db from server.js. You can then do dependency injection, which means you attach any dependencies in the function call, like so (in the main file, server.js):

```js
app.post("/register", (req, res) => {
  register.handleRegister(req, res, db, bcrypt);
});
```

Fixed a bug where you could register without entering any information. The bug was that, after receiving a response with 'user' from the server, I used `if (user) { ...` to reroute after clicking submit. However, if you entered no input, the server responded with "unable to register", which, of course, evaluates to true as a boolean. I fixed it by changing it to `if (user.id) { ...` which will return undefined unless it's an object, and undefined evaluates to false. Yay!

---

#### Day 62/100: 1:30 // connecting the pieces

I got use of bcrypt today for the first time, to hash the user passwords when they register. Testing the hash against the password when the user attempts to sign in worked great.

I kept building on the server and validation today, and I more or less have all the parts working together now. The user can register on the website, then log in, then it keeps track of the number of entries the user has made.

I still have some weird bugs lingering, so the next step is to review the code and figure those things out.

---

#### Day 61/100: 2:00 // integrating db in fare

Today, I finally connected the database, server and front-end on the FaRe app. I can now register a user with post requests to the website, which gets stored in the database, and the sign in feature checks against the database when user enters credentials.

The next step is tidying up the code, adding some features, and lastly deployment!

---

#### Day 60/100: 1:30 // finishing db

Two months in! :D And 85% through the course. I'm excited to finish it up, and start building my own, bigger projects.

Today I finished up the section about databases. Learned about using SQL functions like AVG and SCORE, then about joining tables, and lastly about deleting parts from tables and dropping (removing) a table. After that, I got stuck watch a [computerphile video](https://www.youtube.com/watch?v=ciNHn38EyRc) about SQL injection attacks, which was super interesting.

This weekend, I'm definitely gonna finish up the fare app.

---

#### Day 59/100: 1:00 // DB, continued

Some more hands-on work with databases today, practicing basic SQL commands.

- CREATE TABLE (column1 datatype, column2 datatype,...) // creates a table
- INSERT INTO table (column1, ...) VALUES (value1, ...) // adds entries to the table
- SELECT column1, ... FROM table // displays values from table
- ALTER TABLE table ADD column datatype // adds a column to a table

You can also use the LIKE keyword to select matching strings, for example LIKE 'E%', which selects anything that starts with an E.

The power of databases is that they are built for exactly the purpose of getting, storing, and updating data. Compared to storing user information in something like an array in js, which you'd have to loop through to get some data, databases are far more efficient and optimized for those type of jobs.

---

#### Day 58/100: 1:00 // intro DB

Short day - learned of the introductory stuff about databases. Two main types: SQL and NoSQL, where SQL databases are relational databases - they consist of different tables that contain data related to each other and can point to other data via keys. Example: one table with users and one table with the users' tweets. Nonrelational databases (like MongoDB) are simpler - they create self containing "documents", which are more complete descriptions of an object. Example - a user entry in the database, which contains the user's email, tweets, and about-info. The concept - when you have a clear idea of how to structure your data, use relational, and when it is more unclear, use nonrelational.

I will learn the relational database PostgreSQL to start with, and use PSequel as a GUI for playing around with it.

---

#### Day 57/100: 2:00 // connecting the ends

I finally got to integrating the front end with the back end. Now, you can register a user to the server (which gets stored in the "database"), and sign in only if you're a registered user. Also added the feature of when you use the face recognition feature, your entry count goes up!

One of the last parts is actually creating a database (and to make it all look better and work better). Other than that, I'm pretty excited about the progress!

![dag57](./screenshots/57.png?raw=true "dag57")

---

#### Day 56/100: 2:00 // FaRe, :id, image, bcrypt

Added two routes: /:id and /image. id is used for accessing a users info, given their user id, and image is used whenever an image is submitted. This increments the user's "entries"-counts. I'm just testing to see if these worked - later I'll integrate them with the front end functionalities.

bcrypt is a node package which can be used to encrypt user data, like passwords. The way it works is that it creates a hash from the password when the user registers, which it then can use to compare a login attempt from the user. You use it so that this sort of data isn't stored in plain text in the database. I haven't gotten to the database yet, but at least I got some of the core functions down.

Also thinking of a way of pushing the app to github, without sending the API key with the source code. Currently leaning towards using local environment variables.

---

#### Day 55/100: 2:00 // continuing on face recognition app (FaRe)

I got back to the face recognition app, and started building some back end for it. So far, planned the routes for /signin and /register. The idea is that with post requests, you send user data either to be verified (in signin) or to be stored (in register). So far, it's a rather rudimentary solution, but I'll build it into something more sophisticated. I used Postman to test all these functions, and they worked :)

As a start, this only tested the first user. Later, I'll use a database:

```js
app.post("/signin", (req, res) => {
  if (
    req.body.email === database.users[0].email &&
    req.body.password === database.users[0].password
  ) {
    res.json("success");
  } else {
    res.status(400).json("error logging in");
  }
});
```

---

#### Day 54/100: 2:30 // fs, challenges, fixed bug

Continuing on filesystem. There is also a synchronous way of reading files, with .readFileSync. The difference is that .readFile is asynchronous and therefore has a callback function, while .readFileSync stops the program until it has read the file. Async way is the preferred way when building a server.

So far, we've got

```js
const fs = require("fs");

fs.readFile("./hello.txt", (err, data) => {
  if (err) {
    console.log("ERRR");
  }
  console.log("Async: " + data.toString()); //Hejsan!!
});

console.log("Sync: " + fs.readFileSync("./hello.txt").toString());

fs.writeFile("newFile.txt", "Wassup!", err => {
  if (err) {
    console.log(err);
  }
});

fs.appendFile("./hello.txt", ", some new words", err => {
  if (err) {
    console.log(err);
  }
});

fs.unlink("newFile.txt", err => {
  if (err) {
    console.log(err);
  }
  console.log("Deleting newFile.txt");
});
```

After that, I did an old 'Advent of Code'-challenge, where you get a long string with parentheses (like '(()))(...') and you had to find how many more there were of one or the other. The training was to read the string from a separate file, and then build a function to get the result. I did three versions:

- First I did an array solution with .reduce. I split the string with brackets.split('') to get individual array, and then used reduce with an accumulator on the array, adding to the accumulator when I got ( and subtracting when I got ). This was a fast solution, and is easy to follow. Time: 1.1 ms
- Then I did a string solution with .replace. I simply removed one type of the parentheses with `brackets.replace(/\(/g, '')` and then compared the length of this new string with the original one. I liked this because it was a really short solution. It was also the fastest one. Time: 0.5 ms
- Then I tried splitting them up so I only saved one type in an array, with brackets.split(')'), and then mapping over the whole array to accumulate the total length of '('-elements. Lastly, I compared with the length of the full string to get number of )s. Not a great solution - it iterates over a bunch of empty elements, and wasn't very fast. Time: 2.5 ms.

Lastly, I solved my bug in the face-recognition app! :D Can you spot it...?

```js
onButtonSubmit = () => {
  this.setState({ imageUrl: this.state.input });
  app.models
    .predict(Clarifai.FACE_DETECT_MOD6EL, this.state.input)
    .then(response => this.displayFaceBox(this.calculateFaceLocation(response)))
    .catch(err => console.log(err));
};
```

Yeah, spoilers... `FACE_DETECT_MOD6EL` Don't accidently add numbers to methods. Turns out it produces some weird bugs.

---

#### Day 53/100: 1:00 // RESTful API, intro

RESTful API is an architechtural style, which is used to make sure we have compatibility in transacations over the web. It can be seen as a set of rules, which makes sure everyone plays nicely. It uses GET (receive a resource) PUT (change the state or update a resource), POST (creates a resource), DELETE (remove it). Rest APIs are stateless, meaning that multiple calls can be made simultaneously, and each call is complete (so it doesn't rely on a previous state)

The app-object has a couple of attributes, such as

- **query** - followed by the ? in the url
- **body** - contains the body of a post request
- **header** - additional information included in the request
- **params** - the parameters following the / in the url, like facebook.com/user/emil

After that, I learned shortly about the fs-object. fs has a method, readFile, which takes a file and reads it (duh). Like so

```js
fs.readFile("./hello.txt", (err, data) => {
  if (err) {
    console.log("ERROR");
  }
  console.log(data.toString());
});
```

prints 'Hello there!' (which is the data of 'hello.txt')

---

#### Day 52/100: 2:10 // intro Express.js

Today, I got started on back-end! Created a server file, and then installed nodemon, which was used to watch file change and restart server. Started by doing the old fashioned way of `const http = require('http');` and then created a server that way, but then installed Express.js and started playing around. Learned about how to use the different methods like .use, .get, .post et cetera. Couldn't do much with .post though, so I installed bodyParser to be able to parse whatever the user posted.

To have a nice way of doing get, post, put and so on, I installed Postman, which is a desktop application used which can do all these things and present in a nice view. In short, a way of testing your serving before deploying it.

Excited to learn more about Express and back-end, and integrate it into the face-recognition app!

(By the way, I haven't solved that bug from yesterday yet...)

---

#### Day 51/100: 2:00 // sign in + node

Today, I worked some more on the signing in functionality. I kept track of the where the user was at on the page, with `this.state.route` and could use it the determine whether to render the "sign in"-form, the "register"-form or the "detect face"-view. So far, the user can sign in by just clicking the "Sign in"-button, because I haven't added the back-end yet. I think it's looking pretty good though!

Also got started on node - did some practicing writing code in a script.js-file and then running it with node in the terminal. Very cool!

For some reason, I got a weird bug when using the face detection function after implementing sign in, so now it's not working... Will have to look at it tomorrow.

```
TypeError: Cannot read property 'language' of undefined
```

![dag51](./screenshots/51.png?raw=true "dag51")

---

#### Day 50/100: 1:00 // Sign in, start

Short day - worked on the sign in functionality. Designed a sign in form with the help of tachyons, and then added a state named route, used to identify if the user is signed in or not. Got it to display the sign in form only if user was signed out.

By the way, halfway through!! :D

---

#### Day 49/100: 1:30 // face recognition working!

I got the face recognition to work! The process went like this: get the detected face position with help of the clarifai API, and save these parameters as the 'box'-object with attributes leftCol, topRow, rightCol, bottomRow. Send this object to the FaceRecognition component, which then renders the box with the help of CSS. Excited to implement some backend soon.

Tomorrow I reach halfway to 100. Arnold approves!

![dag49](./screenshots/49.png?raw=true "dag49")

---

#### Day 48/100: 2:00 // clarifai API

Today was pretty exciting! I continued on the face recognition app. I used free clarifai APIs to predict some parameters in images from a URL - color at first. I used the Clarifai color model on a URL which was entered by the user, and console logged the result. It returned an array with the result, which basically just predicted the three top colors of the picture and their probability. Worked great. At the end, I tried the face recognition model instead, which is what I'll be using later as well, and it returned boundaries for what it predicts is the face.

All that remains now is to implement a way of drawing a box around the predicted face(s) of the image.

---

#### Day 47/100: 2:30 // assembly, face recognition app

Did some more assembly coding today. Mostly debugging and testing, and trying to step through our interrupt program to figure out what adresses and register were placed on the stack and why.

Continued the face recognition app as well, this time building some more components. I more or less built all the components for the view, but it doesn't look great yet. I'll add an image.

![dag47](./screenshots/47.png?raw=true "dag47")

---

#### Day 46/100: 2:30 // assembly!

Today, I gave web dev a break, and hacked away at some good old fashioned assembly code! We're programming for a computer engineering course in a low level language, handling registers and storing data and instructions in memory manually. Today, we developed some subroutines used to handling interrupts - initially, we had a loop that printed a string, but then we added two (physical) CPIO buttons, which had higher priority, so the program exits the loop whenever one of those are clicked, to print another string. After clicking the buttons, we paused the program to look at the stack, and tried to analyze step by step what the program had put on the stack since the interrupts.

![dag46](./screenshots/46.png?raw=true "dag46")

---

#### Day 45/100: 1:20 // face recognition app

I started working on a big project in the course - the face recognition app. It's a website where you can log in, and then paste a URL with an image - it then finds faces on the image and marks them with rectangles. So far, I've basically just built some of the basic components, and a background. Tomorrow, I will hopefully finish the components so I can implement the face detection API.

---

#### Day 44/100: 1:30 // star wars foxes, continued

Today, I continued on the 'star wars foxes'-app. I think I came a long way. I managed to loop through several objects from the star wars API and render them in the Card component. Unfortunately, I didn't manage to match it with the random foxes API as I wanted - the error I got was

```js
Access to fetch at 'https://randomfox.ca/floof/' from origin 'chrome-extension://laookkfknpbbblfpciffpaejjkokdgca' has been blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource. If an opaque response serves your needs, set the request's mode to 'no-cors' to fetch the resource with CORS disabled.
```

I got it once before as well, and it seems to be complaining about the fact that it tries to fetch something that isn't on the same domain. Which is weird, because that's what I do with the swapi as well...

Anyway, I managed to solve by sort of ugly-hacking it, (I still thought it looks pretty good). Now, I give the source directly to the img-tag instead, so I don't use the API for getting the foxes. It was also the first time I used flexbox with React, with FlexView! It's a built in component in React, which you use to wrap whatever content you want to display with flex. In this case, it replaced the div. Here is the "ugly hack" with the url, and the FlexView!

```js
<FlexView wrap row>
  {" "}
  {characters.map((char, i) => {
    return (
      <Card
        key={i}
        name={char.name}
        height={char.height}
        hair_color={char.hair_color}
        img={"https://randomfox.ca/images/" + (i + 1) + ".jpg"}
      />
    );
  })}
</FlexView>
```

Here comes a pic of its current look. Not the prettiest, but to be fair, the focus here is on APIs.

![dag44](./screenshots/44.png?raw=true "dag44")

---

#### Day 43/100: 2:00 // APIs, star wars foxes

After the lessons in APIs, it was time for an exercise. The exercise was to build any one-page app using fetch and Star Wars API, http://swapi.co. I decided to make something similar to the robofriends app I built earlier. So the idea is to build an app in React with Card components, displaying each Star Wars character, and some information about them. I'll get the data from swapi. Also, I wanted some pictures with these cards, so I went with a random fox image generator API. We'll see how it turns out. I struggled for a while to figure out how to do the props and states right, but I finally got something to work.

![dag43](./screenshots/43.png?raw=true "dag43")
![dag43-2](./screenshots/43-2.png?raw=true "dag43-2")

---

#### Day 42/100: 2:00 // sidetracked: React Native

Today, I got sidetracked. I didn't follow the course curriculum, but instead stumbled upon the React Native tutorial at https://facebook.github.io/react-native/docs/tutorial. It's fascinating how powerful React seems to be, as the model of components can applied to building both web apps and smartphone apps. I always saw these as separate concerns, but it's natural that they shouldn't have to be. Another great thing is that it gave me another perspective in learning React, so my earlier knowledge really set in. I understand state and props much better now.

It was also nice to see that they used flexbox for handling layout. Earlier, I didn't quite understand how styling and layout played into React (does it have its own layout/styling system?), but as I now see it, you basically treat components the way you would HTML elements. What confused me in the beginning, I think, was tachyons, which I thought was the standard way of styling.

I heard that React and React Native have some differences, and to me, these seem minor. \<View> seems to be the equivalent of \<div>, for example. On top of regular React, a bunch of ways of handling smartphone interaction like pinching and swiping are added, but these things seem like additional components (no pun intended?) of the library rather than different concepts, in terms of React vs React Native. But then again, there's probably more under the hood and I might be wrong.

---

#### Day 41/100: 2:30 // intro backend, APIs

Role of the backend developer: to manage and develop the server-side of an application. Backend basically consists of the server and the database. The server communicates, and the database stores. Examples are: to handle user requests, to store and retrieve data, and deliver the HTML/CSS/JS-files to the user browser. A classic model is LAMP - Linux (OS), Apache (HTTP), MySQL (relational DB) and PHP (serverside code), but there are more modern models such as MEAN (MongoDB, ExpressJS, AngularJS, NodeJS) which is powered by JavaScript. Big applications, such as Facebook or Google use load balancers and multiple servers and databases to handle huge amounts of traffic.

API stands for Application Programming Interface. In short, APIs are a way for websites and applications to communicate and share information with eachother. Say I wanna buy sneakers, but I'm not sure which stores sell sneakers. So I go to Pricerunner. They don't have any sneakers, but they know lots of stores and companies who do. So when I search for size 44 Converse, Pricerunner interacts with these stores' APIs to fetch my request of this particular footwear. Maybe I find my pair, maybe I'm redirected to converse.com and maybe Pricerunner gets a little profit. Everybody's happy.

In JavaScript, the "fetch" method is a way to communicate with these APIs. A standard format for API is JSON (or XML), because both servers and JS can understand it. Example: we want to get the user data for some GitHub user and do something with it. GitHub has its own API, and we request for example https://api.github.com/users/emilerik with fetch, we get a JSON object, and we can parse it and then play around with it. In code:

```js
const getEmil = async function() {
  const resp = await fetch("https://api.github.com/users/emilerik");
  const emil = await resp.json();
  console.log(emil.login + " is a web developer on GitHub.");
  console.log("You can check him out at " + emil.html_url);
};
getEmil(); // prints 'emilerik is a web developer on GitHub' and 'You can check him out at https://github.com/emilerik'
```

To summarize: a server from a websites/company _provides_ an API, which allows us to manipulate _or_ present data they provide _or_ allow us to use a service they provide.

---

#### Day 40/100: 3:00 //ES9, object spread operator + journal deployment!

Today, I deployed my journal to GitHub. I spent some time fixing the styling in markdown and figuring out how to add images. I thought it turned out alright! I also decided to start journalling (blogging?) in English, since it might be a bit more established in the industry than Swedish, to put it humbly.

Todays lesson: ES9 and the object spread operator. The spread syntax ... can be used when an iterable will be expanded in a place where zero or more arguments are expected, for example

```js
const myArray = [1, 5, 7];
const sum = (x, y, z) => {
  console.log(x + y + z);
};
sum(...myArray); // 13
```

The object spread operator is a special case - an object expression is expanded where key-value pairs are expected. (This is new in ECMAScript2018). Example:

```js
const obj1 = { user1: "Tom", pet: "Drake" };
const copyOfObj1 = { ...obj1 };
// copyOfObj1 = { user1: 'Tom', pet: 'Drake' };
```

There is an async functionality from ES9 called for await of. It's similar to the for of, but it can loop over an array of promises. Advantage: write asynchronous code as if it were synchronous.

Finally, I learned the method .finally. It is used when you want to run something after a promise, regardless of the outcome of the promise (including errors)

A little update: I'm currently on part 201/300 in the course, which is (obviously) approximately two thirds, but (satisfyingly) exactly 67%.

![dag40](./screenshots/40.png?raw=true "dag40")

---

#### Dag 39/100: 1:00 //async functions, try/catch

I ES8 introducerades en async await-funktion. Det har samma tillämpning som Promises, och är egentligen bara syntaktiskt socker. Istället för att använda kedjade .then, kan man istället använda keywordet 'await'. För att fånga errors kan man använda "try" för blocket man vill exekvera, och därefter "catch" för att fånga upp eventuella errors. "catch" har ett inargument också, error.

Syntax för async-funktionen är

```js
async function fetchUsers() {
await ...
}
```

![dag39](./screenshots/39.png?raw=true "dag39")

---

#### Dag 38/100: 1:30 //forts Promise

Promise är ett asynchronous fenomen. Det betyder att JS inte behöver blockas under tiden det väntar på ett Promise, utan kan göra andra saker. Ett promise tar in två argument - resolve och reject. Ett Promise kan antingen vara fulfilled, rejected eller pending.

Man kan använda .all för att hämta alla Promises. T.ex.

```js
Promise.all([promise1, promise2]).then(values => {
  console.log(values);
});
```

Med metoden .all inväntas det tills att alla promises är färdiga.

Promise.resolve(value) -metoden returnerar ett objekt som redan är resolvat, och som resolvar med värdet value!

---

#### Dag 37/100: 1:00 // Promises, GitHub-blogg

Lärde mig om Promises idag. Ett Promise är ett objekt som kan producera ett värde senare i tiden. Det har en metod (.then) som som antingen kan ge värdet när det har hämtat (då är Promiset "resolved") eller ge ett error om något gick fel ("rejected"). Man kan använda "catch" för att fånga errors.

Började också undersöka möjligheten att överföra denna dagbok (som just nu är hostad privat) till GitHub, där jag kan dela med den.

---

#### Dag 36/100: 1:00 // AJAX, fetch

Problem: hela sidan reloadades varje gång man klickade någonstans på sidan, vilket var mycket ineffektivt och långsamt.
Lösning: AJAX. Gör så att man kan kommunicera med servern utan att reloada allting. Exempel är Googles searchbar som uppdateras med information från servern kontinuerligt.

fetch är en metod till window, och används för att requesta data från en sida. fetch('http://nånurl.com') returnerar en "Promise". Det är ett löfte att leverera något så fort sidan har laddat. Man kan då använda .then som tar emot svaret, kallat response, använder .json på det, och till sist .then igen för att använda datan. Man använder .then på Promise, och eftersom första .then returnerar ett Promise använder man det två gånger. Exempel:

```js
fetch("https://jsonplaceholder.typicode.com/users")
  .then(response => response.json())
  .then(users => this.setState({ robots: users }));
```

---

#### Dag 35/100: 1:00 // HTTPS, JSON/XML

Webbläsaren är en HTTP-klient. Den skickar förfrågan till servers, till exempel get/post/put/delete. HTTPS används för att göra säkra överföringar. Då krypteras informationen innan den skickas mellan webbläsaren och servern.

Problem: när man använder t.ex. post, kanske man skickar ett objekt, som är skrivet i JavaScript, men servrarna kan inte förstå denna syntax rakt av eftersom de inte använder JS. Lösning: JSON - JavaScript Object Notation. JSON är en syntax för att lagra och skicka data. Alternativet är XML.
JSON är JS-liknande syntax, medan XML är HTML-liknande syntax.
JSON kan läsas av alla (?) språk. Det är en slags medlare mellan språk.

Man kan tolka alt. skriva till JSON mha parse respektive stringify genom t.ex. JSON.parse(user), där user är ett JS-objekt.

---

#### Dag 34/100: 1:00 // commit resa, HTTP

Commitade resa-appen till github. Lärde mig om HTTP - HyperText Transfer Protocol. Använder 4 verb för att interagera med servrar - get/post/put/delete.

---

#### Dag 33/100: 3:00 // resa (journey)

Påbörjade ett tappert försök av en egen journey-kopia med React. Ett bra sätt att repetera allting, men jag kom inte riktigt hela vägen. Två saker fastnade jag på - hur ska man göra så att posts hamnar nedanför varandra och inte bredvid? Och hur ska man göra så att man kan lägga till en post själv? Jag lärde mig också om mappstruktur, men en oklarhet som kvarstår är var man ska lägga styles?

resa: https://github.com/emilerik/resa

![dag33](./screenshots/33.png?raw=true "dag33")

---

#### Dag 32/100: 1:30 // Scroll, componentDidMount, json

Idag la jag till en Scroll-funktion, så att korten har en div som man kan scrolla i, så att titeln och sökrutan finns kvar. Påminner om att sätta header till fix, men skiljer sig i det att allt annat på sidan också är fixt, och korten kan scrollas. Istället för att lagra robots lokalt hämtar jag nu istället hem dem från en sida, och json används för att "fetcha". componentDidMount är en inbyggd React-metod som fungerar som så att den körs så fort en komponent har "mountats". Till exempel, efter att App har renderats är robots bara en tom array, men då körs componentDidMount direkt, och hämtar hem infon mha json från sidan, sen matas de in i CardList osv. Funderar nu på att bygga en egen Journey!

robofriends: https://github.com/emilerik/robofriends

![dag32](./screenshots/32.png?raw=true "dag32")

---

#### Dag 31/100: 1:00 TOT: ~40h // react: states

Gick in på states idag, vilket är centralt inom reactutveckling. Idén är att man vill att t.ex. användaren ska kunna agera med sidan så att saker förändras (man kanske skriver i en search box, säg) och då ska de props som parent components skickar ner till sina children förändras, och children kan också skicka tillbaka värden uppåt. Saker flyter dock bara upp eller ner - aldrig åt sidan. Så ifall det som står i en searchbox ska uppdatera vad som finns med i en CardList så måste det första flyta upp till App, som är parent till båda, sen ner till CardList.

![dag31](./screenshots/31.png?raw=true "dag31")

---

#### Dag 30/100: 1:00 //robofriends

En månad in!! :D

Ett problem tidigare: listade alla cards under index.js, vilket blev stökigt. Lösning: gjorde en CardsList-komponent, som innehöll en array med Cards, som framställdes genom en loop genom dessa med olika index. Fick blanda javascript och JSX (fake-html) vilket var lite funky.

Har nu gjort en App.js-fil, som är huvudkomponenten som innehåller alla andra komponenter. Smaart... Påbörjat en SearchBox, har dock ingen funktion än.

![dag30](./screenshots/30.png?raw=true "dag30")

---

#### Dag 29: 1:00 //robofriends, components

Fortsätter med React! Idag byggde vi den första komponenten till hemsidan - ett robotkort. Vi byggde en komponent som hette Card, och den tar emot ett gäng argument, såsom namn, id och mail. Alla cards har samma struktur, men som sagt olika argument. Sen, i index.js lades alla individuella kort till, som alla hade sina egna 'props' (name, id, email). Stylade också korten med < div className='tc bg-light-green dib br3 pa3 ma2 grow bw2 shadow-5'> som funkade sjukt bra! Det här blir bara roligare och roligare.

![dag29](./screenshots/29.png?raw=true "dag29")

---

#### Dag 28: 1:00 // React forts.

Idén: separation of concerns handlar istället om att varje KOMPONENT har sitt eget universum, med css och sånt. I js-filer kan man skriva "pseudo-HTML", som ser ut som HTML fast inte är det egentligen. Denna pseudo-HTML kallas JSX. React använder något som kallas virtual DOM, vilket är deras egen version av DOM.

Kan inte använda class="car" längre, eftersom class är reserverat av js. Använder istället className.

"Började" bygga på appen robofriends.

![dag28](./screenshots/28.png?raw=true "dag28")

---

#### Dag 27: 2:00 // TSEA28!

Japp, idag var första dagen jag inte gjorde webutveckling! Men det är ju trots alla 100 days of CODE, och jag satt i några timmar och proggade i assembler. Skrev massa tester till alla subrutiner, som funkade (typ alla) och därefter skrev pseudokod till mainprogrammet (som jag tänker att Algirdas får jobba lite hårdare på sen).

![dag27](./screenshots/27.png?raw=true "dag27")

---

#### Dag 26: 2:00 //React!

Kort sammanfattning:
Vi använder npm för att installera packages, moduler. lodash är exempel på ett sådant - utökar javascript med nya funktioner. För att använda lodash i webbläsaren vill vi skriva t.ex. var \_ = require('lodash'), men för att använda require behövs browserify. Eftersom npm var anpassad för node och inte webbläsare så behövs browserify.

React!! :heart-eyed-emoji:
Äntligen fått börja. Verkar riktigt coolt hittills, har dock inte byggt något projekt än. Men det känns verkligen som en heltäckande lösning. Jag gillar verkligen hur npm/node/react samspelar. Förstår inte så mycket än, men det kommer väl.

![dag26](./screenshots/26.png?raw=true "dag26")

---

#### Dag 25: 1:00 // NPM, node, live-server

Wow! Häftiga grejer. NPM används alltså för att hämta moduler/packages som andra har skrivit, och som kan lägga till funktionalitet till sitt program eller hemsida. Man skriver t.ex. npm install live-server för att ladda ner paketet live-server. Som i sin tur var fett coolt! Gör så att man kan köra en lokal server på datorn. node, som jag förstod det, används för att kompilera/köra javascript-kod utanför webbläsaren, t.ex. på en server?

Nästa sektion är React, tagga!!

---

#### Dag 24: 1:00 // hjälp

Andrei pratade om day in a life of a developer. Jag försökte hjälpa folk i help-me i disc. Skulle precis svara en persons fråga när den blev besvarad på annat håll -.- Sen försökte jag hjälpa en annan, som undrade varför Startup Landing Page-sidan behövde ha html och inte bara body till 100% width, height i style.css. Kom inte fram till något. Intressant dock!

---

#### Dag 22 + 23: 1:00 + 1:00 // pretty sublime, git, opensource

Ja, jag vet, jag glömde att skriva dagbok igår. Men jag glömde inte att progga! Dagen lades främst på att göra en snygg layout i sublime text. Blev rätt nöjd! Sen har jag också (åter)lärt mig Git! Känns som att jag har rätt bra koll nu. Fixade faktiskt en gammal bug i sudosolver, vilket var lite roligt. Idag har jag också lärt mig om open source. Är fett taggad på att fortsätta bidra och jobba med sånt! Bra för portfölj + egen erfarenhet. Blivit lite korta dagar nu men det känns okej.

Bild: snyggsublime

![dag22](./screenshots/22.png?raw=true "dag22")

---

#### Dag 21: 1:00 // terminal, och Viktor!

Kort dag! Ja, jag vet. Lekte runt lite i terminal. Men stor grej - jag ringde Viktor! :D Känns jättekul att få berätta, och jag kände mig extra stolt och nöjd när jag fick göra det. Han tyckte att allt det jag skulle lära mig också lät rimligt!

Kände (nästan för första gången) att jag inte pallade progga nånting idag, innan jag skulle gå och lägga mig. Fick tvinga mig att spendera lite tid. Inte så konstigt att det tar emot nu! Honeymoon-fasen kanske är över. Det är nu dagarna faktiskt räknas! Bara att fortsätta kötta på.

---

#### Dag 20: 3:00 // modules, how does JS work?

Avslutade sektionen (typ) advanced JS!! :D Börjar förstå att det finns väldigt mycket att lära sig, och det kan bli en spännande resa! Läste även många andra artiklar, om t.ex. hur javascript fungerar. Lärde mig om single-threaded, non-blocking och asynchronous. Imorrn får jag ringa Viktor! :D

P.S. krossade funktionen i förra inlägget.

![dag20](./screenshots/20.png?raw=true "dag20")

---

#### Dag 19/100: 1:30 // adv. loops

Seegt. Börjar att ta emot lite nu. Är i lite av en svacka vad gäller motivation. Förmodligen en kombination av att det börjar bli lite svårt (mycket att hålla reda på) och att plugget börjat, så det finns inte så mycket mental energi till övers. Också rätt bakis idag. Men blicka framåt! På söndag ska jag ringa Viktor! :D

En av mina tre lösningar funkade (kan du gissa vilken?) men bara sådär. Nya tag imorrn.

![dag19](./screenshots/19.png?raw=true "dag19")

---

#### Dag 18/100: 1:00 // övningar

Morgonprogg, kort dag (kravall ikväll). Gjorde övningar i klasser, ES7-funktioner (.includes, \*\*), ES8 (padStart, padEnd, trim())

---

#### Dag 17/100: 1:30 // Forts JS - map/filter/reduce/classes

Börjar att bli klurigt nu!! jag känner visserligen igen koncepten sen innan (reduce var nytt) men det svåra att att förstå dessa koncept i ett nytt språk (jämfört med Racket), att "lära om sig": Klasser är jag också bekant med sen innan, men syntaxen är rätt så krånglig. Arrays känner jag mig rätt trygg med eftersom jag är van med listor från Racket. Har inte fått jättemycket gjort de senaste dagarna, men det är eftersom jag har precis börjat plugget, och dessa avsnitt kräver lite mer betänketid, inget man rushar igenom.

![dag17](./screenshots/17.png?raw=true "dag17")

---

#### Dag 16/100: 1:30 // Advanced JS

Har lärt mig om avancerad JS. Till exempel: closures, currying och compose.
Closures innebär att en function som exekveras skapar en lokal miljö med variabler den har koll på, en closure.
Currying innebär en funktion som ska ta ett gäng argument, men som består av ett gäng funktioner, som alla tar varsitt argument.
En compose är helt enkelt en sammansatt funktion, f(g(x)).
Side effect: när en funktion påverkar "the outside world". Exempel

```js
let a = 1;
const b = function() {
  a = 1; //side effect
};
```

Målet: en funktion har inga side effects, och returnar alltid något => DETERMINISTISK

---

#### Dag 15/100: 4:00 // jQuery, DOM, advanced JavaScript

Gjorde färdigt DOM-sektionen, där jag avslutade med att göra en "gradient background"-sida. Man kunde välja olika färger eller randomiza, så blev bakgrunden till en gradient av dessa.
Fortsatte med advanced js. Ternary operator till exempel, ett kort sätt att göra en if-sats med bara sant eller falskt.

GitHub: https://github.com/emilerik/gradient-background

![dag15](./screenshots/15.png?raw=true "dag15")

---

Dag14/100: 2:00 // DOM - event listeners

Fortsätter med DOM. Mycket spännande! Kan "lyssna" på vad användaren gör på sidan. Till exempel håller över ett element, eller klickar på det. Skapade en shopping list app. Man kan lägga till element, radera, och stryka över.

![dag14](./screenshots/14.png?raw=true "dag14")

---

#### Dag 13/100: 2:30 // JS: data structures, methods, functions,

conditionals, loops. DOM

Färdig med JavaScript-delen! Gjorde ett antal uppgifter om arrays, objects, methods, osv. Skapade en "facebook lite". To write for example alert() is called "calling" or "invoking" a function. Loopar: for (fixt antal gånger), forEach (metod kopplat till ett object), while (kollar villkor i början), do while (kollar villkor i slutet). Skapade subfunktioner för "facebook lite", typ "isUserValid".

Påbörjade DOM! (Document Object Model).
We can access the DOM through the document object.
window -> document -> html -> body -> ...
Grabbing elements, adding/removing classes

---

#### Dag 12/100: 1:00 // control flow, declarations

Ganska tråkigt och långsamt. Förstår redan koncepten sedan tidigare. var och conditionals, alerts, if, else, Javascript i HTML. Man lägger js sist i HTML-fil, eftersom man vill att HTML och CSS ska laddas först. Exempel på if:

```js
if (name === "Emil") {
  alert("Yes, this is you.");
} else if (name === "Robert") {
  alert("Who dat?");
} else {
  alert("Hello?");
}
```

Console.log - ett sätt att skicka meddelanden i konsolloggen.
console.log("Hello!"); Lärde mig också funktioner:
function myFunction (someArg) {
return someArg
}
Return avslutar funktionen

---

#### Dag 11/100: 1:05 // JavaScript intro

Kollade på developer fundamentals. Han gick igenom internetnärvaro - vikten av att vara aktiv på github, stackoverflow, ha en hemsida eller blogg osv. Påbörjade även JavaScript-avsnittet - spännande! Har gått igenom typer: number, string, boolean.

---

#### Dag 10/100: 1:10 // Prettify

"Prettify": Snyggade till hemsidan. Bytte till färger, tog bort den förinställda skuggeffekten och bytte pointer till vanlig. Lade till rotationseffekt och skugga på grid-boxarna. Gjorde så att headern blev fix med hjälp av en sticky-class:

```js
.sticky {
position: fixed;
top: 0;
width: 100%;
}
```

![dag10](./screenshots/10.png?raw=true "dag10")

---

#### Dag 9/100: 1:10 // jämförelse min lösning vs kursens

Följer solution för "Layout master". Skillnader mot min lösning:

Använder li för alla element i header, och sen lägger till klassen "push" på contacts. Använder sen margin-left: auto; för att flytta den till höger.
Använder nav-tagg istället för div på header (viktigt!), och footer-tagg för footer.
Istället för grid-row-templates använde jag height: 50vh; på container, och sen bara grid-template-columns på gridden. Det gick rätt bra!

![dag9](./screenshots/9.png?raw=true "dag9")

---

#### Dag 8/100 1:30 // Layouts

Layouts. Fördjupade mig i grid-systemet, och påbörjade "layout master". Kom ganska långt, tycker jag! Gjorde ett main grid-system med en header, en cover, en projektgrid, och en footer. Experimenterade en del med margins/padding och lyckades rätt bra med header! Sen tycker jag att det är svårt med "master-width" på sidan. Gör man för mycket finns massa tomrum, för lite så trycks saker ihop. Finns det ingen "auto-height"?

P.S. börjar logga hur lång tid jag proggar nu, också.

![dag8](./screenshots/8.png?raw=true "dag8")

---

#### Dag 7/100 // startup-app avslutn + kolla på "facit"

Gjorde en version 2 av Startup som var en kopia av kursens. Började på ny sektion, advanced CSS. Började prata om CSS Grids, vilket är ett inbyggt, tvådimensionellt gridsystem. Kan kombineras med flexbox också

---

#### Dag 6/100 // startup-app forts

Ett rätt kort pass, men fick mycket gjort! Snyggade till många detaljer på Startup - placerade button där jag ville genom att använda en div runt knappen, sen width 100%, flexbox, justify content: center, sen position:absolute, top: 80% för att få ner den. Sen fixade jag snygg bootstrap-design på knappen, lekte runt med lite fonter och la till en hemsiderubrik. Använde en "header"-div för att dela upp i "logga" och "navigation" - gjorde flexbox på header för att sära på dem.

---

#### Dag 5/100 // startup-app forts

Fixade på Startup-sidan. Lyckades med massa grejer! Fixade bakgrundsbild mha
background-size: cover;
background-position: center;
och fixade texten centrerat mha width, height: 100%, position: absolute, top:28%! Problemet förut var att div-en bara tog upp en liten del av hela sidan, så texten kunde liksom inte centreras mot mitten av sidan eftersom den inte "ägde" den delen. Fortfarande oklart hur jag ska göra med knappen

![dag5](./screenshots/5.png?raw=true "dag5")

---

#### Dag 4/100 // Påbörjad dagbok, Bootstrap, CDN, startup-app

Ska nu börja föra dagbok om mina 100 dagar! Jag har redan kört 3 dagar, så jag orkade inte börja om räkningen från 1 igen. Tanken är att jag ska skriva korta reflektioner om vad jag lärt mig och hur det gått varje dag.

Idag lärde mig om Bootstrap, och CDN: content delivery network. Började på "startup"-sidan. Svårt, flexbox gör inte som jag vill! Hur placerar jag h1 mitt på sidan? Finns det en "master" flexbox och sen enskilda sådana inuti den?
