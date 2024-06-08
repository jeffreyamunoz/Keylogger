# Keylogger using pnput 

## Project Goal:
Create a keylogger that generates a textfile documenting every keystroke we use across the entire computer. **This is for educational purposes only, do not use this code for malicious intent.**


# Preperation 

### Preperation
Begin with proper software, and ensuring all dependencies are installed. Today, we'll be using Visual Studio Code. Ensure you have the Python Visual Code extenstion installed.

-Install pynut in the terminal by using "pip install pynput", as shown below.


![Screenshot 2024-06-07 183122](https://github.com/jeffreyamunoz/Keylogger/assets/172007477/22ad62fd-26fc-4e36-8ebb-75bbe81fd8fb)


# Code
We'll start our code off by typing 
`from pynput import keyboard`

![Screenshot 2024-06-07 184011112](https://github.com/jeffreyamunoz/Keylogger/assets/172007477/2c3f44ce-c556-4c58-ad07-2624a810f88f)

- The 'pynput' library is used to control and monitor input devices. From this, we import the 'keyboard' module to track keyboard events.



We'll then begin to define our parameters. `if __name__ == "__main__":` 
                                            `listener = keyboard.Listener(on_press=keyPressed)`

                                            
![Screenshot 2024-06-07 185608](https://github.com/jeffreyamunoz/Keylogger/assets/172007477/4c60a5dd-aa43-4a1c-a319-aaae70242f95)

                                            
This is going to check what we've defined, in  this instance, it's going to look for keyboard instances, specifically when a key is pressed.




Now that our listener object is defined, we'll start laying down the tracks for what listener will execute for us by adding 
                                                                                        `listener.start()
                                                                                        input()`

![Screenshot 2024-06-07 191618](https://github.com/jeffreyamunoz/Keylogger/assets/172007477/f1d615a9-fca2-4989-b1ba-6acc5a34a222)


We'll define our function by adding def `keyPressed(key):`. The "key" paramter in keyPressed will be tied to our "on_press" in line 7. When then add `print(str(key))` so that the key strokes can be printed to ourselves.

![Screenshot 2024-06-07 192058](https://github.com/jeffreyamunoz/Keylogger/assets/172007477/73962d61-7a88-4e28-be3f-273b5037d5f5)


We'll then create a path to where a text file will be created and sourced from our keystrokes. `with open("keyfile.txt", 'a') as logKey:` is going to create a text document titled "keyfile" that's going to store everything being pressed while our code is running. It's important the the 'a' is included as this will only allow appending to our file, this will ensure that if existing data is in our keyfile document,  that it will only add to our document, ensuring that we are not deleting information.


![Screenshot 2024-06-07 192948](https://github.com/jeffreyamunoz/Keylogger/assets/172007477/92dbcd57-37e0-4ffa-97cd-64028ccb587c)

And lastly, we'll add room  for error in our code with `try:
                            char = key.char
                            logKey.write(char)
                          except:
                            print("error getting char")
`

This is going to handle any exceptions with keys that the code is unable to capture or translate, and rather than  crash the code, it will simply display an error and be able to continue.

Our code is now complete, this is our final product!


![Screenshot 2024-06-07 193724](https://github.com/jeffreyamunoz/Keylogger/assets/172007477/83f57961-db99-4717-ac98-97285877ddd7)



# Running our script

Run the script, and then go into a web browser and start typing. You'll notice that any key you press is now being tracked into the termainl. You'll notice our "Error getting char" message in the terminal as well - this is our error message firing off whenever the space bar is pressed. You'll also notice that our keyfile.txt file has been created, and is capturing and storing any keystokes we make. It's not deleting any new keystrokes, but rather mining every keystroke we type.

![Screenshot 2024-06-07 195052](https://github.com/jeffreyamunoz/Keylogger/assets/172007477/5358aeec-0ed1-47a5-bc0f-4355df907cb6)



# Summary

A keylogger is malicious malware intended for threat actors to spy on and track any keyboard activity in pursuit of passwords, credit card numbers, email addresses, and any personal information. As cybersecurity analysts, it's important that we know how these malicious codes work so that we know what to look for. By learning the behaviors of threat actors, we can strengthen our investigation skills. As a reminder, this is for educational purposes only, do not use this information for malicious intent.
