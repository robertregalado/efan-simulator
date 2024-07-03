# Fan Simulator Documentation

## Table of Contents

1. **Overview**
2. **HTML Structure**
3. **CSS Styles**
4. **JavaScript Functionality**
5. **Socket.IO Integration**
6. **Usage**
7. **Customization**

---

### 1. Overview

Welcome to the documentation for the Fan Simulator web application. This document provides an overview of the HTML structure, CSS styling, and JavaScript functionality used to create a dynamic fan simulation.

### 2. HTML Structure

The HTML structure defines the layout and components of the fan simulator interface:

- **`<!DOCTYPE html>`:** Specifies the HTML5 document type.
- **`<html>`:** Root element with language attribute set to `en`.
- **`<head>`:** Contains metadata such as character set, viewport settings, and page title.
- **`<body>`:** Main content area containing the fan simulator components.

### 3. CSS Styles

CSS styles are used to design and position the elements within the fan simulator:

- **`body`:** Centers content vertically and horizontally with a light gray background.
- **`#fan`:** Main container for the fan simulator, centered on the page.
- **`.fan-container`:** Positions the fan blades and inner circle within the fan structure.
- **`.blades` and `.blade`:** Defines the rotating blades using CSS animations.
- **`.fan-circle`:** Adds a circular border around the fan blades.
- **`.stand` and `.base`:** Styling for the fan's stand and base.
- **`.speed-slider` and `.stop-button`:** Customizes the slider and stop button for controlling fan speed.

### 4. JavaScript Functionality

JavaScript adds interactivity to the fan simulator:

- **Event Listeners:**
  - **`speedSlider.addEventListener('input', function() { ... })`:** Listens for changes in the speed slider input and sends the new speed value to the server via Socket.IO.
  - **`stopButton.addEventListener('click', function() { ... })`:** Stops the fan rotation when the stop button is clicked by emitting a speed value of `0` to the server.

- **Socket.IO Integration:**
  - **`const socket = io();`:** Initializes Socket.IO for real-time communication with the server.
  - **`socket.emit('setSpeed', speed);`:** Sends the current speed value to the server when the slider is adjusted or the stop button is clicked.
  - **`socket.on('updateSpeed', (speed) => { ... });`:** Receives updated speed values from the server and adjusts the fan blade animation duration accordingly.

### 5. Usage

To use the Fan Simulator:

- Open the `index.html` file in a web browser.
- Adjust the speed slider to change the fan speed.
- Click the stop button to pause the fan rotation.

### 6. Customization

Customize the Fan Simulator by:

- Modifying CSS styles (`<style>` section) to change colors, sizes, or layout.
- Editing JavaScript (`<script>` section) to add new features or adjust existing functionality.

