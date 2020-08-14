I always _forget_ how to deploy SPA applications like **Vue or React** in firebase hosting the process is easy so I decided finally to make a tutorial for I don't lose it and for whatever person that needs so let's begin.

What we'll cover in this tutorial

* Setup the firebase Hosting Project
* Installing the Firebase CLI
* Configuring your local project with environment variables
* Initialize Firebase Project using Firebase CLI Tools
* Deploy your application

# Setup the firebase Hosting Project
We can this two ways using the **website or firebase-cli**

**Step 1 - Register**
First, we need to register our project in [firebase](https://console.firebase.google.com/)

![Register](https://raw.githubusercontent.com/JesusRMendez/DevTo/master/firebase-create-project.png?token=AAMMAZ5GQNOQUIWKYCXWD5K7GYSAE)

**Step 2 - Install Firebase CLI**
```
npm install -g firebase-tool
``` 

**Step 3 - Log in with Firebase client**
```
firebase login
```
So the browser will open to enable you to select your Google account. Once you complete the authentication process the following webpage will be display

![IMAGE](https://raw.githubusercontent.com/JesusRMendez/DevTo/master/firebase-cli-sucess.png)

#Configuring your local project with environment variables 
First, if you already have your project you only need to add the files:

* `.env`
* `.env.development`
* `.env.production`

the content the file is:
```
VUE_APP_FIREBASE_API_KEY=''
VUE_APP_FIREBASE_DOMAIN=''
VUE_APP_FIREBASE_DB_URL=''
VUE_APP_FIREBASE_PROJECT_ID=''
VUE_APP_FIREBASE_STORAGE_BUCKET=''
VUE_APP_FIREBASE_MESSAGING_SENDER_ID=''
VUE_APP_FIREBASE_API_ID=''
VUE_APP_FIREBASE_MEASUREMENT_ID=''
```
Of course, every file you can fill with correct value depends on the environment.

> Note that all variables that start with `VUE_APP_` will be statically embedded into the client bundle with `webpack.DefinePlugin` 

# Initialize Firebase Project using Firebase CLI Tools
We now initialize the firebase project with Firebase-CLI tools in our local project app directory executing the following command.

```
firebase init
```
* **Step 1**
We choose _Hosting_

Output:
![IMAGE](https://github.com/JesusRMendez/DevTo/blob/master/firebase-cli-init.png)

* **Step 2**
The next step we asked if we won't use the existing project or make a new project from the console, for this tutorial we choose:  **use and existing project.**

![Image](https://github.com/JesusRMendez/DevTo/blob/master/firebase-association-project.png)

* **Step 3**
The next step of the wizard is the settings for the application, so when is asked about **public directory** we answer write `dist` because by default in **vuejs** we make `npm run build` we have output in folder `dist`, so the next question we answered with `Y` or `Yes`.

Output: 
![IMAGE](https://github.com/JesusRMendez/DevTo/blob/master/firebase-setting.png)

> Note: If later we want to change where is output our `dist` we only updated the file `firebase.json`

# Deploy your application

So, finally the deploy we only need to execute two commands.

First, we build our Vue project:
```
npm run build
```
We expect the next output:

![IMAGE](https://github.com/JesusRMendez/DevTo/blob/master/output-vue-build.png)

And the last command

```
firebase deploy
```
**Output:**
![IMAGE](https://github.com/JesusRMendez/DevTo/blob/master/output-vue-deploy.png)
![IMAGE](https://github.com/JesusRMendez/DevTo/blob/master/firebase-deploy-webpage.png)


