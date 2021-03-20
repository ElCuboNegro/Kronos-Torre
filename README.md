# Kronos Torre

## Description: 
Kronos Torre is a Google Action that can help you to find a job.

- [Kronos Torre](#kronos-torre)
  - [Description:](#description)
  - [Installation:](#installation)
    - [NodeJS](#nodejs)
    - [Gactions](#gactions)
    - [Firebase CLI](#firebase-cli)
  - [Usage:](#usage)
    - [Create and setup the project:](#create-and-setup-the-project)
  - [Get the Torre Assistant code](#get-the-torre-assistant-code)
  - [Deploy and test the Assistant](#deploy-and-test-the-assistant)
  - [In deep documentation:](#in-deep-documentation)
  - [Contributing](#contributing)
  - [Credits:](#credits)
  - [License:](#license)

## Installation: 
### NodeJS
Download and install [Node.js](https://nodejs.org/) according to the Node.js documentation to use the fulfillment library. Your installation of Node.js also allows you to install the Firebase CLI with npm, and later, to run your conversational fulfillment implementation locally.
### Gactions
Install the gactions command line interface (CLI) tool by downloading an installation package, unpacking it, and configuring your execution path.

To install and configure gactions, follow these steps:

1. Download the appropriate package for your operating system:</br>
   
|  Platform	| Package	| checksum 	|
|-	|-	|-	|
|Windows  	|  [Download](https://dl.google.com/gactions/v3/release/gactions-sdk_windows.zip) 	|  [sha256](https://dl.google.com/gactions/v3/release/gactions-sdk_windows.zip.sha256)	|
|Linux  	| [Download](https://dl.google.com/gactions/v3/release/gactions-sdk_linux.tar.gz) 	|  [sha256](https://dl.google.com/gactions/v3/release/gactions-sdk_linux.tar.gz.sha256) 	|
|Mac  	    |  [Download](https://dl.google.com/gactions/v3/release/gactions-sdk_darwin.tar.gz)	|  [sha256](https://dl.google.com/gactions/v3/release/gactions-sdk_darwin.tar.gz.sha256)	|</br>

2. Extract the package to a location of your choice and add the binary to your environment's PATH variable. Alternatively, extract the package to a location that's already in your PATH variable (for example, /usr/local/bin).
3. On Linux and Mac, enable execute permissions if necessary:

```
$ chmod +x PATH_TO/gactions
```

1. Run the following command to authenticate the CLI. This command starts an authentication flow and requires a web browser: 
   
```
$ gactions login
``` 

2. When the flow is complete, the CLI automatically authenticates.

### Firebase CLI
Install and set up the [Firebase CLI](https://firebase.google.com/docs/cli#setup_update_cli) according to the Firebase documentation. The Firebase CLI lets you deploy an Interactive Canvas web app to Firebase Hosting and, if necessary, manually deploy fulfillment to Cloud Functions for Firebase.

## Usage: 
### Create and setup the project:
Before you can use the gactions command-line tool, you must create a project in the Actions console and give gactions access to the project. To create and set up a copy of this project, do the following:

Go to the [Actions console](https://console.actions.google.com/).
Click New project, enter a project name, and click Create project, Select the games category (this will allow us to create html canvas inside the action) and click Next.
Select Blank project and click Start building.
Enable the Actions API in the Google Cloud console by following the instructions in [Enable and disable APIs](https://support.google.com/googleapi/answer/6158841). This allows gactions to interact with your project.


## Get the Torre Assistant code
1. clone this repository into your local machine
2. Open the 'torre-assistant'/sdk/settings/settings.yaml file and change the value of the projectId (torre-assistant) field to YOUR project's ID. (it won't deploy if there is a colission with other firebase project)

## Deploy and test the Assistant
After you set up the project, you can deploy the Torre Assistant web app and your Actions project. This process creates a draft version of your Actions project that you can deploy to the Actions simulator for previewing and testing:
1. From the torre-assistant/ directory, run the following command to deploy the Torre Assistant web app (the contents of the public/ directory).
   ```
   firebase deploy --project PROJECT_ID --only hosting
   ```
   You can see a rendered version of the web app at the URL returned by the Firebase CLI in a browser: https://PROJECT_ID.web.app.
2. Open the `torre-assistant/sdk/webhooks/ActionsOnGoogleFulfillment/index.js` file and change the value of the CANVAS_URL variable to your project's web app URL.
  ```
  const CANVAS_URL = 'https://PROJECT_ID.web.app';
  ```
3. From the torre-assistant/sdk/ directory, run the following command to push the local version of your Actions project to the console as a draft version:
  ```
  gactions push 
  ```
4. From the torre-assistant/sdk/ directory, run the following command to test your Actions project in the simulator:
  ```
  gactions deploy preview
  ```
5. Open the link that the command-line tool returns to go to the simulator.



## In deep documentation:
TBD

## Contributing
TBD

## Credits:
Google Actions SDK -> Google LLC.
Nuxt.js -> Creators

## License: 
Copyright, Juan José Albán (2021)