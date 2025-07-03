# _How to Set Up a React App on the CyVerse VS Code Server_

### Step 1: Configure your VScode server with all the basic installations.
If you haven't already, visit this page about the [base installations in VS Code](exampleurl) and follow the instructions to prep your workspace. This is to ensure that your app has the correct extensions and MCP servers to install correctly.

### Step 2: Create a React App
In your bash terminal, type or copy/paste this code. This will create a basic react app by accessing [React's](https://react.dev/) official [create-react-app github repository](https://github.com/facebook/create-react-app), which contains the rules and instructions for your computer. 

```bash
cd /config
npx create-react-app (your-app-name)
cd (your-app-name)
```
### Step 3: Clone its files
In order to work with your newly created react app, you need to be able to edit the code in real time. Go to the explorer on the left side of your screen, the icon should look like this.

<img width="50" alt="image" src="https://github.com/user-attachments/assets/9fea97f5-f499-4877-a78e-d141515fa8ec" />

Then click on open folder and from the dropdown menu, choose the folder that has your react app's name on it. The `/config` directory should automatically show up in the search bar, your react app's files live inside it.


### Step 4: Build for Production with Correct Path
For your app to be hosted on the correct proxy network, we need to make a few changes to the protocol path. Add this code to your bash terminal.
```bash
PUBLIC_URL=/proxy/3001 npm run build
npx serve -s build -l 3001 -n
```

### Step 5: Access Your App
Your app should be up and functioning, visit a url that looks like https://#your-cyverse-url.cyverse.run/proxy/3001/.

If your not sure what your cyverse url is, you can just click on "Ports" next to your terminal. Then click on the globe icon that appears when you hover your cursor over the number 3001 to open your app in another browser tab.

<img width="230" alt="image" src="https://github.com/user-attachments/assets/f155d024-4b64-4f3f-a5f0-c99c4c203ba6" />


## This is what your screen should look like at the end.
![image](https://github.com/user-attachments/assets/41e5fe11-b450-4505-993b-6ea3cc34a733)

# For Future Development:

Make changes to your React code

Run `PUBLIC_URL=/proxy/3001 npm run build`

Run `npx serve -s build -l 3001 -n`

Refresh your browser

# Key Points:

Don't use the development server (npm start) with CyVerse - it doesn't work with the proxy

Always build for production with the correct PUBLIC_URL=/proxy/3001

Use a simple static server like serve to host the built files

The URL structure is always https://your-instance.cyverse.run/proxy/PORT/



### _That's it! This workflow will work every time with CyVerse, good job!_
