# DEFCON 29
## Talk links will be updated when available

### Unsorted LInks

* https://github.com/magnologan/awesome-k8s-security
* https://www.trendmicro.com/en_us/research/21/e/teamtnt-targets-kubernetes--nearly-50-000-ips-compromised.html
* https://github.com/aquasecurity/kube-bench

## Day 1

### OSQuery (BTV)
> Sebastiaan Provost @Stekkz
>
> * EDR tool
> * Uses sql queries to explore the OS
> * Yara

### Detection Challenges in Cloud Connected Credential Abuse Attacks (CV)
> Rod Soto
>
> * General discussion of the shared responsibility model. 
> * Use of vulnerable components. 
> * Exposure of applications and infrastructure. 
> * Re-use of federated credentials
>     * Golden SAML attack. 
>         * SAML forging
>         * Requires strict SAML assertion checking
>     * OAuth token hijack                                                       
>   	 * The use of a refresh token eliminates the usefulness of MFA  	 
>   * Pass-the-cookie	 
> * Pivoting from providers to internal or converged resources  
> * Post exploitation
>     * ADFSDump   
>         * Exploitation can result in bypass of RDP, exchange online, VPN w/o MFA, etc   
>     * The Colonial Pipeline hack utilized this and a VPN with no MFA
>    
> * Approach to these attacks    
>     * Endpoint (TTP numbers in presentation)
>         * Certutil
>         * Uncommon processes
>         * Registry keys used for privileges 
>         * Mimikatz
>     * Cloud (TTP numbers in presentation - other cloud providers information not provided)
>         * AWS SAML access
>         * AWS SAML update identity provider
>         * O365 Excessive SSO logon errors
>         * O365 added service principal
>         * O365 federated domain added   
>     * Detection via excessive SSO errors 

### AI Village Keynote (AIV)
> Bruce Schneider
>	* https://www.belfercenter.org/publication/coming-ai-hackers
>
>	* Modern AI systems are essentially black boxes (explainability problem)
>	* Deep Patient (medical diagnostic)
>	* Capability vs explainability
>	* Any good AI system will naturally find hacks (loopholes)
>	* Lack of specificity
>	* Feedback method required
>	* First places
>		* Financial Systems (algorithm based)

### What we thought would happen in 2021 (BTV)
> Gert-Jan Brggink @gertjanbruggink
>	* Overall risk is becoming greater
>	* Evolution of crimewave business
>	* Western bias in threat landscape
>	* MacOS based threats
>	* Windows “high ground”
>	* Topics
>		* Focus on old stuff
>		* Extortion scheme evolution
>		* DNS focused attacks
>			* DNS over https
>		* Evolution of browser injection attacks
>			* Malware code
>		* Modern wardriving

### Attacking Modern Environments: Attacking Terraform (CV)
> Mazin Ahmed @mazen160!
>	* **Missed most of this**
>	* Rogue terraform providers

### KubeGOAT (CV)
> Madhu Akula @madhuakula
> * For learning kubernetes security
> * The illustrated children’s guide to kubernetes
> * Kubernetesbyexample
> * DIND exploitation
> * Testing and evaluation of runtime security options

### Trailblazing AI for Cyber (AIV)
> Sagar Samtani
>	* Slides available on aivillage site
>	* Cybersecurity for AI vs the role of AI for cybersecurity
>	* Introduce the role of AI for cyber
>	   * Automate common tasks
>		* Sift through data more efficiently
>		* Identify patterns
>		* Phase 1: Fundamental Cyber Principles and tasks
>		* Phase 2: Data collection and aggregation
>		* Phase 3: AI-enabled analytics
>		* Phase 4: Knowledge usage and dissemination
>	* Provide a background of existing initiatives
>		* Cyber threat intel
>			* Dark web analysis (ISILinux)
>			* Phishing (PhishMonger)
>	* Disinformation & Propoganda
>	* Security Operations
>	* Adversarial Machine Learning
>		* IEEE DLS, ScAINet (EvadeML, SecML)
>	* Summarize potential mechanisms to progress the dicipline

### Kubestriker (DL1)
> Vasant Chinnipilli
>	* Runs as container
>	* Evaluates clusters
>	* New version has much improved interface
>	* Videos available in docs
>	* https://www.kubestriker.io/
>	* https://github.com/vchinnipilli/kubestriker
 

    
## Day 2

## Day 3 

### Identifying toxic combinations of permissions in your cloud infrastrcutre (CV)
> Michael Raggo
> 
> * What am I looking for?
>     * Uptick in identity account activity
>     * High quantity of services
>     * New access methods
>     * S3 GetObjects, PutObjects, ListObjects - signs of lateral movement
>     * Inactive account suddenly is used for lots of activities
>     * Role chaining/cross account activity
>     * New source IP/Geo
>     * Change in security group policy
> * Discussion of cloud over-permissions
>     * CSA Egregious Eleven discussion
> * Cloud Kill Chain
>     * Recon
>         * Cloud infra misconfiguration
>     * Infiltration
>			* Exploitation of resources with IAM permissons
>		* Privilege Escalation
>			* Role chaining or cross-account access
>		* Lateral Movement
>			* Over-provisoined role (RBAC)
>		* Exfiltration
>			* Acess, copy, download read-only cloud storage
>
>	* 	**ROTATE YOUR DAMN ACCESS KEYS**
>
>	* AWS Permissions risks
>		* External access
>			* ec2:AuthorizeSecurityGroupIngress
>				* Modify ACL and FW
>		* Insider Threat
>			* iam:createUser
>				* Can create accounts
>		* Lateral Movement
>			* iam:UpdateAssumeRolePolicy, sts:AssumeRole
>				* Can assume a role
>		* Privilege Escalation
>			* iam:PutUserPolicy
>				* Create or update an inline policy for a user
>	* GCP Permission risks
>		* External Access
>			* compute.securityPolicies.update
>		* Insider Threat
>			* iam.serviceAccounts.create
>		* Lateral Movement
>			* roles/compute.imageUser
>		* Privilege Escalation
>			* resourcemanager.projects.setIamPolicy
>	* Azure Permissions risks
>		* External access
>			* 
>		* Insider Threat
>			*
>		* Lateral Movement
>			* 
>		* Privilege Escalation
>			* 
>	* Issues
>		* GCP
>			* \> 85% have user managed keys not being rotated.
>			* \> 80% have service accounts with owner or editor directly or inherited.
>	* How to fix this?
>		* Virtually impossible to fix this manually
>		* Leverage logging data from the platform and useful analysis
>		* Azure & AWS security center(s)
>		* Anomaly detection
>		* Mitigation
>			* Remove high-risk perms not used >> 90 days
>			* Least-priv custom roles
>			* Inactive identies to read-only
>			* Resource access not used >> 90 days is removed 
>			* Allow temporary access to high-risk permissions on demand or just-in-time
>		* Hygiene
>			* List of high-risk perms
>			* What of these have been assigned
>			* Who has these
>			* Generate new policies removing high-risk
>			* Anomoly & outlier


### I know who has access to my cloud, do you? (CV)
> Igal Flegmann
>
>	* Keep Management accounts to a minimum (0?)
>		* IaC
>			* Make it easy
>		* Just in time access
>			* Dual key approval
>			* Make it hard
>	* Strong identity
>		* Isolated identities
>		* MFA
>		* Conditional access
>		* Remove SP passwords 
>		* Remove VM passwords
>			* local account passwords
>	* Keep your network closed
>		* only open necessary ports
>		* Be strict about IP ranges
>			* Be specific on services IP addresses
>		* Use networking jit
>	* Strong device
>		* intune managed devices (win)
>			* not AD GPOs
>	* Use cloud tools
>		* Az security center
>		* Managed service identites
>		* Azure key vault
>	* Monitor everything
>		* SIEM
>		* Platform service
>		* Enable logs for all service
>		* Write custom alerts in code
>	* Backdoors
>		* Add extra member to group
>		* Adding a classic administrator to azure subscription
>		* Adding a service principal as contributor to a subscription
>		* Remove AAD only to SQL authentication
>		* Add more permissions to AKV access policies
>		* Adding IP addresses to firewall rules
>	* Discussion of CloudWatcher (PowerShell module that runs in Azure automation
>		* Looks for configuration changes
>			* Looks for
>				* RBAC changes
>				* Classic admin
>				* Azure resource provider changes
>				* Resource creation or deletion
>				* Change of group membership (first degree)
>				* SQL firewall changes
>				* SQL server ADD changes
>				* AKV access policy changes
>				* AKV firewall changes

### GCP GOAT (CV)
> Joshua Jebaraj
>
>	* Compute Engine
>	* App Engine
>	* SQL Instance
>	* GCP Buckets
>	* GKE Cluster
>	* Privilege escalation
>	* Github - https://github.com/joshuajebaraj/gcp-goat

### Cloud Security Orienteering (CV)
> Rami McCarthy @ramimacisabird
> 
>	* Securosis cloud adoption patterns
>		* Security typically lags
>	* What does good look like?
>		* Difficult due to complexity and emerging standards
>		* Leveraging guidance and offerings to reduce complexity
>		* Example of the Scott Piper AWS pillar whitepaper updates
>		* CIS for secure configuration
>		* Well architected security pillar
>		* Security roadmap (AWS example)
>	* Principles
>		* Breadth, then depth
>		* Anomaly detection
>		* Inside out
>		* Outside in
>	* Corporate archeology
>		* Items of note
>			* Asset inventory
>			* Standardized tagging (check out Yor!)
>			* Location of crown jewels
>