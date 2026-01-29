## Objective: After participating in one too many incident response activities, PicoSecure has decided to conduct a threat simulation and detection engineering engagement to bolster its malware detection capabilities. You have been assigned to work with an external penetration tester in an iterative purple-team scenario. The tester will be attempting to execute malware samples on a simulated internal user workstation. At the same time, you will need to configure PicoSecure's security tools to detect and prevent the malware from executing. Following the Pyramid of Pain's ascending priority of indicators, your objective is to increase the simulated adversaries' cost of operations and chase them away for good. Each level of the pyramid allows you to detect and prevent various indicators of attack.

# Task 1: Successfully detecting sample1.exe
  * We can given a sample file from our helpful pen-tester, that we will then run through a malware checker. Through this we see that we are given hases, and we will run one of those into checker.

  ![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/9a61c10bf8f72e3ff700d3ede30e31d13105680b/Screenshots/SummitTHMss1.png)

  * This gives us out first flag once we check our inbox.

# Task 2: Successfully detecting sample2.exe
  * We are given sample2.exe from our pen-tester, lets run it through the scan again.
![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/9a61c10bf8f72e3ff700d3ede30e31d13105680b/Screenshots/SummitTHMss2New.png)
  * More hasing outputs are shown, as well as detected malware. We are not able to run hashes again this time, since they are not very reliable because one simple change will change the whole hash.
  * However, we see a suspicous URL attempting a GET method. Lets block this through our firewall manager.
  * We have successfully blocked this ip within our firewall. Egress means nothing will escape, meaning anything from ANY source IP will not be able to reach this destination IP.
![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/9a61c10bf8f72e3ff700d3ede30e31d13105680b/Screenshots/SummitTHMss3.png)
  * This helps us obtain our next flag.

# Task 3: Successfully detecting sample3.exe
  * Now we are unable to detect the hash or block their IP. They are able to obtain a new public IP and keep going! Lets find a new way to stop an attack. We see some new DNS requests. Lets head to our DNS filter.
![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/9a61c10bf8f72e3ff700d3ede30e31d13105680b/Screenshots/SummitTHMss4.png)
  * After blocking the potentially malicious malware, we are able to obtain our next flag and next .exe file.
![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/9a61c10bf8f72e3ff700d3ede30e31d13105680b/Screenshots/SummitTHMss5.png)

# Task 4: Successfully detecting sample4.exe
  * The attacker now knows we are blocking their hashes and IPs, so they are now trying to change up their ways. Lets stop them again.
![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/9a61c10bf8f72e3ff700d3ede30e31d13105680b/Screenshots/SummitTHMss6.png)
  * We see some suspicious registry activity, showing us some modifictaions done to the sample4.exe file. Lets create a new rule to deny this.
![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/9a61c10bf8f72e3ff700d3ede30e31d13105680b/Screenshots/SummitTHMss7.png)
  * The new rule blocks this modification. We see that we are able to block the change, by adding the registry key and its attacking vector. This gives us our next flag.

# Task 5: Successfully detecting sample5.exe
  * The attacker seems to be very frustrated now. They have sent us an outgoing network connections sheet of logs. What can they be telling us now. Lets take a look.
  * We see the attacker isnt so sneaky. We can detect a pattern. Certain logs are being sent to our specific IP, in increments of 30 minutes. The logs are also that same amount of bytes.
  * Lets create a rule to stop this, as we know the source ip is sendthing these same size packets to us and only us.
    ![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/9a61c10bf8f72e3ff700d3ede30e31d13105680b/Screenshots/SummitTHMss8.png)

    ![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/9a61c10bf8f72e3ff700d3ede30e31d13105680b/Screenshots/SummitTHMss10.png)






