# Open-stack
## Open Stack

## Installing OpenStack in ubuntu using MicroStack 
```
sudo snap install microstack --beta
```



### 1. Initialize MicroStack
```
sudo microstack init --auto --control
```
This command:

* Sets up OpenStack services.
* Configures networking.
* Enables an internal bridge for virtual machines.



### 3. Access OpenStack Dashboard
Once initialized, you can access the Horizon web dashboard:

-> Find the dashboard IP address:
```
ip a | grep inet
```


-> for password 
```
sudo snap get microstack config.credentials.keystone-password
```

-Go to web browser and search this above IP address:
```
http://<your-ip>:80
```




![image](https://github.com/user-attachments/assets/72e076d9-69c4-4d83-8290-575464be4995)



## Log in using the default credentials:

* Username: admin
* password: (from above)

![image](https://github.com/user-attachments/assets/78b44b0c-b0d2-4355-bff2-4f652559aa51)


## Start Keystone Service
```
sudo apt install keystone -y
sudo systemctl list-units --type=service | grep keystone

```



## Check if services are working correctly
To check if the services we have deployed are working correctly we will first install openstack Client use this command
```
sudo apt install -y python3-openstackclient
```
Verify installation using
```
openstack --version
```



Check Services using
```
openstack compute service list
```

![image](https://github.com/user-attachments/assets/b599e58f-5f1d-407c-bd7e-805b595cfaee)





