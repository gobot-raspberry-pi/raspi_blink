# raspi_blink
Blinking LED sample project using GOBOT

## Diagram
![image](https://github.com/gobot-raspberry-pi/raspi_blink/blob/master/images/raspi_blink.png)
## How to run
1. Run this command
   ```
   GOARM=7 GOARCH=arm GOOS=linux go build -o=raspi_blink *.go
   ```
2. Then `SCP` the output to your Pi.
    ```
    scp raspi_blink pi@192.168.0.XXX:/home/pi
    ```
    - Change the the IP with your PI IP address.
3. `SSH` into your Pi and execute this command
   ```
   ./raspi_blink
   ```
    - You should see something like this
    ```
      2018/12/29 12:05:29 Initializing connections...
      2018/12/29 12:05:29 Initializing connection RaspberryPi-2CDD29D5 ...
      2018/12/29 12:05:29 Initializing devices...
      2018/12/29 12:05:29 Initializing device LED-5427BD0 ...
      2018/12/29 12:05:29 Robot blinkBot initialized.
      2018/12/29 12:05:29 Starting Robot blinkBot ...
      2018/12/29 12:05:29 Starting connections...
      2018/12/29 12:05:29 Starting connection RaspberryPi-2CDD29D5...
      2018/12/29 12:05:29 Starting devices...
      2018/12/29 12:05:29 Starting device LED-5427BD0 on pin 7...
      2018/12/29 12:05:29 Starting work...
    ```
    and your LED should be blinking every second.
    
    - `Ctrl + c` to stop
 
## Notes

1. LED, short wire is connected to the resitor. On the diagram, the short wire is the straight one, the one with a curve is the long wire. The placement of the resistor, connected to the short wire is OK but as rule of thumb it should be connected to the longer wire (anode) to protect the LED and board.
2. Connect only the GRD part, the one to be controlled is the power in this case it's PIN 7.
3. You could test if your connectivity is correct by connecting the power source to PIN 1 (3.3V).
4. See this [link](http://led.linear1.org/led.wiz) to compute for the resistor to use.
