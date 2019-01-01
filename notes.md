#Setting up the react app

* Creates a react app

        npx create-react-app my-app

(npx on the first line is not a typo — it’s a package runner tool that comes with npm 5.2+.)

* Go to the my-folder and running npm start will start server

        cd my-app
        npm start

* Delete everything in src folder as not needed

        cd my-app
        cd src

        rm -f *

* Create index.js and index.css. At top of index.js type:

        import React from 'react';
        import ReactDOM from 'react-dom';
        import './index.css';

#Notes on React

* A React component class, or React component type, takes in parameters, called props (short for “properties”), and returns a hierarchy of views to display via the render method.

* The render method returns a description of what you want to see on the screen. React takes the description and displays the result. “JSX” makes these structures easier to write. So a normal <div> would be transformed at build time but would be the equivalent to
      return React.createElement('div');

* You can put any JavaScript expressions within braces inside JSX. Each React element is a JavaScript object that you can store in a variable or pass around in your program.

* To “remember” things, components use state.

* React components can have state by setting this.state in their constructors. this.state should be considered as private to a React component that it’s defined in.

Add a constructor to the class to initialize the state.

* In JavaScript classes, you need to always call super when defining the constructor of a subclass. All React component classes that have a constructor should start it with a super(props) call.

* By calling this.setState from an onClick handler in the Square’s render method, we tell React to re-render that Square whenever its <button> is clicked. After the update, the Square’s this.state.value will be 'X', so we’ll see the X on the game board. If you click on any Square, an X should show up.

When you call setState in a component, React automatically updates the child components inside of it too.

* The React DevTools let you check the props and the state of your React components.
