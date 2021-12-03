# Azure IoT hub Addons for webthings.io gateway 
please install the webthings gateway from here: https://github.com/WebThingsIO/gateway

inspired by https://github.com/tim-hellhake/azure-iot-bridge 

the code is heavilly commented please check out the source code /src/

# Create an IoT Hub
1. Go to https://portal.azure.com/#create/hub
2. Search for IoT Hub
3. Click on Create
4. Create your hub
5. Wait for the deployment to be finished
6. Under Deployment detail: click on our hub resource
7. Go to Shared access policies
8. Click on the iothubowner
9. Copy the Connection string — primary key
10. Add the connection string from step 9 to the config
11. Go to http://[your-gateway]/oauth/authorize?response_type=code&client_id=local-token&scope=/things:readwrite
12. Create a token
13. Add the token to the config

# install and use this Addon:
1. clone it `$ git clone https://github.com/JaycHub/fot-azureiothub.git`
2. go inside of fot-azureiothub folder `$ cd fot-azureiothub`
3. run `$ npm install`
4. package.sh is the script that will compile and create a runtime package that will be used by Webthings gateway, it will also copy it directly to .webthing/addons forlder for faster testing assuming you are developing the addon on the same machine that is running the Webthings gateway.
5. so give the package.sh permission to execute : `$ chmod +x package.sh`
6. give permission to gather-licenses.js that will auto gather and compile all licenses from the node_module package into your LICENSE file: `chmod +x gather-licenses.js`
7. next run: `$ npm run build`
8. Open the addon page of the webthings gateway to configure the addon by copying teh authorization token from step 12 to the config page of the addon.
9. everytime you change the source code of teh addon run the build command in step 6 .
10. Enjoy!

# To do:
1. auto delete the device from Azure IoT hub when it is removed from the gateway's things list
2. add option to create a digital twin
3. Update the code to typescript
