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
6. Download the config file and move it to the sysmon directory
   ```
   https://raw.githubusercontent.com/effaaykhan/Sysmon-Installation/refs/heads/main/sysmonconfig-export.xml -OutFile "sysmonconfig-export.xml"
   ```
7. Install Sysmon: Run the following command in the directory where sysmon is installed
   ```
   .\Sysmon.exe -i .\sysmonconfig-export.xml
   ```
8. Update Configuration
   ```
   .\Sysmon.exe -c .\sysmonconfig-export.xml
   ```

9. Install Event Manifest
    ```
    sysmon64 -m
    ```
10. Print Schema
    ```
    .\Sysmon.exe -s
    ```
11. Add the following configuration to the agent's ossec.conf:
    ```
    <localfile>
      <location>Microsoft-Windows-Sysmon/Operational</location>
      <log_format>eventchannel</log_format>
    </localfile>
    ```
 12. Restart the Agent
     
## NOTE: Run every Command with admin rights.

