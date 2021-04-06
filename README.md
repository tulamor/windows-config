# Windows 10 configuration

Permissions & History:  

* SafeSearch: OFF  
* Cloud Search: OFF  
* My devices History: OFF  
Clear my device history  

General -> Change privacy options  
Change browser defaults  
Offline maps -> Map updates -> Automatically update maps -> OFF
***
Taskbar settings (Unpin from taskbar):  

* Microsoft Store  
* Microsoft Edge  
* Mail  
Search -> Hidden

Control Panel -> View by: change from Category to Large icons
System Properties -> Hardware -> Device Installation Settings -> Check "No"
for disabling automatic download manufactures apps

gpedit disabled:  
Configure Automatic Updates -> disabled  
(On 1909 (OS Build 18363.1474):  

* Enter net stop wuauserv (stopped successfully)  
* Enter net stop bits (not started)  
* Enter net stop dosvc (not started)  

***
Uninstall:  

* appwziz.cpl  
* One drive  
* Microsoft Update Health Tools  
* Mozilla Maintenance Service  

***
Adjust power options (powercfg.cpl)-> Create a power plan --> High Performance
***
Disable Unwanted Startup Programs
Task manager --> Startup  
Microsoft Security notification icon --> Disable
***

## ASUS E402S

* Personalizations --> Colors --> Transperancy effects --> OFF  
* Apps & Features -> remove unused apps  
* Windows Features -> Windows Subsystem for Linux -> Unmark checkbox  
* Install ReadyBoost if HDD used  
* Wifi settings -> Metered connection -> Set as metered connection -> ON
* Indexing Options -> Modify -> Change selected locations -> Untick all options (drives)

System -> Advanced power settings -> Choose what the power button does -> Change settings that are currently unavailable ->
Turn on fast startup -> OFF (If ON, In certain cases it's can cause issues (I need to test it))  
Enable Hibernation --> PowerShell --> powercfg /hibernate on  
  
***
Applications:
CrystalDiskInfo --> Use to check the health of HDD's  
***

## Troubleshouting

If Windows Modules Installer service is disabled, then Windows Features window is blank  
***
`winver` <- Show current Windows version
***

Stop Windows to take your bandwidth:
gpedit.msc --> Administrative Templates --> Network --> QoS Packet Scheduler --> Limit Reservable bandwidth --> Enable & Set to 0  
To enable / deploy this policy --> CMD --> `gpupdate`
