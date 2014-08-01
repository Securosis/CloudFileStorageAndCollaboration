Title: The Security Pro's Guide to Cloud File Storage and Collaboration

#The rise of cloud file storage and collaboration

Few technologies have invaded the enterprise as rapidly as cloud file storage and collaboration services. Typically called File Sync and Share, these tools originated as consumer cloud services to help people store, sync, and share files across computers and mobile devices. We hate to dip into hyperbole, but calling these tools groundbreaking is an understatement. Users can now access their files from any computer or device and share files with anyone, anywhere, with ease and simplicity never seen before. To many consumers, this is "the cloud".

These services so quickly proved their value that they inevitably made their way into the enterprise. Unfortunately few of them were architected to support the needs and security requirements of a business. In response, many organizations simply banned and blocked them, but as always happens when a tool provides demonstrable business benefit, use is inevitable -- with or without support.

In response, enterprise-class options emerged. But many security professionals still struggle to understand the implications of cloud storage and collaboration, and the differences between consumer and enterprise-grade services. Even though some of these services can offer superior security to traditional on-premise file storage.

The market is evolving incredibly rapidly, with both new features and new competitors showing up constantly. We see continuous change as everyone scrambles for competitive advantage in this wide-open new market.

>The category is most often called *file sync and share*, but we prefer the term *cloud file storage and collaboration* because many of the services and tools offer much more than basic syncing and sharing.

Cloud file storage and collaboration services are an unavoidable disruptive innovation.

##Security implications, but also significant benefits

The risk is pretty obvious: pick the wrong service, or configure it incorrectly, and it is all too easy to effectively punch a hole in your firewall, allow all denizens of the Internet unfettered access to your files. Without centralized visibility and control, employees make mistakes and expose sensitive information. Choose an insecure service and you suffer the consequences of misplaced trust and exposed files.

Practically speaking, file security is something most organizations have struggled with since long before the Internet. But cloud services enable us to extend our failures across the Internet.

>Tools vs. Services

>You will notice we tend to focus on cloud storage and collaboration services, rather than tools you implement yourself. While tools are available to create your own private file sync and share services, they don't offer all the benefits of a true cloud service. Covering both would complicate this paper, and most of the concerns and questions we receive are about cloud-native services, not internal tools which offer similar functionality.

But pick the right service *and configure it properly*, and you can realize security benefits that are impossible with traditional file storage.

By centralizing all file storage security gains a choke point for complete control and visibility. You can track the full history of access to all files from all users and devices. You can set enterprise-wide policies for how files are managed and shared, both internally and externally. And unlike many other security approaches, you can do so while providing the business *something they want* and are highly likely to adopt.

The alternative? Our existing troves of dozens, if not hundreds or thousands, of file repositories -- all managed separately, with different policies, and usually without any real monitoring capabilities.

This paper delves into the security implications of cloud file storage and collaboration services. It covers the security fundamentals (including risks and benefits), core security features, and some more advanced security features such as encryption options. We will separate out what you can expect from an enterprise-class service vs. a consumer offering -- to help security professionals evaluate, select, and leverage the right options for their organizations.

#Understanding Cloud File Storage and Collaboration Services

Cloud File Storage and Collaboration (often called Sync and Share) is one of the first things people think of when they hear the term 'cloud', and one of the most popular product categories. It tends to be one of the first areas IT departments struggle to manage, because many users and business units want the functionality and use it personally, and there is a wide variety of free and inexpensive options.

As you might expect, since we can't even standardize on a single category name, we also see a wide range of different features and functions across the various services. We will start by detailing the core features with security implications, then the core security features themselves, and finally more advanced security features we see cropping up in some providers.

This isn't merely a feature list -- we cover each feature's security implications, what to look for, and how you might want to integrate it (if available) into your security program.

##Overview and Core Features

When these services first appeared, the term *Cloud Sync and Share* did a good job of encapsulating their capabilities. You could save a file locally, it would sync and upload to a cloud service, and you could expose a *share link* so someone else on the Internet could download the file. The tools had various mobile agents for different devices, and essentially all of them had some level of versioning so you could recover deleted files or previous versions.

> Cloud or not?
>
> Cloud services popularized sync and share, but there are also non-cloud alternatives which rely on hosting within your own environment -- connecting over a VPN or the public Internet. There is considerable overlap between these very different models, but this paper focuses on cloud options. They are where we hear the most concerned about security, and cloud services are dominant in this market -- particularly as organizations move farther into the cloud and prioritize mobility.

Most providers now offer much more than core sync and share. Here are the core features which tend to define these services:

* *Storage:* The cloud provider stores files. This typically includes multiple versions and retention of deleted files. The retention period, recovery method, and mechanism for reverting to a previous version all vary greatly. Enterprises need to understand how much is stored, what users can access/recover, and how this affects security. For example make sure you understand version and deletion recovery so sensitive files you 'removed' don't turn up later.
* *Sync:* A local user directory (or server directory) synchronizes changes with the cloud provider. Edit a file locally, and it silently syncs up to the server. Update it on one device and it propagates to the rest. The cloud provider handles version conflicts (which can leave version orphans in the user folders). Typically users access alternate versions and recover deleted files through the web interface, and sometimes it also manages collisions.
* *Share:* Users can share files through a variety of mechanisms, including sharing directly with another user of the service (inside or outside the organization) which allows the recipient to sync the file or folder like their own content. Shared items can be web only; sharing can be open (public), restricted to registered users, or require a one-off password. This is often handled at the file or folder level, allowing capabilities such as *project rooms* to support collaboration across organizations without allowing direct access to any participant's private data. We will cover security implications of sharing throughout this report, especially how to manage and secure sharing.
* *View:* Many services now include in-browser viewers for different file types. Aside from convenience and ensuring users can see files, regardless of whether they have Office installed, this can also function as a security control, instead of allowing users to download files locally.
* *Collaborate:* Expanding on simple viewers (and the reason *Sync and Share* isn't entirely descriptive any more), some platforms allow users to mark up, comment on, or even edit collaborative documents directly in a web interface. This also ties into the project/share rooms we mention above.
* *Web and Mobile Support:* The platform syncs locally with multiple operating systems using local agents (okay, Windows, Mac, and at least iOS), provides a browser-based user interface for access from anywhere, and offers native apps for multiple mobile platforms.
* *APIs:* Most cloud services expose APIs for direct integration into other applications. This is how, for example, Apple is adding a number of providers at the file system layer in the next versions of OS X and iOS. On the other hand, you could potentially link into APIs directly to pull security data or manage security settings.

These core features cover the basics offered by most enterprise-class cloud file storage and collaboration services. Most of the core security features we are about to cover are designed to directly manage and secure these capabilities.

And since "Cloud File Storage and Collaboration Service" is a bit of a mouthful, for the rest of this paper we will simply refer to them as *cloud storage providers*.

##Core Security Features

Core security features are those most commonly seen in enterprise-class cloud storage providers. That doesn't mean every provider supports them, but to evaluate the security of a service this is where you should start. Keep in mind that different providers offer different levels of support for these features; it is important to dig into the documentation and understand how well the feature matches your requirements. Don't assume any marketure is accurate.

###Security Baseline

Few things matter more than starting with a provider that offers strong baseline security. The last thing you want to do is trust your sensitive files to a company that doesn't consider security among their couple priorities. Key areas to look at include:

* *Datacenter security:* The provider should offer exceptional datacenter security -- including physical controls, logical controls, and all the other essentials to reduce the risk of physical and technical attacks. You cannot necessarily assess this yourself, so look for up-to-date third-party certifications and attestations, such as SOC 2 or ISO 27001. Generally the more the better, but make sure you sign the NDA and get the actual reports, when the assessment occurred, and which organization performed it.
* *Business continuity:* Short of a international asteroid impact, your provider should **never** lose your data. Their business continuity plans should account for multiple catastrophic outages, including complete loss of at least one data center. They should test their plans and provide assurance of their effectiveness, with documentation.
* *Encryption:* All customer data should be encrypted for compliance and to protect data from accidental loss of physical media. Ideally multiple keys should be used for different customers, and you should review their encryption and key management architecture. Note that this is not client-managed encryption -- the provider manages the keys and can see your data, but it provides higher assurance against data spillage or exposure of physical media.
* *Application security:* The web application must be free from vulnerabilities to SQL injection, CSS, CSRF, and other application and business logic attacks. This also applies to direct API access. The provider should offer proof of ongoing security testing and web application security controls.
* *Internal controls:* Providers should have well-documented internal security controls to prevent both external attacks and insider abuse. Don't expect them to provide you with all the details, but one key to ask about is administrative access and auditing. Essentially who can access your data, how, and how it is monitored in case of internal or external abuse. Two-factor authentication for administrators is a must.
* *Transparency, staffing, and documentation:* The short version: you want a provider with a dedicated security team, who is transparent about security operations and provides good documentation -- both of their inherent security, and how to secure the services you use with their platform features.

This isn't an exhaustive list, but key areas to focus on in your initial assessment. Without a solid security baseline it really doesn't matter what else the service offers.

###Identity and Access Management

Managing users and access are the most important features after the security baseline. The entire security and governance model relies on it. These are the key elements to look for:

* *Service and federated IDM:* The cloud service needs to implement an internal identity model to allow sharing with external parties without requiring those individuals or organizations to register with your internal identity provider. The service also must support federated identity so you can use your internal directory and don't need to manually register all *your* users with the service. SAML is the preferred standard. Both models should support API access, which is key to integrating the service with your applications as back-end storage.
* *Authorization and access controls:* Once you establish and integrate identity the service should support a robust and granular permissions model. The basics include user and group access at the directory, subdirectory, and file levels. The model should integrate internal, external, and anonymous users. Permissions should include read, write/edit, download, and view (web viewing but not downloading of files). Additional permissions manage who can share files (internally and externally), alter permissions, comment, or delete files.

> External Users
>
> An external authenticated user is one who registers with the cloud provider but isn't part of your organization. This is important for collaborative group shares, such as deal and project rooms. Most services also support public external shares, but these are open to the world. That is why providers need to support *both* their own platform user model and federated identity to integrate with your existing internal directory.

* *Device control:* Cloud storage services are very frequently used to support mobile users on a variety of devices. Device control allows management of which devices (computers and mobile devices) are authorized for which users, to ensure only authorized devices have access.
* *Two-factor authentication (2FA):* Account credential compromise is a major concern, so some providers can require a second authentication factor to access their services. Today this is typically a text message with a one-time password sent to a registered mobile phone. The second factor is generally only required to access the service from a 'new' (unregistered) device or computer.
* *Centralized management:* Administrators can manage all permissions and sharing through the service's web interface. For enterprise deployments this includes enterprise-wide policies, such as restricting external sharing completely and  auto-expiring all shared links after a configurable interval. Administrators should also be able to identify all shared links without having to crawl through the directory structure.

Sharing permissions and policies are a key differentiator between enterprise-class and consumer services. For enterprises central control and management of shares is essential. So is the ability to manage who can share content externally, with what permissions, and to which categories of users (*e.g.,* restricted to registered users vs. via an open file link). You might, for example, only allow employees to share with authenticated users on an enterprise-wide basis. Or only allow certain user roles to share files externally, and even then only with in-browser viewing only, with links set to expire in 30 days.

Each organizations has its own tolerances for sharing and file permissions. Granular controls allow you to align your use of the service with existing policies. These can also be a security benefit, providing centralized control over all storage, unlike the traditional model where you need to manage dozens or even thousands of different systems, with different authentication methods, and authorization models, and permissions.

###Audit and transparency

One of the most powerful security features of cloud storage services is a complete audit log of all user and device activity. Enterprise-class services track **all** activity: which users touch which files from which devices. Features to look for include:

* *Completeness of the audit log:* It should include user, device, accessed file, what activity was performed (download/view/edit, with before and after versions if appropriate), and additional metadata such as location.
* *Log duration:* How much data does the audit log contain? Is it eternal or does it expire in 90 days?
* *Log management and visibility:* How do you access the log? Is the user interface navigable and centralized, or do you need to hunt around and click individual files? Can you filter and report by user, file, and device?
* *Integration and export:* Logs should be externally consumable in a standard format to integrate with existing log management and SIEM tools. Administrators should also be able to export activity reports and raw logs.

These features don't cover everything offered by these services, but they are the core security capabilities enterprise and business users should have to start with.

##Additional Security Features

The core security features are a baseline most enterprise or business customers should look for when selecting a service for their organization, but the various services also offer a plethora of additional security features. Providers see this as a way to entice enterprise users onto the services, show advantages over traditional storage infrastructure, and create competitive differentiation.

In other words, security is seen as both a competitive baseline and a competitive differentiator, which is why we see new capabilities appearing on a consistent basis. Thus, odds are high this report isn't going to cover everything that is potentially available by the time you read it.

###Universal search and investigation support

As we covered earlier, most cloud storage providers track all files, enable content search, and track every user and every device that accesses a file, including who viewed it in a web browser, downloaded a copy, or syncs it with a computer or device.

Having a central control point enables some fairly powerful security capabilities. Worried a document leaked? Find all copies and the entire access history. Now an obvious caveat applies — once a file leaves the service it isn't tracked, but at least you have a starting point to identify where it went. This is often one of the more difficult first steps in any leak/breach/abuse investigation since traditional storage products rarely track this level of detail.

Enhancing this is full content indexing and search. This isn't purely a security feature, but does allow you to search your entire cloud storage repository for keywords or other specific content. Some providers offer options for more-advanced searches, particularly *regular expressions*. Since this is useful for non-security reasons, we expect indexing and searching capabilities to increase over time, but make sure you understand what your provider supports for now.

Another limitation is that providers don't support every possible document type. For example, the odds are low your CAD file format is supported (today). Typically standard Office and text formats are supported, and check with your potential providers rather than assuming. 

###Client-managed encryption

All enterprise-class cloud storage providers encrypt data in their back-end, but they manage the keys and can thus technically see your content. There are now third-party security vendors who encrypt cloud data using different approaches, and some cloud storage vendors are adapting their architectures to allow customers to encrypt directly within the service, but control their own keys.

This is a different approach than using a third-party tool. Your cloud provider still handles the encryption in their back end, but you control the encryption keys. There are two major options:

* The cloud platform endpoint agents handle encryption operations synchronized with your enterprise key store. To work, they need to include this capability in both workstation and mobile agents, and a mechanism for integrating key distribution. 
* The cloud platform manages encryption in their back end, but opens mechanisms for enterprise users to provision and manage their own keys. From a technical standpoint, there are a few ways to handle this, but typically it will involve a Hardware Security Module (HSM) that is either located in the cloud provider's data centers yet managed by the client, or is in a client data center or infrastructure cloud provider. The important part is that the customer, not the cloud provider, is the only one that manages the keys. Technically they are exposed in the cloud provider's data center during crypto operations, but architected correctly the risk of key exposure can be minimized.

We won't be surprised to see other approaches develop over time, but these are the two we know are either on the market, or will be soon. In both cases, the customer needs their own key management infrastructure.

**One major warning — encrypting data with your own key breaks most or all collaboration features and any indexing/search since the cloud provider can never see the content.** As such, it is something you should generally limit to your most sensitive data. Apply it to everything, and you may see users try to circumvent encryption so they can regain the other features of the platform.

###Data Loss Prevention

If you think about it, full-text index and search combined with a complete audit log of all activity associated with a file is effectively a form of Data Loss Prevention (DLP). This meets the definition of basic content-aware DLP.

In addition, the cloud provider can offer real-time monitoring of all content based on these search terms, and tie that to enforcement policies. For example, the cloud storage provider could quarantine a file anytime a credit card number is found, and alert an administrator. This supports enterprise-wide content policies for the entire cloud storage platform.

More advanced rules could apply on a user or group basis, restrict only certain activities (e.g. "never share a file with PII or this keyword in it externally", or any other combination of analysis and rules (like device restrictions). DLP takes full content index and search, and combines it with persistent policies for near-real time content-aware protection.

The market for integrated DLP is still extremely early, and when it is available the features tend to be limited. Third party integration can provide more capability, and as with everything we expect to see capabilities expand at a reasonable pace. In discussions with clients this seems to be a popular requirement, which will continue to push the market along.

###DRM/IRM

Digital Rights Management, also known as Information Rights Management, is defined as encrypting data and then limiting usage through rights policies. For example, allowing someone to view a file but not email or print it.

Since cloud file storage and collaboration services often include an in-browser reader, and granular rights policies, they can enable a limited version of DRM. Set a policy so a file can only be viewed in a browser, and never downloaded, and you can limit activity. 

However, to be truly considered DRM the service should include in-browser protections against actions like screen capture. Ideally the platform can directly, or through third-party integration, allow document markup and editing, not merely viewing. On the horizon we expect to see services that define DRM policies at the file level via integration with on-premise enterprise DRM, not that anyone is really using that.

###Device security

At the most basic level, the cloud service should support restricting content only to approved devices, and include integration for federated identity. The service should also track all files the device downloaded. Content on the device should be encrypted, either using a proprietary mechanism or native app encryption on the device.

For content security, some providers allow remote wiping of the service's app, effectively destroying the data. Another option is to remotely log out the application, which also restricts access to the data, although depending on the encryption a forensic-level recovery may still be possible if the data (or encryption key) isn't deliberately wiped.

Providers are also exploring additional mobile device features, predominantly centered around Mobile Device Management-like capabilities to better understand the device configuration and even detect certain forms of jailbreaking or other compromise that could expose data on devices.

###API support

Nearly all cloud storage providers support a robust API for integration into other applications and services. It is becoming an essential baseline feature for the market. However, not all APIs are created equal. From the security standpoint, all security features should be API enabled to support integration with existing and future tools. 

###Integrations

While APIs provide the hooks, there are a few common categories of security tools we tend to see pre-integrated more commonly. This is often enabled by vendor partnerships, the API support we mention above, and/or making data from the service (especially security audit logs) consumable in standard formats. Established integrations save you time, and are officially supported, as opposed to coding up something yourself.

Some of the most common and useful integrations include:

* *Cloud security gateways:* This product category has a number of names, but includes products that identify cloud services used by your organization and use multiple techniques to add security (such as more granular controls, inline encryption, better security management, or DLP). 
* *Encryption gateways:* While sometimes a feature of cloud security gateways, these stand-alone products proxy connections to the cloud provider and selectively encrypt data. We aren't the biggest fans of this approach due to the logistics and effects on the cloud service features, but it's a viable option of encryption is mandated and not supported by your vendor.
* *Digital Rights Management:* While we see very few successful enterprise-wide DRM deployments, new providers focused on mobile collaboration scenarios have emerged and appear to support some valuable use cases. 
* *Mobile Device Management:* This integration allows greater granularity and control of what devices and which users can connect to the cloud service.
* *SIEM/log management:* The SIEM tool collects activity directly from the cloud provider and integrates it into consolidated logging, alerting features, and even correlation with other security events.

We also see integrations developing with electronic discovery tools, standard DLP, business intelligence, and others as new use cases emerge. As enterprise adoption of cloud file storage vendors increases, we expect to see many more integrations emerge.

##Conclusions, and a caution

This biggest concern about using a cloud file storage and collaboration service is the worry of entrusting your sensitive information, sometimes your *most* sensitive information, to an outsider that mixes it up with everyone else's data. That can be a tall mental hurdle to leap, especially when your experience is with consumer services with spotty security records.

However, using a secure, enterprise-class service brings some demonstrable security advantages. It reduces file sprawl and provides a total view of all activity that is effectively impossible with our traditional storage practices. Add on some security features, like content indexing and search, and some creative security solutions emerge. Full visibility and control is a heck of a powerful tool.

Despite these advantages, you still need to be careful. One security foible can expose all your files to the entire Internet. These providers need to be absolutely best in class, with extensive transparency, strong governance, and continuous, massive, security testing and dedicated security teams. Even then you might need the occasional dash of encryption to add more assurance you control, especially if you are concerned with government snooping.

Do your homework, choose widely, and you will gain the kind of governance over your files most security professionals never dreamed could actually happen.