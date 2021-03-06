#jQuery

####Resources
- http://api.jquery.com/

jQuery is a library of already created javascript functions, mostly used to interact with your front-end (that place where HTML lives). Think a ruby gem, but for javascript (library == gem).  

You call on a jQuery function with a **$**  
example: get element by id  
`$("#ElementID").whatever();`  

- jQuery is like CSS for javascript, you select an element and then do something with it.  
- jQuery is like SQL for javascript, it is a query language (say Markus, not AJ).  

###JSFiddle Code

http://jsfiddle.net/  


####HTML  

		<body>
    	<h1>Hello World!</h1>
    	<div>
        	<button type="button">Clear</button>
    	</div>
    	<div>Your message: <input type="text" value="blah"/></div>
    	<div>Your copy: <span>xxxx</span></div>
		</body>

####CSS

		div {
    	border: 1px dashed blue;
		}

		span {
    	border 1px solid black;
		}

####Javascript  
```javascript
var message = $('input').val();

alert(message);

// or

var message = $('input').val();

$('span').text(message);
```

**Adding functions**  

```javascript
function update() {
    var message = $('input').val();

    $('span').text(message);
}
  
// same     eventname  selector action (which is a function)
$('body').on('change', 'input', update );

$('input').val('');
$('span').val('');
```

**Adding a button to clear**  

```javascript
var events = $('body')
  ;

function update() {
  var message = $('input').val()
    ;

  $('span').text(message);
}

function clear() {
  $('input').val('');
  $('span').text('');
}

// same      eventname  selector   action  
events.on('keyup', 'input', update);
events.on('click', 'button', clear);
```

In javascript code is only executed when something happens. Our clear and update functions don't get called on until a user interacts with the page (the DOM). Javascript does not ask the user something (like gets.chomp does in ruby) it waits for user input, and then the program starts running.  

jquery assigns events (interactions) to objects vs execution of code line by line.  
You are wiring functions to objects, and it gets executed on diffrent events  
(clicking on something, hovering on something, etc)  

#### Cat Pics

**HTML**  

		<body>
    	<h1>Cat Pics</h1>
    	<div><img class='js-pic'
        	src='http://data.whicdn.com/images/27721013/bgnBP_large.jpg' width='250px' /></div>
    	<div><button type='button' class='js-next'>Next</button></div>
		</body>


**javascript**  

```javascript
var pics,
    i = 0;

loadPics();

function rotateImage() {
    $('img.js-pic').attr('src', pics[i]);
    i += 1;
    if (i === pics.length) {
         i = 0;  
    }
}

$('body').on('click', 'button.js-next', rotateImage);

function loadPics() {
  pics = [];      pics.push("http://images4.fanpop.com/image/photos/16100000/-cats-16140154-1920-1080.jpg");
  pics.push("http://www.myfilmviews.com/wp-content/uploads/2012/12/ryan-gosling-beard-normal1.jpg");
  pics.push("http://phodography.com/wp-content/uploads/2012/08/111119-Alfonso-4046-1024x685.jpg")
  pics.push("http://www.iwallscreen.com/stock/cats-and-dogs-wallpapers.jpg")
  pics.push("http://1.bp.blogspot.com/-kkFsF03oxOo/UPNVOdEtZBI/AAAAAAAABO8/0_I4inBy71I/s1600/tumblr_mbuypt8R0M1ri87b4o1_1280.jpg")
}
```
##Memory Game

**What will we need?**  

- index.html
	- includes (works with) css and javascript files
- stylesheet (css)
	- circles
- javascript (puppies.js)
	- jQuery (goes in javascript file)
- /img/puppies (6 puppy pictures - use each twice)

####Getting Started

		git clone https://github.com/aikalima/memory_template.git


**javascript psuedo code**  

```javascript
$(function(){

	// need to handle click on tile
	// if clicked, diasble it

	// if two images clicked,
	// compare if they are the same
	// if so, we have a match
	// -> for both, apply 'matched' style
		// and disable
	// if not
	// -> reset tiles to 'hidden style'

	// when done, reset board


	// the game is over when all tiles are matched
	// show 'Congrats' and reset board
});
```




