
# Principles of Privileges
## **PIM | Privileged Identity Management**

> - PIM is used to translate a user's role within an organisation into an access role on a system. Whereas PAM is the management of the privileges a system's access role has, amongst other things.
> - Being used when you wanted to manage privileges a system access role had.

## **PAM | Privileged Access Management**

> - PAM incorporates more than assigning access. It also encompasses enforcing security policies such as password management, auditing policies and reducing the attack surface a system faces.
> - Being used when you wanted to create a system role that is based on a users role/responsibilities with an organisation.


# **Frameworks**
### STRIDE:
> A breach of security is known as an incident. And despite all rigorous threat models and secure system designs, incidents do happen. Actions taken to resolve and remediate the threat are known as Incident Response (IR) and are a whole career path in cybersecurity.

>  Incidents are classified using a rating of urgency and impact. Urgency will be determined by the type of attack faced, where the impact will be determined by the affected system and what impact that has on business operations.
```
1. Spoofing Identity
   - This principle requires you to authenticate requests and 
     users accessing a system. Spoofing involves a malicious 
     party falsely identifying itself as another.
     Access keys (such as API keys) or signatures via encryption 
     helps remediate this threat.
2. Tempering with data
   - By providing anti-tampering measures to a system or 
     application, you help provide integrity to the data. Data 
     that is accessed must be kept integral and accurate.
     For example, shops use seals on food products.
3. Repudiation Threats
   - This principle dictates the use of services such as logging 
     of activity for a system or application to track.
4. Information Disclosure
   - Applications or services that handle information of 
     multiple users need to be appropriately configured to only 
     show information relevant to the owner.
5. Denial of Service
   - Applications and services use up system resources, these 
     two things should have measures in place so that abuse of 
     the application/service won't result in bringing the whole 
     system down.
6. Elevation of Privileges 
   - This is the worst-case scenario for an application or 
     service. It means that a user was able to escalate their 
     authorization to that of a higher level i.e. an 
     administrator. This scenario often leads to further 
     exploitation or information disclosure.
```


### Computer Security Incident Response Team (CSIRT):

> An incident is responded to by a **C**omputer **S**ecurity **I**ncident **R**esponse **T**eam (**CSIRT**) which is prearranged group of employees with technical knowledge about the systems and/or current incident. To successfully solve an incident, these steps are often referred to as the six phases of Incident Response that takes place, listed in the table below:
```
1. Preparation
   - Do we have the resources and plans in place to deal with 
     the security incident?
2. Identification
   - Has the threat and the threat actor been correctly 
     identified in order for us to respond to?
3. Containment
   - Can the threat/security incident be contained to prevent 
     other systems or users from being impacted?
4. Eradication
   - Remove the active threat.
5. Recovery
   - Perform a full review of the impacted systems to return to 
     business as usual operations.
6. Lessons Learned 
   - What can be learnt from the incident? I.e. if it was due to 
     a phishing email, employees should be trained better to 
     detect phishing emails.
```

