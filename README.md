# crwn-clothing-contextapi

Replace local state management from redux to the new context API.


## After you fork and clone:
```bash
~ git clone https://github.com/oussamabouchikhi/crwn-clothing-contextapi.git
```

## Install dependencies

To install all project dependencies, run these commands
```bash
#1. 
~ cd crwn-clothing-contextapi
#2. 
~ yarn
# or
~ npm install
```

## Set your firebase config

Remember to replace the `config` variable in your `firebase.utils.js` with your own config object from the firebase dashboard! Navigate to the project settings and scroll down to the config code. Copy the object in the code and replace the variable in your cloned code.

![alt text](https://i.ibb.co/6ywMkBf/Screen-Shot-2019-07-01-at-11-35-02-AM.png "image to firebase config")


## Set your stripe publishable key 

Set the `publishableKey` variable in the `stripe-button.component.jsx` with your own publishable key from the stripe dashboard.

![alt text](https://i.ibb.co/djQTmVF/Screen-Shot-2019-07-01-at-2-18-50-AM.png "image to publishable key")

## Things to set before you deploy

You will also need to connect your existing Heroku app to this new forked and cloned repo, or you have to create a new Heroku app and push to it. A quick refresher on how to do either of these:

<details>
<summary>Set to an existing Heroku app</summary>

To set to an existing Heroku app you already have deployed, you need to know the name of the app you want to deploy to. To see a list of all the apps you currently have on Heroku:

```
heroku apps
```

Copy the name of the app you want to connect the project to, then run:

```
heroku git:remote -a <PASTE_YOUR_APP_NAME_HERE>
```

And now you'll have your repo connected to the heroku app under the git remote name `heroku`.

Then skip to the bottom of this article to see what to do next!
</details>

<details>
<summary>Create a new Heroku app</summary>
<br>
Create a new Heroku project by typing in your terminal:

```
heroku create
```

This will create a new Heroku project for you. Then run:

```
git remote -v
```

You should see heroku `https://git.heroku.com/<RANDOMLY_GENERATED_NAME_OF_YOUR_APP>` in the list. This means you have successfully connected your project to the newly created Heroku app under the git remote of `heroku`.
</details>

<details>
<summary>Deploying to Heroku</summary>

Add the `mars/create-react-app-buildpack` to your heroku project by typing:

```
heroku buildpacks:set mars/create-react-app-buildpack
```

You can then deploy to heroku by running:

```
git push heroku master
```

You will see this warning message if you are pushing to an existing app:

```
! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'https://git.heroku.com/hasura-crwn-clothing.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

This is because we are pushing to an existing app that was deploying an entirely different repository from what we have now. Simply run:

```
git push heroku master --force
```

This will overwrite the existing Heroku app with our new code.

</details>

<details>
<summary>Open our Heroku project</summary>

After heroku finishes building our project, we can simply run:

```
heroku open
```

This will open up our browser and take us to our newly deployed Heroku project!
</details>
