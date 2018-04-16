# Express.js (My Guild to Set Up a Simple Express Server on Linux Ubuntu 16.04)

## Create new folder

```
mkdir express
cd express
```

## Create package.json

```
yarn init
```

**Example**

![picture alt]()

## Install Express.js

```
yarn add express
```

## Create web development files

```
touch server.js index.html style.css app.js
```

**server.js**
```
 var express = require("express");
 var app = express();

 /* serves main page */
 app.get("/", function(req, res) {
    res.sendfile('index.html');
 });

 /* serves all the static files */
 app.get(/^(.+)$/, function(req, res){ 
     console.log('static file request : ' + req.params);
     res.sendfile( __dirname + req.params[0]); 
 });

 var port = process.env.PORT || 5000;
 app.listen(port, function() {
   console.log("Listening on " + port);
 });
```

**index.html**

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="utf-8">
	<meta name="viewport" content="width=device-width,initial-scale=1,shrink-to-fit=no">
	<meta name="theme-color" content="#000000">
	<link rel="manifest" href="./manifest.json">
	<link rel="shortcut icon" href="./favicon.ico">
	<title>Express</title>
	<noscript>You need to enable JavaScript to run this app.</noscript>
	<link type="text/css" rel="stylesheet" href="./style.css">
</head>

<body>
	Express is running!
	<script type="text/javascript" src="./app.js"></script>
</body>

</html>
```

**style.css**

```css
* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}
```

**app.js**
```javascript
console.log('JavaScript is running');
```

**manifest.json**
```json
{
	"short_name": "Express App",
	"name": "My First Express App",
	"icons": [{
		"src": "favicon.ico",
      		"sizes": "64x64 32x32 24x24 16x16",
      		"type": "image/x-icon"
    	}],
	"start_url": "./index.html",
	"display": "standalone",
  	"theme_color": "#000000",
  	"background_color": "#ffffff"
}
```
