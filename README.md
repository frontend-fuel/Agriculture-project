# Agritech - Smart Farm Monitoring & Control 🌾🚰

Agritech is a 4th-year IoT project designed to revolutionize small-scale farming. It provides real-time monitoring of soil and climate conditions, paired with intelligent irrigation control directly from a mobile device.

## 🚀 Features
*   **Live Dashboard**: Real-time visualization of Temperature, Humidity, Soil Moisture, and Water Levels.
*   **Intelligent Pump Control**: Manual toggle with safety overrides for low water levels.
*   **Advanced Analytics**: Historical data trends and session averages powered by ThingSpeak.
*   **Secure Authentication**: JWT-based login, registration, and password management.
*   **Cloud Precision**: Integrated with MongoDB Atlas for persistent user data and ThingSpeak for IoT logging.

## 🛠️ Technology Stack
*   **Frontend**: React Native, Expo, Lucide Icons, React Native Chart Kit.
*   **Backend**: Node.js, Express.
*   **Database**: MongoDB Atlas.
*   **IoT Cloud**: ThingSpeak.
*   **Hardware (Compatible)**: ESP32 / Arduino with Soil Moisture, DHT11, and Ultrasonic sensors.

## 📦 Installation & Setup

### Backend
1. Go to `server` folder: `cd server`
2. Install dependencies: `npm install`
3. Create a `.env` file with your `MONGODB_URI` and `JWT_SECRET`.
4. Start the server: `npm start`

### Frontend
1. Go to `client` folder: `cd client`
2. Install dependencies: `npm install`
3. Start Expo: `npm start`
4. Use **Expo Go** on your phone to scan the QR code.

## 🛰️ IoT Integration
The system uses two ThingSpeak channels:
*   **Sensors (Read)**: Channel ID `3044247` (Fields 1-4 for Temp, Hum, Soil, Water).
*   **Pump (Write/Read)**: Channel ID `2931414` (Field 1 for status).

## 📄 License
This project is developed as part of a 4th-year academic curriculum. All rights reserved.

---
**Developed with ❤️ for Advanced Agriculture.**
