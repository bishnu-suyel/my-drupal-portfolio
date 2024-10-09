# My Drupal Portfolio

This project, **My Drupal Portfolio**, is a part of an assignment showcasing the integration of Drupal 10 as a backend with a separate frontend React app. The Drupal site manages content, while the React app fetches and displays the information. The communication between the two platforms is handled using **JSON:API**. Additionally, the project includes solving CORS issues through the implementation of a `services.yml` file in the Drupal configuration.

## Technologies Used

Built with:

- **Drupal 10**: For managing and storing the backend content.
- **React.js**: Build the separate frontend application (https://github.com/bishnu-suyel/my-drupalreact-portfolio).
- **JSON:API**: Used for managing API requests between Drupal and the React app.
- **Lando**: A local development environment for setting up and managing the Drupal project.
- **YAML**: For configuring the `services.yml` file, solving CORS issues between the frontend and backend.

## Setup and Usage

To get started, follow these steps:

### Step 1: Clone the Repository

```bash
git clone https://github.com/bishnu-suyel/my-drupal-portfolio
```

### Step 2: Start the Lando Environment

Inside the project folder, run the following command to start Lando:

```bash
lando start
```

### Step 3: Install Dependencies

Make sure the necessary dependencies are installed:

```bash
lando composer install
```

### Step 4: Install Drupal and Configure the Database

Run the following command to install the Drupal site and configure the database:

```bash
lando drush site:install --db-url=mysql://drupal10:drupal10@database/drupal10 -y
```

### Step 5: Configure CORS Settings

Edit the services.yml file to manage CORS issues between the frontend and backend. Add the following:

services.yml

```bash
cors.config:
  enabled: true
  allowedHeaders: ["*"]
 allowedMethods: ["GET", "POST", "OPTIONS", "PATCH", "PUT", "DELETE"]
  allowedOrigins: ["*"]
  supportsCredentials: true
```

### Step 6: Set Up JSON

To enable JSON
in Drupal, follow these steps:

### Step 7: Enable the JSON module:

```bash
lando drush en jsonapi -y
```

Access the content through the API at a URL like:

```bash
http://your-drupal-site.com/jsonapi/node/home
```

### Step 8: Launch the React Frontend

Navigate to the React app's folder and run the following command to start the frontend:

```bash
npm run dev
```

This will start the React app on http://localhost:5173, which will fetch data from the Drupal backend.

## Live Page

Not yet

## Screenshot

Not yet

## Sources

- [GitHub Guides - Mastering Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- [Make a README](https://www.makeareadme.com/)
- [Drupal JSON Documentation](https://www.drupal.org/docs/core-modules-and-themes/core-modules/jsonapi-module)
- [Lando Documentation](https://docs.lando.dev/getting-started/)

## Authors and Acknowledgment
This project was developed as part of an assignment.

- [GitHub @bishnu-suyel](https://github.com/bishnu-suyel)
- [LinkedIn @bishnu-suyel](https://www.linkedin.com/in/bishnu-suyel)
