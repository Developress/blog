# Ruby blog
This repo is made from 2 separate repos [blog-frontend](https://github.com/Developress/blog-frontend)
and [blog-backend](https://github.com/Developress/blog-backend). The full commit history can be viewed by the links
provided

## How to run the app
Change the current directory to ```blog``` after cloning the repository
and run the command  
```sudo docker-compose up```  
You may encounter some errors with docker-entrypoint.sh due to
the permission denied, try to run this  
```chmod 755 blog-backend/docker-entrypoint.sh```  
And then repeat the previous command

## Config uploading images to S3 bucket
This feature was implemented in the project, but you need
to set some env variables so that can wok properly
  
Create ```.env``` file in ```blog-frontend``` directory and set
the following variables

```
REACT_APP_ACCESS_KEY_ID=*your AWS access key id*
REACT_APP_SECRET_KEY_ID=*your AWS secret key id*
REACT_APP_BUCKET_NAME=*your S3 bucket name*
```

## Features implemented
- getting started
- authentication with different users
- authorization(partly)   
Users are not allowed to view the page with posts if not
  authenticated, and they can't change and delete posts created
  by other users
    
- filtering posts by categories
- searching posts by title
- uploading images to S3 bucket(env variables, listed above must be specified)
- unit tests, testing models, routes and requests, run when
containers start
  
- JSON API and Client (backend was made using REST architectural
  principles and separate frontend app in React was created)
  
- Docker compose (consists of 3 containers: frontend, backend and database)