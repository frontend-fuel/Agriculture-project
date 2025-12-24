# Agritech Deployment Guide 🚀

This guide will help you move your project from your local computer to the cloud so anyone can use it.

---

## 1. Backend Deployment (Node.js + MongoDB)
The easiest way to host your server for free is **Render**.

### Steps for Render:
1.  **Push to GitHub**: Create a GitHub repository and push your entire `projectapp` folder (or just the `server` folder).
2.  **Create Web Service**:
    *   Log in to [Render.com](https://render.com/).
    *   Click **New +** > **Web Service**.
    *   Connect your GitHub repository.
3.  **Configure Environment Variables**: In the Render dashboard, go to **Environment** and add:
    *   `MONGODB_URI`: `mongodb+srv://yarrusasi_db_user:zgP9wqp5kjaitlGN@cluster0.8x19jvn.mongodb.net/?appName=Cluster0`
    *   `JWT_SECRET`: `your_super_secret_key`
    *   `PORT`: `5000`
4.  **Build Settings**:
    *   **Root Directory**: `server`
    *   **Build Command**: `npm install`
    *   **Start Command**: `node index.js`
5.  **Get Your URL**: Once deployed, Render will give you a URL like `https://agritech-server.onrender.com`.

---

## 2. Connect Mobile App to Production
Once you have your Render URL:
1.  Open `client/src/context/AuthContext.js`.
2.  Update the `PRODUCTION_URL` constant with your Render URL:
    ```javascript
    const PRODUCTION_URL = 'https://agritech-server.onrender.com/api';
    ```

---

## 3. Mobile App Build (Expo APK)
To create an Android APK that you can share with friends or your professor:

### Pre-requisites:
*   Install EAS CLI: `npm install -g eas-cli`
*   Log in to Expo: `eas login`

### Build Steps:
1.  **Initialize EAS**: Run `eas build:configure` in the `client` folder.
2.  **Generate APK**: Run the following command to create a preview build:
    ```bash
    eas build -p android --profile preview
    ```
3.  **Download**: Once the build finishes (about 10-15 mins), Expo will give you a QR code and a link to download the `.apk` file.

---

## 4. Final Verification Checklist ✅
*   [ ] Scan the APK on an Android phone.
*   [ ] Register a new user and ensure it appears in MongoDB Atlas.
*   [ ] Toggle the Pump and check if the ThingSpeak channel updates.
*   [ ] Open the Analytics tab to confirm graphs load from the cloud.

Congratulations! Your Agritech system is now a world-class IoT solution! 🌾✨
