# Annotated Design Specifications: In-Vehicle Display Prototype

This document outlines the human-centered design principles, layout rationale, and component behaviors for the PKC In-Vehicle Display prototype.

## 1. Design Principles & Human-Centered Approach

*   **Minimized Distraction**: The primary interface limits dense text and relies heavily on color-coded, high-contrast visual cues so drivers can absorb information with a quick glance.
*   **Varying Lighting Conditions**: The application strictly enforces a custom Dark Mode palette (deep slate backgrounds, muted borders). This prevents blinding glare during night driving while maintaining sufficient contrast for daylight visibility.
*   **Prioritization of Safety**: The most safety-critical data (Hours of Service limits, Speed, and low fuel warnings) are given the highest visual hierarchy, bypassing standard navigation to sit persistently on the screen when thresholds are met.

## 2. Layout Rationale & Information Architecture

The interface is divided into distinct zones to establish a consistent interaction flow and mental model for the driver.

### 2.1 The Persistent Top Bar
*   **Purpose**: Provides immediate situational awareness regardless of the current screen state.
*   **Components**: 
    *   **Clock/Date**: Large typography for easy reading.
    *   **Fleet Status Badges**: High-level overview of active, break, off-duty, and delivering states.

### 2.2 The Main Viewport (Map & Routing)
*   **Purpose**: Hands-free navigation and location context.
*   **Rationale**: The map occupies the majority of the screen space. Using dark CartoDB tiles ensures the map does not become a distracting light source. Active routes are highlighted in a vibrant, high-visibility blue (`#3B8BFF`).

### 2.3 The Driver Action Panel (Right Side)
*   **Purpose**: Interactive zone for settings, status changes, and deep-dive telemetry.
*   **Rationale**: Positioned on the right for easier reach by the driver's right hand (assuming LHD vehicles) when interacting with a center console touch screen.

## 3. Screen States & Interaction Flows

### 3.1 Driver Dashboard (Settings & Status)
*   **Behavior**: When a driver interacts with the portal, they are presented with large, touch-target optimized buttons for duty status (Driving, On Break, Sleeper).
*   **Transitions**: Selecting a status immediately updates the driver's visual badge color and recalculates HOS timers.

### 3.2 Alerts State
*   **Behavior**: When an alert threshold is crossed (e.g., fuel drops below 25%), an alert card is generated.
*   **Iconography**: 
    *   ⚠️ **Warning (Yellow/Amber)**: Approaching limits (e.g., HOS at 10 hours).
    *   🚨 **Critical (Red)**: Hard limit reached or immediate action required (e.g., Low fuel).
*   **Rationale**: Standardized unicode iconography is used over custom SVGs to ensure immediate, universal recognition without cognitive load.

### 3.3 Vehicle Status & Telemetry
*   **Behavior**: Live readout of speed and fuel.
*   **Color Coding**:
    *   **Green (`#00C896`)**: Safe / Nominal levels.
    *   **Amber (`#FFD600`)**: Warning / Monitor closely.
    *   **Red (`#FF2D3A`)**: Critical / Action required.

## 4. Component Library & Typography

*   **Typeface Choices**:
    *   `Oswald` & `Barlow Condensed`: Used for headers and metric readouts. The condensed nature allows for larger font sizes (better readability) without cluttering horizontal space.
    *   `Share Tech Mono`: Used for raw data, IDs, and timestamps to mimic industrial, high-legibility dashboard instruments.
*   **Buttons**: All actionable items use a minimum height of `48px` to comply with touch-target sizing standards for vehicle environments, reducing mis-taps on bumpy roads.
