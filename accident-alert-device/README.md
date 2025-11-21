# Accident Alert Device

### *An IoT-based Impact Detection & Emergency Notification System*

The Accident Alert Device is a compact IoT product designed to automatically detect accidents and instantly notify emergency contacts with the user’s real-time location. It is built using **Arduino Nano**, **ADXL335 accelerometer**, **NEO-6M GPS**, and **SIM800L GSM module**, making it a low-cost and portable safety solution for two-wheelers, four-wheelers, personal safety kits, and logistics.

---

## 📌 **Key Features**

* **Real-time Impact Detection** using ADXL335 accelerometer
* **Automatic SMS Alert** with Google Maps location link
* **Automatic Emergency Call** via SIM800L
* **30-second Cancellation Window** using a push-button
* **Buzzer Notification** on crash detection
* **LCD Display Feedback** for status updates
* **Low-cost, compact, and portable design**

---

## **How It Works**

1. **Impact Sensing**
   The ADXL335 continuously measures acceleration changes. If a sudden high-magnitude jerk is detected above a predefined threshold, the device assumes a crash event.

2. **Immediate Warning**
   A buzzer activates, and a 30-second timer begins.

   * If the user presses the cancel button → alert is aborted
   * If no cancel input → alert sequence continues

3. **GPS Location Acquisition**
   The NEO-6M GPS gathers latitude and longitude coordinates using the TinyGPS++ library.

4. **Alert Transmission**
   The SIM800L module:

   * Sends an SMS containing a **Google Maps link**
   * Initiates an **SOS call** to the emergency contact

---

## 🛠️ **Hardware Components**

| Component                 | Purpose                                 |
| ------------------------- | --------------------------------------- |
| **Arduino Nano**          | Microcontroller (brain of the system)   |
| **ADXL335 Accelerometer** | Detects sudden impact/jerk              |
| **NEO-6M GPS Module**     | Provides real-time latitude & longitude |
| **SIM800L GSM Module**    | Sends SMS and makes calls               |
| **LCD 16x2 (I2C)**        | Displays device status                  |
| **Buzzer**                | Audible alert during crash detection    |
| **Push Button**           | Cancel false SOS                        |
| **Battery Pack (18650)**  | Portable power supply                   |

---

## 🔧 **Software & Libraries Used**

* **Arduino IDE**
* **TinyGPS++** – GPS parsing
* **AltSoftSerial** – Serial communication with GPS
* **SoftwareSerial** – Serial communication with GSM module
* **LiquidCrystal_I2C** – LCD display

## 📝 **Setup Instructions**

1. Clone the repository
2. Open the `.ino` file in Arduino IDE
3. Install required libraries
4. Configure emergency phone number in code:

   ```cpp
   const String EMERGENCY_PHONE = "+91XXXXXXXXXX";
   ```
5. Upload the code to Arduino Nano
6. Power the device with a 5V battery pack



