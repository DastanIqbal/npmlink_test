#How to use your own npm module using npm link?


Suppose we have two folder a and b in test.

./test/b is developing framework and ./test/a is code folder which is using ./test/b framework.


Steps

1. go to ./test/b folder and run npm init and fill details. then package.json will looks like this

 {  
  "name": "fw",  
  "version": "1.0.0",  
  "description": "this is framework ",  
  "main": "index.js",  
  "scripts": {  
   "test": "fw"  
  },  
  "author": "dastaniqbal",  
  "license": "ISC"  
 }  


2. create file index.js in ./test/a and write this code.

 module.exports=index;  
 function index(data){  
      console.log("in index");  
      return data;  
 }  


3. now go to ./test/a folder and create test.js and write this code.

 var fw=require('fw');  
 console.log(fw('hello link'));  


4.now run node test.js and output will be looks like this.

 in index  
 hello link  



