This application is a CMS front end built in React/Redux.
This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app). See requirements below. (Extra Credit project for Udacity React Nanodegree)

This project connects to a [Node backend server created by Udacity](https://github.com/udacity/reactnd-project-readable-starter). Server endpoints are used to manage storing, reading, updating and deleting data for the CMS.

## Requirements
### Data
There are three types of objects stored on the server:

* Categories
* Posts
* Comments

### Categories
The server supports a small, fixed number of categories that users can put posts into. Categories are simple objects containing a name and a URL path (usually the same string). The server does not have methods for creating/modifying/deleting these categories. If you wish to add to the categories for your app, simply add your desired object to the Array in `categories.js` in the provided server.

### Posts
Posts are the building blocks of your application. Posts include:

Attribute | Type | Description
--- | --- | ---
id | String	| Unique identifier
timestamp	| Integer	| Time created - default data tracks this in Unix time. You can use Date.now() to get this number
title	| String	| Post title
body	| String	| Post body
author	| String	| Post author
category	| String	| Should be one of the categories provided by the server
voteScore	| Integer	| Net votes the post has received (default: 1)
deleted	| Boolean	| Flag if post has been 'deleted' (inaccessible by the front end), (default: false)
### Comments
Comments are attached to parent posts. They include:

Attribute	| Type	| Description
--- | --- | ---
id	| String	| Unique identifier
parentId	| String	| id of the parent post
timestamp	| Integer	| Time created - default data tracks this in Unix time. You can use Date.now() to get this number
body	| String	| Comment body
author	| String	| Comment author
voteScore	| Integer	| Net votes the comment has received (default: 1)
deleted	| Boolean	| Flag if comment has been 'deleted' (inaccessible by the front end), (default: false)
parentDeleted	| Boolean	| Flag for when the the parent post was deleted, but the comment itself was not.

This application is anonymous, with _no_ authentication or authorization. There are no user objects, and comments and posts accept any username/name for creation and editing.

The server is very light weight. It performs zero data validation to enforce the above data types. Make sure you are using the correct types when sending requests to the server.

### Views
Your application should have, at a minimum, four views:

* Default (Root)
   * should list all available categories, which should link to a category view for that category
   * should list all of the posts
   * should have a control for changing the sort method for the list, including at minimum, order by voteScore and order by timestamp
   * should have a control for adding a new post
* Category View
  * identical to the default view, but filtered to only include posts with the selected category
* Post Detail View
  * should show the details of a post, including: Title, Body, Author, timestamp (in user readable format), and vote score
  * should list all of the comments for that post
  * should have controls to edit or delete the post
  * should have a control to add a new comment.
  * implement comment form however you want (inline, modal, etc.)
  * comments should also have controls for editing or deleting
* Create/Edit View
  * should have a form to create new post or edit existing posts
  * when editing, existing data should be populated in the form

**Post/Comment UI**

Posts and comments, in all views where they are displayed, should display their current score and should have controls to increment or decrement the voteScore for the object. Posts should display the number of comments associated with the post.

___

# CREATE REACT APP
## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.<br>
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.<br>
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.<br>
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.<br>
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.<br>
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (Webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: https://facebook.github.io/create-react-app/docs/code-splitting

### Analyzing the Bundle Size

This section has moved here: https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size

### Making a Progressive Web App

This section has moved here: https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app

### Advanced Configuration

This section has moved here: https://facebook.github.io/create-react-app/docs/advanced-configuration

### Deployment

This section has moved here: https://facebook.github.io/create-react-app/docs/deployment

### `npm run build` fails to minify

This section has moved here: https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify
