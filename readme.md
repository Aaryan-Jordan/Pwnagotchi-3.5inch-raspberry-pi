pwnagotchi 3.5 inch screen installation mod


1. flash the given image onto a sd card and add the provided config.toml to boot directory
 1.1 if u dont want your network to be pawned do add your ssid in config.toml or your firewall may blacklist you

2. connect the sd card to rpi0 and the rpi0 to pc via the second port(data port)

3. the device should show up as a RNDIS device in your netwoks 
    3.1 if not go to device manager the usb ports then update the ports driver with the .inf file provided
    this should connect the rpi0 as RNDIS device

4. go to properties of your current working network go to sharing then add the name of the rpi0

5. the open rpi0's properties goo to ipv4 and add static ip 10.0.0.1 and dns 255.255.255.0 (.0 at last is specific for ssh)

6.after saving open terminal 

7. ssh pi@10.0.0.2 (password = raspberry)

8. to enable internet ~ nano /etc/resolv.conf 

9. edit the file add dns 8.8.8.8

10. sudo apt update && upgrade

11. to configure the screen (put in the screen to gpio pins)

12. sudo rm -rf LCD-show

13. git clone https://github.com/waveshare/LCD-show.git

14. cd LCD-show/

15. chmod +x LCD35-show

16. sudo nano /usr/local/lib/python3.7/dist-packages/pwnagotchi/ui/hw/spotpear24inch.py

Remove all the content and replace with the provided screen.mod contents

17. save

18. ./LCD35-show lite

19. the screen will boot dont disconect or you may have to repeat the whole process again 

20. and there you go hurray u have the cute face on your 3.5 inch screen