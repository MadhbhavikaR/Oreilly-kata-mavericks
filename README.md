# O'Reilly Architecture Katas 2023 : The Road Warrior

### Content
- [Introduction](#introduction)
- [Vision](#vision)
  - [Requirements](#requirements)
  - [Goals](#goals)
  - [Non Functional Requirement](#non-functional-requirement)
- [Setting the Stage](#setting-the-stage)
  - [Actors, Actions, and Scenarios](#actors-actions-and-scenarios)
  - [Key System Scenarios](#key-system-scenarios)
- [Architectural Essence](#architectural-essence)
  - [Architecture Characteristics](#architecture-characteristics)
  - [Implicit Characteristics](#implicit-characteristics)
  - [Approach](#approach)
- [Architectural Structures](#architectural-structures)
  - [Components](#components)
  - [System Design](#system-design)
  - [Security](#security)
- [Deployment](#deployment)
- [ADRs](#adrs)
- [References](#references)

---

## Introduction

In a world where travel has become an integral part of modern life, the journey towards creating the ultimate travel companion begins. 

Welcome to the solution architecture document for *The Road Warrior* where we embark on a quest to revolutionize the way travelers manage their trips.

In response to the dynamic needs for millions of users and the relentless pace of the travel industry, we envision a next-generation online trip management dashboard, a unified platform to effortlessly organize and access **Airline**, **Car Rental**, and **Hotel reservations**, whether it's from the comfort of their web browser or mobile device.

The challenge before us is immense, with a user volume that demands peak performance, from real-time travel updates to intuitive reservation management, social sharing capabilities, in-depth analytical insights, seamless integration with existing travel systems, and maintaining high availability and performance.

## Vision

### Requirements
- [Link to Requirements](https://docs.google.com/document/d/1oqQZ03vWqVhqmomslqfp_W929GJDIGQ0cagaT6H0Oxw/edit?usp=sharing)

### Goals

- **Enhanced User Experience**: Provide travelers with an unparalleled user experience, simplifying the complexities of travel management, making it intuitive and insightful.
  
- **Scalable User Base**: Aim to accommodate a user base of 15 million and beyond, ensuring the platform remains accessible and responsive to the needs of every traveler.
  
- **Poll User Emails**: Poll user emails to enrich the trip information data and insights.
  
- **Real-time Updates**: Deliver travel updates with unparalleled speed and accuracy, setting new industry standards. Users should receive updates within five minutes of any change from the integrated travel agencies.
  
- **Comprehensive Trip Management**: Enable users to effortlessly manage their trips.
  
- **Social Sharing**: Empower users to effortlessly share their travel information on social media platforms and within the platform.
  
- **Analytical Insights**: Gather and present analytical data from users' trips, allowing 'Road Warrior' to identify travel trends and preferences.
  
- **Seamless Integration**: Seamlessly integrate with established travel systems like Sabre and Apollo with the flexibility to integrate with additional systems with minimal effort.

- **Internationalization**: We should be able to view the application in different locales and if possible pull in the foreign exchange rates from the base location of the user to his travel destination. Additionally, we can show things to visit in destination based on feeds from trip-advisors and other such aggregation portals.

### Non Functional Requirement

The following NFRs are identified after careful consideration of the business requirement:
 - User Volume: 
    - Support a user base of *2 million* active users per week.
    - Accommodate a total of *15 million* user accounts
 - Availability:
    - Ensure a high level of availability with a target of 99.999%.
 - Data Privacy :
    - Ensure compliance with General Data Protection Regulation (GDPR) requirements.
 - Performance:
    - Achieve an *800ms* or faster response time on web applications.
    - Achieve a first contentful paint time of under *1.4 seconds* on mobile devices.
    - Refresh app content within 5 minutes to provide users with the latest updates.
 - Security:
    - Implement robust security measures, including Access Control Lists (ACLs), to safeguard the system's data and functionality
    
These NFRs cover critical aspects of the solution's architecture, including user scalability, availability, data privacy, performance, and security, and should guide the design and development of the system.

## Setting the Stage

### Actors, Actions, and Scenarios
The following section outlines the important actors, their actions, and the primary scenarios that will guide the architecture of the Road Warrior.

#### Actors and Actions
<table border="1">
  <tr>
    <th>Actor</th>
    <th>Actions</th>
  </tr>
  <tr>
    <td>User / Traveller </td>
    <td>* Registration / Onboarding <br>
        * Updates user profile <br>
        * Manages their trip</td>
  </tr>
  <tr>
    <td>Administrator</td>
    <td>* Manages user access, permissions<br>
        * Manages agencies</td>
  </tr>
  <tr>
    <td>API User</td>
    <td>*View travel insights and trends (based on subscription)</td>
  </tr>
</table>

## Key System Scenarios

The following scenarios, drawn from the actors and actions mentioned earlier, will shape the architecture of Road Warrior.

-  <h3> User Login using email </h3>

![Local Image](uml/Sequence%20Diagrams/user_email_uml.png)

-  <h3> Social Login </h3>

![Local Image](uml/Sequence%20Diagrams/social_email_uml.png)

-  <h3> User initiated expunge (expunge is a process of removing a user from the system) </h3>

![Local Image](uml/Sequence%20Diagrams/expunge_user_uml.png)

-  <h3> Admin initated expunge </h3>

![Local Image](uml/Sequence%20Diagrams/expunge_admin_uml.png)

-  <h3> User Consent Flow </h3>

![Local Image](uml/Sequence%20Diagrams/user_consent_uml.png)

-  <h3> Trends Flow (or travel insights flow) </h3>

![Local Image](uml/Sequence%20Diagrams/trends_uml.png)

-  <h3> Basic Components Interaction </h3>

![Local Image](uml/Sequence%20Diagrams/components_uml.png)


## Architectural Essence

### Architecture Characteristics

Here we have listed the essential traits that define the architecture of this solution which typically should not be more than seven. These, combined with the underlying architectural attributes, will shape the overall design of the Road Warrior.

Using the Architecture Characteristics worksheet, we have identified the following architectural characteristics, and the top 3 marked as [Y]:

<table border="1">
  <tr>
    <th></th>
    <th>Characteristics</th>
    <th>Rationale</th>
  </tr>
  <tr>
    <td>[Y]</td> 
    <td>Interoperability</td>
    <td>System should be able to interface and interact with other systems such as Airline, Hotels, and Car Rentals, etc.</td>
  </tr>
  <tr>
    <td></td>
    <td>Data Consistency</td>
    <td>Data across different platforms are to be streamed and consistent within 5 minutes of changes.</td>
  </tr>
  <tr>
    <td></td>
    <td>Availability</td>
    <td>To ensure users can access the system at all times with no more than 5 minutes of unplanned downtime per month.</td>
  </tr>
  <tr>
    <td>[Y]</td>
    <td>Scalability</td>
    <td>The system should be highly scalable to accommodate the current 2 million active users per week and future expansion.</td>
  </tr>
  <tr>
    <td></td>
    <td>Performance</td>
    <td>Ensures the system handles the high traffic and responds quickly to user requests.</td>
  </tr>
  <tr>
    <td>[Y]</td>
    <td>Integration</td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td>Deployability</td>
    <td>Ensures the Application deployment is smooth, reliable, and frequent.</td>
  </tr>
</table>

## Implicit Characteristics

The following characteristics are like the foundation of our architecture. They play a vital role in shaping the overall architecture.

- Security
- Feasibility
- Usability

## Approach

The key characteristics mentioned above are summarized below. It's important to note that Data Consistency is not currently part of the matrix; however, it will be considered a key characteristic for the Data component.

![Local Image](Architecture%20Diagrams/arch_style_comparison_matrix.png)

[Original comparison matrix from DeveloperToArchitect.com]

Based on the above matrix, the below candidates for our architecture need further analysis:

- Event-Driven
- Microservices
- Service-Oriented

## Architectural Structures

Identifying the different parts of the application and scope of the Architectural characteristics. The approach we have taken are worflow approach and actor-action mapping. An architecture quantum include all the necessary components to function independantly from other parts of the architectures.

### Components
- User Interface
- User Management
- Email Parser
- Trip Management
- Analytics
- Data Transoformation
- Integration    

### System Design

   System Architecture Diagram and Explanation

### Security

   Security and details

### Deployment

This section will discuss the deployment strategy.


## ADRs

This section will contain Architecture Decision Records.

## References
