# 🖥️ Fine Dust Measurement README

<br>

## Project Introduction

- Creating a Gradio interface that compares and provides responses regarding indoor and outdoor fine dust concentrations.  
- Sending a Discord alert when the indoor fine dust level exceeds the threshold.  
- Linking Discord with a mobile app to receive instant notifications.

<br>

## Team Members

<div align="center">

| **Kwon Do-hyeon** | **Gu Hyeon-jun** | **Lee Su-hyeon** | **Ryu Tae-an** |
| :------: |  :------: | :------: | :------: |
| <img src="https://github.com/user-attachments/assets/f7665068-667d-4409-bf56-ea39f9b2bf10" height=200 width=130>| <img src="https://github.com/user-attachments/assets/115d6c7c-4e78-4057-8436-fb73508a2dc8" height=200 width=150>| <img src="https://github.com/user-attachments/assets/c40d7b0d-f7b1-4572-bada-710346446bdb" height=220 width=160>| <img src="https://github.com/user-attachments/assets/5ca8c56b-651b-4b1a-9b5a-8d73342d7592" height=200 width=150>|

</div>

<br>

## 1. Role Assignment

### 🍊Kwon Do-hyeon
- **Role**
    - Overall code implementation  
    - Creating the Discord alert bot  
    - Writing the GitHub documentation  

<br>

### 👻Gu Hyeon-jun
- **Role**
    - Presentation  
    - OpenAPI code implementation  

<br>

### 😎Lee Su-hyeon
- **Role**
    - Overall code implementation  
    - Creating the Discord alert bot  
    - Writing the GitHub documentation  

<br>

### 🐬Ryu Tae-an
- **Role**
    - PPT creation  
    - OpenAPI code implementation  

<br>

## 2. Project Period and Measurement Location

### Project Period

- Total project duration: 2024-12-01 ~ 2025-12-19

<br>

### Measurement Location

- Room 515, Department of Environmental Engineering Student Council Room, Engineering Building #3, Chungnam National University  

<img src="https://github.com/user-attachments/assets/b3fc8b72-4173-422e-8501-d53862660097" height=400 width=400>

<br>

## 3. Overview of Applied Technologies

### function calling

- **Gradio and Arduino**  
  - Gradio: Provided an interface to compare outdoor fine dust data and indoor fine dust data collected via Arduino.  

- **OpenAPI**  
  - OpenAPI Standard: Leveraged the AirKorea API to fetch outdoor fine dust data, implementing the API structure and behavior based on the OpenAPI specification.

### discord

- **Discord Integration**  
  - When the indoor fine dust value exceeds the set threshold, a Discord bot sends an automatic alert using the Discord API.  

- **Alert Message**  
  - The alert includes the indoor fine dust value along with a “Ventilation Needed” message. The outdoor fine dust value is also provided to help users decide whether to ventilate.

<br>

## 4. Project Details

## (1) Applied Technologies and Use Cases

### [Measurement Devices and Data Collection]

- **Indoor Fine Dust Measurement**  
  - Connected a Grove sensor to an Arduino to measure indoor fine dust levels in real time.  
  - Integrated the sensor data with a Discord alert system to inform users when ventilation is necessary.

- **Outdoor Fine Dust Data Collection**  
  - Used the AirKorea API to fetch outdoor fine dust concentration.  
  - Implemented function calling based on the OpenAPI spec for efficient data requests and structured responses.  
  - Compared and analyzed indoor and outdoor data to support better decision-making.

### [Chatbot and Alert System]

- **Gradio**  
  - Built a user interface (UI) using Gradio that responds with indoor and outdoor fine dust data.

- **Discord Integration**  
  - Using the Discord API, implemented an automatic alert system that sends a “Ventilation Needed” message to users when the indoor fine dust value exceeds a certain threshold.

### [function calling]

- **Automation and Efficiency**  
  - Applied function calling to automate data requests and processing.  
  - Provided real-time integration and analysis of data from the Arduino Grove sensor and the AirKorea API, delivering useful information to users instantly.

<br>

## (2) Grove Device Details and Connection Method

- **Grove Sensor System**
    - **Modular Design**: Grove sensors support a plug-and-play approach, enabling easy connection to the Arduino.  
    - **Fine Dust Measurement**: Accurately measures indoor air quality data based on particle sizes such as PM2.5 and PM10.

- **How to Connect the Grove Sensor**
    - As shown in the image below, we connected the Grove sensor to the Arduino UNO to collect data.
    
| Fritzing Diagram |
|----------|
|<img src="https://github.com/user-attachments/assets/de3fe5e8-9d60-409f-9d32-eb0ca83c07f3" height=500 width=800>|

  - **Pin Connections**  
      - Red (VCC): 5V pin  
      - Black (GND): GND pin  
      - Yellow (DATA): D8 pin

---

- **Usage in This Project**
    - The sensor data is analyzed in real time, and the system notifies the user of ventilation needs via a Discord alert system.  
    - By using the Gradio UI, users can receive and compare indoor and outdoor fine dust data in an intuitive manner.

<br>

## (3) Characteristics and Utilization of the AirKorea OpenAPI

- **AirKorea OpenAPI Features**
  - Public Data Provision: AirKorea OpenAPI is a public data platform that provides real-time outdoor air quality information in Korea.  
  - Various Air Quality Indicators: Supports queries for various air pollutants such as fine dust (PM10), ultrafine dust (PM2.5), ozone (O3), and nitrogen dioxide (NO2).  
  - Region-Based Data: Users can request real-time air quality information for specific areas (city/county/district) through the API.

- **Usage in the Project**
  - Collected PM2.5 data for the Daejeon region.  
  - Used the AirKorea OpenAPI to obtain real-time ultrafine dust (PM2.5) levels in the Daejeon area.  
  - Compared the outdoor PM2.5 data from the API with the indoor PM2.5 data from the Grove sensor.

- **Data Collection Method**
  - Function Calling  
    - Implemented function calling according to the OpenAPI request and response structure for efficient data retrieval.  
    - Requested PM2.5 values in the Daejeon region by passing the region code as a parameter.  
  - Data Utilization  
    - The fetched outdoor PM2.5 values were analyzed together with the indoor values and displayed visually via the Gradio UI.  
    - Integrated with the Discord alert system so that, when the indoor fine dust value exceeds the threshold, users can also see the outdoor fine dust status to decide on ventilation.

### Google Colab Code
The code comparing AirKorea OpenAPI data with indoor data can be found at the link below.  
👉 [View Google Colab Code](project_CODE%20(1).ipynb)

---

- **Results**

| indoor > outdoor | indoor < outdoor |
| :------: |  :------: |
| <img src="https://github.com/user-attachments/assets/7ba517c3-1148-4664-aab4-419e50870377" height=300 width=300> | <img src="https://github.com/user-attachments/assets/0f6893db-afef-4eb1-8666-1765c4b11563" height=300 width=300> |

<br>

## (4) Detailed Information on the Discord Chatbot Alert System

- **Creating the Discord Chatbot**
  - **Bot Creation**: Created a dedicated chatbot through the Discord Developer Portal.  
  - **Token Issuance**: Obtained a bot token for communication between the bot and server and applied it to the code.  
  - **Bot ID Setup**: Invited the created chatbot to the Discord server and set the bot ID to integrate it into the project.

- **Alert System Implementation**
  - **Threshold Setting**  
    - Determined an average-based threshold considering the characteristics of the measurement location and adjusted it through experimentation.  
    - The system sends an alert if the measured value exceeds the threshold, and sends a normal status message if it is within the normal range.
  
  - **Notification on Threshold Exceedance**  
    - When the indoor PM2.5 value from the Grove sensor surpasses the set threshold, an alert is automatically sent to the Discord server.  
    - The message includes both indoor PM2.5 data and outdoor PM2.5 data (from the AirKorea API), allowing users to easily determine whether to ventilate.

  - **Discord Server Integration**  
    - Used the Python `discord.py` library to connect the chatbot to the server and implement real-time message transmission.  
    - The indoor air quality status and ventilation prompts are posted in the specified server channel.

  - **Mobile App Alerts**  
    - Through the Discord mobile app, real-time notifications are delivered to users’ smartphones.  
    - Users can quickly check the indoor fine dust status and take immediate action from anywhere.

---

### **Example of Chatbot Alert Message**
<img src="https://github.com/user-attachments/assets/132b5e9b-c93e-41ea-8409-60b92ae40d3a" height=500 width=250>

---

### **Summary of Operation**
1. **Grove Sensor** → Measures indoor PM2.5 data  
2. **AirKorea OpenAPI** → Fetches outdoor PM2.5 data  
3. **Threshold Comparison** → If indoor value exceeds threshold, chatbot triggers  
4. **Discord Server** → Sends real-time alert  
5. **Mobile App Integration** → Push notification arrives on phone  

<br>

## 5. Trial and Error

- **(1) OpenAI and Gradio Version Compatibility Issues**  
  - Encountered an issue where the Gradio chat would not work properly in a Jupyter Notebook environment due to version conflicts between OpenAI and Gradio.

| Gradio Version |
|----------|
| <img src="https://github.com/user-attachments/assets/02e40109-83c3-4f6c-8de0-144b9af3a2e5" height=300 width=300>|

<br>

- **(2) Difficulties Using the AirKorea API**  
  - Faced challenges in understanding the request format and the response structure for the API calls.

<br>

- **(3) Complexity in Setting Up the Gradio Chatbot Calculation Function**  
  - Struggled to set up a calculation function that compares **real-time indoor measurement** values with **outdoor API** values.

<br>

- **(4) Issues with Jetson Nano Camera and Image Data Processing**  
  - Planned to use the Jetson Nano camera to detect whether the door was open or closed, but had difficulties in implementing image processing.

<br>

- **(5) Discord Indoor Fine Dust Alert Bot Implementation**  
  - Initially had issues where the alert would not be delivered to the mobile Discord app.

---

## 5-1. How We Resolved These Issues

- **(1) Resolving OpenAI and Gradio Version Compatibility**  
  - Reinstalled Gradio at **3.0.12** and OpenAI at **0.8.0** to fix compatibility issues.  
  - Reinstallation code:
    ```bash
    pip install gradio==3.0.12
    pip install openai==0.8.0
    ```
  - After these changes, both the Gradio chat and OpenAI API calls worked correctly.

<br>

- **(2) Resolving AirKorea API Usage Difficulties**  
  - Carefully reviewed the API documentation to clearly understand the request parameters and the response structure.  
  - Example code for calling the API:
    ```python
    import requests

    url = "http://api.airkorea.or.kr"
    params = {"region": "Daejeon", "serviceKey": "YOUR_API_KEY"}
    response = requests.get(url, params=params)
    print(response.json())
    ```

<br>

- **(3) Resolving Gradio Chatbot Calculation Function Setup**  
  - Implemented the comparison logic in a Python function:
    ```python
    def compare_pm25(indoor, outdoor):
        if indoor > outdoor:
            return "The indoor air quality is higher. Ventilation is needed."
        return "The indoor measurement is lower. Please keep the window closed."
    ```

<br>

- **(4) Adjusting the Direction for Jetson Nano Camera Image Data Processing**  
  - Acknowledged the complexity and time consumption of image data processing and chose to focus on the fine dust measurement and alert chatbot system instead.

<br>

- **(5) Resolving Issues with the Discord Indoor Fine Dust Alert Bot**  
  - Modified the channel ID and message sending code for the Discord bot to properly receive alerts on the phone.
    ```python
    import discord

    TOKEN = "YOUR_BOT_TOKEN"
    CHANNEL_ID = 123456789012345678

    client = discord.Client(intents=discord.Intents.default())

    @client.event
    async def on_ready():
        channel = client.get_channel(CHANNEL_ID)
        await channel.send("✅ Normal: Indoor PM2.5 level is within normal range.")
    client.run(TOKEN)
    ```
  - **Result**: Successfully received notifications on the mobile app.

<br>

## 6. Future Improvements

- **(1) More Accurate Threshold Settings**  
  - Currently, the threshold is based on an empirical average. A dynamic threshold that reflects changes in air quality over time is needed.  
  - Utilizing AI models to learn from long-term data can yield more precise threshold predictions.

- **(2) Continuous Monitoring of Indoor and Outdoor Data**  
  - Need to build a database for continuous collection of Grove sensor and AirKorea API data, enabling long-term pattern analysis.  
  - Strengthening historical data visualization and prediction capabilities can provide more valuable insights to users.

- **(3) Expanding Outdoor Data APIs**  
  - In addition to AirKorea OpenAPI, consider using other public data APIs (e.g., Ministry of Environment, Korea Meteorological Administration) to gather more diverse air quality data.  
  - This can help reduce measurement errors and provide a comprehensive analysis of local fine dust conditions.

- **(4) Integrating Automated Ventilation Systems**  
  - Go beyond Discord alerts by linking ventilation alerts to automatically operate air purifiers or ventilation devices.  
  - This can be achieved by applying IoT technology to a smart home environment.

<br>

## 7. Project Reflections

### 🍊Kwon Do-hyeon
I had a lot of fun during this project, especially by experimenting with Arduino and Jetson Nano, which I wasn’t very familiar with. As an environmental engineering student, it was meaningful to work on a project involving fine dust concentration data. Creating code that sends Discord notifications directly to my phone using GPT was a new experience, and I plan to delve deeper into related programming. This project also strengthened my interest in both environmental fields and IT technology. It was truly enjoyable!

<br>

### 👻Gu Hyeon-jun
This past month was full of learning opportunities. I realized how impossible it would have been to accomplish this alone, so I want to express my gratitude to my teammates. On a personal note, I regret that I focused solely on implementing features within the given timeframe and didn’t document the details of Arduino or other newly learned things more systematically. Now that I’ve become aware of this, I trust that I will do better in organizing information in the future. Thanks for all your hard work!

<br>

### 😎Lee Su-hyeon
During the initial setup for this team project, I realized the importance of systematic planning. I hope to continue improving, becoming more structured and efficient in future projects. Transitioning directly from regular classes to this project, I found it challenging to apply what I’d learned, but it was a great opportunity to identify areas where I need more practice. Solving issues alongside my teammates really showed me the benefits of collaboration. However, because we were pressed for time, we couldn’t thoroughly document all the issues we resolved together. Thanks for all your hard work, everyone! 🧡

<br>

### 🐬Ryu Tae-an
From this Industrial AI Jetson Nano class, the most interesting takeaway was understanding how indoor air purifiers work. It was meaningful that we could measure fine dust on our own, and I feel like we created a basic yet functional air purifier concept. We even built a feature that sends automatic alerts to our phones, and I’d like to install this system in my own room someday. By measuring my room’s fine dust, I’d know when to ventilate—especially while cooking—and if a fire occurs, I’d be alerted even when I’m away. This experience truly made me feel like a developer, and I hope it leads to future career opportunities in the air quality field.
