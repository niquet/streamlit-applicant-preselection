# Applicant Preselection (Shortlisting)
- Goal: Screening and identifying suitable candidates from large applicant pool [1]
- Problem #1: A lot of time is wasted as recruiters need to go through large amount of CVs and select the right ones [1]
- Problem #2: A lot of time is wasted interviewing the wrong candidates [1]
- Problem #3: Risk that a good candidate is missed [1]
- 

## Table of Contents
1. [Overview]()
2. [Motivation]()
3. [Success Metrics]()
4. [Requirements & Constraints]()
5. [Motivation]()
6. [Implementation]()
7. [Appendix]()

## 1. Overview
A summary of the doc's purpose, problem, solution, and desired outcome (3-5 sentences).

## 2. Motivation
- Why should we solve this problem?
- Why should we solve this problem now?
- Explain the motivation for your proposal and convince readers of its importance
- What is the customer or business benefit?
- If there are alternatives, explain why your proposed system is better.

## 3. Success Metrics
- What are the success criteria?
- Often framed as business goals, such as increased customer engagement, revenue, or reduced cost
- Can also be framed as operational goals or new capabilities (e.g., ability to rollback models, serve features in real-time, etc.)

## 4. Requirements & Constraints
- What are the requirements and constraints?
- Functional requirements are those that must be met to deliver the project
- Describe them from the customer’s point of view—how will the customer experience it and/or benefit?
- Specific to machine learning, we’ll have specific requirements for each application, such as:
  - Recommendations: Proportion of items or customers with >5 recommended items
  - Fraud detection: Upper bound on the proportion or count of false positives
  - Automated classification: Threshold on proportion or count of low-confidence predictions that require human review and approval
- Non-functional/technical requirements define the quality of your system and determine how the system should be implemented
- Usually, customers won’t notice them unless they’re not met (e.g., exceptionally high latency)
- Most systems will consider a similar set of requirements such as throughput, latency, security, data privacy, costs, etc.

### 4.1 What's in-scope & out-of-scope?
- What is in-scope vs out-of-scope?
- Be upfront about what’s out of scope
- Be deliberate about and have a plan to pay off tech debt as soon as possible

### 4.2 What are the assumptions?
- What are our assumptions?
- Make explicit your assumptions and understanding of the environment
- If building a recsys:
  - How many products and users do you have?
  - What is the expected number of requests per second?
- This guides how you frame the problem
- It can be hard to apply reinforcement learning to large discrete action spaces (i.e., a large number of products)
- Whereas simple approximate nearest neighbors scale well

## 5. Methodology

### 5.1. Problem Statement

How will you frame the problem? For example, fraud detection can be framed as an unsupervised (outlier detection, graph cluster) or supervised problem (e.g., classification).

### 5.2. Data

What data will you use to train your model? What input data is needed during serving?

### 5.3. Techniques

What machine learning techniques will you use? How will you clean and prepare the data (e.g., excluding outliers) and create features?

### 5.4. Experimentation & Validation

How will you validate your approach offline? What offline evaluation metrics will you use?

If you're A/B testing, how will you assign treatment and control (e.g., customer vs. session-based) and what metrics will you measure? What are the success and [guardrail](https://medium.com/airbnb-engineering/designing-experimentation-guardrails-ed6a976ec669) metrics?

### 5.5. Human-in-the-loop

How will you incorporate human intervention into your ML system (e.g., product/customer exclusion lists)?

## 6. Implementation

### 6.1. High-level Design

![](https://upload.wikimedia.org/wikipedia/commons/thumb/2/2e/Data-flow-diagram-example.svg/1280px-Data-flow-diagram-example.svg.png)

Start by providing a big-picture view. [System-context diagrams](https://en.wikipedia.org/wiki/System_context_diagram) and [data-flow diagrams](https://en.wikipedia.org/wiki/Data-flow_diagram) work well.

### 6.2. Infra

How will you host your system? On-premise, cloud, or hybrid? This will define the rest of this section

### 6.3. Performance (Throughput, Latency)

How will your system meet the throughput and latency requirements? Will it scale vertically or horizontally?

### 6.4. Security

How will your system/application authenticate users and incoming requests? If it's publicly accessible, will it be behind a firewall?

### 6.5. Data Privacy

How will you ensure the privacy of customer data? Will your system be compliant with data retention and deletion policies (e.g., [GDPR](https://gdpr.eu/what-is-gdpr/))?

### 6.6. Monitoring & Alarms

How will you log events in your system? What metrics will you monitor and how? Will you have alarms if a metric breaches a threshold or something else goes wrong?

### 6.7. Cost
How much will it cost to build and operate your system? Share estimated monthly costs (e.g., EC2 instances, Lambda, etc.)

### 6.8. Integration Points

How will your system integrate with upstream data and downstream users?

### 6.9. Risks & Uncertainties

Risks are the known unknowns; uncertainties are the unknown unknows. What worries you and you would like others to review?

## 7. Appendix

### 7.1. Alternatives

What alternatives did you consider and exclude? List pros and cons of each alternative and the rationale for your decision.

### 7.2. Experiment Results

Share any results of offline experiments that you conducted.

### 7.3. Performance Benchmarks

Share any performance benchmarks you ran (e.g., throughput vs. latency vs. instance size/count).

### 7.4. Milestones & Timeline

What are the key milestones for this system and the estimated timeline?

### 7.5. Glossary

Define and link to business or technical terms.

### 7.6. References

[1] Victor Robin. "Intelligent recruitment using NLP and ML to identify most suitable candidates by Victor Robin," PyData Delhi, 17 Oct 2019. [Online]. Available: https://www.youtube.com/watch?v=KYogyvGiyHQ. [Accessed: 28 Jun 2023].

---

### Other templates, examples, etc
- [A Software Design Doc](https://www.industrialempathy.com/posts/design-doc-a-design-doc/) `Google`
- [Design Docs at Google](https://www.industrialempathy.com/posts/design-docs-at-google/) `Google`
- [Product Spec of Emoji Reactions on Twitter Messages](https://docs.google.com/document/d/1sUX-sm5qZ474PCQQUpvdi3lvvmWPluqHOyfXz3xKL2M/edit#heading=h.554u12gw2xpd) `Twitter`
- [Design Docs, Markdown, and Git](https://caitiem.com/2020/03/29/design-docs-markdown-and-git/) `Microsoft`
- [Technical Decision-Making and Alignment in a Remote Culture](https://multithreaded.stitchfix.com/blog/2020/12/07/remote-decision-making/) `Stitchfix`
- [Design Documents for Chromium](https://www.chromium.org/developers/design-documents) `Chromium`
- [PRD Template](https://works.hashicorp.com/articles/prd-template) and [RFC Template](https://works.hashicorp.com/articles/rfc-template) (example RFC: [Manager Charter](https://works.hashicorp.com/articles/manager-charter)) `HashiCorp`
- [Pitch for To-Do Groups and Group Notifications](https://basecamp.com/shapeup/1.5-chapter-06#examples) `Basecamp`
- [The Anatomy of a 6-pager](https://writingcooperative.com/the-anatomy-of-an-amazon-6-pager-fc79f31a41c9) and an [example](https://docs.google.com/document/d/1LPh1LWx1z67YFo67DENYUGBaoKk39dtX7rWAeQHXzhg/edit) `Amazon`
- [Writing for Distributed Teams](http://veekaybee.github.io/2021/07/17/p2s/), [How P2 Changed Automattic](https://ma.tt/2009/05/how-p2-changed-automattic/) `Automattic`
- [Writing Technical Design Docs](https://medium.com/machine-words/writing-technical-design-docs-71f446e42f2e), [Writing Technical Design Docs, Revisited](https://medium.com/machine-words/writing-technical-design-docs-revisited-850d36570ec) `AWS`
- [How to write a good software design doc](https://www.freecodecamp.org/news/how-to-write-a-good-software-design-document-66fcf019569c/) `Plaid`
