
## Strong Identity Management

Aim for least privilege 
RBAC
ABAC - Attribute based access control  
- complex but gives you more controls
- example validate tls, ip address, tags

AWS and customers share different and some common responsibilities 

## Authentication and Federation

policies - defined in json
there are multiple levels of policies 
- resource policies
- sessions policies

OU - organization unit is like Root Management group in azure - policies can be applied here and they trickle down
![](Pasted%20image%2020240203094112.png)

Federated - use external Identity providers like okta and azure AD 
can be applied at the account level or by using AWS SSO can be applied to all the accounts


## Traceability

gather events, feed/aggregate them to common solutions, enable ML to figure out abnormalities, detect configuration drifts, report and alert and finally react to the events 

There are several solution available on aws

cloud trail -aggregate logs, no audit
aws lambda - for automation 
aws config - dedicated features for determining compliances
aws detective - for forensic analysis after know something is wrong
aws security hub - can evaluate controls, uses aws config under the hood
aws inspector - vulnerability scan

### Defense in depth 

defense at various layers not just network or infrastructure but also code and configuration


## Data Protection and Security Events

![](Pasted%20image%2020240203094953.png)

![](Pasted%20image%2020240203095125.png)
Macie - data classification or protection
