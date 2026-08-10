# IT Troubleshooting Lab

## 📑 Table of Contents

- [Overview](#-overview)
- [Scenarios](#-scenarios)
  - [1. User Account Locked Out](#1--user-account-locked-out)
  - [2. Password Reset Request](#2--password-reset-request)
  - [3. No Internet Connection](#3--no-internet-connection)
  - [4. Printer Not Working](#4--printer-not-working)
  - [5. Computer Running Slow](#5--computer-running-slow)
  - [6. Unable to Connect to Wi-Fi](#6--unable-to-connect-to-wi-fi)
  - [7. Outlook Not Receiving Emails](#7--outlook-not-receiving-emails)
  - [8. Blue Screen of Death (BSOD)](#8--blue-screen-of-death-bsod)
  - [9. Computer Won't Turn On](#9--computer-wont-turn-on)
  - [10. User Cannot Access a Shared Drive](#10--user-cannot-access-a-shared-drive)

---

## 🌐 Overview

This repository contains common IT support and helpdesk troubleshooting scenarios that technicians frequently encounter in enterprise environments. Each scenario includes the problem, troubleshooting process, resolution steps, and  screenshots.

The objective is to demonstrate structured troubleshooting, proper documentation, and familiarity with tools commonly used in IT support roles such as Active Directory, Windows networking utilities, Event Viewer, Services, and Microsoft Outlook.

---

# 🧩 Scenarios

---

## 1. 🔒 User Account Locked Out

### Problem
A user reports they cannot sign in and receive an "Account is locked out" message.

### Troubleshooting Steps

1. Verify the user's identity according to company procedures.
2. Open **Active Directory Users and Computers (ADUC)**.
3. Locate the user's account.
4. Open **Properties** and review the **Account** tab.
5. Unlock the account if it is currently locked.
6. Confirm the account is enabled and not expired.
7. Ask the user to attempt sign-in again.
8. If the account becomes locked repeatedly:
   - Review **Event Viewer** logs.
   - Investigate failed authentication attempts.
   - Check for saved credentials on other devices or mapped drives.

### Resolution
The account was unlocked and the user successfully authenticated.



---

## 2. 🔑 Password Reset Request

### Problem
A user has forgotten their password and cannot access their account.

### Troubleshooting Steps

1. Verify the user's identity.
2. Open **ADUC**.
3. Locate the user account.
4. Right-click the account and select **Reset Password**.
5. Assign a temporary password.
6. Select **User must change password at next logon**.
7. Inform the user of the temporary password using an approved communication method.
8. Verify the user can successfully log in and create a new password.

### Resolution
The password was reset and the user regained access.


---

## 3. 🌐 No Internet Connection

### Problem
A user reports they cannot access websites or online resources.

### Troubleshooting Steps

1. Determine whether the issue affects one device or multiple devices.
2. Open **Command Prompt** and run:

```cmd
ipconfig
```

3. Verify the computer has a valid IP address.
4. Test network connectivity:

```cmd
ping 8.8.8.8
```

5. Test DNS resolution:

```cmd
ping google.com
```

6. If an IP address is missing, renew DHCP:

```cmd
ipconfig /release
ipconfig /renew
```

7. Disable and re-enable the network adapter.
8. Restart the computer if necessary.
9. Escalate to networking staff if the issue appears infrastructure-related.

### Resolution
Network connectivity was restored after renewing the DHCP lease.


---

## 4. 🖨️ Printer Not Working

### Problem
A user cannot print or print jobs remain stuck in the queue.

### Troubleshooting Steps

1. Confirm the printer is powered on and connected.
2. Verify the printer is online.
3. Open the print queue and clear any stuck jobs.
4. Restart the **Print Spooler** service.
5. Print a test page.
6. Verify the correct printer is selected.
7. Remove and re-add the printer if necessary.
8. Reinstall or update printer drivers.

### Resolution
The print queue was cleared and the spooler service restarted.


---

## 5. 💻 Computer Running Slow

### Problem
A user reports poor system performance and slow response times.

### Troubleshooting Steps

1. Open **Task Manager**.
2. Review CPU, RAM, Disk, and Network utilization.
3. Identify resource-intensive processes.
4. Close unnecessary applications.
5. Check available storage space.
6. Run a malware scan using Microsoft Defender.
7. Review startup applications.
8. Perform Disk Cleanup if required.
9. Restart the system and reassess performance.

### Resolution
High CPU usage caused by unnecessary applications was reduced.



---

## 6. 📶 Unable to Connect to Wi-Fi

### Problem
A user cannot connect to a wireless network.

### Troubleshooting Steps

1. Confirm Wi-Fi is enabled.
2. Verify the wireless network is visible.
3. Forget and reconnect to the wireless network.
4. Check wireless adapter status:

```cmd
netsh wlan show interfaces
```

5. Flush DNS cache:

```cmd
ipconfig /flushdns
```

6. Update wireless adapter drivers.
7. Run the Windows Network Troubleshooter.
8. Restart the wireless adapter if necessary.

### Resolution
The Wi-Fi profile was recreated and connectivity was restored.


---

## 7. 📧 Outlook Not Receiving Emails

### Problem
A user reports Outlook is not receiving new email messages.

### Troubleshooting Steps

1. Verify internet connectivity.
2. Check Junk Email and other folders.
3. Confirm Outlook is not in **Work Offline** mode.
4. Verify mailbox storage limits have not been reached.
5. Review account synchronization status.
6. Remove and re-add the mail profile if required.
7. Check Microsoft 365 service health for outages.
8. Escalate to the messaging team if necessary.

### Resolution
Outlook synchronization was restored after reconnecting the account.



---

## 8. 🖥️ Blue Screen of Death (BSOD)

### Problem
A computer unexpectedly crashes and displays a Blue Screen of Death.

### Troubleshooting Steps

1. Record the stop code displayed on the screen.
2. Review Event Viewer system logs.
3. Open Reliability Monitor and review recent failures.
4. Run System File Checker:

```cmd
sfc /scannow
```

5. Check disk integrity:

```cmd
chkdsk /f
```

6. Review recently installed drivers or software.
7. Update system drivers.
8. Test memory using Windows Memory Diagnostic.

### Resolution
Corrupted system files were repaired and stability improved.


---

## 9. 🔌 Computer Won't Turn On

### Problem
A user presses the power button and the computer does not start.

### Troubleshooting Steps

1. Verify power connections.
2. Test a known working power outlet.
3. Check power indicators and status lights.
4. Confirm the power supply switch is enabled (desktop systems).
5. Perform a power drain:
   - Disconnect power.
   - Hold the power button for 30 seconds.
   - Reconnect power and test.
6. For laptops, test with a known working charger.
7. Escalate for hardware diagnostics if the system remains unresponsive.

### Resolution
The system powered on after reseating the power connection.


---

## 10. 🗂️ User Cannot Access a Shared Drive

### Problem
A user receives an "Access Denied" error when attempting to access a network share.

### Troubleshooting Steps

1. Verify the user is logged in with the correct domain account.
2. Confirm the drive is mapped.
3. Map the drive manually if necessary:

```text
\\SERVER\SharedDrive
```

4. Verify network connectivity to the file server.
5. Review group membership in Active Directory.
6. Confirm the user belongs to the correct security group.
7. Have the user sign out and sign back in after permission changes.
8. Review share permissions and NTFS permissions if access still fails.

### Resolution
The user was added to the appropriate security group and access was restored.


---
