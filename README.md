Jan 2020 - Dec 2020
# IoT-enabled Portable 12-Lead ECG System

12-Lead ECGs are usually bulky and mounted on carts. This project in collaboration with NUH Emergency Department developed a portable version of it which displayed ECG tracings on a web-app to increase the efficiency of clinicians and comfort of patients. Take a look at the video below for a short demo of the system.

https://user-images.githubusercontent.com/59247141/186677922-14ab5f33-408b-436f-be4c-0afafe76f2a2.mp4

## Device

The Schematics and Layout of the circuit board design can be viewed directly in the "device" folder as PDF files.

"main.cpp" contains the firmware for the device, which runs on an ESP32 chip. It requires some commonly used ESP32 libraries not included in the "device" folder.

## Web Dashboard

The "app" folder houses both the client and server components of the MERN stack.

### Installation

Install dependencies for frontend by entering the frontend folder and running:
```
yarn install
```
Install dependencies for backend by entering the backend folder and running:
```
npm install
```

### Running Locally

To start the frontend application, enter the frontend folder and run:
```
yarn start
```
This runs the app in the development mode. Open [http://localhost:3000](http://localhost:3000) to view it in the browser. The page will reload if you make edits. You will also see any lint errors in the console.

To start the backend application, enter the backend folder on a separate terminal and run:
```
npm dev
```

### Deploying

The entire stack is deployed using Docker. Docker images are uploaded onto DockerHub and `docker-compose.prd.yml` is uploaded onto the server. To deploy the application, ssh into the server and run the docker-compose file:
```
ssh root@128.199.106.255
docker-compose -f docker-compose.prd.yml up -d --build
```

This will create a "docker network" and attach the three running containers (consisting of the client listening at port `3000`, server listening at port `5000` and mongo database listening at port `27017` on `mongo`) to it.
