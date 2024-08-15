<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arduino Projects Showcase</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            background: linear-gradient(to right, #e0f7fa, #b9fbc0, #ffe0b2, #ffccbc); /* Multi-color gradient */
            background-size: 400% 400%; /* Extend background size for smooth animation */
            color: #333; /* Dark text for readability */
            animation: backgroundAnimation 15s ease infinite; /* Animation for background */
        }

        @keyframes backgroundAnimation {
            0% { background-position: 0% 0%; }
            25% { background-position: 100% 0%; }
            50% { background-position: 100% 100%; }
            75% { background-position: 0% 100%; }
            100% { background-position: 0% 0%; }
        }

        header {
            background-color: #FF4500; /* Darker orange */
            color: white;
            padding: 15px 0;
            text-align: center;
            position: fixed;
            width: 100%;
            top: 0;
            left: 0;
            z-index: 1000; /* Ensure header stays on top */
        }
        header img {
            max-width: 150px; /* Adjust as needed */
            height: auto;
        }
        nav {
            display: flex;
            justify-content: center;
            background: #FF4500; /* Darker orange */
            margin-top: 60px; /* Space for fixed header */
        }
        nav a {
            color: white;
            padding: 14px 20px;
            text-decoration: none;
            text-align: center;
            font-size: 16px;
            transition: background 0.3s; /* Smooth transition */
        }
        nav a:hover {
            background: #FF6347; /* Light red/orange */
        }
        .container {
            max-width: 1000px;
            margin: auto;
            padding: 20px;
            margin-top: 80px; /* Space for fixed header and nav */
        }
        .section {
            margin-bottom: 20px;
            background: #FFFFFF; /* White background for sections */
            color: #333; /* Dark text for contrast */
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease; /* Smooth transition for hover effect */
        }
        .section:hover {
            transform: scale(1.02); /* Slight zoom effect on hover */
        }
        .project-title {
            color: #FF4500; /* Darker orange */
            margin-top: 0;
        }
        .accordion {
            background-color: #FF4500; /* Darker orange */
            color: white;
            cursor: pointer;
            padding: 10px;
            width: 100%;
            border: none;
            text-align: left;
            outline: none;
            font-size: 16px;
            transition: background 0.4s ease; /* Smooth transition */
            margin: 5px 0;
        }
        .active, .accordion:hover {
            background-color: #FF6347; /* Light red/orange */
        }
        .panel {
            padding: 0 18px;
            display: none;
            overflow: hidden;
            background-color: #FFFFFF; /* White background for panels */
        }
        .search-container {
            text-align: center;
            margin-bottom: 20px;
        }
        .search-box {
            padding: 10px;
            font-size: 16px;
            width: 80%;
            max-width: 500px;
        }
        .code-button {
            color: #FF4500; /* Darker orange */
            text-decoration: none;
            border-bottom: 1px dashed #FF4500; /* Dotted underline */
        }
        .code-button:hover {
            color: #FF6347; /* Light red/orange */
            border-bottom: 1px solid #FF6347; /* Solid underline on hover */
        }
        
        img {
            max-width: 25%; /* Scale image to fit its container */
            height: auto;    /* Maintain aspect ratio */
        }
    </style>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            document.querySelectorAll('.accordion').forEach(button => {
                button.addEventListener('click', function() {
                    this.classList.toggle('active');
                    const panel = this.nextElementSibling;
                    panel.style.display = panel.style.display === "block" ? "none" : "block";
                });
            });

            document.getElementById('search-input').addEventListener('input', function() {
                const filter = this.value.toLowerCase();
                document.querySelectorAll('.section').forEach(section => {
                    const title = section.querySelector('.project-title').textContent.toLowerCase();
                    if (title.includes(filter)) {
                        section.style.display = '';
                    } else {
                        section.style.display = 'none';
                    }
                });
            });
        });
    </script>
</head>
<body>
    <header>
        
        <h1>Arduino Projects By Mr_vlegend</h1>
    </header>

    <nav>
        <a href="#smartHome">Smart Home</a>
        <a href="#obstacleAvoidingCar">Obstacle Avoiding Car</a>
        <a href="#lineFollower">Line Follower</a>
        <a href="#autoParkingCar">Auto Parking Car</a>
    </nav>

    <div class="search-container">
        <input type="text" id="search-input" class="search-box" placeholder="Search for projects...">
    </div>

    <div class="container">
        <!-- Project Template: Copy and update as needed -->
        <div id="projectID" class="section">
              <h2 class="project-title">Obstacle Avoiding Car</h2>
    <p>This project demonstrates an obstacle-avoiding car using Arduino and ultrasonic sensors.</p>
    <center>  <img src="https://tse3.mm.bing.net/th?id=OIP.W3P9NOkoZ2SCvHHdEOOa8gHaEK&pid=Api&P=0&h=220" alt="Line Following Robot Diagram"></center>

    <button class="accordion">Components Needed</button>
    <div class="panel">
        <ul>
            <li>Arduino Board (e.g., Arduino Uno)</li>
            <li>Motor Driver Module (e.g., L298N or L293D)</li>
            <li>DC Motors (2 motors)</li>
            <li>Ultrasonic Sensor (e.g., HC-SR04)</li>
            <li>Battery Pack</li>
            <li>Jumper Wires</li>
            <li>Chassis (to mount the components)</li>
        </ul>
    </div>

    <button class="accordion">Connections</button>
    <div class="panel">
        <p>Instructions for connecting the components are detailed below.</p>
        <ul>
            <li>Motor Connections:
                <ul>
                    <li>Connect the DC motors to the Motor Driver Module.</li>
                    <li>Connect the motor driver inputs to the Arduino digital pins.</li>
                </ul>
            </li>
            <li>Ultrasonic Sensor Connections:
                <ul>
                    <li>Connect the VCC of the sensor to the 5V pin on the Arduino.</li>
                    <li>Connect the GND of the sensor to the GND pin on the Arduino.</li>
                    <li>Connect the TRIG pin of the sensor to a digital pin on the Arduino (e.g., pin 6).</li>
                    <li>Connect the ECHO pin of the sensor to a digital pin on the Arduino (e.g., pin 7).</li>
                </ul>
            </li>
            <li>Power Connections:
                <ul>
                    <li>Power the Arduino from a suitable battery pack.</li>
                    <li>Ensure the motor driver and sensors are powered correctly.</li>
                </ul>
            </li>
            <li>Motor Driver Module Pins:
                <ul>
                    <li>Motor A:</li>
                    <li>IN1 to Arduino pin 2</li>
                    <li>IN2 to Arduino pin 3</li>
                    <li>Motor B:</li>
                    <li>IN3 to Arduino pin 4</li>
                    <li>IN4 to Arduino pin 5</li>
                </ul>
            </li>
        </ul>
    </div>
    <button class="accordion">Arduino Code</button>
            <div class="panel">
                <p>The Arduino code for this project. <a href="https://github.com/mrvlegend/Obstacle-Avoiding-Car.git" target="_blank">View Code</a></p>
            </div>

    <button class="accordion">Using the System</button>
    <div class="panel">
        <p>Instructions on how to use the system go here. This section typically includes information on operating the obstacle-avoiding car, such as:</p>
        <ul>
            <li>Powering on the system.</li>
            <li>Placing the car on a flat surface.</li>
            <li>Starting the car and observing its behavior.</li>
            <li>Understanding how the car detects obstacles and changes direction.</li>
            <li>How to troubleshoot common issues.</li>
        </ul>
    </div>

        <!-- Example Project Sections (Duplicate and update as needed) -->
        <div id="smartHome" class="section">
            <h2 class="project-title">Smart Home System with Arduino</h2>
            <p>This project demonstrates a basic smart home system using an Arduino to control light bulbs and a fan via Bluetooth.</p>

            <button class="accordion">Components Needed</button>
            <div class="panel">
                <ul>
                    <li>Arduino board (e.g., Arduino Uno)</li>
                    <li>HC-05 Bluetooth module</li>
                    <li>Relay module</li>
                    <li>One fan</li>
                    <li>Three light bulbs</li>
                    <li>Jumper wires</li>
                    <li>Power supply</li>
                </ul>
            </div>

            <button class="accordion">Connections</button>
            <div class="panel">
                <p>Connect your components as follows:</p>
                <ul>
                    <li>HC-05 Bluetooth Module:
                        <ul>
                            <li>VCC to 5V (Arduino)</li>
                            <li>GND to Ground (Arduino)</li>
                            <li>TXD to RX (Pin 0, Arduino)</li>
                            <li>RXD to TX (Pin 1, Arduino)</li>
                        </ul>
                    </li>
                    <li>Relays:
                        <ul>
                            <li>Relay 1 IN to Pin 2 (Arduino) - Controls Bulb 1</li>
                            <li>Relay 2 IN to Pin 3 (Arduino) - Controls Bulb 2</li>
                            <li>Relay 3 IN to Pin 4 (Arduino) - Controls Bulb 3</li>
                            <li>Relay 4 IN to Pin 5 (Arduino) - Controls Fan</li>
                        </ul>
                    </li>
                    <li>Devices:
                        <ul>
                            <li>Connect each bulb to the COM and NO pins of Relays 1, 2, and 3.</li>
                            <li>Connect the fan to the COM and NO pins of Relay 4.</li>
                        </ul>
                    </li>
                </ul>
            </div>

            <button class="accordion">Arduino Code</button>
            <div class="panel">
                <p>The Arduino code for this project. <a href="https://github.com/mrvlegend/Smart-home.git" class="code-button" target="_blank">View Code</a></p>
            </div>

            <button class="accordion">Using the System</button>
            <div class="panel">
                <p>To control the devices, pair your smartphone with the HC-05 Bluetooth module and use a Bluetooth terminal app to send commands:</p>
                <ul>
                    <li>'1' to turn on Bulb 1</li>
                    <li>'2' to turn off Bulb 1</li>
                    <li>'3' to turn on Bulb 2</li>
                    <li>'4' to turn off Bulb 2</li>
                    <li>'5' to turn on Bulb 3</li>
                    <li>'6' to turn off Bulb 3</li>
                    <li>'7' to turn on the Fan</li>
                    <li>'8' to turn off the Fan</li>
                </ul>
            </div>
        </div>

        <div id="lineFollower" class="section">
            <h2 class="project-title">Line Follower</h2>
            <img src="https://i.ytimg.com/vi/t7k9D1jDEtk/maxresdefault.jpg" alt="Line Following Robot Diagram" style="width: 300px; height: auto;">

            <p>This project demonstrates a basic line-following robot using Arduino.</p>

            <button class="accordion">Components Needed</button>
            <div class="panel">
                <ul>
                    <li>Arduino board (e.g., Arduino Uno)</li>
                    <li>Motor driver module</li>
                    <li>Two DC motors</li>
                    <li>Line sensors</li>
                    <li>Batteries</li>
                </ul>
              <center><img src="https://i.ytimg.com/vi/t7k9D1jDEtk/maxresdefault.jpg" alt="Line Following Robot Diagram"></center>
            </div>

            <button class="accordion">Connections</button>
            <div class="panel">
                <ul>
                
                 <li>Motor Connections:
                        <ul>
                            <li>Connect the DC motors to the Motor Driver Module.</li>
                            <li>Connect the motor driver inputs to the Arduino digital pins.</li>
                        </ul>
                    </li>
                    <li>Sensor Connections:
                        <ul>
                            <li>Connect the line sensors' output to the Arduino analog or digital pins.</li>
                        </ul>
                    </li>
                    <li>Power Connections:
                        <ul>
                            <li>Power the Arduino from a suitable battery pack.</li>
                            <li>Ensure the motor driver is powered correctly.</li>
                        </ul>
                    </li>
                    <li>Motor Driver Module Pins:
                        <ul>
                            <li>Motor A:</li>
                            <li>IN1 to Arduino pin 2</li>
                            <li>IN2 to Arduino pin 3</li>
                            <li>Motor B:</li>
                            <li>IN3 to Arduino pin 4</li>
                            <li>IN4 to Arduino pin 5</li>
                        </ul>
                    </li>
                    <li>Line Sensors:
                        <ul>
                            <li>Left Sensor: Analog pin A0</li>
                            <li>Right Sensor: Analog pin A1</li>
                        </ul>
                    </li>
                </ul>
            </div>
            <button class="accordion">Arduino Code</button>
            <div class="panel">
                <p>The Arduino code for this project. <a href="https://github.com/mrvlegend/line-follwer.git" class="code-button" target="_blank">View Code</a></p>
              
            </div>

            <button class="accordion">Using the System</button>
            <div class="panel">
                <p>Instructions on how to use the system go here.</p>
            </div>
        </div>

      <div id="atomicParkingCar" class="section">
        <h2 class="project-title">Atomic Parking Car</h2>
        <img src="https://example.com/atomic-parking-car-diagram.jpg" alt="Atomic Parking Car Diagram" style="width: 300px; height: auto;">

        <p>This project demonstrates an advanced parking car using Arduino with ultrasonic and proximity sensors.</p>

        <button class="accordion">Components Needed</button>
        <div class="panel">
            <ul>
                <li>Arduino board (e.g., Arduino Uno)</li>
                <li>Motor driver module</li>
                <li>Two DC motors</li>
                <li>Ultrasonic distance sensors</li>
                <li>Proximity sensors</li>
                <li>Battery pack</li>
                <li>Jumper wires</li>
                <li>Chassis (to mount the components)</li>
            </ul>
            <center><img src="https://example.com/atomic-parking-car-diagram.jpg" alt="Atomic Parking Car Diagram" class="small-img"></center>
        </div>

        <button class="accordion">Connections</button>
        <div class="panel">
            <ul>
                <li>Motor Connections:
                    <ul>
                        <li>Connect the DC motors to the Motor Driver Module.</li>
                        <li>Connect the motor driver inputs to the Arduino digital pins.</li>
                    </ul>
                </li>
                <li>Sensor Connections:
                    <ul>
                        <li>Connect the ultrasonic distance sensors to the Arduino pins.</li>
                        <li>Connect the proximity sensors to the Arduino pins.</li>
                    </ul>
                </li>
                <li>Power Connections:
                    <ul>
                        <li>Power the Arduino from a suitable battery pack.</li>
                        <li>Ensure the motor driver and sensors are powered correctly.</li>
                    </ul>
                </li>
                <li>Motor Driver Module Pins:
                    <ul>
                        <li>Motor A:</li>
                        <li>IN1 to Arduino pin 2</li>
                        <li>IN2 to Arduino pin 3</li>
                        <li>Motor B:</li>
                        <li>IN3 to Arduino pin 4</li>
                        <li>IN4 to Arduino pin 5</li>
                    </ul>
                </li>
                <li>Ultrasonic Sensors:
                    <ul>
                        <li>Front Sensor: Trigger pin to Arduino pin 6, Echo pin to Arduino pin 7</li>
                        <li>Rear Sensor: Trigger pin to Arduino pin 8, Echo pin to Arduino pin 9</li>
                    </ul>
                </li>
                <li>Proximity Sensors:
                    <ul>
                        <li>Front Proximity Sensor: Analog pin A0</li>
                        <li>Rear Proximity Sensor: Analog pin A1</li>
                    </ul>
                </li>
            </ul>
        </div>

        <button class="accordion">Arduino Code</button>
        <div class="panel">
            <p>The Arduino code for this project. <a href="https://github.com/yourusername/atomic-parking-car.git" class="code-button" target="_blank">View Code</a></p>
        </div>

        <button class="accordion">Using the System</button>
        <div class="panel">
            <p>Instructions on how to use the system:</p>
            <ul>
                <li>Power on the atomic parking car.</li>
                <li>Place the car in an open space or parking area.</li>
                <li>Observe the car as it uses sensors to detect obstacles and navigate.</li>
                <li>Adjust the sensor thresholds or motor controls if needed.</li>
                <li>Troubleshoot any issues by checking sensor connections and power supply.</li>
            </ul>
        </div>
    </div>
</body>
</html>
