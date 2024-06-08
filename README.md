# Blog Project

This is a simple blog application built using Node.js, Express.js, EJS, and MongoDB. The application allows users to compose new blog posts, view them on the home page, and read individual posts.

## Table of Contents
- [Directory Structure](#directory-structure)
- [File Descriptions](#file-descriptions)
  - [`app.js`](#appjs)
  - [`package.json`](#packagejson)
  - [Views (`views` folder)](#views-views-folder)
  - [Public (`public` folder)](#public-public-folder)
- [How to Run](#how-to-run)
- [Routes](#routes)
- [Example Data](#example-data)
- [Dependencies](#dependencies)
- [Additional Information](#additional-information)
  - [MongoDB Connection](#mongodb-connection)
  - [EJS Templates](#ejs-templates)
  - [CSS Styles](#css-styles)
- [Contributions](#contributions)

## Directory Structure

```bash
home-ejs
├── public
│   └── css
│       └── styles.css
├── views
│   ├── partials
│   │   ├── header.ejs
│   │   └── footer.ejs
│   ├── about.ejs
│   ├── compose.ejs
│   ├── contact.ejs
│   ├── home.ejs
│   └── post.ejs
├── .gitignore
├── app.js
├── package-lock.json
└── package.json
```

## File Descriptions

### `app.js`
The main file that sets up the Express server, connects to the MongoDB database, defines the routes, and renders the EJS templates.

### `package.json`
Contains the project's metadata, including dependencies like Express, EJS, Mongoose, and Body-Parser.

### Views (`views` folder)
- `about.ejs`: Renders the About page.
- `compose.ejs`: Provides a form to compose new blog posts.
- `contact.ejs`: Renders the Contact page.
- `home.ejs`: Displays all blog posts on the home page.
- `post.ejs`: Displays individual blog posts.
- `partial/header.ejs`: Header partial to be included in other EJS files.
- `partial/footer.ejs`: Footer partial to be included in other EJS files.

### Public (`public` folder)
- `css/styles.css`: Contains the CSS styles for the application.

## How to Run

1. **Clone the Repository**
    ```bash
    git clone <repository-url>
    cd Blog
    ```

2. **Install Dependencies**
    ```bash
    npm install
    ```

3. **Start MongoDB**
    Ensure that MongoDB is installed and running on your system.

4. **Run the Application**
    ```bash
    node app.js
    ```
    The server will start on port 3000. Open your browser and navigate to `http://localhost:3000`.

## Routes

- **Home**: `GET /` - Renders the home page with all blog posts.
- **Compose**: `GET /compose` - Renders the compose page to create a new post.
  - `POST /compose` - Handles the form submission for creating a new post.
- **About**: `GET /about` - Renders the about page.
- **Contact**: `GET /contact` - Renders the contact page.
- **Post**: `GET /posts/:topic` - Renders an individual post based on its ID.

## Example Data

- `homeStartingContent`: Initial content for the home page.
- `aboutContent`: Content for the about page.
- `contactContent`: Content for the contact page.

## Dependencies

- [Express](https://www.npmjs.com/package/express)
- [EJS](https://www.npmjs.com/package/ejs)
- [Body-Parser](https://www.npmjs.com/package/body-parser)
- [Lodash](https://www.npmjs.com/package/lodash)
- [Mongoose](https://www.npmjs.com/package/mongoose)

## Additional Information

### MongoDB Connection

The application connects to a local MongoDB instance:
```javascript
mongoose.connect("mongodb://localhost:27017/blogDB");
```

### EJS Templates
The EJS templates dynamically render the content based on the data passed from the server. For example, home.ejs uses a loop to display all posts:

```bash
<% Posts.forEach(function(element){ %>
  <h1><%= element.title %></h1>
  <p><%= element.content.substring(0, 100) + " ... " %><a href="/posts/<%= element._id %>">Read More</a></p>
<% }); %>
```

### CSS Styles
Add your custom styles in public/css/styles.css to style the application as desired.

## Contribution
If you would like to contribute to this project, please fork the repository and submit a pull request. For major changes, please open an issue first to discuss what you would like to change.


