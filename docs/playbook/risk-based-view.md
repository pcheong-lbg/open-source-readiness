---
title: Risk-Based View
---

Organisational change can be very hard to achieve since organisations are naturally protective of themselves and the status quo.  Setting up an OSPO and beginning an open source journey will seem like a risky and dangerous proposition for many parts of an organisation.  

If you want to change an organisation you will need to convince people that what you are presenting:

 - Considers the risks and benefits to _all stakeholders / departments_
 - Provides an approach to mitigating the risks
 - Presents a _preferable risk profile_ to the status quo

## The Benefits

1.  Steering The Technology

 - Banks are first and foremost technology companies.  Before "Big Tech" came along, they were the largest technology companies.
 - There are examples of open source tools (e.g. Prometheus) that are widely used but not optimised for the finance industry.  Therefore, having engineers working on improving these tools to work better for finance makes a lot more sense than going down the route of using vendor solutions that you have little control over.

2.  Talent Retention

 - Finance organisations are great at _attracting_ talent by simply paying very high wages.  The problem is attrition.  
 - It's important to understand that lots of open source is developed for _non-financial rewards_.   
 - If you hire a key engineer who is a top contributor to an open source project and then prevent them from contributing further then they will likely leave.
 - Even if you allow them to continue contributing, if the workflow is onerous (e.g. MD-level reviews of their code) they will also get fed up and leave.
 - To _retain_ these high-performing staff, you have to give them the right tools to carry on contributing effectively.
 - Also: GitHub is _becoming a CV_.  

3. Internal Forks

 - The [Code Duplication](code-duplication) article already describes the maintainance costs associated with internal forks of projects, and in passing discusses how this also presents a security risk.
 - It is hard but perhaps not impossible to get a view of how big a problem this is in your organsisation by looking at the internal repository (e.g. Artifactory) and looking for versions of open source libraries that are _not_ coming from the original external source.
 - An argument _for_ internal forks is that this mitigates the cyber risk of trojan code from an external environment.  However this is specious since 99% of the code running in the organisation is open source anyway: bad actors can exist both inside and outside the bank and this is no substitute for scanning tools.
 - For example, consider a  _bad actor_ performing a [Solar Winds Trojan](https://www.cisecurity.org/solarwinds)-style attack.  This is a consumption risk that _already exists_.  Allowing developers to contribute to open source doesn't worsen or improve this situation.   

## Risks

1.  Data Leakage

 - Financial firms are _technology organisations_. All such organisations need to worry about Intellectual Property Risk.  IP Leakage can happen anywhere.  
 - Arguably, risks are _greater_ in finance because of the penalties that regulators may apply.
 - Historically, use of social media / sharing sites has been prohibited by many firms to mitigate data leakage.   
 - But you have to balance the data leakage risk against the benefits (outlined above).  Therefore:   can employees use a site like GitHub (where uploading data is commonplace) but have controls in place to mitigate the data-leakage aspect?
 - Tools such as [GitProxy](http://github.com/finos/Git-Proxy), personal machines, ephemeral desktops etc. help to mitigate this.  
 - _Training_ of open source developers within the organisation is an important step.  Do developers understand the rules?  Can you be explicit about what is and isn't included in a commit?  For example:  _non-code contributions_ such as test data might be outside the policy.  It's easier to have a blanket policy that this isn't allowed, since it could be hard to tell the difference between fake and real data.  Test data therefore needs to be generated by the tests as they run instead.
 - A _governance process_ needs to be in place for supervising contributions and observing what leaves the organisation.
 - Tools like [GitHub Enterprise](https://github.com/enterprise) also aim to help with Data Leakage Prevention.
 - _Evidence_ (in the form of records) may need to be provided that data hasn't been leaked (according to regulations).

2.  License Compliance

 - What consitutes an acceptable license depends on the software, the license and the context it is used in.  
 - For this reason, it is difficult to get a legal department to review each license and make a blanket decision on each one.
 - Again - look to tooling to help mitigate this risk.  Can a software project's build be failed because the wrong licenses are included in the codebase?

3.  Conflict Of Interest

 - Certain types of open source contribution might represent a conflict of interest.  E.g. a trader contributing to an open source trading platform.  Many of the regulations in place in finance are especially designed to stop this kind of abuse.  

4.  Financial Risk

 - Anything that developers write has a cost associated with it, which is charged to a cost center within an organisation. 
 - These costs are amortised with respect to the assets they create.
 - _Giving away software_ as open source breaks this model and needs to be accounted for correctly.

 5. Information Classification

  - All data and documentation within a bank must be given a classification.  E.g. public, confidential, etc.
  - Part of the DLP process should be to make sure that only _public_ information is allowed to be contributed.

6. Cross-Border Obligations

 - Many organisations are bound by what is allowed to cross their borders.  For example:  in Swiss banks, there are strong controls in place to make sure no data leaves Switzerland.  
 - This is a consideration for code too, as code _contributed to GitHub_ is data leaving the organisation and there may be requirements around these obligations.
 - This is another example of why preventing contributions with "test data" in them may be good policy.

7. Export Regulations

 - In a similar vein, many countries are prevented from selling into certain territories.  US/Iran for example.
 - There are rules in the US about exporting "non-standard crypto" (which might include obfuscated code).
 - Is open source contribution encompassed in "selling"?  

8. Electronic Communications

 - Banking regulations around electronic communications are mainly aimed at broker-dealer relationships, preventing collusion and enforcing "chinese walls" to prevent conflicts-of-interest.  
 - They normally apply to tools like Zoom, Slack, Symphony, Email etc. and cover retention periods, supervision etc.
 - Clearly, an open source contribution needs to adhere to these rules, even if it is not really the subject of them.
 - At the moment, this is an area of active investigation.  Tools like [GitHub Enterprise](https://github.com/enterprise) may help,  or something like [island.io](https://island.io).

## Education

There is a strong component of _education_ here:  once you have performed this risk analysis, you will need to explain it to the various stakeholders.  

Since the risk profile changes for various different departments, senior leaders will need convincing since the departments will have to accept a new way of working and a new approach to the risks involved.

## Proving It

Open source contribution is something that firms can adopt in a piecemeal, pilot way.  _This is also a risk reduction strategy_.   By starting out with a limited amount of contribution on certain key projects, you get to discover what _hidden risks_ were not covered in the risk analysis.   
