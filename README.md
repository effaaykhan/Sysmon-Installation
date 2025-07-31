# Sysmon-Installation
This Repository contains the installation guide of Sysmon on windows 

1. Download the Sysmon Installer
   ```
   https://download.sysinternals.com/files/Sysmon.zip
   ```
2. Unzip the folder
3. Create Sysmon folder in ```C:\```
4. Move the extracted sysmon files to the folder
5. Navigate to the Sysmon folder
   ```
   cd C:\Sysmon
   ```
6. Download the config file
   ```
   Invoke-WebRequest -Uri "https://raw.githubusercontent.com/SwiftOnSecurity/sysmon-config/refs/heads/master/sysmonconfig-export.xml" -OutFile "sysmonconfig-export.xml"
   ```
7. Install Sysmon
   ```
   sysmon.exe -accepteula -i sysmonconfig-export.xml
   ```
8. Update Configuration
   ```
   sysmon.exe -c sysmonconfig-export.xml
   ```

9. Add the following configuration in the agent's ossec.conf
    ```
   <localfile>
      <location>Microsoft-Windows-Sysmon/Operational</location>
      <log_format>eventchannel</log_format>
   </localfile>
   ```
 10. Restart the Agent
     
## NOTE: Run every Command with admin rights.

