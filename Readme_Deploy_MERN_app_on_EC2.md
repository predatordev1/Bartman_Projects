# Deploy MERN app on EC2
## GOAL : Deployment of any Site with Full BackEnd ,FrontEnd and Database using MERN(MongoDB, Express.js, React, Node.js)
Prerequisites:
An AWS account
Basic understanding of cloud computing
Familiarity with the MERN stack
Access to AWS Management Console

### Outcome : Learning of Deployment of FrnotEnd,BanckEnd and Attachments of Database with backend.
In this Project, we will walk through the process of launching an EC2 instance using an Ubuntu image in the default VPC (Virtual Private Cloud). We will also configure the security groups to allow HTTP, HTTPS, and custom application ports. This knowledge is crucial for aspiring developers, especially those interested in building applications using the MERN stack (MongoDB, Express.js, React, Node.js).

## Phase 1: Setup EC2 instance with required packages:

### Step 1: Creation of EC2 instance with Ubuntu and default VPC and allow SSH connection using Port 22.
<img width="1657" height="751" alt="image" src="https://github.com/user-attachments/assets/397772ae-854a-42ed-8459-05d4c25ab107" />
#### Update Security group of EC2 to allow traffic from internet Using HTTP,HTTPS also Allow cutom ports to allow traffic from frontend and backend services on Ports 3000 & 3001.
<img width="1647" height="617" alt="image" src="https://github.com/user-attachments/assets/2a22d51e-a02c-4ccf-b7fc-6d0d4198b050" />

### Step 2: Configuration of EC2 instanse to run Frontend and dependencies like node.js.
#### Connect EC2 instance using putty terminal using your-public-dns:
<img width="853" height="366" alt="image" src="https://github.com/user-attachments/assets/60bfc8df-3124-405c-a91a-c81a0692296d" />
#### Upgrade all packages using sudo apt-get upgrade -y:
<img width="1607" height="437" alt="image" src="https://github.com/user-attachments/assets/96d6307d-d8be-4a7d-9526-e313fc914e2d" />

### Step 3: Install Node.js 22 and npm
#### curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
<img width="1232" height="502" alt="image" src="https://github.com/user-attachments/assets/f7e186d3-645b-40ea-a723-33758d4a8471" />
<img width="1175" height="362" alt="image" src="https://github.com/user-attachments/assets/f2c3fd5b-3a74-40dc-af2c-d1e5ccfb7039" />
#### sudo apt install -y nodejs
<img width="1107" height="698" alt="image" src="https://github.com/user-attachments/assets/f7b633d5-e8f1-422e-b4e8-3d17a5ef4720" />
#### Needs to validate the installed packages node -v & npm -v.
<img width="942" height="102" alt="image" src="https://github.com/user-attachments/assets/d1905905-18ee-471a-a527-4a4448023e89" />

## Phase 2: Setup Database to store backend Data:

### Step 1: Create a Cluster on MongoDB Atlas.
<img width="1338" height="830" alt="image" src="https://github.com/user-attachments/assets/771fd8de-231b-4f36-aea0-bb17c2fc3a4d" />
### Step 2: Create a database and Colloction on MongoDB  Cluster.
<img width="1312" height="708" alt="image" src="https://github.com/user-attachments/assets/75b5c3d7-41d5-400a-b2e9-0b4f4d209ec4" />

## Phase 3: Deployment of backend on EC2 instance:
### Note: At this point EC2 instance should be configured with all mentioned ports and dependencies should be installed like node.js and npm.

### Step 1: Cloning the Repository where website/App data is stored and Navigate to the Backend Folder:
<img width="1035" height="302" alt="image" src="https://github.com/user-attachments/assets/e4cabef2-da01-41d2-9781-49e86bff9a54" />
<img width="1090" height="367" alt="image" src="https://github.com/user-attachments/assets/52336068-0321-445d-b89b-e37ad83de648" />

### Step 2: Creation of Environment to run the backend files and add your database url to store backend data:
MONGO_URI='ENTER_YOUR_URL'
PORT=3001
URI: mongodb+srv://<username>:<password>@cluster0.mongodb.net/travelmemory?retryWrites=true&w=majority
<img width="523" height="63" alt="image" src="https://github.com/user-attachments/assets/16d7a866-eccd-44c3-8ac1-5629a2fd204b" />

### Step 3: Install Necessary Packages:
<img width="765" height="560" alt="image" src="https://github.com/user-attachments/assets/663f34d5-778a-4f5a-86d7-92f482069586" />

### Step 4: Run the Backend Application and test:
<img width="798" height="65" alt="image" src="https://github.com/user-attachments/assets/1b078c53-eead-477d-963b-7f835f641e55" />
<img width="847" height="278" alt="image" src="https://github.com/user-attachments/assets/9e3a06cd-aeb8-4650-aff6-ffa38a6288f3" />

## Phase 4: Deployment of Frontend on EC2 instance:
### Note: We already cloned Github Repo , So no Needs to redo.

### Step 1: Login to EC2 Instance on another window:
<img width="888" height="570" alt="image" src="https://github.com/user-attachments/assets/e66248e0-bea6-477f-bf93-3c6a61ebf328" />

### Step 2: Navigate to Your Frontend Directory:
<img width="852" height="202" alt="image" src="https://github.com/user-attachments/assets/f1f1eef1-59d4-4988-b5ca-3b35e1938a33" />

### Step 3: Create the .env File
echo "REACT_APP_BACKEND_URL=http://EC2_PUBLIC_IP:3001" > .env
<img width="1142" height="303" alt="image" src="https://github.com/user-attachments/assets/eb38174e-88f3-40d3-8996-b4c3525241b7" />

### Step 4: Install Required Packages
npm install
<img width="1581" height="485" alt="image" src="https://github.com/user-attachments/assets/fad7a774-5960-49a9-a60f-6c1e0e1f54ce" />

### Step 5: Run Your Application
npm start

<img width="743" height="462" alt="image" src="https://github.com/user-attachments/assets/40061ed2-5aef-43f4-ba5c-c95f56ed8d65" />
<img width="1871" height="958" alt="image" src="https://github.com/user-attachments/assets/ed3d56dc-d679-4346-bece-01df0a4d6ee1" />










