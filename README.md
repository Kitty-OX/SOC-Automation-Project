# SOC-Automation-Project

### "In this project, I will learn how to set up a Security Operations Center (SOC) automation project (home lab) with <a href="https://www.youtube.com/@MyDFIR">@MyDFIR</a>."

## Skills Learned
- Explore how automation enhances incident response
- Accelerates threat detection
- Streamlines SOC workflows.
  
## Tools Used
- Wazuh
- Shuffle
- The-Hive
- draw.io
## Questions
#### <span style="color:#ec4b4b">What is Wazuh?</span>
>**Wazuh is an open-source security monitoring platform that can be used for threat detection, integrity monitoring, incident response, and compliance.**
#### <span style="color:#ec4b4b">What is Shuffle?</span>
>**Shuffle is a no-code automation platform (SOAR) that lets you automate your processes.**
>**Usecases in Shuffle are divided into 5 types.**
1. Collect
2. Enrich
3. Detect
4. Respond
5. Verify
#### <span style="color:#ec4b4b">What is The-Hive?</span>
>**The-Hive is an open-source incident response platform designed to help organizations manage and investigate security incidents effectively.**
>**It provides features such as incident case management, collaboration tools, alert aggregation and correlation, customizable investigation workflows, artifact management, and extensive integration capabilities.**

## Steps
### Step 1: Draw the Diagram
>**First, we will draw a diagram to understand how the traffic flows.**
---

1. Select the required icons, similar to those shown in the image below.
![1f](https://github.com/Kitty-OX/SOC-Automation-Project/assets/169779602/5332e8fb-2eda-4626-97c9-c011a32619e5)

2. The computer will send events over to "Wazuh Manager" [Gray Link].
![11](https://github.com/Kitty-OX/SOC-Automation-Project/assets/169779602/5c6e42d8-fb98-44a6-b979-6ee1cbeb394e)

3. Then, Wazuh Manager will create an alert and send it over to "Shuffle", But with another link color because it is a different action.
4. When Shuffle receives the alert, it will perform some open-source intelligence gathering to enrich our IOCs[Green Link].
![blu](https://github.com/Kitty-OX/SOC-Automation-Project/assets/169779602/5d34cd17-143b-483a-b2b1-db80c56f49cb)

5. Then we will connect "Shuffle" to "The-Hive".
6. After that, we want Shuffle to send an email to the SOC Analyst.
    - **Clarify the content of the email:** "The email should contain details about the alert and ask the SOC analyst about the action that should be taken."
![email](https://github.com/Kitty-OX/SOC-Automation-Project/assets/169779602/0fedeafb-2a22-465c-a542-bf6545b19ec2)

7. Finally, the response should be sent back to "Shuffle", which will then be sent to "Wazuh Manager", and eventually to the "Win-10 Client" to perform the action.
![fin](https://github.com/Kitty-OX/SOC-Automation-Project/assets/169779602/9bba5b16-7e49-4845-85cc-4782a1618606)

---
#### Explain the purpose:

|                    |                                                                                                             |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------ |
| **Win-10 Wazuh Agent** | Send Events                                                                                                        |
| **Wazuh Manager**      | Trigger alerts & Perform Response actions                                                                          |
| **Shuffle**            | Receive Wazuh alerts & Send responsive actions, Enrich IOCS and send Email to **SOC Analyst** & Responsive actions |
| **The-Hive**           | Create alert in case management                                                                                    |

### References:
- [Integrating Wazuh with Shuffle](https://wazuh.com/blog/integrating-wazuh-with-shuffle/?source=post_page-----983c54d7999c--------------------------------)
- [Shuffle Automation](https://github.com/Shuffle/Shuffle?source=post_page-----983c54d7999c--------------------------------)
