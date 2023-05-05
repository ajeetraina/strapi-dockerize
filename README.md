

## 📖 How to Run

1. Clone this repository :
```bash
git clone https://github.com/kevinadhiguna/strapi-dockerize
```

2. Change directory
```bash
cd strapi-dockerize
```

3. Install dependencies :
```bash
yarn
```

4. Create a `.env` file which stores application configuation, based on the `.env.example` file:
```bash
cp .env.example .env
```

5. Fill in the `.env` file with the application configuration. This step migth be quite long, please refer the [set up application configuration](#%EF%B8%8F-set-up-application-configuration-env-) section.

6. Run your Strapi app : <br/>

using `yarn`
```bash
yarn develop
```

using `docker-compose`
```bash
doocker-compose up
```

<br/>

### ⚠️ Prerequisites of using `docker` and `docker-compose`
Please make sure you have Docker and docker-compose installed in your machine. Please refer here to install them :
1. [Docker](https://docs.docker.com/engine/install/) installation
2. [Docker compose](https://docs.docker.com/compose/install/) installation

<br/>

<hr />

### ⚙️ Set up application configuration (`.env`) :

#### *DATABASE_HOST*

If you run your database locally or in your computer, fill :<br />
```bash
DATABASE_HOST=127.0.0.1
```

Otherwise, please enter your database host URL, such as :<br />
```bash
DATABASE_HOST=cluster3.abc65.mongodb.net
```

The above is an example if you host your database in [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).

<br/>

#### *DATABASE_SRV*

Value of Database SRV in MongoDB. It could be either `true` or `false` as it is boolean. For example :<br />
```bash
DATABASE_SRV=true
```

>SRV is a way to specify a single hostname that resolves to multiple host names. When using SRV, the driver conducts an SRV lookup to get the actual names of all of the hosts. Also, when using SRV, the driver does lookups for TXT records, which can contain specific URI options to configure the driver.

Please have a look at [MongoDB community forum](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwjl6OTUjOXwAhWY4nMBHa4RBgkQFjACegQIBhAD&url=https%3A%2F%2Fdeveloper.mongodb.com%2Fcommunity%2Fforums%2Ft%2Fmongodb-or-mongodb-srv%2F1654&usg=AOvVaw1nNUDlH5GVNZDFSL0jl2kj) for more.

<br/>

#### *DATABASE_PORT*

Port that your Strapi app interacts with database management system (DBMS). For example :<br />
```bash
DATABASE_PORT=27017
```

<br/>

#### *DATABASE_NAME*

The database name in database management system (e.g. : MongoDB, MySQL, PostgreSQL). For instance :<br />
```bash
DATABASE_NAME=myStrapiApp
```

<br/>

#### *DATABASE_USERNAME*

The username of your database that you use in your Strapi app. For instance :<br />
```bash
DATABASE_USERNAME=admin
```

<br/>

#### *DATABASE_PASSWORD*

The password of your database that you use in your Strapi app. For instance :<br />
```bash
DATABASE_PASSWORD=admin123
```

<br/>

#### *DATABASE_SSL*

Usually, you set this field if your database in your Strapi app is hosted, for example : 
- [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) for MongoDB
- [Free MySQL Hosting](https://www.freemysqlhosting.net/) for MySQL
- [ElephantSQL](https://www.elephantsql.com/) for PostgreSQL

Then in order to establish a secure connection, you want enable SSL. If so, set :<br />
```bash
DATABASE_SSL=true
```

This fields is boolean. Hence, you can either set it to `true` or `false` only.

<br/>

#### *CORS_ORIGIN*

Please add URL/IP address of :
- App's client-side (a Web App and/or a Mobile app)
- Strapi Admin Panel

CORS only cares three aspects, namely :
- Scheme (e.g. : `https`, `http`, etc.)
- URL/IP address
- Port

So, if your app's client-side and Strapi admin panel run on http://192.168.1.4:3000 and http://192.168.1.4:1337 respectively, you should write : 
```bash
CORS_ORIGIN=http://192.168.1.4:1337,http://192.168.1.4:3000
```

<br/>

#### *AWS_ACCESS_KEY_ID*

For example :<br />
```bash
AWS_ACCESS_KEY_ID=DGHY4REH7IUVDF908UNV
```

<br/>

#### AWS_SECRET_ACCESS_KEY

For example :<br />
```bash
AWS_SECRET_ACCESS_KEY=3bFhYF76zFG+5F78436KJ8bH3x19TALuIxytfNc/
```

<br/>

#### *AWS_REGION*

For example :
```bash
AWS_REGION=eu-west-2
```

Please see [AWS service endpoints](https://docs.aws.amazon.com/general/latest/gr/rande.html) for details. 

<br/>

#### *EMAIL_DEFAULT_FROM*

An email address your Strapi app will send an email from. For example :<br />
```bash
EMAIL_DEFAULT_DEFAULT_FROM=hello@example.com
```

<br/>

#### *EMAIL_DEFAULT_REPLY_TO*

An email address your Strapi app will be receiving emails. For example :<br />
```bash
EMAIL_DEFAULT_REPLY_TO=reply@example.com
```

<br/>

#### *AWS_BUCKET*

For example :
```bash
AWS_BUCKET=mybucket.mydomain.com
```

<br/>

#### *AWS_S3_STORAGE_CLASSES*

For example :
```bash
AWS_S3_STORAGE_CLASSES=S3 Standard
```

You can read more about [AWS Storage Classes](https://aws.amazon.com/s3/storage-classes/).

<br/>

#### *CLOUD_NAME*

This is the cloud name of your Coudinary account. <br />
This looks like :
```bash
CLOUD_NAME=ehsjuvnxpz
```

Please leave it blank if your Strapi app foes not use Cloudinary. 

<br/>

#### *API_KEY*

This is API key from Cloudinary. <br />
For instance :
```bash
API_KEY=253857109845223
```

You can leave it blank if you do not use Cloudinary.

<br/>

#### *API_SECRET*

This is API secret from Cloudinary. <br /> 
For example :
```bash
API_SECRET=DBVrte27_GtyrIUxFGydk_R8tRX
```

If you do not use Cloudinary, you can leave it blank.

<br/>

#### *SENTRY_DSN*

This is a Sentry DSN that you obtain from Sentry if you use it. Otherwise, leave it blank. <br />
For example :
```bash
SENTRY_DSN=https://vx547s32f45d7v91q865hgh5421z8932@f584318.ingest.sentry.io/6712395
```

<br/>

#### *HOST*

Simply open terminal and type `ip addr show` (MacOS / Linux-based OS) or `ipconfig` (Windows). You should see like `192.168.1.4` which is the value of this variable.<br>
Example : 
```bash
HOST=http://192.168.1.4
```

<br/>

#### *PORT*

Specify the port that you want to run.<br>
For example : 
```bash
PORT=1337
```

<br/>

#### *ADMIN_JWT_SECRET*

Generate a secure token is required for superadmin authentication.<br>
In terminal, please type :
```bash
openssl rand 64 | base64 # (linux/macOS users)
# or
node -e "console.log(require('crypto').randomBytes(64).toString('base64'))" # (all users)
```

Then you should see something like this in your terminal :
```
ErhxCk10YqNCImwodl5Ml/Maqnw46oTyLjr+9Na4bjmJSLVWnCS90BJRAAkLsspj98caylAJgikBO9ZS0jEiOQ==
```

Please copy the token and assign it like this :

```bash
ADMIN_JWT_SECRET=ErhxCk10YqNCImwodl5Ml/Maqnw46oTyLjr+9Na4bjmJSLVWnCS90BJRAAkLsspj98caylAJgikBO9ZS0jEiOQ==
```

<br/>

#### *NODE_ENV*

This refers to the environment that your application runs. It could be `development`, `staging`, `production`, or something else.<br/>
For example :
```bash
NODE_ENV=development
```

<!--
<hr />

### 🐋 using `docker-compose` -> configure `docker-compose.yml` :

<br />

<b>Prerequisites :</b><br>
Please make sure you have Docker and Docker Compose installed in your machine. Please refer here to install them :
1. [Docker](https://docs.docker.com/engine/install/) installation
2. [Docker compose](https://docs.docker.com/compose/install/) installation
<br>

1. Copy `docker-compose.example.yml` file then paste the content into a newly created `docker-compose.yml` file.
2. Assign values of environment variables in `docker-compose.yml` file.

#### NODE_ENV
Here we specify running environment whether it is `production`, `staging`, `development`, etc.
Using `staging` and `development` will turn on AWS S3 storage.

Example:

```bash
NODE_ENV: development
```

#### DATABASE_CLIENT
Name of the database client. Set to `mongo` if you use MongoDB.<br>
```bash
DATABASE_CLIENT: mongo
```

#### DATABASE_HOST
Host of database such as `127.0.0.1` (localhost) or a URL like `cluster3.abc65.mongodb.net` if you useMongoDB Atlas. <br />

If you run your database locally or in your computer, fill :<br />
```bash
DATABASE_HOST: 127.0.01
```

Otherwise, please enter your database host URL, such as :<br />
```bash
DATABASE_HOST: cluster3.abc65.mongodb.net
```

#### DATABASE_SRV
Please note that it must be string or null. Possible values : `true` or `false`. For instance :<br>
```bash
DATABASE_SRV: true
```

#### DATABASE_PORT
Determine the port that will be used for database management system that serves this app. Below is an example :<br>
```bash
DATABASE_PORT: 27017
```
      
#### DATABASE_NAME
Please name the database name. Let's say :<br>
```bash
DATABASE_NAME: myStrapiApp
```

#### DATABASE_USERNAME
Username of database, such as :<br>
```bash
DATABASE_USERNAME: admin
```

#### DATABASE_PASSWORD  
Generate a strong password for database, namely : <br>
```bash
DATABASE_PASSWORD: admin123
```
      
#### DATABASE_SSL
Enable Secure Socket Layer (SSL) ? If so, please fill `'true'` otherwise `'false'`. Please note that this MUST be string or null. As an example :<br>
```bash
DATABASE_SSL: 'true'
```
      
#### CORS_ORIGIN
Put allowed Cross-Origin Resource Sharing (CORS) origin here. It is possibly only one or even more. if your app's client-side and Strapi admin panel run on http://192.168.1.4:3000 and http://192.168.1.4:1337 respectively, you should write : 
```bash
CORS_ORIGIN: http://192.168.1.4:3000,http://192.168.1.4:1337
```

Read [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) for more.
      
#### ADMIN_JWT_SECRET
Generate a secure token for superadmin authentication. Below is an example :<br>
```bash
ADMIN_JWT_SECRET: ErhxCk10YqNCImwodl5Ml/Maqnw46oTyLjr+9Na4bjmJSLVWnCS90BJRAAkLsspj98caylAJgikBO9ZS0jEiOQ==
```

Please refer to [How to generate Admin JWT Secret](#admin_jwt_secret) above for more.

#### ports
These ports are not meant for database management system but for the app. There are a couple of ports which are host port and container port. Host port is a port exposed to public. Meanwhile, container port is an internal port that will be accessed through the machine you use. In particular :<br>
```bash
ports:
    - '1337:1337'
```

#### AWS environment variables

Only if you use Amazon Web Service (AWS) :

* `AWS_REGION`
```bash
AWS_REGION: eu-west-3
```

* `AWS_ACCESS_KEY_ID`
```bash
AWS_ACCESS_KEY_ID: DGHY4REH7IUVDF908UNV
```

* `AWS_SECRET_ACCESS_KEY`
```bash
AWS_SECRET_ACCESS_KEY: 3bFhYF76zFG+5F78436KJ8bH3x19TALuIxytfNc/
```

* `AWS_BUCKET`
```bash
AWS_BUCKET: mybucket.mydomain.com
```

<br />

2. Run your App. <br/>
If you run it for the first time or make changes, please run :
```bash
docker-compose up --build
```

If you do not make changes but want to run the app again :
```bash
docker-compose up
```
-->

<br/>
<hr/>

## 📝 Executing commands inside the Docker container

You can run:
```bash
docker-compose exec <container_ID> /bin/sh
```

or

```bash
docker-compose exec <container_name> /bin/sh
```

<!--
### How to stop the app :
Press `ctrl + c` to stop it.

## Build Docker Image & Push to AWS ECR

In GitLab project, after creating `.gitlab-ci.yml`, set build variables `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` from IAM user `ecr`.

```bash
# To push Docker image to 'staging' tag
git push origin master:staging

# To push Docker image to 'production' tag
git push origin master:production
```
-->
<!--
<br />
<hr />

## 🖼️ Pull this project's docker image from DockerHub

You can also use this project's docker imade from DockerHub:

```bash
docker pull kevinadhiguna/strapi-dockerize:latest
```

DockerHub repo : https://hub.docker.com/repository/docker/kevinadhiguna/strapi-dockerize
-->
<br />
<hr />

## 🔒 Reset Admin password in Strapi client (Strapi with UI)

You can reset Strapi admin password by running this command:

### using Yarn
```bash
yarn strapi admin:reset-user-password --email=<admin_email_address> --password=<new_admin_password>
```

### using NPM
```bash
npm run strapi admin:reset-user-password --email=<admin_email_address> --password=<new_admin_password>
```

However if you have installed Strapi globally (not recommended), you can run this command:

```bash
strapi admin:reset-user-password --email=<admin_email_address> --password=<new_admin_password>
```

<br/>

Example case: <br/>
You have `kai@doe.com` registered as the admin email for login credential in Strapi client but you forgot the password. If you use Yarn and want to reset the password to `Kaidoe12345`, you can do so by running :

```bash
yarn strapi admin:reset-user-password --email=kai@doe.com --password=Kaidoe12345
```

<br />
<hr />

