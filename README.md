# TwitterGlobeFramework
Fun with [d3](https://d3js.org/), [socket.io](http://socket.io/), and the [Twitter API](https://dev.twitter.com/docs)

## The Globe
There's a saying that's common among web developers: "You should build a house first, then paint it."
Your tweets will need a good foundation. Let's create an `index.html` file that will house all your countries:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>YOUR GLOBE TITLE</title>
    <!--This is totally optional. I just like google fonts.
    this is where you would add custom fonts online if you wanted to-->
    <link href="https://fonts.googleapis.com/css?family=Montserrat|PT+Serif" rel="stylesheet">
    <script src="//d3js.org/d3.v3.min.js"></script>
    <script src="//d3js.org/queue.v1.min.js"></script>
    <script src="//d3js.org/topojson.v1.min.js"></script>
    <script src="https://cdn.socket.io/socket.io-1.4.5.js"></script>
  </head>
</html>
```
So far we've gathered all the libraries we need to use for the globe to work, and fonts for the globe.
The scripts we're using are components from d3: `d3-queue` for asynchronous tasks, and `topojson` for displaying
geographic data.

Next, we need to figure out what we want the globe to display. In HTML, we denote custom components by using
`<div>` elements. We'll add to a body tag to `index.html` and then place the div elements:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>YOUR GLOBE TITLE</title>
    <link href="https://fonts.googleapis.com/css?family=Montserrat|PT+Serif" rel="stylesheet">
    <script src="//d3js.org/d3.v3.min.js"></script>
    <script src="//d3js.org/queue.v1.min.js"></script>
    <script src="//d3js.org/topojson.v1.min.js"></script>
    <script src="https://cdn.socket.io/socket.io-1.4.5.js"></script>
  </head>
  <body>
    <div class="container">
      <div class="spinner" id="loader"></div>
      <div class="header">
        <h1 id="logo">YOUR GLOBE TITLE</h1>
      </div>
      <div id="tweet-list">
        <h5>YOUR TWEET LIST TITLE</h5>
      </div>
      <div id="tweet-map">
        <div class="title">
          <h1>your title</br>cool looking subtitle </h1>
          <h5><em>random caption about your globe <br/>and what not <br/>blah, blah blah blah blah</em></h5>
        </div>
      </div>
    </div>
  </body>
</html>
```


## The Client
Originally I wanted to code the Twitter logic and `broswerify` it together, but because of [cross origin reasons](http://stackoverflow.com/questions/33266854/access-control-error-when-using-twitter-npm-module) that did not work. The client
