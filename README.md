# Fan Simulator Project Documentation

## Overview

The Fan Simulator is a web-based application that simulates a fan with customizable features such as blade count and rotation speed. This document provides step-by-step instructions on how to set up and run the project on a Node.js server.

## Prerequisites

Before running the Fan Simulator, ensure you have the following installed on your system:

- Node.js (version 14.x or higher recommended)
- npm (Node Package Manager)

## Installation

### 1. Clone the Repository

Clone the Fan Simulator repository from GitHub or download it as a ZIP file and extract it to your preferred directory.

```bash
git clone <repository_url>
cd fan-simulator
```

Replace `<repository_url>` with the URL of your forked repository or the original repository if you have access.

### 2. Install Dependencies

Navigate into the project directory (`fan-simulator`) and install the required npm packages:

```bash
npm install
```

This command installs all the necessary dependencies specified in the `package.json` file.

## Running the Fan Simulator

### 1. Start the Node.js Server

To run the Fan Simulator, start the Node.js server. The server will serve the HTML, CSS, and JavaScript files required for the application.

```bash
npm start
```

By default, the server will start on `http://localhost:3000`. You can access this URL in your web browser.

### 2. Accessing the Application

Open your web browser and go to `http://localhost:3000` to access the Fan Simulator.

## Usage

The Fan Simulator interface consists of the following components:

- **Speed Slider:** Adjust the slider to change the rotation speed of the fan blades.
- **Stop Button:** Click the "Stop" button to pause the fan blades' rotation.

## Customization

You can customize the appearance and behavior of the fan by modifying the HTML, CSS, and JavaScript files in the `public` directory.

### HTML Structure

The HTML (`index.html`) defines the structure of the Fan Simulator:

- The `<div id="fan">` element contains the entire fan simulation.
- The `.fan-container` holds the fan blades and the inner rotating circle.
- `.blades` contains the rotating fan blades.
- `.inner-circle` represents the inner circle where blades are rotating.
- `.fan-circle` represents the outer circle around the blades.
- `.stand` contains the sliders for controlling speed and the stop button.
- `.speed-slider` is the slider input for controlling fan speed.
- `.stop-button` is the button to stop the fan rotation.

### CSS Styling

The CSS (`styles.css`) styles the elements for visual representation and layout:

- Defines the size, position, and animation of the fan blades.
- Positions and styles the inner circle and outer circle.
- Styles the stand and its components (speed slider and stop button).

### JavaScript Functionality

The JavaScript (`app.js`) handles user interaction and server communication:

- Listens for changes on the speed slider (`#speedSlider`) and emits `setSpeed` event to the server.
- Listens for clicks on the stop button (`#stopButton`) and emits `setSpeed` event with a value of `0` to stop the fan.
- Receives `updateSpeed` event from the server to adjust fan blade rotation animation duration based on the speed.

## Contributing

If you'd like to contribute to the Fan Simulator project, follow these steps:

1. Fork the repository on GitHub.
2. Clone your forked repository locally.
3. Create a new branch (`git checkout -b feature/new-feature`).
4. Make your changes and commit them (`git commit -am 'Add new feature'`).
5. Push to the branch (`git push origin feature/new-feature`).
6. Create a new Pull Request on GitHub.

## Troubleshooting

If you encounter any issues while setting up or running the Fan Simulator, consider the following:

- Check the console in your web browser for any error messages.
- Ensure Node.js and npm are properly installed and up to date.
- Verify that all dependencies are installed (`npm install`).
