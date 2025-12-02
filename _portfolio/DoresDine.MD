---
title: "DoresDine App"
excerpt: "An application to improve Vanderbilt Students' dining experience."
header:
  image: /assets/img/7 DoresDine-Banner.jpg
  teaser: /assets/img/7 DoresDine-Banner.jpg
gallery:
  - image_path: assets/img/5 BikeMount-1.JPG
  - image_path: assets/img/5 BikeMount-2.JPG
  - image_path: assets/img/5 BikeMount-3.JPG
  - image_path: assets/img/5 BikeMount-4.JPG
  - image_path: assets/img/5 BikeMount-5.JPG
  - image_path: assets/img/5 BikeMount-6.JPG
  - image_path: assets/img/5 BikeMount-7.JPG
  - image_path: assets/img/5 BikeMount-8.JPG
  - image_path: assets/img/5 BikeMount-8.JPG
  
---

The DoresDine project is a mobile application designed to enhance the Vanderbilt University campus dining experience for students by providing a community-driven platform for real-time meal information.  

The project addresses the challenges Vanderbilt students face with current official dining information system, [NetNutrition](https://netnutrition.cbord.com/nn-prod/vucampusdining). Students rely on NetNutrition for menus and nutritional information, While NetNutrition provides menus and nutritional information, its core issue is one of poor usability and user experience, especially on mobile devices. The system's navigation is confusing for new users, an issue that is important to address as Vanderbilt gets new students as Freshmen or Transfers every year. For example, to view a dining hall's operating hours, a user must click the button indicating if it's "Open/Closed" rather than a dedicated hours section. Furthermore, menu details are buried behind a multitude of nested drop-down menus (e.g., clicking on "Lunch" then clicking into "Pho main" to see specific dishes), which is highly frustrating for students trying to compare options efficiently. 

DoresDine addresses this by creating a secure mobile application focused on streamlined discovery and feedback. The app's scope includes features like searchable menus, dining hall comparisons, and real-time content that is built for ease of use on the go. Crucially, DoresDine tackles the system's other major flaw: the lack of peer-generated feedback. NetNutrition leaves students unsure of what meals will be like, as a dish might sound appealing on paper but be disappointing. DoresDine empowers students to upload photos, ratings, and written reviews to provide current, visual, and qualitative data, helping their peers make more informed dining choices and avoid wasted meal swipes.  

---

# The List of all user stories 

Insert Response Here

---

# Implementation Report

## Description of Implementation Effort
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
Including choice of framework, reason behind that choice etc.
</p>

The development of DoresDine was structured around a modern, modular, and robust technology stack. The primary considerations when selecting this stack were speed of development, cross-platform compatibility, and scalability to handle a growing user base and real-time data flow. For the frontend, React Native with Expo Go was chosen to achieve cross-platform compatibility (iOS and Android) from a single codebase, a crucial decision given the team's limited prior mobile development experience. Expo Go greatly simplified the development and testing process by providing immediate over-the-air updates, minimizing the overhead associated with native build chains, and enabling rapid iteration and client feedback.

The backend infrastructure utilized Node.js (Express), deployed on AWS Elastic Beanstalk, and PostgreSQL running on AWS RDS. Node.js was selected for its asynchronous, non-blocking architecture, which is highly efficient for handling numerous concurrent API requests such as user logins, fetching menus, and submitting reviews. AWS Elastic Beanstalk provided a managed, auto-scaling deployment environment for the API, minimizing the operational complexity of server setup. PostgreSQL was chosen as the database for its reliability and strong relational schema, which is ideal for managing the complex, linked data required for the app (Users, Ratings, Reviews, Dishes). Hosting the database on AWS RDS ensured a scalable, secure, and fully managed database service, eliminating the need for manual database administration. This strategic reliance on managed cloud services was crucial in mitigating deployment risks and allowing the team to successfully establish a robust infrastructure despite the initial learning challenges.

## Roadblocks and Problem Solving 
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
What the roadblocks were and how they were overcame.
</p>

The implementation effort was met with several significant roadblocks, many of which stemmed from the team's initial assessment of risk. The greatest overall challenge was learning a new tech stack and working with unfamiliar technologies such as React Native and the AWS ecosystem. This learning curve directly impacted the timeline for advanced feature development. To overcome this, the team relied heavily on pair programming to quickly disseminate knowledge and troubleshoot complex issues across the new stack. This strategy, combined with rapid prototyping using Expo Go, provided immediate visual feedback and significantly reduced the time spent on environment setup, allowing the team to concentrate on core component logic.

A major area of difficulty was deployment, encompassing both frontend and backend infrastructure. Initially attempting a bare React Native deployment proved overly complex, necessitating a migration to Expo Go. This migration required significant refactoring and rewriting of existing code to align with the Expo environment's constraints and configurations. Concurrently, the backend deployment presented its own complex hurdles: the team had little prior experience with AWS. Configuring the application server using Elastic Beanstalk (EB) and linking it to the managed database in RDS required substantial effort to correctly set up security groups, environment variables, and implement continuous deployment procedures for updates.

A different technical obstacle was reverse engineering the API calls on NetNutrition to obtain the required dining data. Since Vanderbilt's NetNutrition is an external system with no public API documentation, the team resorted to using the browser's Network tab to meticulously monitor the API calls being made when performing actions like clicking buttons or loading menus on the original site. The team then took these intercepted calls and integrated them into the DoresDine backend. This process was complicated by external factors, as the original site sometimes experienced network errors and downtimes, which further hampered the ability to reliably scrape data and caused inconsistencies in the acquired menu information. This complex reverse-engineering effort was overcome through sustained, collaborative debugging and the construction of a dedicated web-scraping service to formalize the data ingestion process.

## Progress of the Implementation 
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
Is the implementation complete? If not, how much work is left? 
</p>

The implementation of DoresDine is not fully complete when measured against the total set of requirements outlined in the Requirements Analysis document, particularly concerning the advanced features in the Chatbot & Search and Notification & Alerts categories.

The full implementation of the chatbot is missing. While the user-facing search functionality was successfully prioritized and built, the underlying AI integration required for the chatbot to process natural language queries (e.g., "What gluten-free items are available today?") was not completed. This requires significant work in integrating a natural language processing (NLP) model or service, training it on dining data, and building the conversational flow logic. This was consciously deferred due to the steep learning curve and time demands of working with AI/ML concepts.

The feature to provide real-time busyness indicators for dining halls is currently missing. Implementing this would require setting up API calls to Vanderbilt Campus Dining Wait Times, separate from the menu data, to infer or collect data on dining hall occupancy. This complex scraping effort was not initiated due to the need to prioritize the core content and review features, meaning a substantial amount of work is still required to design, implement, and validate this specific web scraping pipeline and display the data on the mobile app's front end.

---

# Picutre of Success 
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
Evaluating the final status of the project against the suggested deliverable from our requirement analysis document. 
</p>

## Criteria from Requirement Analysis 

The final deliverable for the DoresDine project, as defined by the Requirements Analysis (RA) document and corresponding project plan, is a fully functional and secure mobile application accessible for client use and testing through Expo. The team’s primary objective was to complete all principal activities and milestones outlined by the user stories.

The success of this deliverable is measured by how well it satisfies the functional and non-functional criteria defined in the project scope. Functionally, the application was required to provide a mobile-first experience with secure Vanderbilt login integration and meet the user stories relating to these 5 categories: Meal Discovery, Ratings and Reviews, Chatbot and Search, Notifications and Alerts, and Community and Moderation.  All features were to be implemented using the React Native, Node/Express, PostgreSQL, and Firebase stack and undergo full system testing and debugging as outlined in the project plan.

## Criteria Met or Missing

The final status of the DoresDine project shows that the team successfully met a substantial portion of the criteria in the RA document. A secure, functional mobile application was delivered, fulfilling the core mission across the user story categories. The app enables students to browse menus, search for dishes, compare dining halls, and contribute ratings, reviews, and photos while also supporting content moderation through upvoting and flagging.

However, the project did not fully satisfy the requirements for the Chatbot & Search features and the Notification & Alerts system. This limitation stemmed primarily from two factors: the team’s initial learning curve with mobile development (including managing state, handling API calls, and deployment) and specific technical barriers related to data integration. The difficulty with implementing the fully functional Chatbot arose from the complexity of learning AI integration, which was deemed too time-intensive and outside the scope achievable within the project timeline. The team, instead, successfully emphasized the search functions, allowing the user to search for a variety of items, including dining halls and dishes. 

The more critical technical barrier, though, was the structure of the NetNutrition data source that restricted the Notification & Alerts system. NetNutrition lists meals as individual ingredients (e.g., “lettuce,” “carrots”) rather than aggregated dishes (e.g., “salad”). This fundamental mismatch made it impossible to reliably match a user-favorited “dish” with what NetNutrition reports is being served on a given day, preventing the implementation of real-time meal-specific alerts.

---

# Changes that Occured Over the Course of the Semester

## Changes in Requirements 

Over the course of the semester, both the requirements and the solution design for DoresDine underwent necessary changes driven by practical constraints and deeper insights gained during development. The most significant shift was in prioritizing and adjusting user stories. The team was forced to be flexible with the features planned, as the initial timeline did not sufficiently account for the steep learning curves associated with the new tech stack (React Native and AWS), nor for external factors like schedule conflicts and sickness. This led to the conscious de-scoping of complex features, such as the full AI integration for the Chatbot and the advanced real-time meal-specific alerts. This flexibility allowed the team to successfully deliver the core value proposition (ratings, reviews, and search) while deferring high-risk, time-consuming requirements.

## Changes in Solution Design 

In terms of solution design, as features were implemented, the team realized the initial user stories did not fully encompass the complexity of the final mobile application structure. The design evolved to be more detailed, often requiring the creation of new logical entities and screens to support existing functionality. For example, to properly display and manage aggregated peer feedback, the team realized they needed to create a dedicated "profile" page for each dining hall. This page consolidated ratings, reviews, and detailed dish information in a centralized, easily navigable location, mirroring the structure of a user profile. This iterative design process ensured the final app was robust and intuitive, even if it meant the final screen count and internal complexity exceeded the initial requirement analysis.

---

# What was well done 

## 3 Challenges that were Addressed Successfully 
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
Describing at least 3 challenges that came up that the team was able to address successfully. Describe the challenge and actions/steps taken to overcome them.  
</p>

Our first major challenge involved managing collaborative access to the AWS database. We struggled to configure permissions that would allow all team members to work directly with the database, which created a bottleneck in our development workflow. To address this, we delegated most backend changes to Sonya, who owned the database instance. When other team members needed to make backend modifications, they would implement their changes and then pass them to Sonya for debugging and deployment. While this approach allowed us to continue making progress, it highlighted the importance of properly configuring shared development environments and implementing better access management strategies from the project's outset. 

The second significant challenge stemmed from our team's lack of mobile deployment experience. Having primarily worked with web deployment in previous projects, we found the process of deploying a React Native mobile application considerably more complex than anticipated. Issues ranged from platform-specific build configurations to managing dependencies and handling different testing environments for iOS and Android. We relied heavily on TA and professor office hours to troubleshoot deployment issues and learn best practices for mobile app distribution. This experience underscored the value of seeking expert guidance when venturing into unfamiliar technical territory and the importance of allocating adequate time for deployment activities in project planning. 

Our third challenge was a process-related issue: we neglected comprehensive testing for a substantial portion of the development cycle. Focused on implementing features and resolving deployment issues, we failed to maintain adequate test coverage alongside our code development. Upon recognizing this gap, we dedicated an entire work day to addressing ignored tests and achieving sufficient coverage. This experience reinforced the importance of integrating testing into our regular development workflow rather than treating it as an afterthought, and demonstrated the value of continuous integration practices that could have caught this issue earlier. 

---

# Areas of Improvement 

## 2 Problems that Arose due to Mistakes
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
Describing at least 2 problems that came up because of mistakes made. Analyze what went wrong, and how the problem can be avoided in the future
</p>

While the team successfully delivered a core functional application, two major mistakes in planning and scoping hindered the project’s full completion and caused unnecessary turbulence during the implementation phase. 

The initial requirements analysis included highly complex features like full AI integration for the Chatbot (requiring Natural Language Processing capabilities) and the implementation of a comprehensive, real-time Notification and Alerts system (including busyness indicators and meal-specific notifications). These features required knowledge and external integrations that were far more complex than the team's familiarity with the core tech stack. This scope was too aggressive for a semester-long project executed by a team primarily engaged in mastering a new technology stack (React Native and AWS). 

The team failed to adequately factor in the time cost of the learning curve (especially for React Native, AWS configuration, and external API reverse-engineering) when setting the scope for advanced features. We mistakenly assumed that once the core framework was set up, the complex features would integrate quickly. This led to a significant portion of the final sprint being spent playing catch-up, resulting in the necessary de-scoping of key features like the Chatbot AI.   

We should have employed stricter risk-based prioritization during the requirements phase. Instead of planning complex features, we should have defined "Minimum Viable Product (MVP)" versions for each requirement. For the chatbot, the MVP should have been defined as the static search functionality we ultimately implemented, with AI integration listed as a stretch goal for a second phase. This approach would have ensured a complete, functional product that met core requirements on time. 

Although user stories were created, another issue that was faced is the team did not map out enough of the exact technical implementation details and dependencies in the initial planning phase. This lack of detailed technical documentation meant that as we added features, we constantly discovered necessary intermediate components that were not in the original plan. For instance, the need to create a dedicated "Dining Hall Profile" page to consolidate ratings and reviews for a single location was not initially mapped out; we only recognized its necessity when attempting to integrate the rating display into the UI. 

This was a failure in the pre-development design step. By focusing only on the high-level user stories, we missed critical intermediary steps and logical entities required for the final solution. This resulted in constant mid-sprint feature expansion and code refactoring as we retroactively created the necessary design components (like the Dining Hall Profile) to support existing functionality. 

To avoid this, we should have enforced a small, early phase dedicated to more detailed wireframing and entity-relationship diagramming (ERD) before writing any code. By sketching out the necessary screens and identifying all major database entities (Users, Dishes, Reviews, and Dining Hall Profiles), we could have accounted for all major components and prevented unexpected scope creep on the solution design side. 

---

# Software Engineering Lessons Learned 
<p style="font-size: 1.1em; color: #666; margin-top: -0.8em; font-style: italic;">
Any other lessons learned. Software engineering lessons learned illustrated by your particular project. 
</p>

Beyond the structural and planning mistakes, the DoresDine project provided several important lessons in software engineering practice, project management methodologies, and mobile usability. Many of the ideas presented in lectures and readings directly contributed to the team’s progress. In particular, the steep technical learning curve made it essential to adopt and consistently apply principles from Extreme Programming (XP). Formalizing pair programming helped rapidly disseminate knowledge about new and complex technologies—such as React Native’s component model, mobile navigation patterns, and AWS deployment configurations. Combined with collective code ownership, this approach allowed the team to reassign tasks fluidly and prevented individual members from becoming bottlenecks, which was especially important given frequent external schedule conflicts. 

This collaborative structure proved critical for navigating a semester-long project while balancing coursework, travel, and personal commitments. We learned quickly that proactive, asynchronous communication was our strongest risk mitigation strategy. Establishing clear channels (such as a dedicated group message) allowed team members to immediately signal when they were blocked, needed help, or had to shift priorities due to outside obligations. This transparency ensured that individual delays rarely cascaded into broader project setbacks.  

The ongoing pressure to reprioritize also reinforced the importance of the YAGNI (You Ain’t Gonna Need It) design principle. When time was constrained, YAGNI encouraged us to de-scope complex, high-risk features like the AI Chatbot. Although initially appealing, we realized the well-built search function already met user needs without requiring the time-intensive effort of AI integration.  

Finally, working with a mobile application introduced unique challenges in User Experience (UX) and User Interface (UI) design. We learned to optimize interactions for touch rather than mouse input, ensuring appropriate target sizes, padding, and spacing. We also recognized that the smaller screen made information hierarchy far more important; avoiding overly nested menus and excessive scrolling became essential to achieving the streamlined experience we set out to create. 

___


# How to View DoresDine

<iframe width="560" height="315"
src="https://www.youtube.com/embed/p2g1acEJ3hk"
title="YouTube video player" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
allowfullscreen>
</iframe>

---

# Features

* **Generative Lightweight Structural Geometry:** The final hanger integrates both the traditional hanger body and motor mount into a single consolidated component. The generative design engine minimized mass while maintaining stiffness sufficient to support rider weight, resist motor torque, and withstand the forces transmitted through the kingpin and axle.
* **Integrated Adjustable Motor Mounting System:** The preserved regions include slotted motor-mounting holes enabling ±4 mm of belt tension adjustment. Geometry around the motor region automatically forms efficient load paths, ensuring the motor plate remains rigid under acceleration while avoiding print-region violations of the Fuse 1 SLS build volume.
* **Optimized for Dual Materials: Nylon 12 & ALSi10Mg:** Two independent generative design studies were run. One on Nylon 12 and one on ALSi10Mg. Comparing both solutions informed how material stiffness influences topology, mass distribution, and manufacturability.

---

# 3D Printed Parts

| 3D Printed Part | Purpose / Function |
|------------------|--------------------|
| Generative-Designed Truck Hanger (Nylon 12) | Lightweight structural test part for evaluating compliance, geometry, and assembly fit |
| Generative-Designed Truck Hanger (ALSi10Mg) | Final metal component used for physical longboard assembly testing and load-bearing evaluation |

---

{% include gallery caption="Multi Material Pliers Gallery" %}
