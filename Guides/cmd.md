To open cmd:
Click on the windows key and r at the same you should see something like this
<div align="center">
<img width="409" height="207" alt="image" src="https://github.com/user-attachments/assets/bb47b557-8d7f-44de-8031-f7edce224484" />
</div>
Then write there `CMD` and enter
<div align="center">
<img width="979" height="515" alt="image" src="https://github.com/user-attachments/assets/28f65585-e3cb-4d3f-8bd1-38a84da8f7a0" />
</div>
write `ipconfig` and look for the ip

---

## Network Address Verification (macOS) 🍎

On macOS, the active IP address can be identified using one of the following methods:

### System Settings
The local IP address can be viewed through the operating system settings by navigating to:
**System Settings → Network → Active Network Interface (Wi-Fi or Ethernet)**.  
The assigned IP address is displayed under the connection details.

### Terminal Commands
Alternatively, the IP address can be obtained using the command line:

- For Wi-Fi connections:
ipconfig getifaddr en0

- For Ethernet connections:
ipconfig getifaddr en1

- To display all network interfaces:
ifconfig
