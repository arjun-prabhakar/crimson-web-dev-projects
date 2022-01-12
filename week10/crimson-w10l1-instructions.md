
## Core Concepts

1. Client-side routing

- Server-side routing is the norm, but with rise of modern JavaScript and SPAs came **client-side routing**
- On URL change **no request to server** (and thus no page refresh), **only changed state of app and URL adjustment**
- For React, third-party library **React-Router** is most popular
- Most important concepts: `<BrowserRouter />`, `<Route />`, `<Link />`, `<Switch />`, the `location` prop and `history` object

_Explain the following example: [Basic Example](https://reacttraining.com/react-router/web/example/basic)_


## Build with students

To illustrate the workings of React-Router build the following small app with the students.

- [Basic Router](../../examples/router-example)

Make a basic navigation menu that uses React-Router.

- Use `react-router-dom`
- Render a different component for each route

2. Server-side routing

- Routing refresher: the mechanism by which `requests` (as specified by a URL change or HTTP method) are `send to an endpoint on the server`, that then executes code that handles the request.
- Server-side routing happens `when the client sends a request to the server`, usually **triggered by a URL change**

## 2. Global state with `context API`

- Context provides a way to pass data through the component tree without having to pass props down manually at every level.
- Context is designed to share data that can be considered “global” for a tree of React components, such as the current authenticated user, theme, or preferred language.

_Show instance of how to create `context`, pass down the `Provider` and `Consumer` and show the value. After, have the students do the same_

# Today's Exercise: Copy to clipboard
Can you make a hook that takes a user input and copies it to their computer's clipboard?

1. Create a new application via `create-react-app`
2. Add a new component, with a simple text field the user can type in.
3. Add another component consisting of a button.
4. Store the user's entry. (Bonus question: How should you store this value? In the component? Context API? App.js?)
5. It's time to make our hook!

- Create a `hooks` folder in your project, and inside create a file called `useCopy.js`.
- Create (and export!) a function called `useCopy` and inside create another function `handleCopy`.
- Handle copy should take one string as a parameter, copy that parameter to the clipboard.
- For that, we're going to need the [navigator object](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/clipboard). Look for the method that adds text to the user's clipboard.
- Return the `handleCopy` function. (For a familiar syntax, you might want to export it like so: `return [handleCopy]`.)

6. Import `handleCopy` from the `useCopy` function. Based on how you've stored the user input, you will need to call it in different places, but be sure it is triggered by a button click.
7. Let's see if it works!
