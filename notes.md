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


* To collect data from multiple children, or to have two child components communicate with each other, you need to declare the shared state in their parent component instead. The parent component can pass the state back down to the children by using props; this keeps the child components in sync with each other and with the parent component. (Known as lifting state)


* By adding the following to the Board class :

        renderSquare(i) {
          return (
            <Square
              value={this.state.squares[i]}
              onClick={() => this.handleClick(i)}

            />
          );
        }
It passes props down from the parent class (Board) to the child class (Square).

* Breakdown of the onClick method passed from parent to child:
  The onClick prop on the built-in DOM <button> component tells React to set up a click event listener.

  When the button is clicked, React will call the onClick event handler that is defined in Square’s render() method.

  This event handler calls this.props.onClick(). The Square’s onClick prop was specified by the Board.

  Since the Board passed onClick={() => this.handleClick(i)} to Square, the Square calls this.handleClick(i) when clicked.

  We have not defined the handleClick() method yet, so our code crashes.

* The DOM <button> element’s onClick attribute has a special meaning to React because it is a built-in component. For custom components like Square, the naming is up to you. We could name the Square’s onClick prop or Board’s handleClick method differently. In React, however, it is a convention to use on[Event] names for props which represent events and handle[Event] for the methods which handle the events.

* Since the Square components no longer maintain state, the Square components receive values from the Board component and inform the Board component when they’re clicked. In React terms, the Square components are now controlled components. The Board has full control over them.

* In onClick we used slice, this creates a copy of original array for us to use, rather than changing the original array. Examples below are :

  Data change with Mutation :

        var player = {score: 1, name: 'Jeff'};
        player.score = 2;
        // Now player is {score: 2, name: 'Jeff'}

  Data change without Mutation:

        var player = {score: 1, name: 'Jeff'};

        var newPlayer = Object.assign({}, player, {score: 2});
        // Now player is unchanged, but newPlayer is {score: 2, name: 'Jeff'}

        // Or if you are using object spread syntax proposal, you can write:
        // var newPlayer = {...player, score: 2};

* 
