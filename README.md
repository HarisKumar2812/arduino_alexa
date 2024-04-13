**TWO LED LIGHT GLOW (OUR PROTOTYPE MODEL)**
This code is for a simple Arduino project that responds to clapping sounds. Here's a breakdown of what each part does:

1. **Variable Declaration**: At the beginning, there are declarations for pin assignments. `soundSensorPin` is connected to a sound sensor, `ledPin1` is connected to an LED for a single clap response, and `ledPin2` is connected to another LED for a multiple claps response.

2. **Setup Function**: In the `setup()` function, pins are initialized as either inputs or outputs, and the serial communication is started for debugging purposes.

3. **Loop Function**: The `loop()` function runs continuously once the Arduino is powered up.

4. **Sound Detection**: It checks if the sound sensor pin reads a high signal (meaning a sound is detected). If it detects a sound and it's not already listening for a clap, it starts listening and records the time.

5. **Clap Counting**: While it's listening for a clap, it keeps counting the number of claps within a certain time interval (in this case, 500 milliseconds). It uses a debounce delay to avoid counting multiple claps for a single sound event.

6. **Clap Action Execution**: Once the interval is over, it stops listening for claps and executes an action based on the number of claps detected.

7. **Action Function**: `executeClapAction()` is called to perform the appropriate action based on the number of claps detected. If it's one clap, it turns on `ledPin1` for a brief moment. If it's more than one clap, it blinks `ledPin2` twice.

Overall, this code creates a simple clap-responsive system where different LED responses are triggered depending on the number of claps detected within a certain time frame.

**GESTURE MODEL DETECTION USING ARDUINO**
This code is for controlling appliances using gestures detected by a gesture sensor. Here's a simple breakdown:

1. **Include Libraries**: The code includes the necessary libraries for communicating with the gesture sensor and controlling the appliances.

2. **Pin Definitions**: It defines the pins connected to relays that control the appliances. Each relay pin corresponds to a specific appliance.

3. **Constants for Gestures**: It defines constants for different types of gestures that the sensor can detect, such as right swipe, left swipe, up swipe, and down swipe.

4. **Global Variables**: It declares a variable to store the current detected gesture.

5. **Setup Function**: Initializes serial communication, I2C communication, and the gesture sensor. It also sets the relay pins as OUTPUT.

6. **Loop Function**: Continuously checks for gesture data from the sensor. If a gesture is available, it reads the gesture and calls a function to process it.

7. **Process Gesture Function**: Based on the detected gesture, this function turns on or off the corresponding appliance by calling the appropriate function.

8. **Turn On/Off Appliance Functions**: These functions control the relay connected to the specified appliance pin. They turn the appliance on or off and print a message indicating the action taken.

Overall, this code allows you to control appliances by performing different gestures in front of the sensor. For example, a right swipe gesture might turn on one appliance, while a left swipe gesture might turn it off. Similarly, up and down swipe gestures can control another appliance.

**SOUND DETECTION USING ARDUINO**
We include the necessary TensorFlow Lite headers for working with the model.
The detectClapping() function loads the audio data, extracts features, loads the TensorFlow Lite model, sets up the interpreter, runs inference, and determines if clapping sounds are detected.
The extractFeatures() function performs feature extraction (e.g., spectrogram computation).
In the main() function, we call detectClapping() with the audio file path and print the detection result.
