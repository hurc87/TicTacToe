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

* 
