# TwitterGlobeFramework
Fun with [d3](https://d3js.org/), [socket.io](http://socket.io/), and the [Twitter API](https://dev.twitter.com/docs)

## The Globe
There's a saying that's common among web developers: "You should build a house first, then paint it."
Your tweets will need a good foundation. Let's create an HTML file that will house all your countries:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Your Globe Title</title>
    <link href="https://fonts.googleapis.com/css?family=Montserrat|PT+Serif" rel="stylesheet">
    <script src="//d3js.org/d3.v3.min.js"></script>
    <script src="//d3js.org/queue.v1.min.js"></script>
    <script src="//d3js.org/topojson.v1.min.js"></script>
    <script src="https://cdn.socket.io/socket.io-1.4.5.js"></script>
  </head>
</html>
```



## The Client
Originally I wanted to code the Twitter logic and `brosweify` it together, but because of [cross origin reasons](http://stackoverflow.com/questions/33266854/access-control-error-when-using-twitter-npm-module) that did
