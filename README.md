# Multi-Developer Workflow 
Example repository for best practice. 

## Installation
We are using Docker, Git Flow, and Gulp for local development

#### To install Docker: 
 - Download the [Docker Engine](https://www.docker.com/products/overview) that is for your system (windows, mac)
 - Also download the Docker Toolbox for [Mac](https://docs.docker.com/engine/installation/mac/) or [Windows](https://docs.docker.com/engine/installation/windows/).

#### To install NPM 
 - Go to the [Node Website](https://nodejs.org/en/) and download the latest version recommended for most users. 

#### To Install Gulp
 - In Terminal, no matter what folder, type `npm install --global gulp-cli` on windows and `sudo npm install --global gulp-cli` on mac, entering your password.


## Development
- Clone the repository
- Navigate to the project folder
- Run `docker-compose up`
    - Alternatively, click the start button in Kitematic next to this project's container.
- Open Kitematic to make sure the virtual machine has been created (should be visible on the side)
- Also in the project folder (but in a new terminal window/tab), run `gulp`
- Navigate to `localhost:8000` in your web browser.

#### Debugging: 
- "Help! `localhost:8000` returns an error in the browser!"
  Check to make sure that the docker container is running in kitematic. This is signified by a green circle with a flowing wave within it next to the container name.
- "Help! I'm editing my sass and javascript files, but they're not being updated!"
  You likely forgot to run `gulp` in the terminal. This is essential, as your html files are looking in the `dist` folder but you are editing in the `src` folder. 

### Guidelines: 

#### CSS (SCSS)

##### Components
- All major site components should be saved as their own `.scss` file in the form of `_[Component Name].scss`.
    - The file's name should be preceeded by an underscore in order to prevent the sass compiler from producing errors in reference to variables.
- Every component file should open up with a few variables to quickly customize things like colors. Consult with `_nav.scss` for reference.
- Remember to include the component file in `app.scss` with the following code: `@import 'components/[Component Name]';` with the rest of the components. 

##### Classes
- Use the [BEM](http://getbem.com/) naming convention for css classes. 
- All elements should have a class. __Do Not__ style a bare element (i.e., nothing like this: `a { font-size:11px }`)
- If you feel a bare element style is necessary, contact Tim
- Feel free to create as many utility classes in the form of `.u-[Class Name]` in `_utilities.scss`.


#### Javascript
- We are ***NOT*** using jQuery for this project as it will bloat the code unecessarily. 
- Some helper functions inspired by the jQuery library have been written in the `utilities.js` file. 
- Like CSS, each component should have its own javascript file. 
    - Each file should be wrapped in an IIFE
- Put lots of comments, especially in describing what each function does. 
