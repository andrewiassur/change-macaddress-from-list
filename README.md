# change-macaddress-from-list
this is a simple bash script to randomize you mac address based off of a list of mac address this is for education purposes only, i'm not responsible for anything that you do with this.  

#!/bin/bash  
rand=$(shuf -n 1 ~/scripts/macaddress.txt) #location of your mac address list mine is located in ~/scripts/macaddress.txt 
echo $rand sudo ifconfig wlan0 down #change to your interface card  
sudo macchanger -m $rand wlan0 #change to your interface card  
sudo ifconfig wlan0 up #change to your interface card  
sudo service network-manager restart   

macaddress.txt should be formatted like this: 
00:11:22:33:44:55 
aa:22:33:44:55:aa
