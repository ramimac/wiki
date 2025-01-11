---
description: an index of perspectives on phishing simulation
---

Here are some references I use to support my negative view of Phishing Simulation [1]:


_Perspectives:_  

* Sean Cassidy: [Phishing simulations considered harmful](https://www.seancassidy.me/phishing-simulations-considered-harmful.html)
* Jamie Finnigan: [Simulated phishing is not so great](https://chair6.net/simulated-phishing-is-not-so-great.html)
* Yahoo Paranoids: [Stop Giving Impossible Advice: Telling People to Watch Out for SUSPICIOUS EMAILS is Nonsense.](https://www.yahooinc.com/paranoids/stop-giving-impossible-advice-telling-people-to-watch-out-for-suspicious-emails-is-nonsense)
* Jacob Kaplan-Moss: [Don’t include social engineering in penetration tests](https://jacobian.org/2017/jun/27/social-engineering-pentests/)
* Matt Linton: [On Fire Drills and Phishing Tests](https://security.googleblog.com/2024/05/on-fire-drills-and-phishing-tests.html)

_Research:_   

* [Phishing in Organizations: Findings from a Large-Scale and Long-Term Study](https://arxiv.org/pdf/2112.07498.pdf)
* [“What Keeps People Secure is That They Met The Security Team”: Deconstructing Drivers And Goals of Organizational Security Awareness](https://arxiv.org/pdf/2404.18365)
* [“To Do This Properly, You Need More Resources”: The Hidden Costs of Introducing Simulated Phishing Campaigns](https://www.usenix.org/system/files/usenixsecurity23-brunken.pdf)
* [“Employees Who Don’t Accept the Time Security Takes Are Not Aware Enough”: The CISO View of Human-Centred Security](https://www.usenix.org/system/files/usenixsecurity23-hielscher.pdf)
* NDSS 2024 - Symposium on Usable Security and Privacy
    * [Keynote - Dr M Angela Sasse](https://youtu.be/XFeZvQuRWGk?si=34fp21Ja_tR9oCoH&t=1463)
    * [The Impact of Workload on Phishing Susceptibility: An Experiment](https://www.ndss-symposium.org/wp-content/uploads/usec2024-24-paper.pdf)
* [What Motivates and Discourages Employees in Phishing Interventions: An Exploration of Expectancy-Value Theory](https://www.usenix.org/system/files/soups2024-chen.pdf): "Our study reveals a spectrum of factors that influence employees’ intentions to report phishing emails. ... Among the factors discouraging employees, the absence of feedback and perceived low utility value are particularly detrimental."
* [Understanding the Efficacy of Phishing Training in Practice](https://www.computer.org/csdl/proceedings-article/sp/2025/223600a076/21B7RjYyG9q): "Taken together, our results suggest that anti-phishing training programs, in their current and commonly deployed forms, are unlikely to offer significant practical value in reducing phishing risks."

_Commentary:_  

* Good phishing simulations are dependant on a good lure. Meaningful lures involve major threats or inticements, both of which can hurt the end user when followed by the "gotcha" page.  
* Phishing simulations may be needed to check a box for legal, contractual, or compliance requirements. It's up to you to fight the first two getting put in place.  
* Measuring clicks is bad simulation - we mostly care about credential submission or execution of a binary. Simulation vendors often over-emphasize clicks as "bad."  
* Consider gamifying phish detection, as one alternative  
* Phil Venables: [Security Training & Awareness - 10 Essential Techniques](https://www.philvenables.com/post/security-training-awareness-10-essential-techniques)
* Defense in Depth podcast: [Are Phishing Tests Helping or Hurting Our Security Program?](https://www.linkedin.com/pulse/phishing-tests-helping-hurting-our-security-program-david-spark-ulrof/)
* Google's [Phishing Quiz](https://phishingquiz.withgoogle.com/)

[1] Instead, roll out [webauthn/Yubikeys](deploying-webauthn.md)
