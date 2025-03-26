# html-edublocks-to-electron
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
 ```
 powershell -c "irm https://community.chocolatey.org/install.ps1|iex"
```

 -Install Node.js through Chocolotey
 ```
 choco install nodejs-lts --version="22"
```

 -Verify Installation
 ```
 node -v
```

 # MacOS
 -Install Homebrew
 ```
 curl -o- https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh | bash
```

 -Install Node.js through Homebrew
 ```
 brew install node@22
```

 -Verify Installation
 ```
 node-v
```

 # Linux
  -Install Homebrew
  ```
 curl -o- https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh | bash
```

 -Install Node.js through Homebrew
 ```
 brew install node@22
 ```

 -Verify Installation
 ```
 node-v
```

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
-Paste your EduBlocks code into your index.html file (Here is mines for example)

```html
<style>
  body {
    background-color: #ffffff;
  }
</style>
<html>
  <head>
    <title>My Website!</title>
  </head>
  <body>
    <header class="header">
      <h1>My Simple Website</h1>
    </header>
    <div class="prgh1">
      <p>This is my simple website that shows most of the basics features you might want.</p>
    </div>
    <hr>
    <section class="pizzaimg">
      <h2>Image</h2>
      <img src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse1.mm.bing.net%2Fth%3Fid%3DOIP.D4lCG7dGjMJwO07EHm1uIQHaHa%26pid%3DApi&f=1&ipt=b8037f6bad283f7bb0157b6a48fa0269d529958dfd1f4408fcf0b7175dbd762c&ipo=images">
    </section>
    <hr>
    <section class="pizzavid">
      <h2>Video</h2>
      <p>I don't have a server to host it on and YouTube embeds don't work :( sorry</p>
    </section>
    <hr>
    <section class="form">
      <h2>Form</h2>
      <p>Input something into the text box below </p>
      <p>(breaks everything at the moment)</p>
      <form>
        <input type="text">
      </form>
    </section>
    <hr>
    <section class="table">
      <h2>Table</h2>
      <table border="1">
        <tr>
          <th>
            Football Players
          </th>
          <th>
            Baseball Players
          </th>
        </tr>
        <tr>
          <td>
            62
          </td>
          <td>
            38
          </td>
        </tr>
      </table>
    </section>
    <hr>
    <section class="list">
      <h2>Lists</h2>
      <ol>
        <li>
          <p>list1</p>
        </li>
        <li>
          <p>list2</p>
        </li>
        <li>
          <p>list3</p>
        </li>
      </ol>
    </section>
    <hr>
    <footer>
      <p>Everett was here :)</p>
    </footer>
  </body>
</html>
```

-Paste this into your main.js file

```javascript
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
```
### Final Step

-When you are all done, you can run the command below in VsCode to run your Electron app to make your EduBlocks website into a desktop app.
```
npm start
```


