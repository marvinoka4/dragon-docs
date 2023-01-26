---
layout: default
title: Event Tracking
parent: Analytics
grand_parent: General
nav_order: 1
---

# Event Tracking
{: .no_toc}

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}
---

### Introduction
There are three aspects to be considered in order to successfully pull Event (& Custom Event) Tracking off. It isn't complicated, but it is essential that all aspects need to be checked and double-checked as even the placement of a wrong letter at any point can hinder the process from sending, receiving and tracking data.

### Codebase
1. For this aspect, if you aren’t a developer, please ensure that you handle this with the assistance of a developer - or better yet, it should be confirmed by the developer. Incorrectly inserting or editing code in the head of a website could break the website.
2. From Google Tag Manager, create a container for the site to be tracked (if a container does not exist already). This container would have a corresponding Google Tag Manager script. This script can be gotten from the container settings - “Installation Instructions”. 
3. As stated in the “Installation Instructions” suggests, these scripts should be inserted in the <head> and <body> section of the codebase. This should be confirmed in the header.php file. The container ID has the format – “GTM-XXXXXXX”, ensure also that this matches with that on the script in the header.php of the site whose events you want to track. 
4. Any event to be tracked is pushed by the following code snippet;
    ```js
    window.dataLayer.push({
        'event': 'event_pushed',
        'event_parameter1': parameter1,'event_parameter2': parameter2, 'event_parameter2' : 'String'
    });
    ```
5. Note the format for event and event parameters (not just for forms). It is called snake case – all lowercase with underscore between words. It is highly recommended to abide by this for consistency and because Google advises it as part of their machine learning metric.

### Google Tag Manger (GTM)
1. This aspect can be managed by the marketing manager, regardless, it would be done with events and parameters set by the developer and pushed from the website. 
2. On the Google Tag Manager platform, in the container created for the website to be tracked, create a tag. In the "Tag" section, select "New" and select "Tag Configuration", from the canvas that slided in, select "Google Analytics: GA4 Configuration."
![](../../assets/images/docs-images/gtm-1.jpg)
3. From Google Analytics 4, set up the property of the site to be tracked (if the property isn't already set-up). In the course of setting up the property, a data stream would be created, this data stream contains a Measurement ID with the format "G-XXXXXXXXXX". Take note of this Measurement ID. If the property exists, the Measurement ID can be gotten from the "Admin" section, there you'd see "Data Streams". Select the data stream of the website to be tracked.
![](../../assets/images/docs-images/gtm-2.jpg)
4. Upload the Search Station Master Trigger
5. Connect it to the tag.
6. Ensure the parameters are set to be sent from GTM to GA4

### Google Analytics 4 (GA4)
"At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident, similique sunt in culpa qui officia deserunt mollitia animi, id est laborum et dolorum fuga. Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil impedit quo minus id quod maxime placeat facere possimus, omnis voluptas assumenda est, omnis dolor repellendus. Temporibus autem quibusdam et aut officiis debitis aut rerum necessitatibus saepe eveniet ut et voluptates repudiandae sint et molestiae non recusandae. Itaque earum rerum hic tenetur a sapiente delectus, ut aut reiciendis voluptatibus maiores alias consequatur aut perferendis doloribus asperiores repellat."

### 1914 translation by H. Rackham
"On the other hand, we denounce with righteous indignation and dislike men who are so beguiled and demoralized by the charms of pleasure of the moment, so blinded by desire, that they cannot foresee the pain and trouble that are bound to ensue; and equal blame belongs to those who fail in their duty through weakness of will, which is the same as saying through shrinking from toil and pain. These cases are perfectly simple and easy to distinguish. In a free hour, when our power of choice is untrammelled and when nothing prevents our being able to do what we like best, every pleasure is to be welcomed and every pain avoided. But in certain circumstances and owing to the claims of duty or the obligations of business it will frequently occur that pleasures have to be repudiated and annoyances accepted. The wise man therefore always holds in these matters to this principle of selection: he rejects pleasures to secure other greater pleasures, or else he endures pains to avoid worse pains."
