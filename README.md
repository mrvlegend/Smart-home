
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arduino Projects Showcase</title>
    <link rel="stylesheet" href="./style.css">
   
        header {
            background-color: #FF4500; /* Darker orange */
            color: white;
            padding: 15px 0;
            text-align: center;
        }
        header img {
            max-width: 150px; /* Adjust as needed */
            height: auto;
        }
        nav {
            display: flex;
            justify-content: center;
            background: #FF4500; /* Darker orange */
        }
        nav a {
            color: white;
            padding: 14px 20px;
            text-decoration: none;
            text-align: center;
            font-size: 16px;
        }
        nav a:hover {
            background: #FF6347; /* Light red/orange */
        }
        .container {
            max-width: 1000px;
            margin: auto;
            padding: 20px;
        }
        .section {
            margin-bottom: 20px;
            background: #FFFFFF; /* White background for sections */
            color: #333; /* Dark text for contrast */
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
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
            transition: 0.4s;
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
        <img src="https://drive.google.com/file/d/1-AJPvetDc-ogNFqpYRpuWFEYsCtDC2kp/view?usp=sharing" alt="Your Logo">
        <h1>Arduino Projects By Mr_vlegend</h1>
    </header>
, n
    <nav>
        <a href="#smartHome">Smart Home</a>
        <a href="#obstacleAvoidingCar">Obstacle Avoiding Car</a>
        <a href="#lineFollower">Line Follower</a>
        <a href="#autoParkingCar">Auto Parking Car</a>
    </nav>
nt3b  j
    <div class="search-container">
        <input type="text" id="search-input" class="search-box" placeholder="Search for projects...">
    </div>

    <div class="container">
        <!-- Project Template: Copy and update as needed -->
        <div id="projectID" class="section">
            <h2 class="project-title">Project Title</h2>
            <p>Project description goes here.</p>

            <button class="accordion">Components Needed</button>
            <div class="panel">
                <ul>
                    <!-- List of components -->
                </ul>
            </div>

            <button class="accordion">Connections</button>
            <div class="panel">
                <p>Connections instructions go here.</p>
                <ul>
                    <!-- List of connections -->
                </ul>
            </div>

            <button class="accordion">Arduino Code</button>
            <div class="panel">
                <p>The Arduino code for this project. <a href="#" class="code-button" target="_blank">View Code</a></p>
            </div>

            <button class="accordion">Using the System</button>
            <div class="panel">
                <p>Instructions on how to use the system go here.</p>
            </div>
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
            </div>

            <button class="accordion">Connections</button>
            <div class="panel">
                <p>Connections instructions go here.</p>
            </div>

            <button class="accordion">Arduino Code</button>
            <div class="panel">
                <p>The Arduino code for this project. <a href="#" class="code-button" target="_blank">View Code</a></p>
            </div>

            <button class="accordion">Using the System</button>
            <div class="panel">
                <p>Instructions on how to use the system go here.</p>
            </div>
        </div>

        <!-- Add more project sections here by copying and updating the template -->
    </div>
</body>
</html>
