## Emils #100DaysOfCode
Här skriver jag om min framgångar och motgångar i att lära mig webbutveckling. Jag följer en kurs som heter The Complete Web Developer in 2019: Zero to Mastery från Udemy. Idén är att jag ska klara av att programmera 100 dagar i sträck. Vi får se hur det går.

Here, I write of my successes and failures in learning web development. I'm taking a course called The Complete Web Developer in 2019: Zero to Mastery from Udemy. The idea is that I'm going to code for 100 days in a row. We'll see how it goes. The first 39 days of the journal is in Swedish.
***

***
#### Day 48/100: 2:00 // clarifai API
Today was pretty exciting! I continued on the face recognition app. I used free clarifai APIs to predict some parameters in images from a URL - color at first. I used the Clarifai color model on a URL which was entered by the user, and console logged the result. It returned an array with the result, which basically just predicted the three top colors of the picture and their probability. Worked great. At the end, I tried the face recognition model instead, which is what I'll be using later as well, and it returned boundaries for what it predicts is the face.

All that remains now is to implement a way of drawing a box around the predicted face(s) of the image.

***
#### Day 47/100: 2:30 // assembly, face recognition app
Did some more assembly coding today. Mostly debugging and testing, and trying to step through our interrupt program to figure out what adresses and register were placed on the stack and why. 

Continued the face recognition app as well, this time building some more components. I more or less built all the components for the view, but it doesn't look great yet. I'll add an image.

![dag47](./screenshots/47.png?raw=true "dag47")

***
#### Day 46/100: 2:30 // assembly!
Today, I gave web dev a break, and hacked away at some good old fashioned assembly code! We're programming for a computer engineering course in a low level language, handling registers and storing data and instructions in memory manually. Today, we developed some subroutines used to handling interrupts - initially, we had a loop that printed a string, but then we added two (physical) CPIO buttons, which had higher priority, so the program exits the loop whenever one of those are clicked, to print another string. After clicking the buttons, we paused the program to look at the stack, and tried to analyze step by step what the program had put on the stack since the interrupts.

![dag46](./screenshots/46.png?raw=true "dag46")

***
#### Day 45/100: 1:20 // face recognition app
I started working on a big project in the course - the face recognition app. It's a website where you can log in, and then paste a URL with an image - it then finds faces on the image and marks them with rectangles. So far, I've basically just built some of the basic components, and a background. Tomorrow, I will hopefully finish the components so I can implement the face detection API.

***
#### Day 44/100: 1:30 // star wars foxes, continued
Today, I continued on the 'star wars foxes'-app. I think I came a long way. I managed to loop through several objects from the star wars API and render them in the Card component. Unfortunately, I didn't manage to match it with the random foxes API as I wanted - the error I got was
```js
Access to fetch at 'https://randomfox.ca/floof/' from origin 'chrome-extension://laookkfknpbbblfpciffpaejjkokdgca' has been blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource. If an opaque response serves your needs, set the request's mode to 'no-cors' to fetch the resource with CORS disabled.
```
I got it once before as well, and it seems to be complaining about the fact that it tries to fetch something that isn't on the same domain. Which is weird, because that's what I do with the swapi as well...

Anyway, I managed to solve by sort of ugly-hacking it, (I still thought it looks pretty good). Now, I give the source directly to the img-tag instead, so I don't use the API for getting the foxes. It was also the first time I used flexbox with React, with FlexView! It's a built in component in React, which you use to wrap whatever content you want to display with flex. In this case, it replaced the div. Here is the "ugly hack" with the url, and the FlexView!
```js
<FlexView wrap row> {
	characters.map((char, i) => {
		return (
			<Card
			key = {i}
			name = {char.name}
			height = {char.height}
			hair_color = {char.hair_color}
			img ={'https://randomfox.ca/images/' + (i+1) + '.jpg'}
			/>
		)
	})
}
</FlexView>
```

Here comes a pic of its current look. Not the prettiest, but to be fair, the focus here is on APIs.

![dag44](./screenshots/44.png?raw=true "dag44")
***
#### Day 43/100: 2:00 // APIs, star wars foxes
After the lessons in APIs, it was time for an exercise. The exercise was to build any one-page app using fetch and Star Wars API, http://swapi.co. I decided to make something similar to the robofriends app I built earlier. So the idea is to build an app in React with Card components, displaying each Star Wars character, and some information about them. I'll get the data from swapi. Also, I wanted some pictures with these cards, so I went with a random fox image generator API. We'll see how it turns out. I struggled for a while to figure out how to do the props and states right, but I finally got something to work.

![dag43](./screenshots/43.png?raw=true "dag43")
![dag43-2](./screenshots/43-2.png?raw=true "dag43-2")

***
#### Day 42/100: 2:00 // sidetracked: React Native
Today, I got sidetracked. I didn't follow the course curriculum, but instead stumbled upon the React Native tutorial at https://facebook.github.io/react-native/docs/tutorial. It's fascinating how powerful React seems to be, as the model of components can applied to building both web apps and smartphone apps. I always saw these as separate concerns, but it's natural that they shouldn't have to be. Another great thing is that it gave me another perspective in learning React, so my earlier knowledge really set in. I understand state and props much better now.

It was also nice to see that they used flexbox for handling layout. Earlier, I didn't quite understand how styling and layout played into React (does it have its own layout/styling system?), but as I now see it, you basically treat components the way you would HTML elements. What confused me in the beginning, I think, was tachyons, which I thought was the standard way of styling.

I heard that React and React Native have some differences, and to me, these seem minor. \<View> seems to be the equivalent of \<div>, for example. On top of regular React, a bunch of ways of handling smartphone interaction like pinching and swiping are added, but these things seem like additional components (no pun intended?) of the library rather than different concepts, in terms of React vs React Native. But then again, there's probably more under the hood and I might be wrong. 

***
#### Day 41/100: 2:30 // intro backend, APIs
Role of the backend developer: to manage and develop the server-side of an application. Backend basically consists of the server and the database. The server communicates, and the database stores. Examples are: to handle user requests, to store and retrieve data, and deliver the HTML/CSS/JS-files to the user browser. A classic model is LAMP - Linux (OS), Apache (HTTP), MySQL (relational DB) and PHP (serverside code), but there are more modern models such as MEAN (MongoDB, ExpressJS, AngularJS, NodeJS) which is powered by JavaScript. Big applications, such as Facebook or Google use load balancers and multiple servers and databases to handle huge amounts of traffic.

API stands for Application Programming Interface. In short, APIs are a way for websites and applications to communicate and share information with eachother. Say I wanna buy sneakers, but I'm not sure which stores sell sneakers. So I go to Pricerunner. They don't have any sneakers, but they know lots of stores and companies who do. So when I search for size 44 Converse, Pricerunner interacts with these stores' APIs to fetch my request of this particular footwear. Maybe I find my pair, maybe I'm redirected to converse.com and maybe Pricerunner gets a little profit. Everybody's happy.

In JavaScript, the "fetch" method is a way to communicate with these APIs. A standard format for API is JSON (or XML), because both servers and JS can understand it. Example: we want to get the user data for some GitHub user and do something with it. GitHub has its own API, and we request for example https://api.github.com/users/emilerik with fetch, we get a JSON object, and we can parse it and then play around with it. In code:
```js
const getEmil = async function() {
	const resp = await fetch('https://api.github.com/users/emilerik');
	const emil = await resp.json();
	console.log(emil.login + ' is a web developer on GitHub.');
	console.log('You can check him out at ' + emil.html_url);
}
getEmil(); // prints 'emilerik is a web developer on GitHub' and 'You can check him out at https://github.com/emilerik'
```
To summarize: a server from a websites/company *provides* an API, which allows us to manipulate *or* present data they provide *or* allow us to use a service they provide.
***
#### Day 40/100: 3:00 //ES9, object spread operator + journal deployment!
Today, I deployed my journal to GitHub. I spent some time fixing the styling in markdown and figuring out how to add images. I thought it turned out alright! I also decided to start journalling (blogging?) in English, since it might be a bit more established in the industry than Swedish, to put it humbly.

Todays lesson: ES9 and the object spread operator. The spread syntax ... can be used when an iterable will be expanded in a place where zero or more arguments are expected, for example
```js
const myArray = [1, 5, 7];
const sum = (x, y, z) => {
	console.log(x + y + z);
}
sum(...myArray); // 13
```
The object spread operator is a special case - an object expression is expanded where key-value pairs are expected. (This is new in ECMAScript2018). Example:
```js
const obj1 = { user1: 'Tom', pet: 'Drake' };
const copyOfObj1 = { ...obj1 }
// copyOfObj1 = { user1: 'Tom', pet: 'Drake' };
```

There is an async functionality from ES9 called for await of. It's similar to the for of, but it can loop over an array of promises. Advantage: write asynchronous code as if it were synchronous.

Finally, I learned the method .finally. It is used when you want to run something after a promise, regardless of the outcome of the promise (including errors)

A little update: I'm currently on part 201/300 in the course, which is (obviously) approximately two thirds, but (satisfyingly) exactly 67%.

![dag40](./screenshots/40.png?raw=true "dag40")

***
#### Dag 39/100: 1:00 //async functions, try/catch

I ES8 introducerades en async await-funktion. Det har samma tillämpning som Promises, och är egentligen bara syntaktiskt socker. Istället för att använda kedjade .then, kan man istället använda keywordet 'await'. För att fånga errors kan man använda "try" för blocket man vill exekvera, och därefter "catch" för att fånga upp eventuella errors. "catch" har ett inargument också, error.

Syntax för async-funktionen är
```js
async function fetchUsers() {
await ...
}
```

![dag39](./screenshots/39.png?raw=true "dag39")

***
#### Dag 38/100: 1:30 //forts Promise

Promise är ett asynchronous fenomen. Det betyder att JS inte behöver blockas under tiden det väntar på ett Promise, utan kan göra andra saker. Ett promise tar in två argument - resolve och reject. Ett Promise kan antingen vara fulfilled, rejected eller pending.

Man kan använda .all för att hämta alla Promises. T.ex.
```js
Promise.all([promise1, promise2])
.then(values => {
console.log(values);
})
```
Med metoden .all inväntas det tills att alla promises är färdiga.

Promise.resolve(value) -metoden returnerar ett objekt som redan är resolvat, och som resolvar med värdet value!

***
#### Dag 37/100: 1:00 // Promises, GitHub-blogg

Lärde mig om Promises idag. Ett Promise är ett objekt som kan producera ett värde senare i tiden. Det har en metod (.then) som som antingen kan ge värdet när det har hämtat (då är Promiset "resolved") eller ge ett error om något gick fel ("rejected"). Man kan använda "catch" för att fånga errors.

Började också undersöka möjligheten att överföra denna dagbok (som just nu är hostad privat) till GitHub, där jag kan dela med den.

***
#### Dag 36/100: 1:00 // AJAX, fetch

Problem: hela sidan reloadades varje gång man klickade någonstans på sidan, vilket var mycket ineffektivt och långsamt.
Lösning: AJAX. Gör så att man kan kommunicera med servern utan att reloada allting. Exempel är Googles searchbar som uppdateras med information från servern kontinuerligt.

fetch är en metod till window, och används för att requesta data från en sida. fetch('http://nånurl.com') returnerar en "Promise". Det är ett löfte att leverera något så fort sidan har laddat. Man kan då använda .then som tar emot svaret, kallat response, använder .json på det, och till sist .then igen för att använda datan. Man använder .then på Promise, och eftersom första .then returnerar ett Promise använder man det två gånger. Exempel:
```js
fetch('https://jsonplaceholder.typicode.com/users')
.then(response => response.json())
.then(users => this.setState({ robots: users }));
```

***
#### Dag 35/100: 1:00 // HTTPS, JSON/XML

Webbläsaren är en HTTP-klient. Den skickar förfrågan till servers, till exempel get/post/put/delete. HTTPS används för att göra säkra överföringar. Då krypteras informationen innan den skickas mellan webbläsaren och servern.

Problem: när man använder t.ex. post, kanske man skickar ett objekt, som är skrivet i JavaScript, men servrarna kan inte förstå denna syntax rakt av eftersom de inte använder JS. Lösning: JSON - JavaScript Object Notation. JSON är en syntax för att lagra och skicka data. Alternativet är XML.
JSON är JS-liknande syntax, medan XML är HTML-liknande syntax.
JSON kan läsas av alla (?) språk. Det är en slags medlare mellan språk.

Man kan tolka alt. skriva till JSON mha parse respektive stringify genom t.ex. JSON.parse(user), där user är ett JS-objekt.

***
#### Dag 34/100: 1:00 // commit resa, HTTP

Commitade resa-appen till github. Lärde mig om HTTP - HyperText Transfer Protocol. Använder 4 verb för att interagera med servrar - get/post/put/delete.

***
#### Dag 33/100: 3:00 // resa (journey)

Påbörjade ett tappert försök av en egen journey-kopia med React. Ett bra sätt att repetera allting, men jag kom inte riktigt hela vägen. Två saker fastnade jag på - hur ska man göra så att posts hamnar nedanför varandra och inte bredvid? Och hur ska man göra så att man kan lägga till en post själv? Jag lärde mig också om mappstruktur, men en oklarhet som kvarstår är var man ska lägga styles?

resa: https://github.com/emilerik/resa

![dag33](./screenshots/33.png?raw=true "dag33")

***
#### Dag 32/100: 1:30 // Scroll, componentDidMount, json

Idag la jag till en Scroll-funktion, så att korten har en div som man kan scrolla i, så att titeln och sökrutan finns kvar. Påminner om att sätta header till fix, men skiljer sig i det att allt annat på sidan också är fixt, och korten kan scrollas. Istället för att lagra robots lokalt hämtar jag nu istället hem dem från en sida, och json används för att "fetcha". componentDidMount är en inbyggd React-metod som fungerar som så att den körs så fort en komponent har "mountats". Till exempel, efter att App har renderats är robots bara en tom array, men då körs componentDidMount direkt, och hämtar hem infon mha json från sidan, sen matas de in i CardList osv. Funderar nu på att bygga en egen Journey!

robofriends: https://github.com/emilerik/robofriends

![dag32](./screenshots/32.png?raw=true "dag32")

***
#### Dag 31/100: 1:00 TOT: ~40h // react: states

Gick in på states idag, vilket är centralt inom reactutveckling. Idén är att man vill att t.ex. användaren ska kunna agera med sidan så att saker förändras (man kanske skriver i en search box, säg) och då ska de props som parent components skickar ner till sina children förändras, och children kan också skicka tillbaka värden uppåt. Saker flyter dock bara upp eller ner - aldrig åt sidan. Så ifall det som står i en searchbox ska uppdatera vad som finns med i en CardList så måste det första flyta upp till App, som är parent till båda, sen ner till CardList.

![dag31](./screenshots/31.png?raw=true "dag31")

***
#### Dag 30/100: 1:00 //robofriends

En månad in!! :D

Ett problem tidigare: listade alla cards under index.js, vilket blev stökigt. Lösning: gjorde en CardsList-komponent, som innehöll en array med Cards, som framställdes genom en loop genom dessa med olika index. Fick blanda javascript och JSX (fake-html) vilket var lite funky.

Har nu gjort en App.js-fil, som är huvudkomponenten som innehåller alla andra komponenter. Smaart... Påbörjat en SearchBox, har dock ingen funktion än.

![dag30](./screenshots/30.png?raw=true "dag30")

***
#### Dag 29: 1:00 //robofriends, components

Fortsätter med React! Idag byggde vi den första komponenten till hemsidan - ett robotkort. Vi byggde en komponent som hette Card, och den tar emot ett gäng argument, såsom namn, id och mail. Alla cards har samma struktur, men som sagt olika argument. Sen, i index.js lades alla individuella kort till, som alla hade sina egna 'props' (name, id, email). Stylade också korten med < div className='tc bg-light-green dib br3 pa3 ma2 grow bw2 shadow-5'> som funkade sjukt bra! Det här blir bara roligare och roligare.

![dag29](./screenshots/29.png?raw=true "dag29")

***
#### Dag 28: 1:00 // React forts.

Idén: separation of concerns handlar istället om att varje KOMPONENT har sitt eget universum, med css och sånt. I js-filer kan man skriva "pseudo-HTML", som ser ut som HTML fast inte är det egentligen. Denna pseudo-HTML kallas JSX. React använder något som kallas virtual DOM, vilket är deras egen version av DOM.

Kan inte använda class="car" längre, eftersom class är reserverat av js. Använder istället className.

"Började" bygga på appen robofriends.

![dag28](./screenshots/28.png?raw=true "dag28")

***
#### Dag 27: 2:00 // TSEA28!

Japp, idag var första dagen jag inte gjorde webutveckling! Men det är ju trots alla 100 days of CODE, och jag satt i några timmar och proggade i assembler. Skrev massa tester till alla subrutiner, som funkade (typ alla) och därefter skrev pseudokod till mainprogrammet (som jag tänker att Algirdas får jobba lite hårdare på sen).

![dag27](./screenshots/27.png?raw=true "dag27")

***
#### Dag 26: 2:00 //React!

Kort sammanfattning:
Vi använder npm för att installera packages, moduler. lodash är exempel på ett sådant - utökar javascript med nya funktioner. För att använda lodash i webbläsaren vill vi skriva t.ex. var _ = require('lodash'), men för att använda require behövs browserify. Eftersom npm var anpassad för node och inte webbläsare så behövs browserify.

React!! :heart-eyed-emoji:
Äntligen fått börja. Verkar riktigt coolt hittills, har dock inte byggt något projekt än. Men det känns verkligen som en heltäckande lösning. Jag gillar verkligen hur npm/node/react samspelar. Förstår inte så mycket än, men det kommer väl.

![dag26](./screenshots/26.png?raw=true "dag26")

***
#### Dag 25: 1:00 // NPM, node, live-server

Wow! Häftiga grejer. NPM används alltså för att hämta moduler/packages som andra har skrivit, och som kan lägga till funktionalitet till sitt program eller hemsida. Man skriver t.ex. npm install live-server för att ladda ner paketet live-server. Som i sin tur var fett coolt! Gör så att man kan köra en lokal server på datorn. node, som jag förstod det, används för att kompilera/köra javascript-kod utanför webbläsaren, t.ex. på en server?

Nästa sektion är React, tagga!!

***
#### Dag 24: 1:00 // hjälp

Andrei pratade om day in a life of a developer. Jag försökte hjälpa folk i help-me i disc. Skulle precis svara en persons fråga när den blev besvarad på annat håll -.- Sen försökte jag hjälpa en annan, som undrade varför Startup Landing Page-sidan behövde ha html och inte bara body till 100% width, height i style.css. Kom inte fram till något. Intressant dock!

***
#### Dag 22 + 23: 1:00 + 1:00 // pretty sublime, git, opensource

Ja, jag vet, jag glömde att skriva dagbok igår. Men jag glömde inte att progga! Dagen lades främst på att göra en snygg layout i sublime text. Blev rätt nöjd! Sen har jag också (åter)lärt mig Git! Känns som att jag har rätt bra koll nu. Fixade faktiskt en gammal bug i sudosolver, vilket var lite roligt. Idag har jag också lärt mig om open source. Är fett taggad på att fortsätta bidra och jobba med sånt! Bra för portfölj + egen erfarenhet. Blivit lite korta dagar nu men det känns okej.

Bild: snyggsublime

![dag22](./screenshots/22.png?raw=true "dag22")

***
#### Dag 21: 1:00 // terminal, och Viktor!

Kort dag! Ja, jag vet. Lekte runt lite i terminal. Men stor grej - jag ringde Viktor! :D Känns jättekul att få berätta, och jag kände mig extra stolt och nöjd när jag fick göra det. Han tyckte att allt det jag skulle lära mig också lät rimligt!

Kände (nästan för första gången) att jag inte pallade progga nånting idag, innan jag skulle gå och lägga mig. Fick tvinga mig att spendera lite tid. Inte så konstigt att det tar emot nu! Honeymoon-fasen kanske är över. Det är nu dagarna faktiskt räknas! Bara att fortsätta kötta på.

***
#### Dag 20: 3:00 // modules, how does JS work?

Avslutade sektionen (typ) advanced JS!! :D Börjar förstå att det finns väldigt mycket att lära sig, och det kan bli en spännande resa! Läste även många andra artiklar, om t.ex. hur javascript fungerar. Lärde mig om single-threaded, non-blocking och asynchronous. Imorrn får jag ringa Viktor! :D

P.S. krossade funktionen i förra inlägget.

![dag20](./screenshots/20.png?raw=true "dag20")

***
#### Dag 19/100: 1:30 // adv. loops

Seegt. Börjar att ta emot lite nu. Är i lite av en svacka vad gäller motivation. Förmodligen en kombination av att det börjar bli lite svårt (mycket att hålla reda på) och att plugget börjat, så det finns inte så mycket mental energi till övers. Också rätt bakis idag. Men blicka framåt! På söndag ska jag ringa Viktor! :D

En av mina tre lösningar funkade (kan du gissa vilken?) men bara sådär. Nya tag imorrn.

![dag19](./screenshots/19.png?raw=true "dag19")

***
#### Dag 18/100: 1:00 // övningar

Morgonprogg, kort dag (kravall ikväll). Gjorde övningar i klasser, ES7-funktioner (.includes, **), ES8 (padStart, padEnd, trim())

***
#### Dag 17/100: 1:30 // Forts JS - map/filter/reduce/classes

Börjar att bli klurigt nu!! jag känner visserligen igen koncepten sen innan (reduce var nytt) men det svåra att att förstå dessa koncept i ett nytt språk (jämfört med Racket), att "lära om sig": Klasser är jag också bekant med sen innan, men syntaxen är rätt så krånglig. Arrays känner jag mig rätt trygg med eftersom jag är van med listor från Racket. Har inte fått jättemycket gjort de senaste dagarna, men det är eftersom jag har precis börjat plugget, och dessa avsnitt kräver lite mer betänketid, inget man rushar igenom.

![dag17](./screenshots/17.png?raw=true "dag17")

***
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
}
```
Målet: en funktion har inga side effects, och returnar alltid något => DETERMINISTISK

***
#### Dag 15/100: 4:00 // jQuery, DOM, advanced JavaScript

Gjorde färdigt DOM-sektionen, där jag avslutade med att göra en "gradient background"-sida. Man kunde välja olika färger eller randomiza, så blev bakgrunden till en gradient av dessa.
Fortsatte med advanced js. Ternary operator till exempel, ett kort sätt att göra en if-sats med bara sant eller falskt.

GitHub: https://github.com/emilerik/gradient-background

![dag15](./screenshots/15.png?raw=true "dag15")

***
Dag14/100: 2:00 // DOM - event listeners

Fortsätter med DOM. Mycket spännande! Kan "lyssna" på vad användaren gör på sidan. Till exempel håller över ett element, eller klickar på det. Skapade en shopping list app. Man kan lägga till element, radera, och stryka över.

![dag14](./screenshots/14.png?raw=true "dag14")

***
#### Dag 13/100: 2:30 // JS: data structures, methods, functions, 
conditionals, loops. DOM

Färdig med JavaScript-delen! Gjorde ett antal uppgifter om arrays, objects, methods, osv. Skapade en "facebook lite". To write for example alert() is called "calling" or "invoking" a function. Loopar: for (fixt antal gånger), forEach (metod kopplat till ett object), while (kollar villkor i början), do while (kollar villkor i slutet). Skapade subfunktioner för "facebook lite", typ "isUserValid".

Påbörjade DOM! (Document Object Model).
We can access the DOM through the document object.
window -> document -> html -> body -> ...
Grabbing elements, adding/removing classes

***
#### Dag 12/100: 1:00 // control flow, declarations

Ganska tråkigt och långsamt. Förstår redan koncepten sedan tidigare. var och conditionals, alerts, if, else, Javascript i HTML. Man lägger js sist i HTML-fil, eftersom man vill att HTML och CSS ska laddas först. Exempel på if:
```js
if (name === "Emil") {
alert("Yes, this is you.")
} else if (name === "Robert") {
alert("Who dat?")
} else {
alert("Hello?")
}
```

Console.log - ett sätt att skicka meddelanden i konsolloggen.
console.log("Hello!"); Lärde mig också funktioner:
function myFunction (someArg) {
return someArg
}
Return avslutar funktionen

***
#### Dag 11/100: 1:05 // JavaScript intro

Kollade på developer fundamentals. Han gick igenom internetnärvaro - vikten av att vara aktiv på github, stackoverflow, ha en hemsida eller blogg osv. Påbörjade även JavaScript-avsnittet - spännande! Har gått igenom typer: number, string, boolean.

***
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

***
#### Dag 9/100: 1:10 // jämförelse min lösning vs kursens

Följer solution för "Layout master". Skillnader mot min lösning:

Använder li för alla element i header, och sen lägger till klassen "push" på contacts. Använder sen margin-left: auto; för att flytta den till höger.
Använder nav-tagg istället för div på header (viktigt!), och footer-tagg för footer.
Istället för grid-row-templates använde jag height: 50vh; på container, och sen bara grid-template-columns på gridden. Det gick rätt bra!

![dag9](./screenshots/9.png?raw=true "dag9")

***
#### Dag 8/100 1:30 // Layouts

Layouts. Fördjupade mig i grid-systemet, och påbörjade "layout master". Kom ganska långt, tycker jag! Gjorde ett main grid-system med en header, en cover, en projektgrid, och en footer. Experimenterade en del med margins/padding och lyckades rätt bra med header! Sen tycker jag att det är svårt med "master-width" på sidan. Gör man för mycket finns massa tomrum, för lite så trycks saker ihop. Finns det ingen "auto-height"?

P.S. börjar logga hur lång tid jag proggar nu, också.

![dag8](./screenshots/8.png?raw=true "dag8")

***
#### Dag 7/100 // startup-app avslutn + kolla på "facit"

Gjorde en version 2 av Startup som var en kopia av kursens. Började på ny sektion, advanced CSS. Började prata om CSS Grids, vilket är ett inbyggt, tvådimensionellt gridsystem. Kan kombineras med flexbox också

***
#### Dag 6/100 // startup-app forts

Ett rätt kort pass, men fick mycket gjort! Snyggade till många detaljer på Startup - placerade button där jag ville genom att använda en div runt knappen, sen width 100%, flexbox, justify content: center, sen position:absolute, top: 80% för att få ner den. Sen fixade jag snygg bootstrap-design på knappen, lekte runt med lite fonter och la till en hemsiderubrik. Använde en "header"-div för att dela upp i "logga" och "navigation" - gjorde flexbox på header för att sära på dem.

***
#### Dag 5/100 // startup-app forts

Fixade på Startup-sidan. Lyckades med massa grejer! Fixade bakgrundsbild mha
background-size: cover;
background-position: center;
och fixade texten centrerat mha width, height: 100%, position: absolute, top:28%! Problemet förut var att div-en bara tog upp en liten del av hela sidan, så texten kunde liksom inte centreras mot mitten av sidan eftersom den inte "ägde" den delen. Fortfarande oklart hur jag ska göra med knappen

![dag5](./screenshots/5.png?raw=true "dag5")

***
#### Dag 4/100 // Påbörjad dagbok, Bootstrap, CDN, startup-app

Ska nu börja föra dagbok om mina 100 dagar! Jag har redan kört 3 dagar, så jag orkade inte börja om räkningen från 1 igen. Tanken är att jag ska skriva korta reflektioner om vad jag lärt mig och hur det gått varje dag.

Idag lärde mig om Bootstrap, och CDN: content delivery network. Började på "startup"-sidan. Svårt, flexbox gör inte som jag vill! Hur placerar jag h1 mitt på sidan? Finns det en "master" flexbox och sen enskilda sådana inuti den?
