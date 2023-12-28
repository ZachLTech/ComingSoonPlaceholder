# 🚧 Under Construction Page

Welcome to my Under Construction Page. This simple site that allows you to set up an "Under Construction" page for your domain. The project includes Docker support for easy deployment/self hosting.

This was originally just for my domains I plan to host projects on, but if anyone wants to change the background, favicon/avatar, and hrefs then feel free to do so.

## Features

- 🐳 **Docker Support:** Easily deploy and self-host the under construction page using Docker and Docker Compose.
- 🖱️ **Custom Cursor:** Enjoy a unique custom cursor for an enhanced user experience.
- 💫 **Cursor Effects:** Interact with an orb that follows your mouse movements.
- 📱 **Mobile/Tablet Support:** The under construction page is responsive and optimized for various devices.
- 🚀 **Image Optimization:** Images are optimized for faster loading times without compromising quality.

## App

### Getting Started Locally

1. Clone the repository:

   ```bash
   git clone https://github.com/ZachLTech/ComingSoonPlaceholder.git
   ```

2. Navigate to the `app` directory:

   ```bash
   cd app
   ```

3. Install dependencies:

   ```bash
   npm install
   ```

### Customizing the Under Construction Page

Edit the content of the under construction page by modifying the files in the `app/components` directory.

- `app/components/TopBar.vue` - edit to change site avatar image by URL, avatar href, & Alt text
- `app/assets/img/ComingSoonBackground.png` - swap file for different site background
- `app/public/favicon.ico` - swap file to change site favicon (obviously lol)
- `app/components/Hero.vue` & `app/components/HeroMobile.vue` - edit to change splash message & github account href

### Running the App Locally

Run the following command to start the development server:

```bash
npm run dev
```

Visit `http://localhost:3000` in your browser to see the under construction page.

## Docker Support & Self Hosting

Ensure that both the `Dockerfile` and `docker-compose.yml` are in the same directory. Also feel free to edit the `docker-compose.yml` file to change what ports you want the webpage on.

### Build the Docker Image

Build the Docker image using:

```bash
docker-compose build
```

### Run the Docker Container

Start the Docker container with:

```bash
docker-compose up -d
```

#### OR (Recommended)

One liner to Build and Start the Docker file & container

```bash
docker-compose up --build -d
```

Visit `http://localhost:3000` in your browser to access the under construction page served by the Docker container or replace `localhost` with the hosts iPv4 on another device if you're on the same network.

### Stopping the Docker Container

To stop the Docker container, run:

```bash
docker-compose down
```

## Self-Hosting

To deploy the under construction page on your server:

1. Ensure Docker is installed on your server.
2. Upload your project files (including the `Dockerfile` and `docker-compose.yml`) to your server.
3. Build and run the Docker container as mentioned in the "Docker Support" section.

Now, your "Under Construction" page should be accessible through your server's local ip.

Feel free to customize the page content, styles, and configurations based on your preferences.

🚀 Happy self-hosting!