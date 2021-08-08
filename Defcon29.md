# DEFCON 29
## Talk links will be updated when available

### Medical Device Panel
> Stephanie Domas  
> Kymberlee Price	

## Day 1

### OSQuery (BTV)
> Sebastiaan Provost @Stekkz
>> Presentation slides
>
>	* EDR tool
>	* Uses sql queries to explore the OS
>	* Yara

### Detection Challenges in Cloud Connected Credential Abuse Attacks (CV)
> Rod Soto
>> Presentation slides
>
>	* General discussion of the shared responsibility model
>	* Use of vulnerable components
>	* Exposure of applications and infrastructure
>	* Re-use of federated credentials
>		* Golden SAML attack
>			* SAML forging
>			* Requires strict SAML assertion checking
>		* OAuth token hijack                                                       
>			* The use of a refresh token eliminates the usefulness of MFA
>		* Pass-the-cookie
>	* Pivoting from providers to internal or converged resources
>	* Post exploitation
>		* ADFSDump
>			* Exploitation can result in bypass of RDP, exchange online, VPN w/o MFA, etc
>				* The Colonial Pipeline hack utilized this and a VPN with no MFA
>	* Approach to these attacks
>		* Endpoint (TTP numbers in presentation)
>			* Certutil
>			* Uncommon processes
>			* Registry keys used for privileges
>			* Mimikatz
>		* Cloud (TTP numbers in presentation - other cloud providers information not provided)
>			* AWS SAML access
>			* AWS SAML update identity provider
>			* O365 Excessive SSO logon errors
>			* O365 added service principal
>			* O365 federated domain added
>		* Detection via excessive SSO errors

### AI Village Keynote (AIV)
> Bruce Schneider  
> [Based on this paper](https://www.belfercenter.org/publication/coming-ai-hackers) 
>> Presentation slides
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
>> Presentation slides
>
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
>> Presentation slides
>
>	* **Missed most of this**
>	* Rogue terraform providers

### KubeGOAT (CV)
> Madhu Akula @madhuakula
>> Presentation slides
>
>	* For learning kubernetes security
>	* The illustrated children’s guide to kubernetes
>	* Kubernetesbyexample
>	* DIND exploitation
>	* Testing and evaluation of runtime security options

### Trailblazing AI for Cyber (AIV)
> Sagar Samtani
>> Presentation slides
>
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
>> Presentation slides  
>> [Kubestriker](https://github.com/vchinnipilli/kubestriker)
>
>	* Runs as container
>	* Evaluates clusters
>	* New version has much improved interface
>	* Videos available in docs
>	* https://www.kubestriker.io/

### Kubernetes Security 101 (CV)
> Mango Logan @mangologan
>> Presentation slides
>>	* https://github.com/magnologan/awesome-k8s-security
>>	* https://www.trendmicro.com/en_us/research/21/e/teamtnt-targets-kubernetes--nearly-50-000-ips-compromised.html
>	* MITRE ATT&CK for Containers and k8s
>	* K8s threat matrix by Microsoft
>	* Definition of CNCF, cloud native, etc.
>	* Mid-level description of kubernetes architecture
>	* Description of k8s yaml configuration
>	* MITRE ATT&CK for IaaS
>	* Slides??
>		* K8s attack scenario
>		* Utilizing node tokens 
>		* Amicontained (GitHub)
>		* Env | grep -I kube
>		* SA token
>			* /var/run/secrets/kubernetes/io/serviceaccounts
>		* Privilege pod - container escape
>	* Defending k8s
>		* Not secure by default
>		* Master node
>			* K8s ownership and file permissions from CIS
>			* NSA k8s hardening guidance doc in addition to CIS
>		* Worker nodes
>			* K8s ownership and file permissions from CIS
>		* Kube-system namespace
>			* Master node resources are in this namespace
>		* Kube api server
>			* Exposure
>		* Kubelet
>			* Agent that runs on each node
>			* Restrict kubelet permissions
>			* Rotate kubelet certificates
>		* [kube-bench](https://github.com/aquasecurity/kube-bench)
>			* Checks if deployed securely
>				* Validated against CIS k8s benchmark
>				* In Go
>		* Image scanning
>		* Runtime
>			* Falco
>				* Parses kernel sys calls at runtime
>				* Detects unexpected behavior
>				* Generates alerts
>				* Rules engine 
>				* Sidekick (??)
>			* Limit resources to pods
>			* Security context
>			* Seccomp/apparmor/selinux
>			* Pod Security Policies (Deprecated)
>			* Alternatives
>				* OPA/Gatekeeper
>				* Kyverno
>				* PSP++/ContainerBoundary?
>			* Treat cluster-admin like root
    
## Day 2

### Scaling appsec through education (ASV)
> Grant Ongers @rewtd
>> Presentation slides
>
>	* Almost all problems in code
>		* Traditional focus doesn’t cover enough
>		* Security Level Objectives (SLO)
>			* [BlackHat EU talk](https://www.blackhat.com/eu-20/features/schedule/index.html#are-you-big-friendly-giant---red-unless-blue-finds-green-ru-bfg-22029)
>	* Curriculum Development
>		* Based on OWASP standards
>			* ASC Foundation
>				* Slide and speaker notes for each of the top 10
>				* OWASP application security curriculum
>			* ASC Security Intermediate
>				* Uses Cornucopia
>				* Kind of OWASP top 5
>				* Uses [Cornucopia](https://www.youtube.com/watch?v=BZVoQurTEMc)
>				* AuthN
>				* AuthZ
>				* Session mgmt
>				* Crypto
>				* Data validation
>				* Misc
>				* Play the game with devs
>					* Guide them through the cards
>					* Encourage the cards use each sprint
>						* Tagging stories
>						* Retain Score sheet
>			* Application Security Tertiary Education
>				* OWASP ASVS
>				* ASVS Suitability
>					* 3 Levels
>						* Level 1 (opportunistic) used for all apps
>						* Level 2 (Standard) discussions
>						* Level 3 (Advanced) serious about security
>				* OWASP SAMM
>					* Prescriptive rather than descriptive (ASVS)
>				* Online version of Cornucopia?

### z/OS Container Breakout (Track2)
> Chad Rikansrud @bigendiansmalls  
> Ian Coldwater @IanColdwater
>> Presentation slides
> 	
>	* z/OS Container extensions z/CX
>		* Uses docker
>	* Evil Mainframe class
>	* Known DIND security holes
>	* z/CX auth plugin
>	* docker socket
>		* Known security hole if exposed
>		* Engine API

### What ML can do for security (BTV):
> Wendy Edwards @wayward710
>> Presentation slides
>
>	* ML Definition
>		* Supervised
>		* Unsupervised
>			* Abstractions from unlabeled datasets
>	* Neural Network
>		* Modeled on human brain
>		* Learning by analyzing training examples
>		* clideo.com
>			* Tensor flow example
>	* Deep Learning
>		* Stacked neural networks
>		* Supervised, semi-supervised, or unsupervised
>		* Requires extensively labeled dataset
>		* Anamoly detection (UBEA)
>	* Preparing the data
>		* Selection and sampling
>		* Feature extraction
>		* Encoding & vectorization
>		* Normalization
>	* Pattern recognition
>		* Can be used to teach an algorithm to recognize other forms of the data
>	* Clustering
>		* Grouping
>		* k-means and dbscan
>		* Clustering SOC events
>		* Can be applied to data, requires statistical validation
>	* Classification
>		* Predict the likelihood that a given sample belongs to a predefined class
>		* Is supervised
>		* Training, validation, testing, and deployment
>		* Not a yes or no but a measure of likelihood
>	* Contextual Embedding
>		* word2vec algorithm
>		* Useful for finding aliases
>	* Anomaly detection
>		* Establish what normal is
>		* Deviation from normal
>		* Examples    
>			* (N|H)IDS
>				* Describe desirable IDS parameters
>				* Describe HIDS parameters
>				* Describing OSQuery
>				* Web app intrusion detection
>				* Malware analysis

### How do you do ALL THE CLOUDS (BTV):
> henry @Bazinga73
>> [Presentation slides](https://cfc.blueteamvillage.org/media/call-for-content-2021/submissions/ZMUGGE/resources/BTV-henry_-_How_do_you_ALL_THE_CLOUDS_17ACPJP.pdf)
>
>	* General cloud challenges
>		* Security
>			* Account sprawl
>			* Misconfiguration
>			* Reliable identity and asset mgmt
>			* Lack of cloud security arch
>			* Lack of visibility/control
>			* Insufficient identity, credential, access, and key mgmt
>			* Insecure interfaces/API
>			* Unknown public exposure
>			* Cloud usage visibility
>		* GRC
>		* Interoperability
>		* Expense Management

### Modern Auth for security admins (BTV)
> Bailey Bercik @BaileyBercik. 
> Mark Morowczynski @markmorow
>> Presentation slides
>
> **MS Identity Product Group**
>	* Discussion of modern auth methods	
>		* SAML
>			* XML based AuthN
>			* Golden SAML attack
>				* Compromise the cert (SAML assertion) and can forget SAML
>			* ACS URL
>			* SAML logout
>			* Token monitoring
>				* Swapping SAML token for session token
>				* Inactivity and max lifetime
>			* Reduce risk
>				* Protect IdP like a domain controller
>				* Protect certs
>				* aka.ms/AzureADSecOps
>		* Oauth2
>			* AuthZ framework
>				* Delegation protocol
>			* Leverages HTTP, tokens and scopes
>			* Components
>				* Resource Owner
>				* Protected Resource
>				* Clien
>				* Authorization Server
>			* Access Token
>				* “Bearer” Token
>				* Must be used within of HTTPS
>				* JWT common format
>				* Auth server issues token
>				* Protected resource consumes the token
>			* Proper OAuth flows
>				* Authorization code grant - majority
>				* Implicit grant
>				* On-behalf-of-grant
>				* Device code grant 
>				* Client credentials grant
>				* Resource owner password credentials (ROPC) grant
>		* OpenID Connect
>			* Bult on OAuth2 for AuthN
>				* Used JWT with JSON object signing and encryption
>				* Gets an ID token along with access token
>			* Ask vendors to support OIDC
>			* Use an oauth OIDC library
>			* Do not use ROPC flow
>			* Ensure HTTPS is used and protect access tokens
>			* Focus on least privileges on application consent
>			* App consent phishing attacks
>				* Delegated permissions vs application permissions

### DevSecOps (ASV)
> Mango Logan @mangologan
>> [Presentation video](https://www.youtube.com/watch?v=JRWH8AdPpeE)

## Day 3 

### Identifying toxic combinations of permissions in your cloud infrastrcutre (CV)
> Michael Raggo
>> Presentation slides
>
>	* What am I looking for?
>		* Uptick in identity account activity
>		* High quantity of services
>		* New access methods
>		* S3 GetObjects, PutObjects, ListObjects - signs of lateral movement
>		* Inactive account suddenly is used for lots of activities
>		* Role chaining/cross account activity
>		* New source IP/Geo
>		* Change in security group policy
>	* Discussion of cloud over-permissions
>     * CSA Egregious Eleven discussion
>	* Cloud Kill Chain
>		* Recon
>			* Cloud infra misconfiguration
>		* Infiltration
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
>> Presentation slides
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
>> Presentation slides  
>> [GCP-Goat](https://github.com/joshuajebaraj/gcp-goat)
>
>	* Compute Engine
>	* App Engine
>	* SQL Instance
>	* GCP Buckets
>	* GKE Cluster
>	* Privilege escalation

### Cloud Security Orienteering (CV)
> Rami McCarthy @ramimacisabird
> > [Presentation slides](https://speakerdeck.com/ramimac/cloud-security-orienteering)
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
>	* [Hierarchy of Discovery](https://disruptops.com/aws-vs-azure-vs-gcp-a-security-pros-quick-cloud-comparison)
> 	* Be aware of CSPM exceptions or enabled/disabled rules
>	* Claims GCP has excellent asset inventory tools out of the box
>	* Prioritization
>		* Identity is the perimeter but the network perimeter is stil a thing
>		* [Kill chains](https://disruptops.com/stop-todays-top-10-cloud-attack-killchains/)
>	* Identity perimeter
>		* Management plane access model (local users vs federated users, MFA, etc)
>		* SSH/Server access model
>			* Bastion
>			* Direct SSH
>			* SSM-only
>			* Tooling (ZTA)
>		* Least privilege & IAm sec
>			* IAM credential report
>			* OSS tooling
>				* Cloudsplaining
>				* PMapper
>		* Network Perimeter
>			* Public resources
>			* Wildcard security groups
>			* Default resources (VPC, SGs)
>				* Launch-wizard SGs
>		* Hosted applications & services
>			* Out of date, known vulnerabilities
>			* Unauthenticated services
>			* Sensitive or internal (CI/CD, config mgmt)
>		* Exposed secrets
>		* Secret managment pattern
>		* Supply chain
>	* Blanket AWS harding recommendations
>		* Enable Guardduty
>		* Enable cloudtrail
>			* Enable optional security features, including encryption at-rest and file validation
>			* Centralize and backup logs
>		* Access analyzer
>		* Security visibity to all accounts
>		* S3 block public access, EBS and all other default encryption
>	* Maturity models
>		* [Cloud Security Maturity Model (CSMM)](https://www.iansresearch.com/resources/cloud-security-maturity-model/what-is-the-csmm) - IANS, CSA, Securosis
>		* [Marco Lancini's](https://roadmap.cloudsecdocs.com/)

#### Unsorted Links
https://www.dataquest.io/blog/jupyter-notebook-tutorial/
https://blog.appsecco.com/hacker-days-understanding-aws-cloud-attacks-using-cloudgoat-owasp-bay-area-cdeb39006e12
https://www.github.com/mandaroryprogrammer/PaperChaser
Cyber Aces

