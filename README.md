The workflows pushes a theme to a Shopify store when code is pushed to the main branch.

1- Checkout repository: This step checks out the repository's code.

2- Deploy using Docker: This step runs a Docker container using the Ruby 2.7 image. It installs the Shopify Theme Kit gem, updates it, and displays the version of Theme Kit. The environment variables for the Shopify password, store URL, theme ID, and theme path are passed to the container using Docker's -e flag.

3- Deploy Shopify theme using pgrimaud/action-shopify: This step uses the pgrimaud/action-shopify action to deploy the Shopify theme. It requires various environment variables, which seem to be related to different environments and configurations. Here are the environment variables used in this step:


SHOPIFY_PASSWORD: Your Shopify private app password.

SHOPIFY_STORE_URL: Your Shopify store URL.

SHOPIFY_THEME_ID: The theme ID on your Shopify store.

THEME_PATH: The path of your theme in your GitHub repository.
# Shopify Theme Deployment Workflow

This repository contains the necessary workflow to automatically push a theme to a Shopify store when new code is pushed to the main branch. The workflow utilizes Docker for containerization and the `pgrimaud/action-shopify` GitHub Action for seamless Shopify theme deployment.

## Workflow Steps

### 1. Checkout Repository

This step checks out the latest code from the main branch of this repository.

### 2. Deploy Using Docker

This step utilizes a Docker container with the Ruby 2.7 image to manage the deployment process. It performs the following actions:
- Installs the Shopify Theme Kit gem to interact with Shopify themes.
- Ensures that Theme Kit is up-to-date.
- Displays the version of Theme Kit being used.
- Passes necessary environment variables for authentication and deployment.

### 3. Deploy Shopify Theme Using pgrimaud/action-shopify

This step employs the `pgrimaud/action-shopify` GitHub Action to deploy the Shopify theme. It requires the following environment variables:
- `SHOPIFY_PASSWORD`: Your Shopify private app password for authentication.
- `SHOPIFY_STORE_URL`: The URL of your Shopify store.
- `SHOPIFY_THEME_ID`: The unique ID of the theme on your Shopify store.
- `THEME_PATH`: The path of the theme within this GitHub repository.

## Getting Started

To set up this workflow for your own Shopify store, follow these steps:

1. Create a private app on your Shopify store and obtain the private app password.
2. Fork this repository to your own GitHub account.
3. Modify the `.github/workflows/deploy-theme.yml` file to update the environment variables according to your Shopify store's details.
4. Push your changes to the main branch of your forked repository.

The workflow will automatically trigger whenever new code is pushed to the main branch.

## Contributing

Contributions to this repository are welcome! Feel free to submit pull requests or raise issues for any improvements or bug fixes.
