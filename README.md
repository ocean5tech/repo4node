# PoC

### react install ： 直接安装到windows
1. https://learn.microsoft.com/en-us/windows/dev-environment/javascript/react-on-windows
2. Open a terminal(Windows Command Prompt or PowerShell).
3. Create a new project folder: mkdir ReactProjects and enter that directory: cd ReactProjects.
4. npx create-react-app my-app
5. cd my-app
6. npm start
7. When you're ready to deploy your web app to production, running npm run build will create a build of your app in the "build" folder. You can learn more in the Create React App User Guide.

### node install ：在wsl中node
1. https://learn.microsoft.com/en-us/windows/dev-environment/javascript/nodejs-on-wsl
2. Install WSL 2
3. sudo apt update && sudo apt upgrade
4. Open your Ubuntu command line，sudo apt-get install curl
5. Install nvm, with: curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash
6. command -v nvm， if you receive 'command not found' or no response at all, close your current terminal, reopen it, and try again.
7. nvm ls
8. nvm install --lts
9. npm --version

### Podman - postgresql install：在wsl安装podman，在podman中安装postgres
1. sudo apt-get -y update
2. sudo apt-get -y install podman
3. podman pull docker.io/library/postgres
4. mkdir /home/wuyang/postgres_docker
5. podman run -dt --name my-postgres -e POSTGRES_PASSWORD=123456 -v "/home/wuyang/postgres_docker:/var/lib/postgresql/data:Z" -p 5432:5432 postgres
6. podman exec -it my-postgres bash
7. psql -U postgres
8. \l
9. create database testdb;
10. \c testdb
11. \d

# sample depolyment

### backend
https://github.com/bezkoder/node-express-sequelize-postgresql
1. powershell: git clone https://github.com/bezkoder/react-typescript-api-call.git
2. cd react-typescript-api-call
3. npm install
4. npm start

### frontend
https://github.com/bezkoder/react-typescript-api-call
1. git clone https://github.com/bezkoder/node-express-sequelize-postgresql.git
2. cd node-express-sequelize-postgresql
3. npm install
4. edit db.config.js: password:123456
5. node server.js
