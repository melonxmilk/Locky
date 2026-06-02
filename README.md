# Locky

Locky is an Android application built as part of a large-scale, multi-disciplinary final-year 
project spanning IoT, blockchain, and backend systems, developed over 9 months by a 
cross-functional team of final-year students.

My team owned the backend cycle, responsible for cloud data storage, user authentication, 
and blockchain integration, while separate teams handled the IoT hardware layer.

---

## Tech Stack

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-039BE5?style=for-the-badge&logo=Firebase&logoColor=white)
![Android Studio](https://img.shields.io/badge/Android%20Studio-3DDC84.svg?style=for-the-badge&logo=android-studio&logoColor=white)
![Solidity](https://img.shields.io/badge/Solidity-363636?style=for-the-badge&logo=solidity&logoColor=white)

> Note: Firebase integration requires collaborator access to run as intended.

---

## System Architecture

Locky was developed across three independently owned cycles:

| Cycle | Responsibility |
|---|---|
| IoT | Physical locker hardware and sensor integration |
| Backend (our team) | Firebase data storage, authentication, and blockchain integration |
| Blockchain | Smart contract deployment for tamper-proof booking records |

---

## Features

**Bluetooth Connectivity**
Establishes a connection between the Android app and the physical locker, enabling real-time 
data exchange via a gateway string interface.

**Live Locker Availability**
Reads sensor data from in-built locker sensors and syncs availability status to Firebase 
Realtime Database.

**Google Authentication**
User login is handled via Firebase Authentication with Google Sign-In, providing secure and 
seamless access.

**Firebase Cloud Backend**
All locker state and user data is persisted on Firebase, serving as the central data layer 
between the Android client and the IoT hardware.

**Firebase Cloud Messaging (FCM)**
Push notification support integrated via FCM, enabling real-time alerts to users.

**Blockchain-backed Booking Records**
Locker bookings are registered on-chain via a Solidity smart contract (`BookingContract.sol`) 
deployed on Ethereum. Each booking record stores a document number, receiver, locker ID, and 
booker identity, ensuring records are immutable and auditable.

---

## Smart Contract

`BookingContract.sol` is written in Solidity (^0.7.0) and exposes a single public function:

- `registerNewBooking()` -- records a new locker booking on-chain with document number, 
  receiver, locker, and booker fields
- All bookings are stored in a public mapping and accessible on-chain for auditability

---

## Demo

https://user-images.githubusercontent.com/58766039/173226385-7d23ade0-8bc6-4631-9efd-30f858d67d01.mp4
