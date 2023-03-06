---
description: an index of risks and threats to AWS Lambda 
---

Every couple years I find myself needing to brush up on the risks and threat model of AWS Lambda. 

This is an index of security considerations. It excludes web application risks like authentication and authorization. It focuses on attack vectors, and as a result skips CI/CD concerns like [the risks of Lambda Layers](https://www.clearvector.com/blog/lambda-spy/).

Attackers targeting a Lambda can:

1. [backdoor it](https://hackingthe.cloud/aws/post_exploitation/lambda_persistence), given RCE
2. [retrieve the source](https://raw.githubusercontent.com/OWASP/Serverless-Top-10-Project/master/OWASP-Top-10-Serverless-Interpretation-en.pdf), given RCE
3. [retrieve environment variables](https://hackingthe.cloud/aws/exploitation/lambda-steal-iam-credentials/), given a file read vulnerability or SSRF (with the `file:` protocol). This includes IAM credentials for the Lambda and event data.
4. [given permission to invoke the function, view its logs](https://docs.aws.amazon.com/lambda/latest/dg/API_Invoke.html#API_Invoke_RequestSyntax)
4. generate a [fork bomb](https://en.wikipedia.org/wiki/Fork_bomb)
4. abuse a low concurrency limit by causing a DoS
5. abuse a high concurrency limit by causing a [Denial of Wallet attack](https://portswigger.net/daily-swig/denial-of-wallet-attacks-how-to-protect-against-costly-exploits-targeting-serverless-setups)
6. cause a DoS by exhausting disk capacity (i.e `tmp`) 
6. cause a DoS by exhausting API limits 
7. monetize an RCE via [cryptomining](https://www.cadosecurity.com/cado-discovers-denonia-the-first-malware-specifically-targeting-lambda/) (_note_: there is a GuardDuty detection, but it will not function if the Lambda is not attached to a VPC)
8. pivot via shared or over-privileged IAM roles
9. access data cross-process exposed in `/tmp` during warm start invocations
10. exfiltrate the account id via get-caller-identity and attack outside-in

**References:** 

* [OWASP Serverless Top 10](https://owasp.org/www-project-serverless-top-10/)
* [The 12 Most Critical Risks for Serverless Applications](https://cloudsecurityalliance.org/blog/2019/02/11/critical-risks-serverless-applications/))
* [Hacking the Cloud: Lambda Persistence](https://hackingthe.cloud/aws/post_exploitation/lambda_persistence/)
* [Hacking the Cloud: Steal IAM Credentials and Event Data from Lambda](https://hackingthe.cloud/aws/exploitation/lambda-steal-iam-credentials/)
* [fwd:cloudsec 2020 - Winning in the Dark: Defending Serverless Infrastructure](https://www.youtube.com/watch?v=5erD8yA6jjw)
    * [serverless-prey](https://github.com/pumasecurity/serverless-prey)
* [https://riyazwalikar.github.io/pentestawslambda](https://riyazwalikar.github.io/pentestawslambda)
* [lambda-internals](https://github.com/epsagon/lambda-internals)
* [Hacking Serverless Runtimes Profiling Lambda, Azure, and more.](https://www.blackhat.com/docs/us-17/wednesday/us-17-Krug-Hacking-Severless-Runtimes.pdf)
    * [Gone in 60 Milliseconds](https://media.ccc.de/v/33c3-7865-gone_in_60_milliseconds)
* [CloudGoat goes Serverless](https://rhinosecuritylabs.com/cloud-security/cloudgoat-vulnerable-lambda-functions/)
* Conversation in CloudSecForum on threat modeling "run something in python/node sandbox"