### Steps to setup Vite, React, TypeScript, and Tailwind CSS with their latest versions.

## Step 1 - Create Your Project

`npm create vite@latest`

It will ask for your project name, select framework as React and select TypeScript for the variant.

![image](https://github.com/user-attachments/assets/2728b4dc-a221-4099-b505-630661ea7464)

This will create a directory named vite-project with typescript configurations.

Now, we need to enter the vite-project directory, install the necessary packages, and run the project. So, enter the commands given below in the terminal

```
cd vite-project
npm install 
npm run dev
```

### Step 2 - Install Tailwind CSS and Other Dependencies
We need to install tailwindcss, postcss, and autoprefixer

`npm install -D tailwindcss postcss autoprefixer`

This will install
- The Tailwind CSS framework
- Post CSS is a tool for transforming CSS with JavaScript plugins. Tailwind CSS uses PostCSS to process its CSS.
- Autoprefixer, which is a PostCSS plugin that parse CSS and add vendor prefixes to CSS rules.
Make sure these dev dependencies are added in your package.json file.

### Step 3 - Generate the Configuration Files

- Input the command below in your terminal

`npx tailwind init -p`

This command will generate tailwind.config.js and postcss.config.js configuration files; these will help you to interact and customize your project.

### Step 4 - Configure Source Path for Tailwind CSS

- Now, we need to add the path of our template files in our **tailwind.config.js** file. Template files include HTML templates, JavaScript components, and other source files that contain Tailwind class names. This is to make sure that vanilla CSS is generated for the corresponding elements.

Currently, your **tailwind.config.js** file will look like this:
![image](https://github.com/user-attachments/assets/1d4d12e2-e447-4640-bf34-f96729c0c45f)

- We will add `"./index.html", "./src/**/*.{js,ts,jsx,tsx}"` this in our content section.

Now our tailwind.config.js file will look like this
![image](https://github.com/user-attachments/assets/e9bf5940-331f-4685-bce4-aae938a8af93)

- Make sure that you don’t add space in between them *.{js,ts,jsx,tsx}

### Step 5 - Adding Tailwind Directives to your CSS

- Tailwind directives are custom Tailwind-specific statements that instruct Tailwind CSS to process certain features or configurations during the build process.
- We need to add the statements given below in our **index.css** file. But before that, clear all the content of the **index.css** file and add the Tailwind directives:

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```
- The directives are used to include the respective parts of Tailwind CSS in your CSS files. These directives are commonly used within your CSS files to ensure that the base styles, component styles, and utility classes provided by Tailwind CSS are included in the final output.

- You can also remove **App.css file**.

### Step 6 — Start using Tailwind CSS

Now, we can start using tailwind. Open your App.tsx file, and now you can use Tailwind CSS classes
![image](https://github.com/user-attachments/assets/1492d1ca-ee46-4b5f-8844-cb57253e4a1a)

Now start your server using

`npm run dev`


