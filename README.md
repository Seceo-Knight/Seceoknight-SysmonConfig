# Sysmon Installation

### This Repository contains the installation guide of Sysmon on windows
1. 
```
https://download.sysinternals.com/files/Sysmon.zip
```

2. UNZIP the Folder
3. Create a Sysmon folder in C:\
4. Move the extracted sysmon files to the folder
5. Using Powershell as a administrator Navigate to the Sysmon folder
```
cd C:\Sysmon
```
6. Download the config file and move it to the sysmon directory.
```
https://raw.githubusercontent.com/Seceo-Knight/Seceoknight-SysmonConfig/refs/heads/main/sysmonconfig-export.xml -OutFile "config.xml"
```
7. Installing Sysmon with downloade config follow :
```
Sysmon64.exe -accepteula -i config.xml
```
### Configure Seceoknight agent to monitor Sysmon events under ossec.conf
```
<localfile>
<location>Microsoft-Windows-Sysmon/Operational</location>
<log_format>eventchannel</log_format>
</localfile>
```
### Add the following block to the configuration file to enable Windows Defender log collection:
```
<localfile>
  <location>Microsoft-Windows-Windows Defender/Operational</location>
  <log_format>eventchannel</log_format>
</localfile>
```
Restart the Agent

