import javafx.application.Application;
import javafx.geometry.Insets;
import javafx.scene.Scene;
import javafx.scene.control.Label;
import javafx.scene.control.ListView;
import javafx.scene.control.TextArea;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.layout.VBox;
import javafx.stage.Stage;

public class SmartHomeGuideApp extends Application {

    @Override
    public void start(Stage primaryStage) {
        // Set up the main layout
        VBox root = new VBox();
        root.setPadding(new Insets(20));
        root.setSpacing(20);
        
        // Header
        Label header = new Label("Smart Home Setup Guide with Arduino and Bluetooth");
        header.setStyle("-fx-font-size: 24px; -fx-font-weight: bold; -fx-text-fill: #fff; -fx-background-color: #0044cc; -fx-padding: 10px;");
        header.setPrefWidth(600);
        
        // Introduction Section
        Label introTitle = new Label("Introduction");
        introTitle.setStyle("-fx-font-size: 20px; -fx-font-weight: bold; -fx-text-fill: #0044cc;");
        Label introText = new Label("Learn how to create a smart home system controlled via Bluetooth using Arduino.");
        
        // Components Section
        Label componentsTitle = new Label("Components Needed");
        componentsTitle.setStyle("-fx-font-size: 20px; -fx-font-weight: bold; -fx-text-fill: #0044cc;");
        ListView<String> componentsList = new ListView<>();
        componentsList.getItems().addAll(
                "Arduino Board",
                "HC-05 Bluetooth Module",
                "Relay Module",
                "Power Supply",
                "Various Home Appliances (Lights, Fans, etc.)"
        );
        
        // Wiring Diagram Section
        Label wiringTitle = new Label("Wiring Diagram");
        wiringTitle.setStyle("-fx-font-size: 20px; -fx-font-weight: bold; -fx-text-fill: #0044cc;");
        Image wiringImage = new Image("wiring-diagram.png"); // Make sure to have this image in your resources folder
        ImageView wiringImageView = new ImageView(wiringImage);
        
        // Arduino Code Section
        Label arduinoTitle = new Label("Arduino Code");
        arduinoTitle.setStyle("-fx-font-size: 20px; -fx-font-weight: bold; -fx-text-fill: #0044cc;");
        TextArea arduinoCode = new TextArea();
        arduinoCode.setText(
                "#include <SoftwareSerial.h>\n\n" +
                "// Set up Bluetooth serial communication\n" +
                "SoftwareSerial bluetooth(10, 11); // RX, TX\n\n" +
                "// Pin definitions\n" +
                "const int ledPin1 = 2; // LED 1\n" +
                "const int ledPin2 = 3; // LED 2\n" +
                "const int ledPin3 = 4; // LED 3\n" +
                "const int fanPin = 5;  // Relay control for the fan\n\n" +
                "void setup() {\n" +
                "    // Start serial communication with the computer and Bluetooth module\n" +
                "    Serial.begin(9600);\n" +
                "    bluetooth.begin(9600);\n\n" +
                "    // Set LED and relay pins as outputs\n" +
                "    pinMode(ledPin1, OUTPUT);\n" +
                "    pinMode(ledPin2, OUTPUT);\n" +
                "    pinMode(ledPin3, OUTPUT);\n" +
                "    pinMode(fanPin, OUTPUT);\n\n" +
                "    // Initialize LEDs and fan to OFF\n" +
                "    digitalWrite(ledPin1, LOW);\n" +
                "    digitalWrite(ledPin2, LOW);\n" +
                "    digitalWrite(ledPin3, LOW);\n" +
                "    digitalWrite(fanPin, LOW); // Fan OFF\n" +
                "}\n\n" +
                "void loop() {\n" +
                "    // Check if data is available from Bluetooth\n" +
                "    if (bluetooth.available()) {\n" +
                "        char command = bluetooth.read();\n\n" +
                "        // Process the received command\n" +
                "        switch (command) {\n" +
                "            case '1': // Turn on LED 1\n" +
                "                digitalWrite(ledPin1, HIGH);\n" +
                "                bluetooth.print(\"LED 1 ON\\n\");\n" +
                "                break;\n" +
                "            case '2': // Turn off LED 1\n" +
                "                digitalWrite(ledPin1, LOW);\n" +
                "                bluetooth.print(\"LED 1 OFF\\n\");\n" +
                "                break;\n" +
                "            case '3': // Turn on LED 2\n" +
                "                digitalWrite(ledPin2, HIGH);\n" +
                "                bluetooth.print(\"LED 2 ON\\n\");\n" +
                "                break;\n" +
                "            case '4': // Turn off LED 2\n" +
                "                digitalWrite(ledPin2, LOW);\n" +
                "                bluetooth.print(\"LED 2 OFF\\n\");\n" +
                "                break;\n" +
                "            case '5': // Turn on LED 3\n" +
                "                digitalWrite(ledPin3, HIGH);\n" +
                "                bluetooth.print(\"LED 3 ON\\n\");\n" +
                "                break;\n" +
                "            case '6': // Turn off LED 3\n" +
                "                digitalWrite(ledPin3, LOW);\n" +
                "                bluetooth.print(\"LED 3 OFF\\n\");\n" +
                "                break;\n" +
                "            case 'F': // Turn on Fan\n" +
                "                digitalWrite(fanPin, HIGH);\n" +
                "                bluetooth.print(\"Fan ON\\n\");\n" +
                "                break;\n" +
                "            case 'f': // Turn off Fan\n" +
                "                digitalWrite(fanPin, LOW);\n" +
                "                bluetooth.print(\"Fan OFF\\n\");\n" +
                "                break;\n" +
                "            default:\n" +
                "                bluetooth.print(\"Unknown command\\n\");\n" +
                "                break;\n" +
                "        }\n" +
                "    }\n" +
                "}"
        );
        arduinoCode.setWrapText(true);
        
        // Testing and Troubleshooting Sections
        Label testingTitle = new Label("Testing the System");
        testingTitle.setStyle("-fx-font-size: 20px; -fx-font-weight: bold; -fx-text-fill: #0044cc;");
        Label testingText = new Label("Pair your Bluetooth device with your smartphone and use a Bluetooth terminal app to send commands to the Arduino.");

        Label troubleshootingTitle = new Label("Troubleshooting");
        troubleshootingTitle.setStyle("-fx-font-size: 20px; -fx-font-weight: bold; -fx-text-fill: #0044cc;");
        ListView<String> troubleshootingList = new ListView<>();
        troubleshootingList.getItems().addAll(
                "Ensure correct wiring connections.",
                "Check the baud rate settings on both the Arduino and Bluetooth module.",
                "Verify the Bluetooth pairing process."
        );

        // Footer
        Label footer = new Label("By mr_vlegend\n© 2024 Smart Home Projects");
        footer.setStyle("-fx-background-color: #0044cc; -fx-text-fill: #fff; -fx-padding: 10px; -fx-text-align: center; -fx-font-size: 14px;");
        
        // Add all elements to the root layout
        root.getChildren().addAll(header, introTitle, introText, componentsTitle, componentsList, wiringTitle, wiringImageView, arduinoTitle, arduinoCode, testingTitle, testingText, troubleshootingTitle, troubleshootingList, footer);
        
        // Set up the scene and stage
        Scene scene = new Scene(root, 800, 600);
        primaryStage.setTitle("Smart Home Setup Guide");
        primaryStage.setScene(scene);
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
