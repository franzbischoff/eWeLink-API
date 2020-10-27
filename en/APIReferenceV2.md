<!--
 * @Author: Carl
 * @Date: 2020-07-24 15:19:34
 * @LastEditors: Carl
 * @LastEditTime: 2020-10-20 18:19:57
-->

# API Reference

## Manage Account

| Name   | API       | Description       |
|------|-----------|-----------|
| Create Account | post /v2/user/register | You can create an account with your email. |
| Login   | post /v2/user/login     | You should log in before you access device data or other resources |
| SMS Login | post /v2/user/sms-login     |  Only users registered by phone number in mainland China has access to this. |
| Send Verification Code | post /v2/user/verification-code| Send verification code to email or phone number.|
| Reset Password | post /v2/user/reset-pwd    |  When you forgot your password, reset password with this endpoint. |
| Change Password | post /v2/user/change-pwd     | After you have logged in, you can use this endpoint to change your password with your old password. |
| Get User Info | get /v2/user/profile     | Get the information of current account such as the nickname. |
| Update User Info | post /v2/user/profile     | Update the information of current account such as the nickname. |
| Refresh Access Token | post /v2/user/refresh     | “access token” expires in 30 days (for security reasons) by default. When this happens, no need to log in again to get 'access token', just use 'refresh token' endpoint to refresh the 'access token'.   |
| Logout | delete /v2/user/logout     | Log out |
| Delete Account | post /v2/user/close-account     | Delete account |

## HomePage

| Name   | API       | Description       |
|------|-----------|-----------|
| HomePage | post /v2/homepage     |  Allows you to check messages, scenes, things, homes, and user info.  |

## Manage Device

| Name   | API       | Description       |
|------|-----------|-----------|
| Get Thing List | get /v2/device/thing     |  Get all the devices and groups under the specified home ID. |
| Get Specified Things list |  post /v2/device/thing    | Get specified groups or devices |
| Get Device or Group Status | get /v2/device/thing/status     |  Get the status of one device or a group, such as the on/off of a switch. |
| Update the Status of a Device or Group | post /v2/device/thing/status     | Set the status of a device or a group, such as the on/off of a switch. |
| Update the Status of Multiple Devices or Groups | post /v2/device/thing/batch-status | Update the statuses of multiple devices or groups such as the on/off of switches. |
| Add WiFi Device | post /v2/device/add     | Add a WiFi device  |
| Add GSM Device | post /v2/device/add-gsm    | Add a device with IoT sim card. Scan its QR code to get its device ID.  |
| Update Name/Room of Device |post /v2/device/update-info    | Update the name or room of the device | 
| Delete Device | delete /v2/device    | Delete your own devices or devices shared with you. |
| Change Device Tags | post /v2/device/tags    | Used to change the names of different channels of a multi-channel device or to create some special functions based on your own needs. |
| Get Group List | get /v2/device/group    | Get the list of groups in current home |
| Add a Group | post /v2/device/group    | Create a group of devices of the same type, to control all the grouped devices with one tap.  |
| Change Group Name | put /v2/device/group    | Currently, this endpoint only allows you to change the name of the group.  |
| Delete Group | delete /v2/device/group    | Delete a group |
| Change Group Status | post /v2/device/group/status    | Update the status of a group, such as turning on/off a group.  |
| Add Devices to a Group | post /v2/device/group/add    | The device to add should have the same UIID as existing devices in the group.  |
| Delete Devices from Group | post /v2/device/group/delete    | Delete devices from the group  |
| Update the Device List of a Group | post /v2/device/group/update    | Add multiple devices to a group |
| Share devices | post /v2/device/share    | Share devices to another user (in the same region server) |
| Change Sharing Permission | post /v2/device/share/permit    | Edit the timer permissions for the shared user |
| Cancel Sharing | delete /v2/device/share    | Cancel sharing devices with a user |
| Get Device Operating History | get /v2/device/history    | Get Device Operating History |
| Clean Device Operating History | delete /v2/device/history    |  Clean device operating history |
| Get Device OTA Update Information | post /v2/device/ota/query | Check if there is any new firmware available for the device |

## Homes and Rooms

| Name   | API       | Description       |
|------|-----------|-----------|
| Get Homes and Rooms | get /v2/family    |  Get the list of all the homes and rooms in the current account. Each account should have one home at least  |
| Add a Home | post /v2/family   | Add a new home |
| Add a Room | post /v2/family/room   | Add a new room |
| Change Home Name | put /v2/family    | Currently, it only allows you to change the name of a home  |
| Change Room Name| put /v2/family/room   | Currently, it only allows you to change the name of a room |
| Sort Rooms | post /v2/family/room/index  | To change the order, you must designate the order of each room in the home. |
| Delete Home | delete /v2/family | Delete specified home |
| Delete Room | delete /v2/family/room    | Delete specified room |
| Sort Things in a Home | post /v2/family/thing/sort    | To change the order, you must specify the order of each device or group in the home.  |
| Move Things | post /v2/family/room/thing    | Move groups and devices to a specified room  |
| Switch Current Home | post /v2/family/current    | Switch to the default home |

## Message

| Name   | API       | Description       |
|------|-----------|-----------|
| Get the List of Messages | get /v2/message/read |  Get share notifications, device notification, and other messages. |

## Manage and Control Device

| Name   | API       | Description       |
|------|-----------|-----------|
| Dispatch Service | Fixed interface  | Get the distributed address of the persistent connection for the app |

# Summary

With all the endpoints above, you can develop an application with complete functions from register and login, add device, to manage device and control device. You may find an  API to call for each step of your workflow. 