# DefCon29
## Talk links will be updated when available

### Unsorted LInks
* https://www.kubestriker.io/ 
* https://github.com/vchinnipilli/kubestriker
* https://github.com/magnologan/awesome-k8s-security
* https://www.trendmicro.com/en_us/research/21/e/teamtnt-targets-kubernetes--nearly-50-000-ips-compromised.html
* https://github.com/aquasecurity/kube-bench

## Day 1

### OSQuery (BTV)
Link -   
Sebastiaan Provost  

* EDR tool
* Uses sql queries to explore the OS
* Yara

### Detection Challenges in Cloud Connected Credential Abuse Attacks (CV)
Link  
Rod Soto

- General discussion of the shared responsibility model. 
- Use of vulnerable components. 
- Exposure of applications and infrastructure. 
- Re-use of federated credentials
    - Golden SAML attack. 
        - SAML forging
        - Requires strict SAML assertion checking
    - OAuth token hijack                                                       
  	 - The use of a refresh token eliminates the usefulness of MFA  	 
  * Pass-the-cookie	 
- Pivoting from providers to internal or converged resources  
- Post exploitation
    - ADFSDump   
        - Exploitation can result in bypass of RDP, exchange online, VPN w/o MFA, etc   
    - The Colonial Pipeline hack utilized this and a VPN with no MFA
    
- Approach to these attacks    
    - Endpoint (TTP numbers in presentation)
        - Certutil
        - Uncommon processes
        - Registry keys used for privileges 
        - Mimikatz
    - Cloud (TTP numbers in presentation - other cloud providers information not provided)
        - AWS SAML access
        - AWS SAML update identity provider
        - O365 Excessive SSO logon errors
        - O365 added service principal
        - O365 federated domain added   
    - Excessive SSO errors 
     



## Day 2

## Day 3 