# Fix MongoDB's 'How to Use MERN Stack' code breakages
Recent updates to dependencies used in MongoDB's [How to use MERN stack guide](https://www.mongodb.com/languages/mern-stack-tutorial) introduce several app-breaking changes. Most notably React Router's need to wrap `<Route />` components with `<Routes></Routes>` tags, as well as moving to the `useNavigate` hook.

While you could simply install the same dependency version listed in MongoDB's package.json, I wanted to roll with the newer updates and teach myself a thing or two in the process of troubleshooting.

## What was changed

The main change is in the edit.js file (within client > src > components), which has been refactored into a functional component and now uses useState and useEffect hooks, as well as useParams and useNavigate from react-router/react-router-dom.

Additionally, an update was made to App.js (within client > source), wrapping `<Route />` components with `<Routes></Routes>`. Note, the `<Route />` components also required a little refactoring due to changes with the react-router dependency.

## What else?

You will still need to create a `config.env` file. I have not included it in my repo because, y'know, credentials, but you will still need to create one in `server` folder:
```
ATLAS_URI=mongodb+srv://<username>:<password>@cluster0.hf3t4.mongodb.net/myFirstDatabase?retryWrites=true&w=majority
PORT=5000
```

## Dependencies
This code uses the following dependencies:

### Server dependencies
- "cors": "^2.8.5",
- "dotenv": "^10.0.0",
- "express": "^4.17.1",
- "mongodb": "^4.2.0"

### Client dependencies
- "@testing-library/jest-dom": "^5.11.4",
- "@testing-library/react": "^11.1.0",
- "@testing-library/user-event": "^12.1.10",
- "axios": "^0.24.0",
- "bootstrap": "^5.1.3",
- "react": "^17.0.2",
- "react-dom": "^17.0.2",
- "react-router-dom": "^6.0.2",
- "react-scripts": "4.0.3",
- "web-vitals": "^1.0.1"