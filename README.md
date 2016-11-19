# reactsamples
React Samples

The following setup to create new sample project and adding required node modules.

1) Create a Project Folder

	  mkdir es6-react-setup 
	  
2) init NPM and package.json

    npm init
    
3) install react react-dom

    npm install react react-dom --save
    
4) install babel loader, core, preset modules

    npm install babel-loader babel-core babel-preset-es2015 babel-preset-react
    
5) Globally install babel, webpack webpack-dev-server

    npm install babel webpack webpack-dev-server -g
    
6) Create below project files under the  'es6-react-setup' folder

    index.html, App.js , main.js , webpack.config.js
 
7) setup webpack server 
  webpack.config.js
  
  	module.exports ={
	
	 entry : './main.js',
	 
	 output : {
	 
	   path : './',
	   
	   filename : 'index.js'
	   
	 },
	 
	 devServer:{
	 
	   inline : true,
	   
	   port : 3333
	   
	 },
	 
	 module :{
	 
	   loaders : [
	   
	     {
	     
	     test: /\.js$/,
	     
	     exclude : /node_modules/,
	     
	     loader : 'babel',
	     
	     query : {
	     
	       presets : ['es2015','react']
	       
	      }
	      
	    }
	    
	  ]
	  
	 }
	 
	}



8) index.html
   	<!DOCTYPE html>
	
	<html lang="en">
	<head>
	  <meta charset="utf-8">
	  <title>HelloREACT</title>
	</head>
	<body>
	  <div id="app"></div>
	  <script src="index.js"></script>
	</body>
	</html>
	

9) App.js

import React from 'react';
class App extends React.Component {
   render (){
     return <div>Hello World</div>
   }
}

export default App


10) main.js

import React from 'react'
import ReactDOM from 'react-dom'
import App from './App'

ReactDOM.render(<App />,document.getElementById('app'))

