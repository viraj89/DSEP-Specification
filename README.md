
# Decentralized Skilling and Education Protocol
This project provides open interoperable specifcations for creating decentralized skills and education networks. It is an adaptation of beckn protocol core specification with added taxonomies and sample network policies for the skills and education sector.

## Current Working Draft Branch: 
draft

## Versioning Scheme
[Semantic Version Scheme 2.0.0](https://semver.org/)

## Core specification version

| DSEP Specification Version       | Beckn Protocol Core Specification Version         |
|----------------------------------|---------------------------------------------------|
| 0.5.0 (Genesis Version)          | 0.9.3-draft                                       |
| 0.5.1-draft (Patch version)      | -                                     |
| 0.6.0-draft (Next Minor Version) | 1.1.0-draft                                                 |
| 0.7.0-draft (Next Major Version) | 1.1.0-draft                                                 |
| 0.8.0-draft (Next Major Version) | -                                                 |

## Introduction

The community is currently working on Discovery of Jobs, Training, mentors and courses etc. The skill development, lifelong learning and employment landscape is large, heterogeneous, diversified,  fragmented and complex; which is high on friction and low on outcomes. It inherently has significant challenges such as information asymmetry, high cost of trust verification, lack of discoverability, and portability. A monolithic approach to this would not serve the purpose, rather we need to adopt an ecosystem approach which facilitates innovative solutions.

Hence the need of the hour is a unifying framework which will allow many platforms, applications, service providers, and business models to innovate with the underlying protocols and specifications using a set of configurable, extendable, modular open-source digital building blocks. In such a paradigm, the seamless discovery of opportunities along with trust in transactions would be a key to allowing a frictionless exchange for skill development, deployment & associated supply-chain and enabling services. 

To enable this ‘trusted discovery’, a group of people from different organisations are collaborating and co-creating solutions, open-source specs & software, and much more to drive this whole initiative forward. The members meet regularly every week in community calls to discuss use-cases, draft specifications, implement prototypes, and create innovative solutions. The community is thriving with active participation from members on weekly calls and on chat/discussion forums.

The community is organised into two sub-groups (most members are common across both groups). 
1. DSEP, which stands for Decentralised Skilling and Education Protocol, will enable the Discovery of content, courses, training, jobs, mentors, scholarships, and more through discovery protocol. 
2. INCOMS, which stands for Interoperable Credential Object Model Specifications for use in Skilling, Work, and Education domains, will enable Proof of Training, Work, Skill, Reputation, and more through verifiable credentials.

Next steps:
- Join the community by [filling up this form](https://docs.google.com/forms/d/e/1FAIpQLSexE0GdpRoSSF0DA-SDz0wl4NHrfXHXJ1mzKkSXQYyhhCbe8g/viewform?usp=sf_link)
- Participate in Working Group Weekly Calls
- Check out these public GitHub repositories for learning more and engaging with the community: github.com/beckn/DSEP-Specification/discussions and github.com/INCOMS/vc-specs/discussions 
- Join the Discord channel of both the communities: INCOMS (Sunbird discord.gg/muHqfEkvSy) and DSEP (Beckn discord.gg/pcNc4aFn2x)

You’re invited to Engage with the ecosystem to identify what can be leveraged/contributed, Experiment with the specs for your use cases, and Evolve the same into live implementation for your customers.

## Working Group Members

| Name             | Role                           | Github Username |
|------------------|--------------------------------|-----------------|
| Ravi Prakash     | Maintainer, Protocol Architect | @ravi-prakash-v |
| Pramod Varma     | Maintainer, Reviewer           | @pramodkvarma   |
| Sujith Nair      | Reviewer                       | @sjthnrk        |
| Mayank Bansal    | Maintainer                     | @emmayank       |
| Viraj Kulkarni    | Maintainer                     | @viraj89       |

## Acknowledgements

The author(s) of this specification would like to thank the following volunteers for their contribution to the development of this specification

### Version 0.7.0
- Ravi Prakash
- Pramod Varma
- Surendrasingh Sucharia
- Faiz Mohammed
- Sanjay


## Implementing the specification

To understanding how to implement the specification click [here](./docs)

## Learn about the Use Cases
Learn about their logical flows, user experience designs using Figma, and explore example JSONs for better understanding. 

### Use Case - Courses
- The user begins by logging into the app with the goal of finding courses to enhance their skills. They proceed to search for specific courses, such as "Data Analyst," by typing in the keywords and clicking the search button. The app then displays search results based on the matched keywords.

- Within the search results, the user can view key details about each course, including the course title, duration, seller information, price, and ratings. The user then selects a desired course to pursue, leading them to the course description page, where they find more comprehensive information about the course. This page includes details such as the course description, highlights, duration, price, prerequisites, eligibility criteria, and an option to add the course to the cart.

- Upon deciding to proceed, the user navigates to the cart page for checkout. At this point, they notice an option to apply for a scholarship. Opting to explore scholarship opportunities, the user selects the "Check for Scholarship" option and searches for available scholarships. <br/>

[Read about Courses](./docs/4_Courses.md) <br/>

### Use Case - Scholarship
- The user discovers a few scholarships and, after selecting one, is presented with detailed information about the scholarship, including its description, application start and end dates, eligibility criteria, required documents, and an option to apply. Choosing to apply, the user is directed to a form, which they fill out, upload the necessary documents, and submit the application.

- To track the status of the scholarship application, the user can visit the scholarship page at a later time. Once the scholarship provider approves the application, the user is directed back to the cart page. Here, the sub-total amount is displayed as zero, indicating that the user has successfully availed of the scholarship.

- With the scholarship secured, the user proceeds to checkout and completes the necessary transaction. In this way, the user successfully identifies courses of interest, searches for and applies for scholarships, and finally enhances their skill set. <br/>

[Read about Scholarships](./docs/5_Scholarships.md) <br/>

### Use Case - Jobs
- The user starts by logging into the app with the intention of finding and applying for a job. They initiate a search, for instance, using the keywords "data analyst" in the search box, resulting in a list of jobs that match the specified criteria.

- Within the job search results, the user can see key details such as the job location and the name of the hiring company for each job listing. The user selects a specific job to view more details, including the job description, requirements, necessary qualifications, and whether the position is full-time or part-time. Additionally, there is an option to apply for the selected job.

- Opting to apply, the user selects the "Apply Now" option, leading them to a form that captures basic user details like name, mobile number, and email ID. The form also provides an option to upload requested documents, such as the user's resume and degree certificates. After completing the form, the user selects "Apply Now" to submit their application.

- Once submitted, the user's application is sent to the respective company. If there is a match between the user's profile and the company's requirements, the company will directly connect with the user.

- The user has the flexibility to search for and apply to multiple jobs simultaneously. After submitting a job application, the user receives an appropriate message, confirming the successful submission of their application. This process allows the user to efficiently explore and apply for multiple job opportunities within the app. <br/>

[Read about Jobs](./docs/6_Jobs.md) <br/>

## Specification Examples

The Specification examples for each sub-domains are given in a detailed format. you can find them as follows:
1. [Courses](./examples/courses)
2. [Expert Connect](./examples/expert-connect)
3. [Financial Support](./examples/financial-support)
4. [Jobs](./examples/work-opportunities)

## Test it yourself
Import the postman collection containing all these requests [via](link-to-be-updated)

OR

[![Run in Postman](https://run.pstmn.io/button.svg)](link to be updated)

## Demo Link
Here is the Demo Link for the BAP implemented for course, jobs and financial support domains, [click here](https://dsep-dev.becknprotocol.io/)

