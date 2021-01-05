# Youtube Links - <https://www.youtube.com/watch?v=2C2F5USR6N4&list=PLbRoZ5Rrl5lfLXUjFjS0mP1XzNzNZMhYN>

## Identifying Hidden Dependencies

<https://www.youtube.com/watch?v=aY_k9DwxIkU>

Velocity & Reliability

- Quantify Reliability
- Identify areas of risk
- Design experiments to probe risk
- What is too broken?
- Everyone understands SLOs
  
---

## Are We Getting Better Yet?

<https://www.usenix.org/sites/default/files/conference/protected-files/srecon20americas_slides_elman.pdf>

Prioritize a learn and adapt safety mode over a prevent and fix safety mode

- Action items form a defensive strategy but do not lead to learning

Preparation

- Emphasizes a more accurate and complete understanding
- Barriers and guardrails are used to prevent people from repeating mistakes
- Automation an opportunity to enhance or enable humans

Reporting reliability

- Reliability outcomes and human performance are monitored and influenced
- Incidents are a source of insights but not a good measure of reliability
  
Mistakes are a feature not a bug
Reliability - Historically good performance
Robustness - Retains good performance within a threshold when challenged
Brittleness - Predictably poor performance when challenged

Assessing accountability

- People who make mistakes feel supported which inspires them to seek opportunities.
- Attribution is important to learning but can also lead to blame

Incident analysis

- Incidents are investments in more capable organizations

Incident write-ups

- Incident write-ups faithfully present multiple perspectives
- "Our system has been very reliable over the past few quarters. Why?"

<https://www.learningfromincidents.io/>

---

## Observing from Incidents

<https://www.usenix.org/sites/default/files/conference/protected-files/srecon20americas_slides_watson.pdf>

### “Perhaps a better way is to make memory unnecessary: put the required information into the world"

Dashboards;
Looking for Surprise, Confusion, Dead Ends, Edge Cases, Inefficiency

Incidents can inform how tools can be improved

---

## Study on Human Factors and Team Culture to Improve Pager Fatigue

<https://www.usenix.org/sites/default/files/conference/protected-files/srecon20americas_slides_barteneva.pdf>

Becoming an agent of change

- Write troubleshooting guides
- Build feedback loops
- Communicate
- Empathy
- Build trust
- Praise successes
- Find/Become a mentor

---

## Revisiting "Automate All The Things"

<https://www.usenix.org/sites/default/files/conference/protected-files/srecon20americas_slides_reed.pdf>

How to drift into failure

- Long running system with legacy requirement
- Eras of modification
- Addition of supplemental features to address changes and maintain system abstractions
- Disparate, disconnected requirements gathering
- Siloed testing and validation
- Early, weak stress signals missed or ignored

<https://medium.com/@jpaulreed/the-737max-and-why-software-engineers-should-pay-attention-a041290994bd>

- Automatic systems should fail obviously.
- Tracing the decision trees made by algorithms can be difficult (or today, impossible).
- This leads to the inability to fully understand the current context of the system when you are paged.

---

## Low Context DevOps: Improving SRE Team Culture through Defaults, Documentation, and Discipline

<https://www.usenix.org/sites/default/files/conference/protected-files/srecon20americas_slides_limoncelli.pdf>

High Conext

- Communication is implicit
- Reading between the lines is essential
- Long Term Relationships
- Central authority

Low Context

- Explicit communication
- You are told the rules
- Codified, public, and accessible knowledge
- Knowledge is transferable

### How to make your environment low context

- Carefully constructed defaults
- New Employee  onboarding time minimized
- Make right easy
- The lazy path guides you to the right way
  
### Ubiquitous Documentation

- Set expectations
- Treat doc bugs same as software
- Culture of updating as you work
- Doc is NOT documentation

Write in small batches & Include doc time in work estimates

---

## Cloudy with a Chance of Chaos

<https://www.usenix.org/sites/default/files/conference/protected-files/srecon20americas_slides_yakomin.pdf>

Why is Chaos Engineering Valuable?

- Infrastructure Fails all the time
- Validate automated resilience mechanisms
- Training incident responders and engineers

Build vs Buy

- Build creates Easy adoption, and well defined guardrails
- Integrated reporting is another benefit
- Better documentation

---

## Pragmatic Security For SRE  

<https://www.usenix.org/sites/default/files/conference/protected-files/srecon20americas_slides_wickett.pdf> (This was my favorite talk)

Security is covering the wrong things, and it's hurting productivity at the same time

Security is NOT inhibiting change

Think "Shift Left"

Mature DevOps practices show a 350% increase in likelihood of integrating automated security

<https://learning.oreilly.com/library/view/building-secure-and/9781492083115/>

Security Considerations:

- Threat Modeling
- Security Stories
- Authentication to Push
- Dev Standards
- Peer Review
- Static Code Analysis
- Unit Tests for Security

### 4 Steps to Security Chaos Engineering

1. Define expected behavior of a security defense
2. Hypothesize that when security turbulence is introduced it will be either prevented, remediated, or detected.
3. Introduce a variable that introduces security turbulence.  
4. Try to disprove the hypothesis by looking for a difference in expected behavior and actual behavior

---

## Failure is Not an Option! SRE Lessons 50 Years after the Apollo 13 Flight to the Moon

<https://www.usenix.org/sites/default/files/conference/protected-files/srecon20americas_slides_barron.pdf>

- Train for failures, and responses to failure
- Build/code for failure
- Failure has many shapes and forms
- Self healing deflects failure
- Avoid failure through robustness & resilience
- Failure isn't an option, deal with the problems, have a plan
- Tools fail, validate your assumptions
- Avoid future failure by reducing technical debt
- Don't rely on improvisation, plan ahead

---

## 3 learning of an SRE

<https://www.usenix.org/sites/default/files/conference/protected-files/srecon20americas_slides_charagondla.pdf>

Proactive > Reactive

Proactive - Focus on building tools to minimize impact, or prevent outages

- Chaos Engieering
- Gamedays

---

## Automatically Detect the Top Performance & Scalability Issues in Distributed Architectures

<https://www.usenix.org/sites/default/files/conference/protected-files/srecon20americas_slides_grabner.pdf>

When you move to a more distributed architecture, your dependencies  grow, and the potential impact of a failure grows along in kind

In distributed architectures, it needs to be decided who is depending on me? What is the risk of this change?

Common patterns:
N + 1 Call - 1 Initial call + 1 call per N results
N + 1 Query - Same as above, but focus on DB queries
Payload flood - Sending useless info across the network
Inefficient Service Flow - Think web performance optimization

If it can be detected on a dashboard, it can be automated!

---

## Achieving Mutual TLS: Secure Pod-to-Pod Communication Without the Hassle

<https://www.usenix.org/sites/default/files/conference/protected-files/srecon20americas_slides_hahn.pdf>

<https://gitlab.com/gauntletwizard_net/kubetls>

Every Kubernetes pod should include an SSL cert, to verify its identity
Manual creation is a headache

KubeTLS has a built-in CA
Kubernetes should create TLS certs for all pods/services/deployments
Kuberbetes has a webhook interface for verifying objects - <https://kubernetes.io/docs/reference/access-authn-authz/extensible-admission-controllers/>
Kube TLS implements a webhook looking for pod creations
Any creation request are modified to include a TLS secret with the cert and key

---

## It's a Trap! How our Abstractions are failing us

<https://www.usenix.org/sites/default/files/conference/protected-files/srecon20americas_slides_henry.pdf>

Abstraction - a technique for arranging complexity of a computer system. It works by establishing a level of complexity on which a person interacts with the system and suppresses the complex details below that level

Abstraction is a positive, but we lose proficiency with the foundation when that happens, it's important to not forget the people who abstraction is supposed to help (users)

There needs to be a point at which we stop abstracting for the sake of abstraction

---

## Additional Links

<https://www.learningfromincidents.io/blog/incident-analysis-and-chaos-engineering>
<https://copyconstruct.medium.com/monitoring-and-observability-8417d1952e1c>
<https://principlesofchaos.org/>
<https://www.bundesbrandschatzamt.de/~baron/blog/20150602-Literate_DevOps.html>
<https://vimeo.com/369638117> - Cory Watson - How Dashboards work and how to improve them
<https://medium.com/doing-devops/your-user-hates-your-code-1a03613afeff>
<https://thenextweb.com/shareables/2015/11/25/this-man-is-a-genius/>
<https://www.youtube.com/watch?v=C11LNUEaHuo> - Netflix Precision Chaos
<https://www.youtube.com/watch?v=CZ3wIuvmHeM> - Mastering Chaos
<https://queue.acm.org/detail.cfm?id=3197520>
