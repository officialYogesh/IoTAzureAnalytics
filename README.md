# Azure IoT Analytics Project

## Overview

This project demonstrates the implementation of an IoT analytics system using Azure services. The system collects telemetry data from simulated IoT devices, processes it using Azure Stream Analytics, and stores the results in Azure Blob Storage for further analysis.

## System Architecture

The system consists of the following components:

1. **Azure IoT Hub**: Receives telemetry data from simulated IoT devices
2. **Python Simulator**: Generates and sends simulated sensor data (temperature and humidity)
3. **Azure Stream Analytics**: Processes the incoming telemetry data
4. **Azure Blob Storage**: Stores the processed data in CSV format

## Step-by-Step Implementation

### Step 1: Azure IoT Hub Setup

1. Created an Azure IoT Hub named "IoTWeek10Yogesh"
2. Registered a new device "YogeshIoTDeviceWeek10"
3. Generated and saved the device connection string

### Step 2: Device Simulation

1. Created a Python script (`send_telemetry.py`) to simulate IoT device data
2. Implemented telemetry data generation with:
   - Temperature (20-30°C)
   - Humidity (30-50%)
   - Timestamp in ISO format
3. Set up secure connection using environment variables

### Step 3: Azure Stream Analytics Configuration

1. Created a Stream Analytics job
2. Configured input from IoT Hub
3. Set up SQL query for data processing
4. Configured output to Blob Storage in CSV format

### Step 4: Data Verification

1. Monitored telemetry data flow through IoT Hub
2. Verified data processing in Stream Analytics
3. Confirmed CSV file generation in Blob Storage

## Environment Setup

1. Create a virtual environment:

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

2. Install required packages:

```bash
pip install -r requirements.txt
```

3. Configure environment variables:
   - Copy `.env.example` to `.env`
   - Update the following variables:
     ```
     IOT_HUB_CONNECTION_STRING=your_connection_string
     DEVICE_ID=your_device_id
     ```

## Running the Application

1. Start the telemetry simulator:

```bash
python send_telemetry.py
```

2. Monitor the output in the terminal for sent messages
3. Check Azure Portal for:
   - IoT Hub metrics
   - Stream Analytics job status
   - Blob Storage output files

## Project Structure

```
.
├── .env                    # Environment variables (not in git)
├── .env.example           # Example environment variables
├── requirements.txt       # Python dependencies
├── send_telemetry.py      # IoT device simulator
└── README.md             # Project documentation
```

## Reflection and Learnings

### Challenges

1. **Connection String Management**:

   - Initially hardcoded the connection string
   - Resolved by implementing environment variables for better security

2. **Data Format**:

   - Ensured proper JSON formatting for telemetry data
   - Added timestamp in the required format

3. **Azure Service Integration**:
   - Learned to work with Azure IoT Hub's device registry
   - Gained experience with Stream Analytics query language

### Learnings

1. **Azure vs AWS**:

   - Azure IoT Hub provides a more streamlined device management experience
   - Stream Analytics offers powerful real-time processing capabilities
   - Blob Storage integration is seamless with other Azure services

2. **Best Practices**:
   - Environment variable management for sensitive data
   - Proper error handling in device communication
   - Structured telemetry data format

### Personal Insights

1. **Azure Advantages**:

   - Better integration between services
   - More intuitive portal interface
   - Comprehensive monitoring tools

2. **Improvements**:
   - Could add data visualization using Power BI
   - Implement error handling for network issues
   - Add data validation before sending

## Future Enhancements

1. Add data visualization dashboard
2. Implement alerting for threshold violations
3. Add more sensor types and data points
4. Implement data retention policies
5. Add automated testing

## Contributing

Feel free to submit issues and enhancement requests!
