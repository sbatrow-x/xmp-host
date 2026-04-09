# Android TV App + Telegram Mini App + Admin Panel
## Client Approval Proposal

**Prepared for:** Client Review  
**Project Type:** Streaming Platform with Android TV App, Telegram Mini App, Admin Panel, Serial Key Activation, and Ad Management  
**Purpose:** Approval of concept, features, scope, and development direction

---

## 1. Executive Summary

This project is a media streaming platform designed around a simple and scalable business model.

The business owner will sell a **Google TV / Android TV device** with a custom app already installed. The customer buys the device, takes it home, connects it to the TV, opens the app, enters a **serial activation key** included in the box, and starts using the service.

The platform will include:

1. **Android TV App** for watching movies and TV channels  
2. **Telegram Mini App** for access through Telegram  
3. **Admin Panel** to manage content, channels, ads, serial keys, and platform settings  
4. **Backend APIs** for activation, movie management, TV channel management, and ad delivery

The platform will **not require user account creation**. Instead, access will be controlled through **serial number activation**.

A built-in advertising system will allow the admin to show **image or video ads** at key moments during movie playback, including:

- one ad before the movie starts  
- one ad in the middle of the movie  
- one ad near the end of the movie

Video ads may be **15 or 25 seconds long**, with a **Skip** option available **after 15 seconds**, similar to YouTube-style ad behavior.

This document is intended to define the project clearly so the client can review, approve, and proceed to the next phase.

---

## 2. Business Idea

### Main Concept

The business model is based on selling a ready-to-use streaming device.

### Customer Journey

1. Customer buys the TV device with the app pre-installed  
2. Customer takes the device home and connects it to the TV  
3. Customer opens the app  
4. Customer enters the serial key found in the box  
5. Device is activated  
6. Customer can start watching movies and TV channels immediately

### Key Advantage

This approach removes the need for:

- email registration  
- passwords  
- account creation  
- complicated onboarding

The experience is simple and suitable for users who want instant access.

---

## 3. Project Goals

The goal is to build a complete streaming ecosystem that is easy for customers to use and easy for the business owner to manage.

### Main Goals

- Provide a simple activation process using serial numbers only  
- Deliver movies and live TV channels through Android TV  
- Extend access through a Telegram Mini App  
- Manage all content from a central admin panel  
- Monetize usage through image and video ads  
- Support a device-based business model

---

## 4. Project Components

## 4.1 Android TV App

The Android TV App is the main customer-facing product.

### Core Functions

- Launch on Google TV / Android TV devices  
- Activation using a serial number  
- Browse movies  
- Browse TV channels  
- Play movies  
- Play live TV streams  
- Show ads before and during movie playback  
- Remote-control friendly interface

### Key Features

- TV-optimized UI/UX  
- Large focus states for navigation with remote  
- Fast activation screen  
- Home screen with movies and channels  
- Search and category browsing  
- Movie details page  
- Video player with ad insertion support  
- Secure API communication with backend

### Activation Flow

- User opens app for first time  
- App asks for serial key  
- User enters key with remote  
- App sends serial number and device information to backend  
- Backend validates the key  
- If valid, app activates device and unlocks content  
- If invalid, app shows error and asks to retry

### Movie Playback Ad Flow

For each movie, the app should support:

1. **Pre-roll ad** before movie starts  
2. **Mid-roll ad** during the movie  
3. **Near-end ad** close to the end of the movie

### Ad Rules

- Ads can be image or video  
- Video ads can be 15 or 25 seconds  
- Skip button appears after 15 seconds  
- Admin controls ad placement and content  
- The player resumes the movie after the ad ends or is skipped

---

## 4.2 Telegram Mini App

The Telegram Mini App is the secondary access point for users.

### Purpose

It allows the service to be accessed within Telegram for convenience and wider reach.

### Possible Features

- Browse available movies  
- Browse TV channels  
- View featured content  
- Enter or verify serial activation  
- Access subscription or activation status  
- Open support/contact options  
- Watch supported media if technically and policy-wise allowed

### Recommended Use

The Telegram Mini App should be treated as:

- an additional customer access channel  
- a lightweight companion product  
- a promotional and support entry point

### Important Note

The exact video playback capabilities inside Telegram Mini Apps must be validated during technical planning, because Telegram Web App behavior, playback restrictions, and platform policies may affect the final implementation.

---

## 4.3 Admin Panel

The Admin Panel is the control center for the whole platform.

### Main Responsibilities

- Manage movies  
- Manage TV channels  
- Manage ads  
- Manage serial numbers  
- Monitor device activations  
- Configure app settings

### Admin Panel Modules

#### A. Dashboard
- total activated devices  
- total available movies  
- total live channels  
- total ads  
- recent activations  
- playback statistics (optional in later phase)

#### B. Movie Management
- add movies  
- edit movie details  
- delete movies  
- upload posters and thumbnails  
- assign categories  
- add video source URL or stream source  
- enable or disable titles

#### C. TV Channel Management
- add live TV channels  
- edit channel name  
- upload channel logo  
- configure stream URL  
- group channels by category  
- enable or disable channels

#### D. Ads Management
- add image ads  
- add video ads  
- set ad duration  
- set skip timing  
- assign ad position:
  - before movie  
  - middle of movie  
  - near end of movie
- choose campaign status  
- upload media files  
- manage ad scheduling

#### E. Serial Key Management
- generate serial numbers  
- assign serial keys to devices or product boxes  
- activate/deactivate keys  
- set expiry date if subscription model is used  
- mark key as used or unused  
- view which device used which key

#### F. Settings
- branding  
- player settings  
- app configuration  
- support links  
- maintenance mode

---

## 5. No User Accounts Requirement

A major requirement is that users should **not need to create accounts**.

### Approved Logic

Instead of usernames and passwords, the platform will use:

- serial number activation  
- device registration after activation  
- backend validation to authorize content access

### Benefits

- easier onboarding  
- lower support burden  
- better fit for TV-based customers  
- simple buying and setup experience

### Technical Note

The backend should still keep an internal device record for:

- activation status  
- device ID  
- serial number used  
- last active time  
- subscription or expiry state if needed in future

---

## 6. Serial Key Activation System

The serial key is the main access control mechanism.

### How It Works

- Each sold device or product box includes a unique serial key  
- Customer enters the key in the TV app  
- Backend checks if the key is valid  
- If valid, the backend links the key with the device  
- Access is granted

### Suggested Rules

- one serial key per sold device  
- serial can be single-use  
- serial can optionally include expiry date  
- serial should be stored securely in backend  
- backend should prevent repeated unauthorized use

### Recommended Data Stored for Each Serial

- serial code  
- status (unused / active / expired / blocked)  
- activation date  
- linked device ID  
- validity period  
- notes

---

## 7. Advertising System Requirements

The ad system is a core monetization feature.

### Ad Types

- image ads  
- video ads

### Video Ad Behavior

- 15-second or 25-second ad formats  
- skip button shown after 15 seconds  
- full-screen playback on TV app

### Ad Placement for Movies

1. **Start of movie**  
2. **Middle of movie**  
3. **Near end of movie**

### Admin Controls

- upload ad media  
- set ad type  
- set ad duration  
- define skip timing  
- assign ad positions  
- activate/deactivate ads  
- optionally schedule campaigns by date

### Playback Logic Example

- User clicks a movie  
- Pre-roll ad plays  
- Movie begins  
- At configured playback time, mid-roll ad plays  
- Movie resumes  
- Near the end, final ad plays  
- Movie continues until end

### Optional Advanced Features for Later Phase

- campaign targeting by movie category  
- frequency caps  
- impressions reporting  
- click tracking for image ads in companion app  
- sponsor labels

---

## 8. Movie API Requirements

The system needs APIs to manage movie content.

### Required Movie APIs

#### Admin APIs
- create movie  
- update movie  
- delete movie  
- upload poster  
- upload thumbnail  
- set source URL  
- set category  
- publish/unpublish movie

#### App APIs
- get movie list  
- get featured movies  
- get movie details  
- search movies  
- get movie stream/playback URL  
- get ad rules for selected movie

### Movie Data Fields

- movie ID  
- title  
- description  
- category  
- language  
- release year  
- duration  
- poster image  
- banner image  
- playback source  
- subtitle options  
- active status

---

## 9. TV Channel API Requirements

The system also needs APIs to manage live TV channels.

### Required TV Channel APIs

#### Admin APIs
- create channel  
- update channel  
- delete channel  
- upload logo  
- set stream URL  
- assign category  
- publish/unpublish channel

#### App APIs
- get channel list  
- get categories  
- get channel details  
- get live stream URL

### Channel Data Fields

- channel ID  
- channel name  
- logo  
- category  
- stream URL  
- status  
- display order

---

## 10. Backend System Requirements

The backend will connect all platform components.

### Backend Responsibilities

- validate serial numbers  
- activate devices  
- serve movies and channels  
- serve ad configuration  
- handle admin panel operations  
- store platform data  
- manage security and access control

### Suggested Backend Modules

- authentication for admin only  
- serial key service  
- device activation service  
- movie service  
- live channel service  
- ad service  
- media metadata service  
- analytics service (optional)

### Suggested Database Entities

- admins  
- devices  
- serial keys  
- movies  
- movie categories  
- TV channels  
- channel categories  
- ads  
- ad campaigns  
- activation logs

---

## 11. Recommended Technical Architecture

The following architecture is recommended for a scalable solution.

### Frontend Applications

- **Android TV App**: native Android TV application  
- **Telegram Mini App**: web application integrated with Telegram  
- **Admin Panel**: web dashboard for management

### Backend

- REST API or GraphQL API  
- Secure admin authentication  
- Media and metadata management  
- Activation and ad services

### Storage

- database for app data  
- cloud file storage for posters, logos, and ads  
- secure storage/CDN for media delivery if required

### Video Playback Support

- video player supporting streaming formats such as HLS/DASH  
- ad playback logic integrated into media player flow  
- resume playback after ad completion or skip

---

## 12. Suggested User Flows

## 12.1 Customer Activation Flow

1. Connect device to TV  
2. Open app  
3. Enter serial key  
4. Backend validates key  
5. Device becomes active  
6. Home screen opens  
7. User starts browsing content

## 12.2 Customer Movie Flow

1. Open movie details  
2. Press play  
3. Pre-roll ad starts  
4. Movie begins  
5. Mid-roll ad plays at configured point  
6. Movie resumes  
7. Near-end ad plays  
8. Movie finishes

## 12.3 Admin Content Flow

1. Login to admin panel  
2. Add movie or TV channel  
3. Upload poster/logo and media source  
4. Publish content  
5. Content becomes visible in apps

## 12.4 Admin Ad Flow

1. Login to admin panel  
2. Upload image or video ad  
3. Select ad duration and skip timing  
4. Choose placement positions  
5. Save and publish  
6. Ad becomes active in movie playback

---

## 13. Suggested Phased Development Plan

### Phase 1 - Planning and UX
- final requirement collection  
- technical validation  
- wireframes  
- user flow definitions  
- architecture planning

### Phase 2 - Core Backend and Admin Panel
- backend setup  
- database design  
- serial activation system  
- movie API  
- TV channel API  
- ad management API  
- admin panel development

### Phase 3 - Android TV App
- TV app UI  
- activation flow  
- movie and channel browsing  
- player integration  
- ad playback support  
- API integration

### Phase 4 - Telegram Mini App
- Telegram Mini App UI  
- content browsing  
- activation/status functions  
- supported playback features  
- API integration

### Phase 5 - QA and Launch Preparation
- testing  
- device compatibility checks  
- serial key testing  
- stream testing  
- ad behavior testing  
- admin workflow testing

### Phase 6 - Production Launch
- deploy backend  
- deploy admin panel  
- publish app distribution process  
- preload app on devices  
- prepare customer support process

---

## 14. Risks and Important Considerations

Before final approval and development, the following points should be reviewed carefully.

### A. Content Rights and Licensing
All movies and TV channels must be legally licensed or properly authorized for distribution.

### B. Google TV / Android TV Distribution Strategy
If apps are pre-installed on sold devices, the distribution and maintenance strategy should be clearly planned.

### C. Telegram Mini App Limitations
Telegram Mini App capabilities, especially for full streaming experiences, must be validated during planning.

### D. Ad User Experience
Too many ads may reduce customer satisfaction. Ad timing should be configured carefully.

### E. Stream Stability
Movie and live TV streams must be stable and scalable for real customer use.

### F. Security
Serial numbers, stream URLs, and admin functions should be protected from misuse.

---

## 15. Items Requiring Client Approval

Please review and approve the following points:

1. Overall business concept  
2. Android TV App scope  
3. Telegram Mini App scope  
4. Admin panel scope  
5. No-account activation model using serial number  
6. Movie and TV channel management APIs  
7. Ad logic with 3 placements during movie playback  
8. YouTube-style skip behavior for video ads  
9. Recommended phased development process

---

## 16. Proposed Final Scope Summary

The approved project scope will include:

- Android TV App  
- Telegram Mini App  
- Admin Panel  
- Serial key activation system  
- Movie content management  
- TV channel management  
- Ad management system  
- Movie playback ads at start, middle, and near end  
- Image and video ad support  
- Skip button after 15 seconds for video ads  
- Backend APIs for apps and admin operations

---

## 17. Recommendation

This project is commercially attractive because it combines:

- hardware-based sales  
- easy customer onboarding  
- recurring content usage  
- centralized management  
- ad monetization potential

It is recommended to proceed first with **detailed technical planning and UI/UX design**, followed by phased development.

---

## 18. Approval Section

**Client Decision:**  
[ ] Approved  
[ ] Approved with changes  
[ ] Not approved

**Comments / Requested Changes:**  

____________________________________________________________  
____________________________________________________________  
____________________________________________________________

**Client Name:** __________________________  
**Signature:** ____________________________  
**Date:** _________________________________

---

## 19. Closing Note

This document is intended to confirm the business concept, product scope, and technical direction before development begins. After approval, the next step will be to prepare the detailed technical specification, UI/UX design, and implementation roadmap.
