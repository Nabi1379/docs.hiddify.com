<div dir=rtl markdown=1>
[**![Lang_farsi](https://user-images.githubusercontent.com/125398461/234186932-52f1fa82-52c6-417f-8b37-08fe9250a55f.png) &nbsp;فارسی**](https://github.com/hiddify/hiddify-config/wiki/Cloud-init-%D9%86%D8%B5%D8%A8)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="https://github.com/hiddify/hiddify-config/wiki/All-tutorials-and-videos"><img width="100" src="https://github.com/hiddify/hiddify-config/assets/125398461/8ac5b906-105c-4b98-acf5-0e12e39e33f6" /></a>

</div>

# Cloud-init installation

This section is suitable for hosting that supports cloud config
Copy and paste this code into the appropriate field
```
#cloud-config
package_upgrade: true
packages:
  - apt-transport-https
  - ca-certificates
  - curl
  - wget
  - gnupg-agent
  - software-properties-common
  - git

runcmd:
  - cd /opt
  - bash -c "export CREATE_EASYSETUP_LINK='true';curl i.hiddify.com/release|bash"

final_message: "The system is finally up, after $UPTIME seconds"
output: { all: "| tee -a /root/cloud-init-output.log" }

# you can see the generated link from the website by using https://yourip.sslip.io/hiddify in one hour, after that, it will be disappear.  
```

After installing this script, follow the installation from [here](https://github.com/hiddify/hiddify-config/wiki/Guide-for-Setting-up-the-Domain-and-Finalizing-the-Installation) to complete the installation.
