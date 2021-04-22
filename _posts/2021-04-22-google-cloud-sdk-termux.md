---
layout: post
title:  "How to access Google cloudshell via termux and ssh"
description: "Install google cloud sdk in termux to access google cloudshell via termux or to be precisely ssh"
categories: [ google, cloudshell, termux ]
featured: true
comments: false
---

Let's setup **Google cloud sdk** in order to gain access to **Google cloudshell** via termux ssh. 

Among all the cloudshells available in market. I personally love google **cloudshell** most. There's numbers of reason behind it like it offers better specifications and freely available. 

We need **python 2.7** for sure in termux because Cloud SDK requires Python; supported versions are Python 3 (preferred, 3.5 to 3.8) and Python 2 (2.7.9 or higher).
Preferred versions 3.5 to 3.8 is not available in termux. The latest python3 version available is python 3.9 which is not supported by cloud sdk. So we will go for python 2.7 

Now just execute following scripts. It will take upto 500 MB space and Internet data for sure. So make sure you have stable Internet connection. 

```bash 
pkg install python2 openssh -y 

export CLOUDSDK_PYTHON='python2.7'
echo "export CLOUDSDK_PYTHON='python2.7'" >> ~/.bashrc
echo "export PATH=$PATH:$PREFIX/google-cloud-sdk/bin"
curl -o sdk.sh sdk.cloud.google.com
chmod +x sdk.sh
./sdk.sh --install-dir=$PREFIX

``` 
Now it will ask few questions, just attend it and go forward. Reload your shell to ensure that all commands is in your **PATH**. 

If everything is right for now then you are just a mile away from your goal. Authentic yourself now. 

`gcloud auth login` 

Above command will output a link. Copy that link and paste it into your browser and then choose google account/email id and now  done. 

Access your Google cloudshell via following command. 
`gcloud alpha cloud-shell ssh` 

Best of luck 👍 

