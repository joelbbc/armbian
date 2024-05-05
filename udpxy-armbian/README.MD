How to Install 
1. Install udpxy 
    -  wget https://raw.githubusercontent.com/joelbbc/armbian/main/udpxy-armbian/udpxy-1.0.25-1.tar.gz
    -  tar -xzvf udpxy-1.0.25-1.gz
    -  cd udpxy-1.0.25-1
    -  make 
    -  su -c 'make install'  
2.  Create udpxy config
    -  wget https://raw.githubusercontent.com/joelbbc/armbian/main/udpxy-armbian/udpxy.conf
    -  sudo cp udpxy.conf /etc/udpxy.conf
3.  Create Udpxy as service
    -  wget https://raw.githubusercontent.com/joelbbc/armbian/main/udpxy-armbian/udpxy.service
    -  sudo cp udpxy.service /etc/systemd/system/udpxy.service
4.  Last Step
    - sudo systemctl daemon-reload
    - sudo systemctl enable udpxy.service
    - sudo systemctl start udpxy.service
    - sudo systemctl status udpxy.service

HOW TO RUN
-    Default PORT 4022 
-    Check status : http://udpxy_server_ip:4022/status
-    if your multicast address 239.0.0.1:8000
-    run in VLC Player 
-    http://<udpxy_server_ip>:4022/239.0.0.1:8000

