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
