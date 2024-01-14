---
description: an index of real world stories of JIT Cloud Access
---

# JIT Cloud Access

Also known as "temporary access", see: [Google's Building Security and Reliable Systems:](https://google.github.io/building-secure-and-reliable-systems/raw/ch05.html#temporary_access)
>    You can limit the risk of an authorization decision by granting temporary access to resources. This strategy can often be useful when fine-grained controls are not available for every action, but you still want to grant the least privilege possible with the available tooling.
>
> You can grant temporary access in a structured and scheduled way (e.g., during on-call rotations, or via expiring group memberships) or in an on-demand fashion where users explicitly request access. You can combine temporary access with a request for multi-party authorization, a business justification, or another authorization control. Temporary access also creates a logical point for auditing, since you have clear logging about users who have access at any given time. It also provides data about where temporary access occurs so you can prioritize and reduce these requests over time.
>
> Temporary access also reduces ambient authority. This is one reason that administrators favor sudo or “Run as Administrator” over operating as the Unix user root or Windows Administrator accounts—when you accidentally issue a command to delete all the data, the fewer permissions you have, the better!

## Case Studies

| Year      | Company      | CSP | Tool | Blog Post |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| 2015 | Coinbase | AWS | [(OSS) self-service-iam](https://github.com/coinbase/self-service-iam) | [Self-Service Cloud Security with Amazon IAM](https://web.archive.org/web/20150908082141/https://developers.coinbase.com/blog/2015/03/30/self-service-iam) |
| 2017 | Addepar | AWS | Internal ("Concierge") | [(video) Access Control with Concierge: One Tool to Rule Them All](https://www.youtube.com/watch?v=121TkWzXXYI) |
| 2018, 2021 | Segment | AWS, GCP | Internal | [Secure access to 100 AWS accounts](https://segment.com/blog/secure-access-to-100-aws-accounts/), [Access Service: Temporary Access to the Cloud](https://segment.com/blog/access-service/) |
| 2019 | Riot | AWS | [(OSS) key-conjurer](https://github.com/RiotGames/key-conjurer) | [Key Conjurer: Our Policy of Least Privilege](https://technology.riotgames.com/news/key-conjurer-our-policy-least-privilege) |
| 2021 | Netflix | AWS | [(OSS) consoleme](https://github.com/Netflix/consoleme) | [ConsoleMe: A Central Control Plane for AWS Permissions and Access](https://netflixtechblog.com/consoleme-a-central-control-plane-for-aws-permissions-and-access-fd09afdd60a8) |
| 2021 | Bryj | AWS | [(OSS) consoleme](https://github.com/Netflix/consoleme) | [Achieving least-privilege at Bryj (former FollowAnalytics) with Repokid, Aardvark and ConsoleMe](https://medium.com/followanalytics/granting-least-privileges-at-followanalytics-with-repokid-aardvark-and-consoleme-895d8daf604a) |
| 2023 | Temporal | AWS | Common Fate | [Rolling out access hours at Temporal](https://temporal.io/blog/rolling-out-access-hours-at-temporal) |
| 2023 | Material Security | GCP | Internal | [Reimagining Access Management: Part 1](https://material.security/blog/reimagining-access-management-part-1) |
| 2023 | Ramp | AWS | ConductorOne | [Finding the right balance of speed and security through just-in-time access to cloud resources](https://engineering.ramp.com/jit-access) / [(video)  How Ramp Manages Authorization in the Cloud and Achieves Least Privilege](https://www.youtube.com/watch?v=v5f-1U3Y0xA) |
| 2023 | Rippling | AWS | (OSS) Common Fate [glide](https://github.com/common-fate/glide) | [Streamlining AWS access with Rippling at scale — Integrating IAM Identity Center and Just-In-Time access](https://www.rippling.com/blog/streamlining-aws-access-with-rippling-at-scale) |

## (Quality) Blogs about JIT Access 

* [Identity Crisis: The Biggest Prize in Security](https://research.contrary.com/reports/identity-crisis)
* Entitle - [Common uses of just-in-time access in the cloud](https://www.entitle.io/resource/just-in-time-use-cases)
* Firemon - [On Least Privilege, JIT, and Strong Authorization](https://defense.firemon.cloud/on-least-privilege-jit-and-strong-authorization/)
* Evervault - [A security paradigm for 2024: ATAF—Access To, Access From](https://evervault.com/blog/security-paradigm-access-to-access-from?ref=hn)


## Open Source Tools (AWS)

* [common-fate/glide](https://github.com/common-fate/glide)
* [aws-samples/iam-identity-center-team](https://github.com/aws-samples/iam-identity-center-team/blob/main/README.md), [blog](https://aws.amazon.com/blogs/security/temporary-elevated-access-management-with-iam-identity-center/)



## Vendor list

* [Entitle](https://www.entitle.io/)
* [ConductorOne](https://www.conductorone.com/)
* [Lumos](https://www.lumos.com)
* [Opal](https://opal.dev/)
* [Indent](https://indent.com)
* [Sym](https://symops.com)
* [Common Fate](https://www.commonfate.io/)
* [Leapp](https://www.leapp.cloud/)
* [CloudYali](https://www.cloudyali.io/)
* [p0](https://p0.dev/)
* [SGNL](https://sgnl.ai/solutions/amazon-web-services/)
* [Zilla Security](https://zillasecurity.com/)
* [AccessOS](https://www.accessos.com/)
* [abbey](https://www.abbey.io/)
* [Ermetic](https://ermetic.com/platform/just-in-time/)

### As a feature of IdP or PAM

* Okta IGA
* CyberArk Secure Cloud Access
* Jumpcloud [docs](https://jumpcloud.com/support/integrate-with-aws-iam-identity-center)
* Delinea

### Based on ticketing system

* [ClearSkye](https://clearskye.com/) (ServiceNow)
* [Multiplier](https://multiplierhq.com/) (Jira Service Management)