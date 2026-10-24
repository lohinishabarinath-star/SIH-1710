# Smart India Hackathon Workshop
# Date: 24.10.2026
## Register Number: 212225240079
## Name: LOHINI S
## Problem Title
SIH 1710: Enhancing Navigation for Railway Station Facilities and Locations
## Problem Description
Background: Railway stations are complex environments with numerous facilities and locations such as ticket counters, platforms, restrooms, food courts, and waiting areas. Passengers often face difficulties in navigating these spaces, especially in large or unfamiliar stations. Efficient and user-friendly navigation systems are crucial for improving passenger experience, reducing congestion, and ensuring timely travel connections. Description: The problem involves developing a comprehensive navigation solution for railway stations that assists passengers in locating various facilities and destinations within the station premises. This includes creating detailed maps, providing real-time directions, and integrating features such as accessibility options for individuals with disabilities. The solution should be intuitive, easy to use, and accessible via multiple platforms, including mobile devices and digital kiosks. Key challenges include updating navigation information in real-time, ensuring accuracy, and accommodating the diverse needs of all passengers. Expected Solution: The expected solution is a multi-platform navigation system that provides detailed, real-time directions to all facilities and locations within a railway station. This system should include: A mobile application with 3D interactive maps and step-by-step navigation. Digital kiosks located throughout the station with touch-screen interfaces. Voice-guided navigation for visually impaired passengers. Regular updates to reflect changes in station layout and facility locations. Integration with existing railway apps and services for seamless user experience. The solution should enhance the overall passenger experience by reducing confusion, saving time, and improving accessibility within the station.

## Problem Creater's Organization
Ministry of Railway

## Idea

"RailWayfinder”: a multi-platform, indoor navigation system for railway stations.

GPS fails indoors, so the system combines BLE beacons, Wi-Fi positioning and QR-code anchors to locate passengers inside the station. A routing engine then guides them to the nearest platform, ticket counter, restroom, food court, or waiting room. Every station has a digital twin (a 3D map plus a graph of walkable paths) that station staff can update through an admin portal, so the information stays current.

Key differentiators:

1.Works everywhere: a mobile app, touch kiosks and a voice interface share one backend.
2.Accessibility first: step-free routing for wheelchair users, and audio and haptic guidance for visually impaired passengers.
3.Live awareness: routes adapt to platform changes, crowd density, lift outages and construction closures.
4.Train-aware: enter a PNR or train number and the app shows your platform, coach position and the shortest path to it.
5.Works offline: station maps are cached on the phone, so navigation continues even if the network drops.

## Proposed Solution / Architecture Diagram

Solution flow

1. The passenger opens the app or a kiosk and either searches
for a facility or enters a PNR or train number.

2. The system fetches the train's platform and coach position
from the railway APIs.

3. The positioning module estimates the user's location
(BLE/Wi-Fi/QR).

4. The routing engine computes the best path using A* or
Dijkstra on the station graph, filtered by user profile (normal,
wheelchair, elderly, visually impaired).

5. The app shows a 3D map with step-by-step directions. Voice
mode gives turn-by-turn spoken guidance.

6. If the user goes off route or a closure occurs, the system re-
routes in real time.

Architecture Diagram


<img width="722" height="656" alt="image" src="https://github.com/user-attachments/assets/542d6510-bd1d-48d5-94d6-b52d968e3737" />


## Use Cases

1.First-time traveller: finds the platform, ticket counter and restroom in a large station using the 3D map and step-by-step directions.

2.Train-based guidance: enters a PNR, and the app shows the platform, the walking time and where the coach will stop.

3.Visually impaired passenger: uses voice-guided navigation with audio cues, vibration feedback and screen-reader support.

4.Wheelchair or elderly passenger: gets step-free routes via ramps and lifts, with the nearest accessible restroom and help desk.

5.Last-minute platform change: a push notification arrives with a new route and updated walking time.

6.Kiosk user without a smartphone: searches on the kiosk touchscreen, then scans a QR code to carry the route to a phone or prints it.

7.Emergency or crowd management: shows evacuation routes and avoids congested corridors.

8.Station administrators: update maps, add or close facilities, and view heatmaps of footfall and popular destinations.

9.Multilingual support: the interface and voice work in Hindi, English and regional languages.

## Technology Stack

<img width="857" height="532" alt="image" src="https://github.com/user-attachments/assets/b0c9c577-3e0e-4771-ba0e-f53877b149ee" />


## Dependencies
-> Railway data APIs: NTES/IRCTC for live train status, platform and coach position (needs Ministry/Indian Railways approval and access).

-> Station floor plans and CAD/BIM data: needed to build accurate digital twins.

-> Hardware: BLE beacons, Wi-Fi access points, kiosk touch screens and power/network points at stations.

-> Mobile OS permissions: Bluetooth, location, microphone and notifications.

-> Connectivity: station Wi-Fi or mobile data for live updates (offline cache as fallback).

-> Third-party services: map SDKs, speech and translation services, push notification services (FCM/APNs).

-> Accessibility standards: WCAG 2.1 and Indian accessibility guidelines (GIGW) for the UI.

-> Data privacy compliance: the DPDP Act 2023, with anonymised location data and user consent.

-> Station staff cooperation: to keep maps and facility information updated.
