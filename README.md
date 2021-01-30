# Farmassist IoT Device Simulator

*[Ray Jasson](mailto:holmesqueen2070@yahoo.com)*<br>
*31/01/2021*<br>

<br>

## :satellite: IoT Device Simulation

This is a minimal IoT device simulator built using [Node-RED](https://nodered.org/). It sends telemetry data to [Firebase Realtime Database](https://firebase.google.com/docs/database) for Farmassist app. There are 5 types of telemetry data:
- Air Humidity (%)
- Air Temperature (°C)
- Soil Moisture (%)
- Soil pH (pH)
- Soil Salinity (Millisiemens/cm)

<p align=center><img src="/docs/img/nodes.png"></p>
<p align="center"><i>Connected Nodes in Node-RED editor</i></p>

<br>

<p align=center><img src="/docs/img/ui.png"></p>
<p align="center"><i>UI Dashboard of the IoT Device Simulator</i></p>

<br>

## :computer: How to Run the IoT Device Simulator

The IoT device simulator is a Node-RED flow stored using JSON. The functions are written in JavaScript.

### Run the Node-RED flow locally

- To run the simulator locally, you will need a supported version of Node.js and Node-RED editor.
- To install Node.js, download the recent version from [here](https://nodejs.org/en/download/).
- To install Node-RED editor, run:
  ```
  npm install -g --unsafe-perm node-red
  ```
- Open Node-RED editor by running:
  ```
  node-red start
  ```
- Open [http://localhost:1880](http://localhost:1880) to view the editor in the browser.
- 2 extra node modules: `node-red-dashboard` and `node-red-contrib-firebase-data`, are required to run the simulator. `node-red-dashboard` is used to create a dashboard, whereas `node-red-contrib-firebase-data` is used to connect the nodes to Firebase Realtime Database. To install them, run:
  ```
  npm install node-red-dashboard
  npm install node-red-contrib-firebase-data
  ```
- Download the JSON file and import it into the Node-RED editor. You will see the import option at the upper-right corner of the editor.

### Customize the simulator

- You need to add your Realtime Database URL into the configuration node. You can find the URL in the Realtime Database section of your Firebase console. The configuration node :gear: is located at the third option in the right panel.
- Double-click `Add Firebase` node to configure your Firebase URL and set the child path to where the telemetry data is stored in the database. Also, there are several methods for you to write data into Realtime Database, for example, `set`, `push` or `update`. The default method in the JSON file is `update`.
- Remember to click "Deploy" to save your configurations.
- Open the dashboard, and use the sliders to select the range of the telemetry data you would want to send.
- Toggle the switch to start/stop sending the telemetry data.

<br>

## :black_nib: References

- [A YouTube tutorial teaching you how to build a Node-RED IoT Device Simulator](https://www.youtube.com/watch?v=2GcVvD08nGE)
- [Reference for types of telemetry data from Microsoft Azure Virtual Hackathon 2020 in Asia Pacific](https://news.microsoft.com/apac/2020/08/20/drones-data-science-and-innovation-at-the-microsoft-azure-virtual-hackathon-in-asia-pacific/)