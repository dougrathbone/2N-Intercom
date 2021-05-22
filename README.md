# 2N-Intercom

Python script for executing commands against the Https API of the 2N Verso line of POE Intercoms.

2N API Guide: https://wiki.2n.cz/hip/hapi/latest/en

### Commands supported
- system_info
- system_status
- system_restart
- firmware_upload
- firmware_apply
- config_get
- config_upload
- factory_reset
- switch_caps
- switch_status
- switch_control
- io_caps
- io_status
- io_control
- phone_status
- call_status
- call_dial
- call_answer
- call_hangup
- camera_caps
- camera_snapshot
- display_caps
- display_upload_image
- display_delete_image
- log_caps
- log_subscribe
- log_unsubscribe
- log_pull
- audio_test
- email_send
- pcap
- pcap_restart
- pcap_stop

### Usage Example 

```
import core

username = 'test'
password = 'testpassword'
ip = '192.168.0.2'
ssl = True
auth_type = 2  # 0=None, 1=Basic, 2=Digest

ip_cam = IPCam(ip, ssl=ssl, auth_type=2, user=username, password=password)

# For the complete list of commands and their description please take a look
# to commands.py within the CommandService class.

print(ip_cam.commands.system_info())  # basic device information
print(ip_cam.commands.system_status())  # current intercom status
print(ip_cam.commands.call_dial('**618'))  # dial number
```
