
1. **Overview**
   - Dashboard features 
   - It is a web dashboard that visualizes the real-time data from the Rideau Canal Skateway IoT sensors.
   - Technologies used (Node.js, Express, Chart.js)
2. **Prerequisites**

3. **Installation**
   - Node.js and npm installed
   - Clone the repository: `git clone https://github.com/JunfengRong/25F_CST8916_Final_Project_Web-Dashboard.git`
   - Install dependencies: `npm install`
   - Start the server api and web dashboard: ` npm run start`
4. **Configuration**
   - Create a `.env` file in the root directory
   - Add the following environment variables:
     - `COSMOS_ENDPOINT`
     - `COSMOS_KEY`
     - `COSMOS_DATABASE`
     - `COSMOS_CONTAINER`
     - `PORT`
5. **API Endpoints**
   - List all endpoints with descriptions
     - `/api/latest`: Get the latest monitoring data
     - `/api/history/:location`: Get the history monitoring data for a specific location
     - `/api/status`: Get overall system status
     - `/api/all`: Get all data (for debugging)
     - `/health`: Health check endpoint
   - Example requests/responses
     - request: `http://localhost:3000/api/latest`
     - response: 
        ```json
        {
          "success": true,
          "timestamp": "2025-11-30T15:52:09.353Z",
          "data": [
            {
              "ConnectionDeviceId": "Dow-Lake",
              "AvgIceThickness": 20.538275862069,
              "MinIceThickness": 1.2,
              "MaxIceThickness": 49.6,
              "AvgSurfaceTemperature": -5.21758620689655,
              "MinSurfaceTemperature": -17.21,
              "MaxSurfaceTemperature": 4.1,
              "MaxSnowAccumulation": 97.13,
              "AvgExternalTemperature": -0.516896551724137,
              "ReadingCount": 29,
              "EventTime": "2025-11-30T03:35:00.0000000Z",
              "SafetyStatus": "Unsafe",
              "id": "5f7eca86-fc3e-42de-b484-ad9270956622",
              "_rid": "d7xKAJOORWoDAAAAAAAAAA==",
              "_self": "dbs/d7xKAA==/colls/d7xKAJOORWo=/docs/d7xKAJOORWoDAAAAAAAAAA==/",
              "_etag": "\"5600b8c9-0000-0800-0000-692bbb6c0000\"",
              "_attachments": "attachments/",
              "_ts": 1764473708
            },
            {
              "ConnectionDeviceId": "Fifth-Avenue",
              "AvgIceThickness": 23.003,
              "MinIceThickness": 1.53,
              "MaxIceThickness": 47.06,
              "AvgSurfaceTemperature": -7.51366666666667,
              "MinSurfaceTemperature": -18.97,
              "MaxSurfaceTemperature": 3.45,
              "MaxSnowAccumulation": 97.64,
              "AvgExternalTemperature": 0.302,
              "ReadingCount": 30,
              "EventTime": "2025-11-30T03:35:00.0000000Z",
              "SafetyStatus": "Unsafe",
              "id": "4666d2ec-271d-45d9-888c-893f7ba19ac8",
              "_rid": "d7xKAJOORWoCAAAAAAAAAA==",
              "_self": "dbs/d7xKAA==/colls/d7xKAJOORWo=/docs/d7xKAJOORWoCAAAAAAAAAA==/",
              "_etag": "\"5600b7c9-0000-0800-0000-692bbb6c0000\"",
              "_attachments": "attachments/",
              "_ts": 1764473708
            },
            {
              "ConnectionDeviceId": "NAC",
              "AvgIceThickness": 23.7162068965517,
              "MinIceThickness": 3.53,
              "MaxIceThickness": 47.39,
              "AvgSurfaceTemperature": -7.83655172413793,
              "MinSurfaceTemperature": -18.92,
              "MaxSurfaceTemperature": 3.93,
              "MaxSnowAccumulation": 94,
              "AvgExternalTemperature": -5.98344827586207,
              "ReadingCount": 29,
              "EventTime": "2025-11-30T03:35:00.0000000Z",
              "SafetyStatus": "Unsafe",
              "id": "c4932983-f23f-4df8-8b5e-e530acc3f88a",
              "_rid": "d7xKAJOORWoBAAAAAAAAAA==",
              "_self": "dbs/d7xKAA==/colls/d7xKAJOORWo=/docs/d7xKAJOORWoBAAAAAAAAAA==/",
              "_etag": "\"5600b6c9-0000-0800-0000-692bbb6c0000\"",
              "_attachments": "attachments/",
              "_ts": 1764473708
            }
          ]
        }
        ```

1. **Deployment to Azure App Service**
   - Step-by-step deployment guide
     - Create an Azure App Service instance, select the Node.js runtime and configure the App Service to use the Node.js runtime
     - Deploy the application code to the App Service
   - Configuration settings
     - set environment variables in the App Service
2. **Dashboard Features**
   - Real-time updates
     - update every 30 seconds as new data is received from the IoT sensors.
   - Charts and visualizations
     - display ice thickness, surface temperature, and external temperature trends over time.
   - Safety status indicators
     - show the current safety status for each location (Safe/Unsafe)
     - show a visual indicator (e.g., a red dot for Unsafe, green dot for Safe) for each location.
3. **Troubleshooting**
   - If the dashboard is not updating, check if the server is running and the API endpoints are accessible.