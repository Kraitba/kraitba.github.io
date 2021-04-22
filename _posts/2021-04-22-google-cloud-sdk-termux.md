---
layout: post
title:  "How to access Google cloud shell via Termux and ssh"
description: "Install google cloud sdk in termux to access google cloudshell via termux or to be precisely ssh"
categories: [ google, cloudshell, termux ]
featured: true
comments: false
---

Let's set up **Google cloud SDK** to gain access to **Google cloud shell** via Termux ssh. Stay tuned for accessing cloud shell just with your Android. 

Among all the cloud-shell available in the market. I love google **cloud shell** most. There are numbers of the reason behind it like it offers better specifications and freely available. 

We need **python 2.7** for sure in Termux because Cloud SDK requires Python; supported versions are Python 3 (preferred, 3.5 to 3.8) and Python 2 (2.7.9 or higher).
Preferred versions 3.5 to 3.8 is not available in Termux. The latest Python3 version available is python 3.9 which is not supported by cloud SDK. So we will go for python 2.7 

Now just execute the following scripts. It will take up to 500 MB of space and Internet data for sure. So make sure you have a stable Internet connection. 
```bash 
pkg install python2 OpenSSH -y 

export CLOUDSDK_PYTHON='python2.7'
echo "export CLOUDSDK_PYTHON='python2.7'" >> ~/.bashrc
echo "export PATH=$PATH:$PREFIX/google-cloud-sdk/bin"
curl -o sdk.sh sdk.cloud.google.com
chmod +x sdk.sh
./sdk.sh --install-dir=$PREFIX

``` 
Now it will ask few questions, just attend it and go forward. Reload your shell to ensure that all commands are in your **PATH**. 

If everything is right for now then you are just a mile away from your goal. Authentic yourself now. 

`cloud auth login` 

The above command will output a link. Copy that link and paste it into your browser and then choose google account/email id and now done. 

Access your Google cloud shell via the following command. 
`cloud alpha cloud-shell ssh` 

Best of luck 👍 


