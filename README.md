# Practice Web Dev Authentication
## Basic Authentication Practice

![](doc/images/home.png)

![](doc/images/register.png)

Practice using node and express

## Usage

Must have mongodb running for website to work. This command below is for [WSL](https://docs.microsoft.com/en-us/windows/wsl/about), it might look different for Mac.

    sudo service mongodb start
    [sudo] password for caitlyn: 
    * Starting database mongodb  

Start app.js using nodemon.

![](doc/images/nodemon.png)


Open browser and go to `localhost:3000`

## Technologies Used

* [node.js](https://nodejs.org/en/) - A way to use JavaScript without the browser.
* [express](http://expressjs.com/) - Web Framework. I used it for get and post HTTP requests to communicate with the browser. 
* [mongodb](https://www.mongodb.com/) - A NoSQL Database that holds our users.
* [mongoose](https://mongoosejs.com/) - Connects to the mongodb and creates a Schema, which is a model template. Also used to create a new model using that Schema. 
* [passport](http://www.passportjs.org/) - Used to authenticate the users in both local and remote authentication. Examples of remote authentication endpoints are Google, Facebook, GitHub, Twitter and others.  
* [oauth2](https://developers.google.com/identity/protocols/OAuth2) - I used it to login and verify my users with Google. 
* [ejs](https://ejs.co/) - A HTML file that includes javascript using the ejs tags. ex: `<%`

## What I Learned

### Google Oauth2

In this module, I learned  how to set up Google authentication using Oauth2. I used the [Google developer console](https://console.developers.google.com/).

![](doc/images/google1.png)
![](doc/images/google2.PNG) 

### MongoDB

The information is stored in MongoDB in a JSON format. The password is hashed and salted so that the real password is not stored. The actual fields are 

    email: String,
    password: String,
    googleId: String,
    secret: String. 

### Security Risks

Level 1 - When registering users' password in plain text, anyone is able to view the password.

Level 2 - Encrypting a code with a secret key is easy to hack.

Level 3 - MD5 is a hash but hashing is easy to break.

Level 4 - Using bcrypt, salting is possible and it adds integers/symbols to the end of the hash.

Level 5 - A cookie is used to track users' information. A session is like a login session. The problems of local storage is that it seems unreliable and people like to use Google authentication because it is more secure to them.

Level 6 - Using Oauth2 with Google is the most secure method compared to the other methods previously mentioned. 

If the password is not stored properly, then a hacker could use the secret key and get the password easily. 