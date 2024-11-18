# Deployment of React Application using GitHub Pages

## Prerequisites
- A GitHub account
- Node.js and npm installed
- Basic knowledge of React and Git

## Why Use GitHub Pages for Deployment?
- Free Hosting: GitHub Pages offers free hosting for static websites, making it an ideal choice for deploying React applications.
- Easy Integration: Seamlessly integrate your GitHub repository with GitHub Pages.
- Automatic Updates: Automatically update your live site by pushing changes to your repository.

## Steps
### Step 1
- Create your react project.
  
Choose any one of the method
- `npx create-react-app my-app --template typescript`
- `yarn create react-app my-app --template typescript`
- `npm create vite@latest`

If you are using react-router-dom, add base url in the browser router or hash router.

### Step 2
- Adding the GitHub Pages dependency packages
- The gh-pages package allows us to publish the build file of our application into a gh-pages branch on GitHub, where we are going to host our application. Install the gh-pages dependency using npm

`npm install gh-pages --save-dev`

### Step 3
- Adding the properties to the package.json file
- The package.json file is been configured so that we can point the GitHub repository to where our react app is been deployed. The first property we have to add is at the top of the package.json file which will be given the name “homepage“, and the value for it will be in the following format

`"homepage": "https://<Username>.github.io/<Repository-name>"`

- Then we will add “deploy” and “predeploy “properties in the script field with the following values.
- If you have your build files under different folder name change the folder name in the scripts instead of build.

```
"scripts":{
    "predeploy": "npm run build",
    "deploy": "gh-pages -d build" 
}   
```

### Step 4
- Upload the project to git hub.

Note : Tips To Upload Existing Repo to your new repo

```
git init
git add .
git commit -m "first commit"
git branch -M main
```

`git remote add origin https://github.com/<username>/<rep Name>.git`

`git push -u origin main`

### Step 5
- And now finally deploy the application using the following command in the terminal
`npm run deploy`

- Get your websites link there else the url you have mentioned in the package.json as homepage will be your website url.

### Additional Notes
- Check git hub actions on your repositor to view your projects deployment status.
- The actions will re-run only if there is any changes in the UI file.
- If you are using Vite project you need to use `Hash Router` insetad of `Browser Router`,set baseurl in the vite.config file.
