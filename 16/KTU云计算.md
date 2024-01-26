### GPT名称：KTU云计算
[访问链接](https://chat.openai.com/g/g-HZ2WpdsT5)
## 简介：用于消除关于KTU云计算的所有疑问的GPT
![头像](../imgs/g-HZ2WpdsT5.png)
```text
1. CLOUD COMPUTING- MODULE 4
   Syllabus:
   Part 1: Basic terms and concepts in security- Threat Agents, Cloud Security threats/risks, Trust.
   Part 2: Operating System security- Virtual machine security-Security of virtualization-Security risks posed by shared images, Security risks posed by management OS.
   Part 3: Infrastructure security - Network level security, Host level security, Application level security, Security of the physical systems. Identity & Access Management- Access Control.

   Part 1

   # Basic terms and concepts in security
   Confidentiality
   Confidentiality is the characteristic of something being made accessible only to authorized parties. Within cloud environments, confidentiality primarily pertains to restricting access to data in transit and storage.

   TRACE KTU
   Figure: The message issued by the cloud consumer to the cloud service is considered confidential only if it is not accessed or read by an unauthorized party.

   Integrity
   Integrity is the characteristic of not having been altered by an unauthorized party. An important issue that concerns data integrity in the cloud is whether a cloud consumer can be guaranteed that the data it transmits to a cloud service matches the data received by that cloud service. Integrity can extend to how data is stored, processed, and retrieved by cloud services and cloud-based IT resources.

   Figure: The message issued by the cloud consumer to the cloud service is considered to have integrity if it has not been altered.

   Authenticity
   Authenticity is the characteristic of something having been provided by an authorized source. This concept encompasses non-repudiation, which is the inability of a party to deny or challenge the authentication of an interaction. Authentication in non-repudiable interactions provides proof that these interactions are uniquely linked to an authorized source. For example, a user may not be able to access a non-repudiable file after its receipt without also generating a record of this access.

   Availability
   Availability is the characteristic of being accessible and usable during a specified time period. In typical cloud environments, the availability of cloud services can be a responsibility that is shared by the cloud provider and the cloud carrier. The availability of a cloud-based solution that extends to cloud service consumers is further shared by the cloud consumer.

   Threat
   A threat is a potential security violation that can challenge defenses in an attempt to breach privacy and/or cause harm. Both manually and automatically instigated threats are designed to exploit known weaknesses, also referred to as vulnerabilities. A threat that is carried out results in an attack.

   Vulnerability
   A vulnerability is a weakness that can be exploited either because it is protected by insufficient security controls, or because existing security controls are overcome by an attack. IT resource vulnerabilities can have a range of causes, including configuration deficiencies, security policy weaknesses, user errors, hardware or firmware flaws, software bugs, and poor security architecture.

   Risk

   TRACE KTU

   Risk is the possibility of loss or harm arising from performing an activity. Risk is typically measured according to its threat level and the number of possible or known vulnerabilities. Two metrics that can be used to determine risk for an IT resource are:
   • the probability of a threat occurring to exploit vulnerabilities in the IT resource
   • the expectation of loss upon the IT resource being compromised

   Security Controls
   Security controls are countermeasures used to prevent or respond to security threats and to reduce or avoid risk. Details on how to use security countermeasures are typically outlined in the security policy, which contains a set of rules and practices specifying how to implement a system, service, or security plan for maximum protection of sensitive and critical IT resources.

   Security Mechanisms
   Countermeasures are typically described in terms of security mechanisms, which are components comprising a defensive framework that protects IT resources, information, and services.

   Security Policies
   A security policy establishes a set of security rules and regulations. Often, security policies will further define how these rules and regulations are implemented and enforced. For example, the positioning and usage of security controls and mechanisms can be determined by security policies.

   # Threat Agents
   A threat agent is an entity that poses a threat because it is capable of carrying out an attack. Cloud security threats can originate either internally or externally, from humans or software programs. Corresponding threat agents are described in the upcoming sections. Figure illustrates the role a threat agent assumes in relation to vulnerabilities, threats, and risks, and the safeguards established by security policies and security mechanisms.

   TRACE KTU
   Figure: How security policies and security mechanisms are used to counter threats, vulnerabilities, and risks caused by threat agents.

   Anonymous Attacker
   An anonymous attacker is a non-trusted cloud service consumer without permissions in the cloud (Figure 6.4). It typically exists as an external software program that launches network-level attacks through public networks. When anonymous attackers have limited information on security policies and defenses, it can inhibit their ability to formulate effective attacks. Therefore, anonymous attackers often resort to committing acts like bypassing user accounts or stealing user credentials, while using methods that either ensure anonymity or require substantial resources for prosecution.

   Figure: The notation used for an anonymous attacker.

   Malicious Service Agent
   A malicious service agent is able to intercept and forward the network traffic that flows within a cloud. It typically exists as a service agent (or a program pretending to be a service agent) with compromised or malicious logic. It may also exist as an external program able to remotely intercept and potentially corrupt message contents.

   Figure: The notation used for a malicious service agent.

   Trusted Attacker
   A trusted attacker shares IT resources in the same cloud environment as the cloud consumer and attempts to exploit legitimate credentials to target cloud providers and the cloud tenants with whom they share IT resources. Unlike anonymous attackers (which are non-trusted), trusted attackers usually launch their attacks from within a cloud’s trust boundaries by abusing legitimate credentials or via the appropriation of sensitive and confidential information. Trusted attackers (also known as malicious tenants) can use cloud-based IT resources for a wide range of exploitations, including the hacking of weak authentication processes, the breaking of encryption, the spamming of e-mail accounts, or to launch common attacks, such as denial of service campaigns.

   Figure: The notation that is used for a trusted attacker.

   Malicious Insider

   TRACE KTU

   Malicious insiders are human threat agents acting on behalf of or in relation to the cloud provider. They are typically current or former employees or third parties with access to the cloud provider’s premises. This type of threat agent carries tremendous damage potential, as the malicious insider may have administrative privileges for accessing cloud consumer IT resources.

   # Cloud Security Threats
   Traffic Eavesdropping
   Traffic eavesdropping occurs when data being transferred to or within a cloud (usually from the cloud consumer to the cloud provider) is passively intercepted by a malicious service agent for illegitimate information gathering purposes. The aim of this attack is to directly compromise the confidentiality of the data and, possibly, the confidentiality of the relationship between the cloud consumer and cloud provider. Because of the passive nature of the attack, it can more easily go undetected for extended periods of time.

   Figure: An externally positioned malicious service agent carries out a traffic eavesdropping attack by intercepting a message sent by the cloud service consumer to the cloud service. The service agent makes an unauthorized copy of the message before it is sent along its original path to the cloud service.

   Malicious Intermediary
   The malicious intermediary threat arises when messages are intercepted and altered by a malicious service agent, thereby potentially compromising the message’s confidentiality and/or integrity. It may also insert harmful data into the message before forwarding it to its destination. Figure illustrates a common example of the malicious intermediary attack.

   TRACE KTU

   Figure: The malicious service agent intercepts and modifies a message sent by a cloud service consumer to a cloud service (not shown) being hosted on a virtual server. Because harmful data is packaged into the message, the virtual server is compromised.

   Denial of Service

   Figure: Cloud Service Consumer A sends multiple messages to a cloud service (not shown) hosted on Virtual Server A. This overloads the capacity of the underlying physical server, which causes outages with Virtual Servers A and B. As a result, legitimate cloud service consumers, such as Cloud Service Consumer B, become unable to communicate with any cloud services hosted on Virtual Servers A and B. The objective of the denial of service (DoS) attack is to overload IT resources to the point where they cannot function properly. This form of attack is commonly launched in one of the following ways:
   • The workload on cloud services is artificially increased with imitation messages or repeated communication requests.
   • The network is overloaded with traffic to reduce its responsiveness and cripple its performance.
   • Multiple cloud service requests are sent, each of which is designed to consume excessive memory and processing resources.

   Insufficient Authorization
   The insufficient authorization attack occurs when access is granted to an attacker erroneously or too broadly, resulting in the attacker getting access to IT resources that are normally protected. This is often a result of the attacker gaining direct access to IT resources that were implemented under the assumption that they would only be accessed by trusted consumer programs

   TRACE KTU
   Figure: Cloud Service Consumer A gains access to a database that was implemented under the assumption that it would only be accessed through a Web service with a published service contract (as per Cloud Service Consumer B). A variation of this attack, known as weak authentication, can result when weak passwords or shared accounts are used to protect IT resources. Within cloud environments, these types of attacks can lead to significant impacts depending on the range of IT resources and the range of access to those IT resources the attacker gains

   Virtualization Attack
   A virtualization attack exploits vulnerabilities in the virtualization platform to jeopardize its confidentiality, integrity, and/or availability. This threat is illustrated in Figure, where a trusted attacker successfully accesses a virtual server to compromise its underlying physical server. With public clouds, where a single physical IT resource may be providing virtualized IT resources to multiple cloud consumers, such an attack can have significant repercussions.

   Figure: An authorized cloud service consumer carries out a virtualization attack by abusing its administrative access to a virtual server to exploit the underlying hardware.

   Overlapping Trust Boundaries
   If physical IT resources within a cloud are shared by different cloud service consumers, these cloud service consumers have overlapping trust boundaries. Malicious cloud service consumers can target shared IT resources with the intention of compromising cloud consumers or other IT resources that share the same trust boundary. The consequence is that some or all of the other cloud service consumers could be impacted by the attack and/or the attacker could use virtual IT resources against others that happen to also share the same trust boundary. Figure illustrates an example in which two cloud service consumers share virtual servers hosted by the same physical server and, resultantly, their respective trust boundaries overlap.

   TRACE KTU

   Figure: Cloud Service Consumer A is trusted by the cloud and therefore gains access to a virtual server, which it then attacks with the intention of attacking the underlying physical server and the virtual server used by Cloud Service Consumer B.

   # Trust
   According to the Merriam-Webster dictionary trust means “assured reliance on the character, ability, strength, or truth of someone or something.” Trust is a complex phenomenon, it enables cooperative behavior, promotes adaptive organizational forms, reduces harmful conflict, decreases transaction costs, facilitates formulation of ad hoc work groups, and promotes effective responses to crisis. Two conditions must exist for trust to develop. The first is risk, the perceived probability of loss. Indeed, trust would not be necessary if there is no risk involved, if there is a certainty that an action can succeed. The second is interdependence, the interests of one entity cannot be archived without reliance on other entities. A trust relationship goes though three phases:
   1. Building phase, when trust is formed.
   2. Stability phase, when trust exists.
   3. Dissolution phase, when trust declines. There are different reasons and forms of trust. Utilitarian reasons could be based on the belief that the costly penalties for breach of trust exceed any potential benefits from opportunistic behavior. This is the essence of deterrence-based trust. Another reason is the belief that the action involving the other party is in the self-interest of that party. This is the so-called calculus-based trust. After a long sequence of interactions relational trust between entities can developed based on the accumulated experience of dependability and reliance on each other. Persistent trust is based on the long term behavior of an entity, while dynamic trust is based on a specific context, e.g., state of the system or the effect of technological developments. Internet trust “obscures or lacks entirely the dimensions of character and personality, nature of relationship, and institutional character” of the traditional trust [360]. The missing identity, personal characteristics, and role definitions are elements we have to deal with in the context of online trust.

   TRACE KTU

   Policies and reputation are two ways of determining trust. Policies reveal the conditions to obtain trust, and the actions when some of the conditions are met. Policies require the verification of credentials. Reputation is a quality attributed to an entity based on a relatively long history of interactions or possibly observations of the entity.

   PART-2

   # Operating System Security
   An operating system allows multiple applications to share the hardware resources of a physical system subject to a set of policies. A critical function of an OS is to protect applications against a wide range of malicious attacks such as unauthorized access to privileged information, tampering with executable code, and spoofing. Access control, authentication usage, and cryptographic usage policies are all elements of the mandatory OS security. Access control policies specify how OS controls access to different system objects, authentication usage defines the authentication mechanisms used by the OS to authenticate a principal, and cryptographic usage policies specify the cryptographic mechanisms used to protect the data. Applications with special privileges performing security-related functions are called trusted applications. Such applications should only be allowed the lowest level of privileges required to perform their functions. Commercial operating systems do not support multi-layered security. They only distinguish between a completely privileged security domain and a completely unprivileged one. A highly secure operating system is necessary but not sufficient. Application-specific security is also necessary. Sometimes, security implemented above the operating system is better, e.g., electronic commerce requires a digital signature on each transaction.

   An OS is a complex software system consisting of millions of lines of code and it is vulnerable to a wide range of malicious attacks. An OS poorly isolates one application from another; once an application is compromised, the entire physical platform and all applications running on it can be affected. Operating systems provide only weak mechanisms for applications to authenticate one another and do not have a trusted path between users and applications. These shortcomings add to the challenges of providing security in a distributed computing environment.

   # Virtual Machine Security
   Virtual security services are typically provided by the hyp
```