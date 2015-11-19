# Project: Make a Wepage!

You have been teaching yourself to program all semester and now you finally get to build something cool! Each of you are going to make your own wepage.

## Create a Git/Github Repo to hold the code
First things first. You're going to create a Git/Github repository to store your code. Using github will allow you to have free, low hastle, public hosting of your site.

This step will vary depending on if you are running Mac/Linux or windows but the highlevel steps are:
* Install Git
* Create a Github account
* Create a Gravatar linked to your email
* Create repository 
* Push it to github repo

## Install text editor
You will need a text editor in order to code on your computer. I'm using [Sublime Text](http://www.sublimetext.com/) but many people use the newer [Atom](https://atom.io/). Either way, you'll want to use a text editor that has syntax highlighting for HTML/JS/CSS. 

## Create an index.html
Up untill this point you have been programming in an online learning environment. In that environment you didn't have to worry about creating HTML/CSS/JS files because you put the code directly in the browser and it was saved to the Khan Academy servers. Now we are moving out of that environment and you will be creating HTML/CSS/JS files on your computer.

Your browser is a general purpose tool that can render HTML/CSS/JS. But that HTML/CSS/JS doesn't have to come from a webserver sent over the internet, you can load HTML files direclty from your computer.

In your git repository folder create a new file called ```ka_port.html```. In your text editor, just save the empty file you currently have open.

Add the normal HTML boilerplate

```html
<html>
<head>
  <title>Khan Academy Port</title>
</head>
<body>
</body>
</html>
```

# Port Khan Academy: Intro to JS Code
![introduction-to-programming-ka-port](https://cloud.githubusercontent.com/assets/12886386/11261291/a2a26c6e-8e38-11e5-8d27-604fad905dde.gif)

For the first page you are going to **port** one of you *Khan Academy Intro to JS* Projects to this repo. To **port** means to take code from one place, and trasnfer it somewhere else. In our case, you will take code from your Khan Academy workspace and move it to this repository.

## Processing.js
In the *Khan Academy: Intro to JS: Drawing an Animation* course whenever you were using function like ```ellipse```, ```circle```, ```draw```, ```mousePressed``` you were actually using a JavaScript library called [Processing.js](http://processingjs.org/). And you can use Processing.js in any webpage you create. 

### Include Processing.js Library in your page
To use Processing.js you need to include it in your webpage. We're going to use a publicly available CDN.

```html
<script src="http://cdnjs.cloudflare.com/ajax/libs/processing.js/1.4.16/processing.js" type="text/javascript"></script>
```

### Include JQuery
You pretty much always have a reason to include and use JQuery in you webpages. We're going to be using it for the ```$(document).ready()``` feature. Include it in your page from the JQuery CDN.

```html
<script src="https://code.jquery.com/jquery-2.1.4.js" type="text/javascript"></script>
```

### Include Bootstrap CSS
A little while agao, Twitter released [Bootstrap](http://getbootstrap.com/2.3.2/) which is a *"Sleek, intuitive, and powerful front-end framework for faster and easier web development."*. It provides you with sane defaults that look good and makes it easy to do common CSS things. Inlcude it in your webpage via this CDN.

```html
<link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css" rel="stylesheet" integrity="sha256-MfvZlkHCEqatNoGiOXveE8FIwMzZg4W85qfrfIFBfYc= sha512-dTfge/zgoMYpP7QbHy4gWMEGsbsdZeCXz7irItjcC3sPUFtf0kuFbDz/ixG7ArTxmDjLXDmezHubeNikyKGVyQ==" crossorigin="anonymous">
```

### Create a canvas element
The element that Processing.js uses to display your drawing is a [canvas](https://www.google.com/webhp?sourceid=chrome-instant&ion=1&espv=2&ie=UTF-8#q=html%20canvas) element. Add a canvas element to the **body** of your page and give it an id.

```html
<canvas id="my-drawing" class="effect-8" width="700" height="500"></canvas>
```

### Create a script element
Now we need a place to put your code. Underneath the convas element add a [script](http://www.w3schools.com/tags/tag_script.asp) tag. 

```html
<script type="text/javascript"></script>
```

#### Add a document ready function
Whenever the broswer renders a webpage, it starts at the top and goes through all of the elements at the same time. This can lead to a situation where you try to do something with an element that isn't fully rendered and the code won't work the way you expect it to. To prevent this you can wait to execute your code until the document is "ready". To do this, add this to you **script** tag.

```html
<script type="text/javascript">
$(document).ready(function() {
// Put Khan Academy Code in here
});
</script>
```


### Copy and update code from Khan Academy
Now copy your code from your Khan Academy project or challenge and paste it in the **script** tag in the the document ready function. In the Khan Academy brwoser environment, they did some magic behind the scenes to make it cleaner and to reduce the amount of you had to right to get your drawings to work. We are no longer in that environment, so you need to update your code to make it run here.

First you have to select the **canvas** element by id. Then you have to create a new Processing object and pass it the canvas element and a function to execute your code.

```html
<script type="text/javascript">
$(document).ready(function() {
  var canvas = document.getElementById("my-drawing");
  new Processing(canvas, function(processing) {
    // You're Khan Academy Code goes here
  });
});
</script>
```

Then you have to update all of the calls to the built in processing functions (```line```, ```text```, ```ellipse```) and add ```processing.*``` to them (```processing.line```, ```processing.text```, ```processing.ellipse```)

```html
<script type="text/javascript">
$(document).ready(function() {
var canvas = document.getElementById("my-drawing");
new Processing(canvas, function(processing) {
    console.log("Started function");
    processing.setup = function() {
      processing.size(600,500);
    };

    var leftX = 146;
    var rightX = 267;
    var sunRadius = 100;

    processing.draw = function() {
        console.log("Started draw function");
        processing.background(184, 236, 255);
        
        processing.fill(255, 170, 0);
        processing.ellipse(200, 100, sunRadius, sunRadius);
  
  ....
  console.log("ended");
  
  });
});
</script>
```

### Move script to external file
So far, we added the JavaScript directly in the page using a **script** tag. This is hardly ever done because it makes the page really long and messy quickly. It's much cleaner to separate your HTML, CSS, and JavaScript into seperate files.

Open up a new tab in your text editor and copy all of the JS in the **script** tag to the new tab. Then save the file as ```ka_port.js```. Back on the HTML page, remove all of the code in the **script** tag and add source attribute to the tag

```html
<script type="text/javascript" src="ka_port.js"></script>
```

Now reload the page. It should be working as it did before.

# Slideshow
![introduction-to-programming-slide-show](https://cloud.githubusercontent.com/assets/12886386/11261273/7fff5d52-8e38-11e5-80b7-d2577a665940.gif)

For the homepage you will need to build a slideshow of screenshots of the work you've done this semester. For the slideshow, you will experience what it's like to develop software in the "real world". You will have a list of requirements and an example/mock-up, and you will have to figure out how to make it happen.

### Slideshow requirements
* The slideshow must have at least 10 screenshots of the work you've done in Khan Academy and Codeacademy
* You cannot use an existing slideshow library but you can and should Google for ideas
* You must have a "stop/start" button of some kind. In my example, clicking anywhere on the images stops and restarts the slideshow
* You have to have some kind of transation between slides like fade-in or slide-in.
* You can work with one partner on the slideshow code but everyone must have their own webpage, with slides of their own work, in their own repo

# Header
Pretty much every site that you'll ever go to has a consistent header at the top of the page. It really goes a long way towards makeing random pages have continuity. Also, the header is often used as a consistent place to store navigation so the user can easily navigate from any page.

### Khan Academy
![screen shot 2015-11-18 at 9 26 11 pm](https://cloud.githubusercontent.com/assets/12886386/11261538/2c8e8cbc-8e3b-11e5-9f68-9d1f8c796e54.png)

### Github
![screen shot 2015-11-18 at 9 25 20 pm](https://cloud.githubusercontent.com/assets/12886386/11261547/364a3e90-8e3b-11e5-9cee-13610712c25d.png)

### Google
![screen shot 2015-11-18 at 9 25 32 pm](https://cloud.githubusercontent.com/assets/12886386/11261541/300ae2e6-8e3b-11e5-9264-d839fd94094b.png)

## Requirements
![header](https://cloud.githubusercontent.com/assets/12886386/11261549/39be7bcc-8e3b-11e5-9607-83c4fa0f3933.png)

For each of your wepabes in this project you must have a consistent header with:
* Navigation links to the **Slideshow**, **Khan Academy Port**, and **Blog**
* A picture of yourself and your name

# Don't forget
* Don't forget to continually commit your code and push it to Github
* Don't forget to Google for answers and suggestions if you get stuck
* Don't forget to ask me questions!
