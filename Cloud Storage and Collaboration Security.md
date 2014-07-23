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

Cloud File Storage and Collaboration (Sync and Share) is one of the first things people think of when they hear the word "cloud" and one of the most popular product categories out there. It also tends to be one of the first areas IT departments struggle to manage since many users and business units want the functionality, use it personally, and there is no shortage of free and inexpensive options.

As you might expect since we can't even standardize on a single category name, there is also a wide range of different features and functions across the different services. To start, we detail out the core features with security implications, then the core security features themselves, and finally more-advanced security features we see cropping up in some providers. 

This isn't merely a feature list — in each case we cover the security implications, what to look for, and how you might want to integrate the feature (if available) into your security program.

##Overview and Core Features

When they first appeared, the term *Cloud Sync and Share* really did encapsulate the capabilities of these services. You could save a file locally, it would sync and upload to a cloud service, and you could expose a *share  link* so someone else on the Internet could download the file. The tools had various mobile agents for different devices, and essential all of them had some level of versioning so you could recover deleted files or previous versions.

> Cloud or not?
> Cloud services really popularized sync and share, but there are also non-cloud alternatives that still rely on hosting in your own environment, and connecting over a VPN or an open service. While there can be a lot of overlap, this paper focuses completely on cloud options. This is where most people are concerned about security, and we consider it the dominant model as most organizations continue to adopt more cloud and mobile.

Most providers now offer far more than core sync and share, all to differing degrees. Here are the core features that tend to define these services:

* *Storage:* The cloud provider stores files. Most typically this includes versioning and deleted files. The time period for retention, way to recover, and means of reverting to a previous version all vary greatly. Enterprises need to understand how much is stored, what users can access/recover, and if this affects security. For example, make sure you understand version and deletion recovery so you don't think you have removed a sensitive file only to have it turn up later. 
* *Sync:* A local user directory (or server directory) synchronizes changes with the cloud provider. Edit a file locally, and it background syncs to the server. Change it on one device, and it propagates to the rest. The cloud provider handles version conflicts (which can sometimes leave version orphans in the user's folder). Typically the user needs to access the web interface to access versions, recover deleted files, and manage collisions.
* *Share:* Users can share files through a variety of mechanisms, including, sharing directly with another user of the service (inside or outside the organization) which allows the user to sync the file or folder similar to their own content. Shares can also be web only, and either open to the Internet or specific only to users registered with the service or using a one-off password. This is often on a file or folder level, allowing capabilities such as creating a *project room* to support collaboration among different organizations, without allowing any direct access to any participant's private data. We will cover a lot of the security implications of sharing throughout this report, especially how to manage and secure sharing.
* *View:* Many services now include in-browser viewers for different file types. This isn't merely for convenience and ensuring users can see a file regardless of having a local version of Office installed, but can also be used as a security control when you don't want to enable local downloads.
* *Collaborate:* Expanding on simple viewers (and the reason we think *Sync and Share* isn't the best term anymore), some platforms allow users to mark up, comment on, or even edit collaborative documents directly in the web interface. This also ties into the project/share rooms we mention above.
* *Web and Mobile Support:* The platform syncs locally with multiple operating systems using local agents (okay, Windows and Mac), provides a browser-based user interface for access from anywhere, and offers native apps for multiple mobile platforms.
* *APIs:* Most cloud services expose APIs for direct integration of the platform into other applications. This is how, for example, Apple is adding a number of providers directly into the file system of the next versions of OS X and iOS. On the other hand, you could potentially link into APIs directly to pull security data or manage security settings.

These core features cover the basics offered by most enterprise-class cloud file storage and collaboration services. Most of the core security features we are about to cover are designed to directly manage and secure these capabilities.

And since "Cloud File Storage and Collaboration Service" is a but of an eyeful, for the rest of this paper we will simply refer to them as *cloud storage providers*. 

##Core Security Features

Core security features are those most commonly seen in enterprise-class cloud storage providers. It doesn't mean every provider necessarily supports them, but when evaluating the security of a service this is where you should start. Also keep in mind that different providers will support these features to different levels; it is important to dig into the documentation and understand how well the feature matches your requirements. Definitely don't assume the marketure is accurate.

###Security Baseline

Few things matter more than starting with a provider that offers strong baseline security. The last thing you want to do is trust your sensitive files with a company that doesn't consider security one of their top one or two priorities. The key areas to look at include:

* *Datacenter security:* The provider should offer exceptional datacenter security, including physical controls, logical controls, and all the other essentials to reduce the possibility of both physical and technical attacks. Since you can't necessarily assess this yourself, look for up-to-date third party certifications and attestations, such as an SOC 2 or ISO 27001. Generally, the more the better, but make sure you sign the NDA and get to see the actual reports, when the assessment occurred, and which organization performed the assessment.
* *Business continuity:* Short of a multi-nation asteroid collision, your provider should never lose your data... ever. Their business continuity plans should account for multiple, catastrophic outage scenarios, including complete losses of at least one data center. They should test the plan, and provide assurance and documentation of its effectiveness.
* *Encryption:* All customer data should be encrypted to meet compliance needs and protect data in case of accidentally loss of physical media. Ideally, multiple keys are used for different customers, and you should ask to review the encryption and key management architecture. Note that this isn't client-managed encryption; the provider manages the keys and can see your data, but it provides higher assurance against data spillage or exposure on physical media.
* *Application security:* The web application must be free of SQL Injection, CSS, CSRF, and other application and business logic attacks. This also applies to direct API access. The provider should offer proof of ongoing security testing and web application security controls.
* *Internal controls:* Providers should have well-documented internal security controls to prevent both external attacks and insider abuse. Don't expect them to provide you with all the details, but one key to ask about is administrative access and auditing. Essentially, who can access your data, how, and is it monitored for internal or external abuse? Two-factor authentication for admins is a must.
* *Transparency, staffing, and documentation:* The short version is you want a provider with a dedicated security team, who is transparent about security operations, and provides good documentation both of their inherent security, and how to *be* secure using the features of the platform.

This isn't an exhaustive list, but the key areas to focus your initial assessment. Without a solid security baseline, it really doesn't matter what else the service offers.

###Identity and Access Management

Managing users and access are the most important features after a security baseline. The entire security and governance model relies on it. These are the key elements to look for:

* *Service and federated IDM:* The cloud service needs to implement an internal identity model to allow sharing with external parties without requiring those individuals or organizations to register with your internal identity provider. However, the service also needs to support federated identity so you can use your internal directory and don't need to manually register all of *your* users with the service. SAML is the preferred standard. Both models should support API access, which is key to integrating the service as back-end storage to your applications.
* *Authorization and access controls:* Once you establish and integrate identity, the service should support a robust, granular permissions model. The basics include user and group access at the directory, sub-directory, and file levels. The model should integrate internal, external, and anonymous users. Permissions should include read, write/edit, download, and view (to allow web viewing, but not downloading of files). Additional permissions manage who can share a file (internal and external), alter permissions, comment, or delete files. 

> External Users
> An external, authenticated user is one that registers with the cloud provider, but isn't part of your organization. This is important for collaborative group shares, like deal and project rooms. Most services also support open external shares, but these are open to the world. That's why providers need to support both their own platform user model, and federated identity to integrate with your existing internal directory.

* *Device control:* Cloud storage services are very frequently used to support mobile users on a variety of devices. Device control allows management of which devices (computer and mobile devices) are authorized for which users, to ensure only authorized devices gain access. 
* *Two-factor authentication (2FA):* Since account credential compromise is a major concern, some providers support requiring a second authentication factor when accessing the service. Today, this is most typically a text message with a one time password sent to a registered mobile phone. Also, it is usually only triggered when accessing the service from a new or unregistered device or computer. 
* *Centralized management:* Administrators can manage all permissions and sharing through the service's web interface. For enterprise deployments, this includes setting enterprise-wide policies, like restricting external sharing completely, or various sharing options (like auto-expiring all shared links after a certain amount of time). Admins should also be able to identify all shared links, without having to crawl through the directory structure.

Sharing permissions and policies are a key differentiator between enterprise-class and consumer services. For enterprises, central control and management of shares is critical. As is the ability to manage who can share content externally, with what permissions, and to which categories of users (e.g. registered vs. an open file link). You might, for example, only allow employees to share with authenticated users on an enterprise-wide basis. Or only allow certain user roles to share files externally, and even then only with in-browser viewing only, with links set to expire in 30 days.

All organizations have different tolerances for sharing and file permissions. Granular controls allow you to align your use of the service with your existing policies. These can also be a security benefit, since you gain centralized control over all storage, as opposed to the traditional model of having to manage dozens, if not thousands, of different systems with different authentication methods and authorization and permissions models.

###Audit and transparency

One of the most powerful security features of cloud storage services is a complete audit log of all user and device activity. Enterprise-class services track absolutely all activity — Which users touched which files from which devices. Features to look for include:

* *Completeness of the audit log:* Ideally it includes user, device, what file was accessed, what activity was performed (download vs. view), and additional metadata, like location.
* *Log duration:* How much data does the audit log contain? Is it eternal? Or does it expire in 90 days?
* *Log management and visibility:* How do you access the log? Is the user interface navigable and centralized, or do you need to hunt around and click on individual files? Can you filter and generate reports by user, file, and device? 
* *Integration and export:* Logs should be externally consumable in a standard format to integrate with existing log management and SIEM tools. Administrators should also be able to export activity reports and raw logs.

These features don't cover everything all the services offer, but are the core-set of security capabilities enterprise and business users should start with.



