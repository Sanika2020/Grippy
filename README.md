# 🛡️ SafeGrip — Women's Safety Glove

> **Smart. Swift. Secure.**  
> A wearable emergency safety device designed to provide discreet, instant, and multi-layered protection.

## OVERVIEW

**SafeGrip** is a wearable women's safety glove designed to provide immediate assistance during emergency situations. Unlike conventional safety applications that require access to a smartphone and multiple actions, SafeGrip allows the user to activate multiple safety features through a **hidden button or voice command**.

Once activated, the system simultaneously:

- Captures the user's location using GPS
- Sends an emergency SMS with a Google Maps location link
- Activates a loud alarm to attract attention
- Activates an electric shock defense mechanism

The system operates using **GSM connectivity rather than requiring an internet connection or smartphone**, making it suitable for areas with limited internet access.

---

##  PROBLEM STATEMENT

During emergency situations, accessing a smartphone may be difficult or impossible. Existing solutions such as safety applications and whistles can require multiple steps or may not be effective when the user is under stress.

This can result in:

- Delayed emergency alerts
- Difficulty communicating the user's location
- Dependence on smartphones and internet connectivity
- Limited time to respond to an attacker

**SafeGrip addresses these challenges by integrating multiple emergency functions into a single wearable device.**

---

##  PROPOSED SOLUTION

SafeGrip integrates three primary safety mechanisms into a wearable glove:

###  Location SMS Alert
The **NEO-6M GPS module** obtains the user's coordinates, while the **SIM800L GSM module** sends an SMS containing a location link to pre-selected emergency contacts.

###  Loud Alarm
A buzzer generates a loud alarm to attract the attention of people nearby and potentially deter an attacker.

###  Electric Shock Defense
An electric shock circuit is activated as an additional defense mechanism, intended to provide the user with an opportunity to escape.

###  Voice Trigger
The proposed system also includes a voice-trigger mechanism that can recognize predefined commands such as **"Help!"** or **"Emergency!"** and activate the safety functions.

---

##  SYSTEM WORKFLOW

```text
              ┌──────────────────┐
              │   User in        │
              │   Emergency      │
              └────────┬─────────┘
                       │
              Hidden Button /
               Voice Trigger
                       │
                       ▼
              ┌──────────────────┐
              │  Microcontroller │
              │   Arduino Uno R4 │
              └────────┬─────────┘
                       │
          ┌────────────┼────────────┐
          ▼            ▼            ▼
      ┌───────┐   ┌──────────┐  ┌───────────┐
      │  GPS  │   │   GSM    │  │  Safety   │
      │NEO-6M │   │ SIM800L  │  │ Features  │
      └───┬───┘   └────┬─────┘  └─────┬─────┘
          │             │              │
          │             ▼         ┌────┴────┐
          │        Emergency SMS   │         │
          │        + GPS Location  ▼         ▼
          │                     Alarm     Shock
          │
          └────── Location Data
```

---

##  Hardware Components

| Component | Purpose |
|---|---|
| **Arduino Uno R4** | Main microcontroller |
| **SIM800L GSM Module** | Sends emergency SMS |
| **NEO-6M GPS Module** | Obtains location coordinates |
| **Switch / Hidden Button** | Manual emergency activation |
| **Buzzer / Alarm** | Audible emergency alert |
| **SPDT Relay** | Controls safety circuit |
| **Electric Shock Circuit** | Additional defense mechanism |
| **9V Battery** | Power source |
| **16×2 LCD** | System information display |

---

##  TECHNICAL APPROACH

SafeGrip uses an **Arduino Uno R4** as the central controller.

When the emergency trigger is activated:

1. The controller initiates the safety sequence.
2. The GPS module obtains the user's location.
3. The GSM module sends an SMS containing the location.
4. The alarm is activated.
5. The defense circuit is activated.
6. The user can use the resulting response window to move away from the threat.

The design is intended to operate without requiring a smartphone or internet connection, provided GSM service is available.

---

##  Sample Emergency Message

```text
I'm in trouble. Please help.
http://maps.google.com/?q=12.9716,77.5946
```

The coordinates in the message represent the location obtained from the GPS module.

---

## Key Features

- **Discreet activation** — Hidden emergency trigger
- **One-step emergency response** — Multiple functions activated together
- **GPS-based location sharing** — Sends real-time coordinates
- **GSM-based communication** — Does not require internet access
- **Loud emergency alarm** — Attracts attention
- **Wearable design** — Designed to resemble a regular glove
- **Voice-trigger capability** — Supports predefined emergency commands
- **Low-power operation** — Designed around a replaceable battery
---

##  Technology Stack

**Hardware**
- Arduino Uno R4
- SIM800L GSM
- NEO-6M GPS
- SPDT Relay
- Buzzer
- 9V Battery
- Electric Shock Circuit

**Software / Embedded**
- Arduino
- Embedded C/C++
- GPS communication
- GSM communication

---

## ⚠️ Safety Notice

SafeGrip is a **prototype developed for educational and hackathon purposes**. The electrical defense mechanism involves safety risks and should only be implemented, tested, and handled under appropriate supervision and with suitable electrical safety precautions.

The prototype should not be considered a certified personal safety device or a substitute for emergency services.

---

##  Project Documentation

Project presentations and supporting documentation can be found in this repository.

---

##  Vision

> **Safety shouldn't depend on finding your phone.  
> With SafeGrip, help is just a press away.**
