# Modern UI/UX with React
Creating a modern UI/UX React App

## Creating a React Application
- After install npm, type ``` npx create-react-app ./ ``` in the terminal (inside the folder of your project)
> The parameter ./ just create the React App inside your folder, without giving another name for that.

![image](https://user-images.githubusercontent.com/39681960/203071628-97e27885-60e0-4d7a-97d6-da8685c8e7dd.png)

Obs: we will remove all the subfolders of the Source folder (src) to understand how the things work inside a React Project.

### Creating index.js file
The most important file inside this folder is *index.js*, that has the following code:
  ```
  import React from 'react';
  import ReactDOM from 'react-dom'; 
  
  import App from './App';
  
  ReactDOM.render(<App />, document.getElementById('root'));
  ```
> The ReactDOM is used just in this file, to access the *index.html* file in the *public* folder and render all the React Application (the *App* component) inside the *root* div element of this HTML file.

![image](https://user-images.githubusercontent.com/39681960/203074964-9d100b58-a498-4cad-90e6-df91c7631446.png)

### Creating the App.js component file
To create the App component, let's take advantage of the ES7 Snippets extension: type **rafce** + **TAB** in the new file to see the miracle:
> This extension automatically will provide you the structure of a **React Arrow Function Export Component** .
  
![image](https://user-images.githubusercontent.com/39681960/203076982-b32ef4b4-2ae0-45a2-99ad-df50e7ae9b38.png)

### Instaling the single dependency of the project
Install the react-icons dependency: ``` npm install react-icons ```

### Creating the folders structure of the components of the project
1. Create the *components* folder and its subfolders: *article*, *brand*, *cta*, *feature*, *navbar* ;
2. Each subfolder will have two kinds of corresponding files: [subfolder_name].jsx (Functional Component) , [subfolder_name].css :

![image](https://user-images.githubusercontent.com/39681960/203083123-b4d7edc4-859f-46c6-91fd-4d31f92a5d73.png)

> The same thing showed in the image above must be done to all subfolders.

3. After create all these components files (Step 2), you would have to import all of them for you App component, one by one:

![image](https://user-images.githubusercontent.com/39681960/203100049-d3422c0a-4106-4c07-89e6-ba8623491b65.png)

There's a better way to do this:
  - Create an *index.js* file inside the *components* folder and make this file export all components as default:
  
  ![image](https://user-images.githubusercontent.com/39681960/203100851-91788197-0818-419f-8f61-edceb0260896.png)

  - Now we can import all these components in a single line of the App component:
  
  ![image](https://user-images.githubusercontent.com/39681960/203102258-4c9615f0-5d61-4036-a2d7-18c59186a3d4.png)

### Creating the containers folder structure 
A Container can be used as sections that contains multiples components.
1. Create the *containers* folder and its subfolders: *blog*, *features*, *footer*, *header*, *possibility*, *whatGPT3* ;
2. Each subfolder will have two kinds of corresponding files: [subfolder_name].jsx (Functional Component) , [subfolder_name].css;
3. The same way as before, let's create an *index.js* file inside de containers folder to facilitate the import of containers

The index.js file is:
```
export { default as Blog} from './blog/Blog'
export { default as Features} from './features/Features'
export { default as Footer} from './footer/Footer'
export { default as Header} from './header/Header'
export { default as Possibility} from './possibility/Possibility'
export { default as WhatGPT3} from './whatGPT3/WhatGPT3'
```

The App.js component will import and use the components and containers as shown below:
```
import React from 'react';

import { Blog, Features, Footer, Header, Possibility, WhatGPT3 } from './containers';
import { CTA, Brand, Navbar} from './components';

const App = () => {
  return (
    <div className="App">
        <div className='gradient__bg'>
            <Navbar />
            <Header />
        </div>
        <Brand />
        <WhatGPT3 />
        <Features />
        <Possibility />
        <CTA />
        <Blog />
        <Footer />
    </div>
  )
}

export default App
```

Now we have all the structure of the application project ready to be developed:

![image](https://user-images.githubusercontent.com/39681960/203128119-d084c3f1-cea9-40f7-a1e1-d45884689e51.png)

Obs: the question is: how these elements were chosen as containers or components? Header, Footer and Blog is clearly sections of the page, so it's clearly containers; Brand is clearly a component but the other ones are not so clear like that. 
> Let's continue and see if this question will be answered in future.

## CSS style for general components
To define a general style for the project, we have to use a stylesheet for the App.js component, that is the general component of the project. And, another stylesheet for the index.js component, that we will name it as index.css component. 
> See that we informed App as a className of the main div inside the App.js component. So, we need to create the App.css file in src folder, corresponding to this className that will be evolving all another stylesheet of the project (the parent of those stylesheets).
1. App.css code:
```
* {
    box-sizing: border-box;
    padding: 0;
    margin: 0;
    scroll-behavior: smooth;
}

body {
    background: var(--color-bg);
}

a {
  color: unset;
  text-decoration: none;
}
```
> The * means that all components will be defined by that style. </br>
> The background of the body page will receive the variable --color-bg, defined in the index.css file. 

2. index.css code:
```
@import url('https://fonts.googleapis.com/css2?family=Manrope:wght@200;300;400;500;600;700;800&display=swap');

:root {
  --font-family: 'Manrope', sans-serif;

  --gradient-text: linear-gradient(89.97deg, #AE67FA 1.84%, #F49867 102.67%);
  --gradient-bar: linear-gradient(103.22deg, #AE67FA -13.86%, #F49867 99.55%);
  
  --color-bg: #040C18;
  --color-footer : #031B34;
  --color-blog: #042c54;
  --color-text: #81AFDD;
  --color-subtext: #FF8A71;
}
```
> Import the App.css file in the App.js component and the index.css file in the index.js component.

## Creating a gradient for the background page
Link: https://angrytools.com/gradient

## Developing the first container: Navbar












#### Shortcuts for VS Code
1. Selecting the same word in a file: double click on the word + **CTRL** + **D** (as many as equal words you would like to select)
2. Copying a line and paste it below: **ALT** + **SHIFT** + **UP/DOWN ARROW**

## Referency:
JavaScript Mastery (Youtube Channel): https://www.youtube.com/watch?v=F627pKNUCVQ&t=7624
