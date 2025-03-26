# edublocks-to-electron
Transfer your EduBlocks code into an Electron app.

# Step One

### Create your EduBlocks project and code it.

# Step Two

### Get your EduBlocks text code
- This is done by clicking on the code button above your preview.
- Once there, press Ctrl+A or Cmd+A depending on OS to select all the code
- Then press Ctrl+C or Cmd+C to copy the code

# Step Three
Instal Node.js on your desktop

 # Windows
 -Install Chocolotey
 powershell -c "irm https://community.chocolatey.org/install.ps1|iex"

 -Install Node.js through Chocolotey
 choco install nodejs-lts --version="22"

 -Verify Installation
 node -v

 # MacOS
 -Install Homebrew
 curl -o- https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh | bash

 -Install Node.js through Homebrew
 brew install node@22

 -Verify Installation
 node-v

 # Linux
  -Install Homebrew
 curl -o- https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh | bash

 -Install Node.js through Homebrew
 brew install node@22

 -Verify Installation
 node-v

 # Step Four
 
### Make a new Electron/Node.js Project in your IDE, preferably VsCode
(Make sure you have JavaScript and HTML extensions installed on VsCode)
-Open the folder you want to install the app onto in VsCode
-Initilize the project as a Node.js project by running this command in the VsCode terminal
npm init -y
-You should see a package.json file pop up in your file explorer
-Install Electron through the VsCode terminal by running this command
npm install electron --save-dev

# Step Five

### Create the needed files for transfer
-Create a main.js file and an index.html file in your folder
-Paste this into your main.js file

const { app, BrowserWindow } = require('electron');
const path = require('path');

function createWindow() {
  const win = new BrowserWindow({
    width: 800,
    height: 600,
    webPreferences: {
      nodeIntegration: true,
    },
  });

  win.loadFile(path.join(__dirname, 'index.html')); // Load your local HTML file
}

app.whenReady().then(createWindow);

-

