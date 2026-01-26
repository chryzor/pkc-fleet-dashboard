# PKC Commercial Vehicle Dashboard & Fleet Control Center

A conceptual in-vehicle display prototype and dispatcher ecosystem built as a Single Page Application (SPA) using React, Vite, and Leaflet.js. 

This project serves as a comprehensive prototype for a commercial truck dashboard, focusing on navigation, safety-critical alerts, vehicle telemetry, and driver settings. It also includes a secondary dispatcher view to demonstrate real-time fleet tracking and routing.

## In-Vehicle Display Prototype (Driver-Centered)

The core of this project is the driver-centric interface, designed with human-centered principles to minimize driver distraction while surfacing critical data.

*   **Dark Mode UI**: Specifically engineered with high-contrast, dark-mode elements to ensure readability across varying lighting conditions (especially night driving) without blinding the driver.
*   **Safety-Critical Alerts**: Prominent, distraction-free visual cues for Hours of Service (HOS) violations, low fuel, and home-time scheduling limits.
*   **Vehicle Status & Telemetry**: Live readout of speed, fuel levels, miles driven, and drive-time remaining.
*   **Driver Settings & HOS Management**: Simplified clock-in/out functionality, duty status toggles (Driving, On Duty, Break, Sleeper), and maintenance reporting flows designed for quick interactions.

## Dispatcher & Routing Engine

To simulate a real-world environment, the prototype is backed by a dispatcher control center:
*   **Interactive Navigation & Fleet Map**: Built with Leaflet.js and OpenStreetMap (dark CartoDB tiles). Tracks active trucks in real time.
*   **Route Planning**: Calculates the shortest or fastest driving route between any two US cities using the Open Source Routing Machine (OSRM). Displays distances in miles, drive times, and fuel cost estimates.
*   **Data Simulation Engine**: Tracks multiple drivers moving across the US on interstate routes, updating their location, speed, and fuel at regular intervals.

## Annotated Design Specifications

See the `docs/` directory for project planning, walkthroughs, and interaction flows. 
*   **`design_specifications.md`**: Documents component behavior, iconography choices, layout rationale, and screen transitions for the in-vehicle display.

## Technology Stack
*   Frontend: React 18, Vite
*   Styling: Vanilla CSS (Custom UI scaling and typography)
*   Maps and Geocoding: Leaflet, react-leaflet, Nominatim (OpenStreetMap)
*   Routing: OSRM (Open Source Routing Machine) API

## Setup and Installation

1. Clone the repository.
2. Navigate to the project directory: `cd pkc-fleet-dashboard`
3. Install dependencies: `npm install`
4. Start the development server: `npm run dev`
5. Open `http://localhost:5173` in your browser.
