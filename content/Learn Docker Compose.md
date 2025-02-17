- Great! Since you're comfortable with the basics, let's move on to the **next step: managing multi-container applications using Docker Compose**.
  
  ---
- ### **Step 1: What is Docker Compose?**
  
  Docker Compose simplifies managing multi-container applications by using a single configuration file (`docker-compose.yml`). With it, you can define services, networks, and volumes for your app in a declarative manner.
  
  ---
- ### **Step 2: Install Docker Compose**
  
  Docker Compose is included with Docker Desktop on macOS and Windows. On Linux, you may need to install it separately:
  
  ```
  sudo apt-get update
  sudo apt-get install docker-compose
  ```
  
  Verify the installation:
  
  ```
  docker-compose --version
  ```
  
  ---
- ### **Step 3: Create a Multi-Container App**
  
  Let’s create an app with two services:
- A **web server** using Nginx.
- A **database** using MySQL.
  
  ---
- #### Directory Structure:
  
  ```
  docker-compose-example/
  ├── docker-compose.yml
  ```
  
  ---
- #### Example  `docker-compose.yml` :
  
  ```
  version: "3.8"
  
  services:
  web:
    image: nginx:latest
    ports:
      - "8080:80"
    networks:
      - app-network
  
  db:
    image: mysql:latest
    environment:
      MYSQL_ROOT_PASSWORD: example
    networks:
      - app-network
  
  networks:
  app-network:
  ```
  
  ---
- ### **Step 4: Run the App**
- Navigate to the directory containing `docker-compose.yml`.
- Start the application:
  
  ```
  docker-compose up
  ```
  
  This will pull the images, create containers, and start the services.
- Open a browser and visit:
	- Web server: `http://localhost:8080`
- To stop the application:
  
  ```
  docker-compose down
  ```
  
  ---
- ### **Step 5: Extend the Application**
  
  You can add features like:
- **Custom Volumes**: Persist database data.
  
  ```
  volumes:
  db-data:
  services:
  db:
    volumes:
      - db-data:/var/lib/mysql
  ```
- **Environment Variables**: Configure services dynamically.
  
  ```
  environment:
  MYSQL_DATABASE: myappdb
  MYSQL_USER: user
  MYSQL_PASSWORD: password
  ```
  
  ---
- ### Practice Task:
- Build and run the example above.
- Extend it by adding another service, such as a Python web app.
  
  Let me know when you’re ready to discuss or move on!