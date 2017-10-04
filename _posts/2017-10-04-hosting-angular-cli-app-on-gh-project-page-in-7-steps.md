---
layout: post
title:  "Hosting an Angular-CLI app on github project page in 7 steps"
author: JoA-MoS
category: Dev
tags: [Angular, Angular-CLI, Github Pages]
---

1. Create a new Angular Application

    ```Shell
    ng new <AppName>
    ```

2. Create a new GitHub Repository https://github.com/new
3. Add a remote to your local git of your angular application you created in step 1.

    ```Shell
    git remote add origin https://github.com/{{username}}/{{RepoName}}.git
    ```

4. Build your application to a specific folder

    ```Shell
    ng build --base-href /{{RepoName}}/ --output-path ./docs  
    ```
    
    _You can add --prod as well to build the prod version of your code_

5. Git commit and Push your code to github

    ```Shell
    git add .
    git commit -m 'Initial Commit'
    git push -u origin master
    ```
6. Update github settings https://github.com/\{\{username\}\}/\{\{RepoName\}\}/settings/ and choose master branch docs folder. Now go to https://\{\{username\}\}.github.io/\{\{RepoName\}\}/. _You wont be able to select docs folder until the docs folder exists._

7. To publish your page you will need to push you application again. Updating your repo will tell github to kick off its processes

### To update your code
1. Make a change
2. Run step 4 from above
3. git commit and and git push

### Pros
* It's free
* It's easy

### Cons
* No database
* No refresh or deep linking - you might be able make something work using the pattern followed here but it wont be easy https://github.com/jekyll/jekyll-redirect-from

### Considerations
* API communication must be done over https, so your api server must be using a ssl certificate and running https.
    * By default you cannot turn off https but if you setup a custom domain you are then allowed to.
* If you host your own API server you must enable cors on your express server or other server for express see:
    * https://github.com/expressjs/cors
    * or this https://enable-cors.org/server_expressjs.html

