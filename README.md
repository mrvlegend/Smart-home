<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arduino Projects Showcase</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            background-color: #f0f0f0;
            color: #333;
        }
        header {
            background-color: #007bff;
            color: white;
            padding: 15px 0;
            text-align: center;
        }
        nav {
            display: flex;
            justify-content: center;
            background: #0056b3;
        }
        nav a {
            color: white;
            padding: 14px 20px;
            text-decoration: none;
            text-align: center;
            font-size: 16px;
        }
        nav a:hover {
            background: #003d7a;
        }
        .container {
            max-width: 1000px;
            margin: auto;
            padding: 20px;
        }
        .section {
            margin-bottom: 20px;
            background: white;
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        .project-title {
            color: #007bff;
            margin-top: 0;
        }
        .accordion {
            background-color: #007bff;
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
            background-color: #0056b3;
        }
        .panel {
            padding: 0 18px;
            display: none;
            overflow: hidden;
            background-color: white;
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
        <h1>Arduino Projects Showcase</h1>
    </header>

    <nav>
        <!-- Navigation links can be updated dynamically if needed -->
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

        <!-- Add more project sections here by copying and updating the template -->
 <div id="LineFollower" class="section">
            <h2 class="project-title">line Follower</h2>
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
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <style>
        body{
            margin: 0;
            width: 100%; 
            height: 100vh;
            background-color: Orange;
            display: flex;
            justify-content: center;
            align-items: center;
        } 

        .box{
            width: fit-content;
            padding: 20px 50px;
            background-color: black;
            border: 1px solid white;
        }
        h2{
            font-family: sans-serif;
            font-size: 4rem;
            color:  #FFA500;
            -webkit-text-stroke: 2px #383d52;
            text-transform: uppercase;
            width: 100%;
            height: 100%;
            position: relative;
        }


        h2::before{
            content: attr(data-text);
            width: 100%;
            height: 100%;
            position: absolute;
            color: #FFA500;
            text-shadow: 0px 0px 12px #26f0fe;
            -webkit-text-stroke: 0px #383d52;
            border-right: 1px solid #0ef;
            overflow: hidden;
            animation: animate 6s linear infinite;
        }
        
        @keyframes animate {
            0%,10%,100%{
                width: 0;
            }
            70%,90%{
                width: 100%;
            }


        }
    </style>
</head>
<body>

    <div class="box">
        <h2 data-text="By.mr_vlegend">By.mr_vlegend</h2>
    </div>
    </div>
</body>
</html>

