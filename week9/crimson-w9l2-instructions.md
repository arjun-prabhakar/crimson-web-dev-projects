
## Core concepts

## 1. Making HTTP requests within a React component

### Explanation

Making HTTP requests is an essential task of the frontend. Within React, we make these requests at specific points: (1) after a user action (like a button click), or (2) at a certain point in the component lifecycle.

### Example

```jsx
// 1. After a user action
const Users = () => {
  const [users, setUsers] = useState([]);

  const fetchUsers = async () => {
    const response = await fetch("https://jsonplaceholder.typicode.com/users");
    const users = await response.json();

    setUsers(users);
  };

  return (
    <div>
      {
        // Do something with users...
      }
      <button onClick={fetchUsers}>Get users!</button>
    </div>
  );
};
```

Sometimes we also want to make HTTP requests before or after a component has been rendered/updated:

```jsx
// 2. At a certain point in the component lifecycle
const Users = () => {
  const [users, setUsers] = useState([]);

  const fetchUsers = async () => {
    const response = await fetch("https://jsonplaceholder.typicode.com/users");
    const users = await response.json();

    setUsers(users);
  };

  useEffect(() => {
    // Fetches users after component has rendered
    fetchUsers();
  }, []);

  return (
    <div>
      {
        // Do something with users...
      }
    </div>
  );
};
```

We send HTTP requests in React as a consequence of user interaction (like a button click) or when the component is rendered/updated. We do this is a separate function that we execute, either on an event (like `onClick`) or after a component has been rendered/updated (with `useEffect`).

# Dog photo gallery

Let's make a randomized dog photo gallery!

In this exercise we'll be using the following API endpoint: `https://dog.ceo/api/breeds/image/random`

1. Create 3 functional components: `<DogGallery>`, `<DogPhoto>` and `<Button>`
2. Inside `<DogGallery>` create a state variable called `dogPhotos` (initialize with value `[]`) and state handler `setDogPhotos`
3. Inside (before the return statement) also create a function called `getDogPhoto`. The purpose of this function is to make an API call to `https://dog.ceo/api/breeds/image/random`. You can either use `fetch` or `axios`. At the end of the function push the new `dog image URL` into the `dogPhotos` array state variable using `setDogPhotos`
4. Inside the `<Button>` component, create a `<button>` that has the text "Get a dog!" and `onClick` attribute
5. Pass down the function `getDogPhoto` to `<Button>`
6. Inside `<DogGallery>` return all the dogs stored in the `dogPhotos` array using the `map()` function. Pass down each `dogPhoto` into an instance of `<DogPhoto>`.
7. However, when there are no dogs in the array yet make sure to display the message "Get your first dog by clicking the button!"
8. Check your components by importing it into the top level component, which is `<App>`
9. Now write the tests!
