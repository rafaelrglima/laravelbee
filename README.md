##Project Readme: Optimizing Laravel Development with Docker
###Purpose of the Image
Developing with Sail can become cumbersome when managing multiple projects, each requiring its own container. With this Docker image, managing Laravel projects becomes simpler and more efficient. Rather than configuring individual containers for each project, this image allows for a centralized approach. With just one database image, you can seamlessly run multiple Laravel applications, each on a different port, without the hassle of extensive configuration changes.

##How to Use
###Step 1: Build the Image Locally
bash
Copy code
docker build -t laravelbee .
Step 2: Run the Container Locally
Navigate to the root directory of your Laravel project and execute the following command:

bash
Copy code
docker run -d --name yourappname -v ${PWD}:/var/www/html -p 8001:80 -p 5173:5173 laravelbee
Make sure to replace yourappname with your preferred container name. Additionally, you can modify the port mappings (8001:80 and 5173:5173) as needed for your project.

Step 3: Optional - Setup a Local Development Database
If you require a local development database, you can easily set up a PostgreSQL instance using the following command:

bash
Copy code
docker run -d --name postgres15 -p 5432:5432 -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=admin postgres:15
This command will start a PostgreSQL container with version 15, exposing it on port 5432. You can customize the username and password as needed.

By following these steps, you can streamline your Laravel development process, making it easier to manage multiple projects and eliminating unnecessary complexity.