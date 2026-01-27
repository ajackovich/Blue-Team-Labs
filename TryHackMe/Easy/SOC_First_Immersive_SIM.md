## Handling beginner SIEM logs

## First Alert
-> Here we see a user attempted to access an external URL that has been blacklisted by the company or other intelligence

![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/eb0689ad7b14a4ad4150152e8615820af24ba9cd/Screenshots/SOCFirstImmersiveRealss1.png)

-> Lets proceed by first using a built-in tool in our Analyst VM to see where/what this URL takes us to/does 

![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/eb0689ad7b14a4ad4150152e8615820af24ba9cd/Screenshots/SOCFirstImmersivess2.png)

-> We see that this is deemed malicious from our analysis tool, therefore we will concluded this users access attempt to go to this site was blocked with good intent

![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/eb0689ad7b14a4ad4150152e8615820af24ba9cd/Screenshots/SOCFirstImmersivess3.png)

-> We will now conduct our report writing 

![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/eb0689ad7b14a4ad4150152e8615820af24ba9cd/Screenshots/SOCFirstImmersivess4.png)

## Second Alert
-> A user has receieved a link to finalize their onboarding process

![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/eb0689ad7b14a4ad4150152e8615820af24ba9cd/Screenshots/SOCFristImmersiveSRss1.png)

-> The first thing we can do is check if the link comes up as malicous or is reported as non-maliware

![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/eb0689ad7b14a4ad4150152e8615820af24ba9cd/Screenshots/SOCFristImmersiveSRss2.png)

-> After confirming link is not malicious, we also see that the domain is not malicious. We can conduct a more thorough investigation through Splunk. While investigation, we can see that the sender email the IT Team earlier regarding the onboarding process, therefore 
we can conclude that this sender is real and part of our network

![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/eb0689ad7b14a4ad4150152e8615820af24ba9cd/Screenshots/SOCFristImmersiveSRss3.png)

-> We can now write our case report

![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/eb0689ad7b14a4ad4150152e8615820af24ba9cd/Screenshots/SOCFristImmersiveSRss4.png)

# Thrid Alert
-> We receive a fishing alert from a suspicious Amazon sender, so lets take a look

![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/c9283eb7097b1908ce659acb3a22b828ac224596/Screenshots/SOCFirstImmersiveTRss1.png)

-> Lets continue doing what we have been doing, and that is putting the suspicious link into the URL checker

![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/c9283eb7097b1908ce659acb3a22b828ac224596/Screenshots/SOCFirstImmersiveTRss2.png)

-> The link shows up as malicious, we dont have much luck with trusting any "bit.ly/...." link. Lets check the domain and splunk for any suspicious results as well. Seeing that the domain is clear and there is no suspicious splunk details, we can still
mark this as a true positive. The malicious link is far too dangerou to trust from a clean domain, as the danger lies within that link. That is why I believe we will mark this as true positive.

![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/c9283eb7097b1908ce659acb3a22b828ac224596/Screenshots/SOCFirstImmersiveTRss3.png)

# Fourth Alert
-> We have another phishing attempt, and almost instantly I can see that this one is malicious. I can immedialty see that both the sender and link provided are written as "m1crosoft", with a '1' instead of an 'i'. This immediately raises my suspicion, 
but lets us conduct more investigation.

![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/406430242578508eca670038bdd14f4c0b0bb68d/Screenshots/SOCFirstImmersiveFoRss1.png)

-> Both the link provided, as well as the domain are reported as malicious. 

![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/406430242578508eca670038bdd14f4c0b0bb68d/Screenshots/SOCFirstImmersiveFoRss2.png)

-> We will take a quicck look at the Splunk reports to see if any other users have received contact from this domain.

![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/406430242578508eca670038bdd14f4c0b0bb68d/Screenshots/SOCFirstImmersiveFoRss3.png)

![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/406430242578508eca670038bdd14f4c0b0bb68d/Screenshots/SOCFirstImmersiveFoRss4.png)

-> The desination ip detected by our firewall lists the destination ip as malicious, therefore we will not allow this to pass through. We can note this in our report that we could be connected to a bad external server.

![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/406430242578508eca670038bdd14f4c0b0bb68d/Screenshots/SOCFirstImmersiveFoRss5.png)

# Completion

![image alt](https://github.com/ajackovich/Blue-Team-Labs/blob/406430242578508eca670038bdd14f4c0b0bb68d/Screenshots/SOC_Immersion_Done.png)









