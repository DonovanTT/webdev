# Web Development Tutorial

Project Notes:
This is a tutorial for building a website with HTML, JavaScript, and CSS using the Node framework.

You'll need to install Node, our runtime environment.
https://nodejs.org/en/

You'll need to install Node Package Manager (NPM), our package manager.
https://www.npmjs.com/

You'll need to install Git and create a GitHub account if you don't already have one. We're using GitHub for version control.
https://github.com/

# My Development Environment

I am developing in Visual Studio Code. I like a code environment with a text editor and a built-in command line, but you could also use something like Notepad or Notepad++. I'm pretty sure you could just open a cmd terminal to run the github and npm commands I'm using. I think you'll have to run your project files from the cmd terminal to see any console logs you call, though. Honestly, you should just use an IDE. Do your research though, and figure out which IDE works best for you. I don't feel like doing it for you right now, but I might review a few popular IDEs later. I've only used Visual Studio, Visual Studio Code, and Eclipse, but that way so long ago that I don't really remember it at all.

I'm using Google Chrome as my browser. Code sometimes behaves differently on different browsers. It's good practice to check that any updates you make to your code work on any browsers you anticipate your users running it on.

# Initialize a New GitHub Repository

Navigate to your GitHub dashboard and create a new repo.
Name the repo, give it a brief description, add a RREADME file and set the .gitignore template to Node.
You can choose public or private, and you can choose a license or not. No license will mean that the rights are exclusively yours, and MIT is the most popular license for open source software.

# Clone Your New Repo to Your PC

Now that you have created a new GitHub repository, you want to find its HTTPS connection string. At time of writing, this can be done by clicking the green "Code" button. A small window will pop up - make sure you're on the HTTPS tab, and the string in the box will be your connection string.

In your IDE, open a new terminal. Make sure you are navigated to the directory where you want your new project files to be created and run the following command:

    git clone {your connection string}

# Initialize a Node Project

In the terminal, navigate into your new project folder with the following command:

    cd {your new project folder name}

Then enter the following command in the terminal:

    npm init

Enter a package name (press Enter to accept the default project name provided by the folder name).
Enter a version (again, press Enter to accept the default).
Enter a description (the default is blank).
Enter an entry point (I recommend the default).
Enter a test command ("Test?" Or "Debug?").
The git repository should correctly point to your GitHub repo.
Enter any keywords you like. These might be good for SEO, I don't know. I'll have to look into that. I entered a bunch.
Enter an author, or your name.
Enter your license. I chose MIT.
Finally, press Enter one last time to confirm your changes to the new package.json file.

# A Few Notes On Version Control Before We Continue

## How to Save Your Work on GitHub:

Save all of your files locally.
Run the following command to check the status of your local repository:

    git status

This will tell you if you have any modified or untracked files. If you do, enter the following command to stage all of them for saving:

    git add .

Now that you have added all of your modifications to the staged commit, you can commit them to your local repository with the following command (Note that you need to add a message with the -m option. Just give of a brief description of any changes you have made since your last commit.):

    git commit -m "{Your message here.}"

This will create a commit on your local repository. Think of it like creating a new save file. Now we want to push this new save file up to the GitHub repository so other people can access it and/or so it is backed up in the cloud. We can do this with the following command:

    git push

## How Someone Else can Clone Your Repo And Start Working On It:

I'm just going to address this third theoretical someone.
Get the connection string from your friend's GitHub repository and enter the following command:

    git clone {your friend's connection string}

This will pull down all of the existing code in the repository.

Now, for the reason I included this section: if your friend has included any node packages - which they likely will have if they have progressed at all in this tutorial - you will need to install them in order for the code to run properly on your machine. You can do this will the following command:

    npm install

# Install Express

The first node package you'll need to install with npm is Express. Install it with the following command:

    npm i express

# Create the HTML File (Client)

Create a file called index.html in your project folder. For a basic "Hello World" page, enter the following content:

    <!DOCTYPE html>

    <html lang="en">
        <head>
            <meta charset="UTF-8">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">

            <title>Hello World!</title>
        </head>
        <body>
            <div>Hello World!</div>
        </body>
    </html>

The <title> tag sets the title that will appear in the tab at the top of your browser.
Everything inside the <body> tag is the content that will appear on the user's screen.

# Create the JS File (Server)

We need to set up an express server.

First, require the express library that we downloaded at the top of the file:

    const express = require('express');

Then create an instance of express called "app":

    const app = express();

Now, set a port. This is the port that the client will connect to. Select a number between 3000 and 8000.

    const port = process.env.PORT || 3000;

Next, enter the following:

    app.get('/', function (req, res) {
        res.sendFile('index.html', {root: __dirname});
    })

This is an example of an express route. This get route takes two parameters: the path ("/", in this case) and a callback function. This callback function is called middleware, because it runs in the middle of the route's path to the server and back. The content of the function here will send the index.html file to the client.

Finally, the app needs to listen on the route:

    app.listen(port, () => {
        console.log(`Now listening on port ${port}`);
    });

# Run The Server

Finally, run your server with the following command in the terminal:

    node server.js

Now you can open your app at the following URL:

    http://localhost:{Your port}}/

# Deploying to Heroku

On Heroku.com, create a new app.

Select GitHub as the deployment method.

Select your GitHub repository to connect to.

Enable automatic deploys.

Add a start script to the project's package.json file.

    "start": "node server.js",

Now add a Procfile:

    web: npm run start

# Next Steps

Now that you've gotten started, you should create a Trello account if you haven't already got one. It's an excellent tool for keeping track of progress.

Moving forward, we want to:

We need a Navbar, and multiple pages.

Figure out what kind of database we want to use and figure out how to connect to it. I'm going to be using SQL because I like SSMS.

Set up authorization. It needs to save tokens or something to remember if the user is logged in. Different users should be able to see their own data.

Email newsletter sign up and means for the admin to send emails. Latter does not need to be built in.

Payment processing and a store page.

Google Ads. Maybe look into other services, as well.

Search Engine Optimization (SEO)

User Content - Allow certain user roles to create articles, which create pages and are navigable to.

Search functionality - allow users to search site's articles. Articles should be filterable by title, tags, content, date, and author. "Relevance" is the number of times a keyphrase and/or keyword appears in any/all of these.

Admin Studio: Where admins can see and edit users, send email, and see orders.

User Roles:

- Administrator: Can see and edit any/all user roles/permissions.
- Operator: Can see and edit user roles/permissions, except changing users to/from Operators or Administrators.
- Author: Can add/edit/delete articles.
- Manager: Can add/edit/delete store posts.
- Email: Can read and send email.

# References

Set Up and Run a Simple Node Server Project:
https://levelup.gitconnected.com/set-up-and-run-a-simple-node-server-project-38b403a3dc09

# References

GitHub Integration (Heroku GitHub Deploys)
https://devcenter.heroku.com/articles/github-integration

Getting Started on Heroku with Node.js
https://devcenter.heroku.com/articles/getting-started-with-nodejs?singlepage=true

Best Practices for Node.js Development
https://devcenter.heroku.com/articles/node-best-practices
