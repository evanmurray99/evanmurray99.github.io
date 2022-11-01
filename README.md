# How to host a Markdown resume on GitHub Pages using Jekyll  

## Purpose and Software Introduction  

This guide has two goals:  

1. This tutorial describes the practical steps of how to host and format a resume Markdown, Visual Studio Code, GitHub Pages, and Jekyll.
2. Relate the practical steps described above to the general principles of current Technical
Writing, as explained in Andrew Etter's book [Modern Technical Writing](https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS).


### Software stack overview

Markdown

* Markdown is an easy to use text-to-HTML conversion tool for web writers.
* Markdown provides an easy-to-read, easy-to-write, lightweight markup language used for formating plaintext.

Visual Studio Code 

* Visual Studio Code is a source-code editor that can be used to edit Markdown type files.
* Also can be used for editing most coding languages.

GitHub Pages 

* GitHub Pages is a static site hosting service that takes source code straight from a repository on GitHub. It then runs the files through a build process, and publishes a website.
* GitHub Pages only needs a Markdown file and a Jekyll generated site.

Jekyll

* Jekyll is a static site generator needed to host a site on GitHub Pages.
* It takes text written in markup languages and uses layouts to create a static website.


## Requirements/Setup

#### Markdown

* Create a Markdown formatted resume using Visual Studio Code.
	* A guide for setting up Visual Studio Code to edit markdown can be found [here](https://code.visualstudio.com/docs/languages/markdown).
	* A guide for Markdown syntax can be found [here](https://www.markdownguide.org/basic-syntax/).


#### Github

* Create a GitHub account, as it is required for using GitHub Pages. GitHub will be used to host your website's repository.
	* 	Users can create a new account [here](https://github.com/signup).

#### Git

* Downloaded Git for version control and for uploading files to GitHub using Git Bash.
	* Git can be downloaded from [here](https://git-scm.com/downloads).

#### Jekyll

* Download Ruby and Jekyll in order to create the static site. Ruby must be installed in order to download Jekyll.
	* A guide on how to install Ruby and Jekyll can be found [here](https://jekyllrb.com/docs/installation/windows/).

## Creating and Hosting

### **<u>Step 1</u>** 

This step we will setup a repository on GitHub. Make sure you are signed in on your GitHub account before moving on.

1. Go to the main page of GitHub 
2. Click the green ***New*** button on the left side of the page located in the "Recent Repositories" tab.
3. Once on theCreate a new repository page name your repository ***YOUR-USERNAME.github.io***
	* 	You do not need to change any of the other settings on this page.
4. Scroll to the bottom of the page and click the green ***Create repository*** button.

>Step 1 and Step 4 implement Etter's recommendation of using distributed version control systems. Etter's continues by saying it is ideal to store your documentation and source code in the same repository allowing better synchronization between the two. 

### **<u>Step 2</u>** 

This step will use Jekyll to generate the needed files needed for creating the static site. 

**Note**: This step requires basic command line knowledge. A short guide can be found under the ***More resourses*** section of this how-to. 

1. Open ***Git Bash*** and change directory to where you would like to save the static site on your computer.
2. Run the command `jekyll new mySite` to ceate a new Jekyll site at `./mySite`
3. Move into the newly created directory by running the command `cd mySite`
4. Build and run the default site locally by running the command `bundle exec jekyll serve`

The default site can be seen locally at <http://localhost:4000>

> Step 2 demonstrates Etter's key principal of formating documentation using a static site generator. Static sites can be hosted basically anywere since they have no dependencies and no databases. Moving a site is as easy as moving a file from your desktop to a USB. This ease of use makes it easy for people of any programing skill set to use a static site generator such as Jekyll to host documentation.

### **<u>Step 3</u>** 
 
This step will add your resume to the site in the format of a post.

**Note**: You can edit multiple settings of your static site by editing the `_config.yml` file.

1. Move your `resume.md` inside the `_Posts` folder 
2. Rename the resume to follow same format as the sample post. It will look like this: `2022-10-29-evan's-resume.md`
3. Open the resume file, add the following table at the top of the document using Visual Studio Code. 

		---
		layout: post/m
		title:  "My Resume"  
		date:   2022-10-29 17:51:45 -0500
		categories: jekyll update
		---	
3. Save and exit Visual Studio Code.

> Step 3 highlights Etter's principal of using lightweight markup langauges. Lightweight markup languages such as Markdown have easy learning curse, therefor giving access to a larger group of people. This ease helps encourage contributions from those who have deep, helpful product knowledge, enhancing overall documentation. 

### **<u>Step 4</u>** 

This step will setup a Git repository inside of your mySite folder. In preparation to upload to Git

1. Open up ***Git Bash*** and change directory to `./mySite`
2. Run the command `git init` to initalize a git repository.
3. Run the command `git add .` to add all the files to the git repository.
4. Run the command `git commit -m 'first commit'` to commit all files.
5. Run the command `git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git` to connect the GitHub repository.
6. Run the command `git push -u origin master` to upload your local files to GitHub.

Once you have completed these steps you can go to ***YOUR-USERNAME.github.io*** and click on the most recent post to view the newly created page. It should look something like this:

![](myResume.gif)

## More Resources

[Markdown Cheat Sheet](https://www.markdownguide.org/basic-syntax/)

[Command Line Command Guide](https://www.freecodecamp.org/news/command-line-commands-cli-tutorial/)

[Modern Technical Write by Andrew Etter](https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS)

## Authors and Acknowledgment

Evan Murray  
Benjamin Paspaporn  
Junyi Lu  
Zac Kolton  

## FAQ

#### Why is Markdown better than a word processor?

Markdown is a better than a word processor because it allows for formating to be done from the keyboard rather than having to use a toolbar. This allows for writers to better focus on their writing without having switch from keyboard to mouse. 

#### Why is my resume not showing up?

GitHub takes some time to build and deploy static sites. Wait a few minutes and your resume will appear. If your resume is still not showing up make a commit to your repository to force GitHub to rebuild and redeploy the static site.

