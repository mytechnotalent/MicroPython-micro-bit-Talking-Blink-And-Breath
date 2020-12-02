![image](https://github.com/mytechnotalent/MicroPython-micro-bit_Talking_Blink_And_Breath/blob/main/MicroPython-micro-bit%20Talking%20Blink%20And%20Breath.png?raw=true)

# MicroPython-micro-bit
# Talking Blink And Breath
The micro:bit Talking LED Blink And Breath is a micro:bit Electronic Educational Engagement Tool designed to help students create a talking blink and breath application.

## Schematic
![image](https://github.com/mytechnotalent/MicroPython-micro-bit_Talking_Blink_And_Breath/blob/main/schematic.png?raw=true)<br>
*** NOTE *** USE PIN1 INSTEAD OF PIN0 (GREEN WIRE)

## Parts
[micro:bit](https://microbit.org/buy/?location=US&version=microbitV2)<br>
[Ks0360 Keyestudio Sensor Shield V2 for BBC micro:bit](https://www.amazon.com/gp/product/B08H7VSLZH/)<br>
* Keyestudio Micro bit Sensor V2 Shield * 1
* keyestudio 3W LED Module * 1
* Dupont jumper wire * 3

## STEP 1: Navigate To The FREE micro:bit Python Web Editor
[micro:bit Python Web Editor](https://python.microbit.org/v/beta)<br><br>
![image](https://github.com/mytechnotalent/MicroPython-micro-bit_Talking_Blink_And_Breath/blob/main/STEP%201.png?raw=true)

## STEP 2: Plug micro:bit V2 Into Computer
***PLUG IN USB CABLE TO COMPUTER AND DEVICE**

## STEP 3: Click CONNECT
![image](https://github.com/mytechnotalent/MicroPython-micro-bit_Talking_Blink_And_Breath/blob/main/STEP%203.png?raw=true)

## STEP 4: Click "BBC micro:bit CMSIS-DAP" & CONNECT
![image](https://github.com/mytechnotalent/MicroPython-micro-bit_Talking_Blink_And_Breath/blob/main/STEP%204.png?raw=true)

## STEP 5: Highlight Sample Code - Select All
![image](https://github.com/mytechnotalent/MicroPython-micro-bit_Talking_Blink_And_Breath/blob/main/STEP%205.png?raw=true)

## STEP 6: Click Backspace On Keyboard To Delete Sample Code
![image](https://github.com/mytechnotalent/MicroPython-micro-bit_Talking_Blink_And_Breath/blob/main/STEP%206.png?raw=true)

## STEP 7: Copy Study Buddy Python Code Template Into Python Web Editor

# CODE
```python
from time import sleep
from time import sleep_ms

from microbit import pin1, display, Image
from speech import say

while True:
    # We set the blink_count to 0 and increment
    # 2 times to allow this while loop to execute
    # twice
    blink_count = 0
    while blink_count < 2:
        pin1.write_digital(1)
        display.show(Image.SURPRISED)
        say('The light is on!')
        display.show(Image.HAPPY)
        sleep(5)
        pin1.write_digital(0)
        display.show(Image.SURPRISED)
        say('The light is off!')
        display.show(Image.HAPPY)
        sleep(5)
        blink_count += 1
        
    # We set the breath_count to 0 and increment
    # 2 times to allow this while loop to execute
    # twice
    breath_count = 0    
    val = 0
    while breath_count < 2:
        display.show(Image.SURPRISED)
        say('The light is getting brighter!')
        display.show(Image.HAPPY)
        # The val is initialized to 0 on line 6 and 
        # increments by one through each iteration
        # through the while loop until it hits 
        # 1022 and as it does it increments the value
        # of pin1 which makes the light brigter
        # every 5 ms
        while val <= 1022:
            val += 1
            pin1.write_analog(val)
            sleep_ms(5)
       
        display.show(Image.SURPRISED)
        say('The light is getting darker!')
        display.show(Image.HAPPY)    
        # After we complete the first loop the val
        # is now equal to 1023 so during this
        # while loop it gets smaller until it hits 
        # 0 and as it decrements the value
        # of pin1 which makes the light darker
        # every 5 ms
        while val > 0:
            val -= 1
            pin1.write_analog(val)
            sleep_ms(5)
            
        breath_count += 1
 ```       
 
## STEP 8: Rename Script Name To talking_blink_and_breath

## STEP 9: Click Save
![image](https://github.com/mytechnotalent/MicroPython-micro-bit_Talking_Blink_And_Breath/blob/main/STEP%209.png?raw=true)

## STEP 10: Click Download Python Script
![image](https://github.com/mytechnotalent/MicroPython-micro-bit_Talking_Blink_And_Breath/blob/main/STEP%2010.png?raw=true)

## STEP 11: Click Flash
![image](https://github.com/mytechnotalent/MicroPython-micro-bit_Talking_Blink_And_Breath/blob/main/STEP%2011.png?raw=true)

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0)
