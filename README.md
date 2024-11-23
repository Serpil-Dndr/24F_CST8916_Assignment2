# Assignment 2: Real-time Monitoring System for Rideau Canal Skateway

## Scenario: Rideau Canal Skateway Monitoring
The Rideau Canal Skateway, a historic and world-renowned attraction in Ottawa, needs constant monitoring to ensure skater safety. Your team has been hired by the National Capital Commission (NCC) to build a **real-time data streaming system** that will:
1. Simulate IoT sensors to monitor ice conditions and weather factors along the canal.
2. Process incoming sensor data to detect unsafe conditions in real time.
3. Store the results in Azure Blob Storage for further analysis.

---

### Overview
In this assignment, you will work in **groups of 3** to design and implement a **real-time monitoring system** for the **Rideau Canal Skateway** using simulated IoT sensors, **Azure IoT Hub**, **Azure Stream Analytics**, and **Azure Blob Storage**. The system will simulate sensor data, process it in real time, and store the output in Azure Blob Storage.
## Requirements

### 1. **Simulate IoT Sensors**
- Create a script or application to simulate IoT sensors at **three key locations** on the Rideau Canal (e.g., Dow's Lake, Fifth Avenue, NAC).
- Sensors must generate the following data every **10 seconds**:
  - **Ice Thickness** (in cm): A key safety metric.
  - **Surface Temperature** (in °C): Indicates ice melting risks.
  - **Snow Accumulation** (in cm): Impacts ice strength and usability.
  - **External Temperature** (in °C): Adds weather context.

**Example JSON payload:**
```json
{
  "location": "Dow's Lake",
  "iceThickness": 27,
  "surfaceTemperature": -1,
  "snowAccumulation": 8,
  "externalTemperature": -4,
  "timestamp": "2024-11-23T12:00:00Z"
}
```
The simulated sensors should push this data to **Azure IoT Hub**.

### 2. **Real-time Data Processing**
Use **Azure Stream Analytics** to process the data in real time. Implement the following:
 - Aggregate data for each location over a 5-minute window, calculating:
    - Average ice thickness.
    - Maximum snow accumulation.

Ensure the processed data is output to Azure Blob Storage.

## 3. Submission via GitHub

Your entire submission must be uploaded to a **GitHub repository**. The repository must include the following components:

### a. `README.md` File
The `README.md` file must document your solution and include the following sections:

1. **Scenario Description**:  
   - Provide an overview of the Rideau Canal Skateway monitoring scenario and explain the problem your solution addresses.

2. **System Architecture**:  
   - Include a clear diagram illustrating the data flow:
     - IoT sensors pushing simulated data to Azure IoT Hub.
     - Azure Stream Analytics processing the incoming data.
     - Processed data being stored in Azure Blob Storage.

3. **Implementation Details**:  
   - **IoT Sensor Simulation**:
     - Describe how the simulated IoT sensors generate and send data to Azure IoT Hub.
     - Include the structure of the JSON payload and any scripts or applications used.
   - **Azure IoT Hub Configuration**:
     - Explain the configuration steps for setting up the IoT Hub, including endpoints and message routing.
   - **Azure Stream Analytics Job**:
     - Describe the job configuration, including input sources, query logic, and output destinations.
     - Provide sample SQL queries used for data processing.
   - **Azure Blob Storage**:
     - Explain how the processed data is organized in Blob Storage (e.g., folder structure, file naming convention).
     - Specify the formats of stored data (JSON/CSV).

4. **Usage Instructions**:  
   - **Running the IoT Sensor Simulation**:
     - Provide step-by-step instructions for running the simulation script or application.
   - **Configuring Azure Services**:
     - Describe how to set up and run the IoT Hub and Stream Analytics job.
   - **Accessing Stored Data**:
     - Include steps to locate and view the processed data in Azure Blob Storage.

5. **Results**:  
   - Highlight key findings, such as:
     - Aggregated data outputs (e.g., average ice thickness).
   - Include references to sample output files stored in Blob Storage.

6. **Reflection**:  
   - Discuss any challenges faced during implementation and how they were addressed.

---

### b. IoT Sensor Simulation Code
Include the script or application used to simulate the IoT sensors. The code should:
- Be included in the repository under a directory such as `sensor-simulation/`.
- Be well-documented with comments and clear instructions for running.

---

### c. Screenshots
Add a directory in the repository named `screenshots/` containing:
- Azure IoT Hub configuration screenshots.
- Azure Stream Analytics job settings and queries.
- Azure Blob Storage screenshots showing stored output files (processed data).

---

### Submission Instructions
- Ensure that all files (e.g., `README.md`, simulation code, screenshots) are organized and uploaded to a public or private GitHub repository.
- Share the link to the repository in the course submission portal.

## Evaluation Criteria

The following table outlines how your submission will be evaluated:

| **Category**             | **Weight** | **Criteria**                                                                                                                                   |
|--------------------------|------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| **Pipeline Implementation** | 50%    | - **IoT Sensor Simulation**: Functional and accurate simulated sensors generating proper JSON payloads.<br>- **Azure IoT Hub Configuration**: Correct setup to ingest real-time data.<br>- **Azure Stream Analytics**: Accurate SQL queries for aggregating data.<br>- **Azure Blob Storage**: Properly stores processed data and alerts in organized format (JSON/CSV). |
| **Documentation**        | 30%        | - **README.md**: Includes scenario description, architecture diagram, implementation details, usage instructions, results, and reflection.<br>- **Architecture Diagram**: Clear depiction of the system's components and data flow.<br>- **Usage Instructions**: Steps for replicating the solution are clear and easy to follow. |
| **Results**              | 10%        | - **Processed Data**: Aggregated outputs (e.g., average ice thickness).<br>- **Sample Output**: Realistic and complete sample outputs stored in Azure Blob Storage. |
| **Presentation**         | 10%        | - **Screenshots**: Clear images of Azure IoT Hub, Stream Analytics configuration, and Blob Storage outputs.<br>- **Clarity and Engagement**: Effective explanation and demonstration of how the system addresses the scenario. |

---
