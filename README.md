ROUTER SECURITY CONFIGURATION.

Set up 2 routers- R1, R2. 
- configure basic security using the enable password [ for privileged mode]
-Connect R1 and R2 by their GB Ethernet 0/0 interface using a cable.
![1](https://github.com/kelubia/CISCO-ROUTER-PASSWORD-SECURITY-CONFIGURATION/assets/98921903/1ab79dce-7b93-4d31-aac2-5f8e1804c841)
![2](https://github.com/kelubia/CISCO-ROUTER-PASSWORD-SECURITY-CONFIGURATION/assets/98921903/53952630-68de-41f4-970e-59eea0a22eff)
Set hostnames according to the R1 and R2 network diagram
open the CLI mode and change the hostname of the router to Privileged exec mode and then to General config mode 
=> enable
The enable secret is a password to protect access to privileged EXEC and configuration modes. After being entered, this password becomes encrypted in the configuration.

=> Configure terminal (conf t)
change the hostname to R1
=> Hostname R1
repeat for router 2
![3](https://github.com/kelubia/CISCO-ROUTER-PASSWORD-SECURITY-CONFIGURATION/assets/98921903/befd3179-ce98-4036-b386-c513bd5592b6)
![4](https://github.com/kelubia/CISCO-ROUTER-PASSWORD-SECURITY-CONFIGURATION/assets/98921903/76881dce-a69b-47e1-9bee-8d8a23ba240e)
Set the enable password on each router; this is used to enter the privileged exec mode. Without a set password, anyone can enter the privileged exec mode, which should only be accessed by the Admin
![5](https://github.com/kelubia/CISCO-ROUTER-PASSWORD-SECURITY-CONFIGURATION/assets/98921903/ab30855b-ef76-4112-af63-43f2d7d853b6)
once the password has been set, the user will always be asked for the admin password in order to access the privilege exec; failure to enter the right password will result in a bad secrets error...
![6](https://github.com/kelubia/CISCO-ROUTER-PASSWORD-SECURITY-CONFIGURATION/assets/98921903/55fe3ac1-cd8d-472b-9b88-29e470b04fab)
![7](https://github.com/kelubia/CISCO-ROUTER-PASSWORD-SECURITY-CONFIGURATION/assets/98921903/743008a9-87a8-4ed0-b7e4-0c7c1d4b740b)
configure the enable secret for a more secured and encrypted password; the enable password is stored in clear text on the configuration file
=> do sh run
to confirm that the password is not encrypted
![8](https://github.com/kelubia/CISCO-ROUTER-PASSWORD-SECURITY-CONFIGURATION/assets/98921903/8c3cd07e-0b4d-48c5-ac90-b020846c914c)
Once enable secrets is configured, return to the exec mode (normal user), and attempt to enter the privileged exec mode... won't work

with =>sh run config command
We can see that our private mode password is now encrypted.
![9](https://github.com/kelubia/CISCO-ROUTER-PASSWORD-SECURITY-CONFIGURATION/assets/98921903/ab17c1ad-a903-4f92-882d-aab5bf9796e9)
![10](https://github.com/kelubia/CISCO-ROUTER-PASSWORD-SECURITY-CONFIGURATION/assets/98921903/473a8c22-1f2d-44ea-a8a3-52803f3bec5c)
We haven't saved anything yet, and there is no set router startup-config to set it...
use the => copy run config startup
or=>startup config
or=> write
![11](https://github.com/kelubia/CISCO-ROUTER-PASSWORD-SECURITY-CONFIGURATION/assets/98921903/f18056c3-f18f-431f-8efb-40bb06d901b3)
Now, reload the router.
and in the privileged enabled mode, use the show startup command to see if configuration settings have been saved
![12](https://github.com/kelubia/CISCO-ROUTER-PASSWORD-SECURITY-CONFIGURATION/assets/98921903/ae4ec520-3abd-437b-a80c-eecbbc67ab9b)
![13](https://github.com/kelubia/CISCO-ROUTER-PASSWORD-SECURITY-CONFIGURATION/assets/98921903/731f082d-65b7-48c0-ab70-709fb4f57e3f)

