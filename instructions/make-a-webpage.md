# Project: Make a Wepage!

You have been teaching yourself to program all semester and now you finally get to build something cool! Each of you are going to make your own wepage! 

## Create a Git/Github Repo for the Wepage
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

# Port Khan Academy: Intro to JS Code
The first page **port** one of you *Khan Academy Intro to JS* Projects to this repo. To **port** means to take code from one place, and trasnfer it somewhere else. In our case, you will take code from your Khan Academy workspace and move it to this repository.

## Processing.js
In the *Khan Academy: Intro to JS: Drawing an Animation* course whenever you were using function like ```ellipse```, ```circle```, ```draw```, ```mousePressed``` you were actually using a JavaScript library called [Processing.js](http://processingjs.org/). And you can use Processing.js in any webpage you create. 

### Include Processing.js Library in your page
To use Processing.js you need to include it in your webpage. We're going to use a publicly available CDN.

```
<script src="http://cdnjs.cloudflare.com/ajax/libs/processing.js/1.4.16/processing.js" type="text/javascript"></script>
```

### Include JQuery

```
<script src="https://code.jquery.com/jquery-2.1.4.js" type="text/javascript"></script>
```

### Include Bootstrap CSS
```
<link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css" rel="stylesheet" integrity="sha256-MfvZlkHCEqatNoGiOXveE8FIwMzZg4W85qfrfIFBfYc= sha512-dTfge/zgoMYpP7QbHy4gWMEGsbsdZeCXz7irItjcC3sPUFtf0kuFbDz/ixG7ArTxmDjLXDmezHubeNikyKGVyQ==" crossorigin="anonymous">
```

### Create a canvas element

### Create a script element

### Copy and update code from Khan Academy

### Move script to external file
