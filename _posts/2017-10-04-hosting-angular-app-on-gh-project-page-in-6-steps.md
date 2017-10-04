---
layout: post
title:  "Hosting an Angular app on github project page in 6 steps"
author: JoA-MoS
category: Dev
tags: [angular, github pages]
---

1. Create a new Angular Application
2. Create a new GitHub Repository
3. Add a remote to your local git of your angular application
4. Build your application to a specific folder

    ```
    ng build --base-href /{{RepoName}}/ --output-path ./docs  
    ```
    
    _You can add --prod as well to build the prod version of your code_

5. Git commit and Push your code to github
6. Update github settings https://github.com/\{\{username\}\}/\{\{RepoName\}\}/settings/ and choose master branch docs folder. Now go to https://\{\{username\}\}.github.io/\{\{RepoName\}\}/

_Note: You may have to push again to get the page to publish_

## To update your code
1. Make changes
2. run step 4
3. git commit and and git push

## Pros
* It's free
* It's easy

## Cons
* No database
* No refresh or deep linking - you might be able make something work using the patern followed here but it wont be easy https://github.com/jekyll/jekyll-redirect-from

## Considerations
* API communication must be done over https, so your api server must be using a ssl certificate and running https
* If you host your own API server you must enable cors on your express server or other server for express see:
    * https://github.com/expressjs/cors
    * or this https://enable-cors.org/server_expressjs.html

