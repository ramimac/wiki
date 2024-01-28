---
description: an index of information on AWS SCPs 
---

Tips on using SCPs  

* [Quick Tip: Minimizing Terraformed SCPs](https://ramimac.me/terraform-minimized-scps)
* [Wiz, Scott Piper: Using Service Control Policies to protect security baselines](https://www.wiz.io/blog/using-service-control-policies-to-protect-security-baselines)
* [Summit Route, Scott Piper: AWS SCP Best Practices](https://summitroute.com/blog/2020/03/25/aws_scp_best_practices/#understand-scps)
* [Seshu Pasha: AWS Governance — Service Control Policies](https://medium.com/@seshu/aws-governance-service-control-policies-6d23b144ec72)

Lists of Recommended SCPs   

* AWS Organizations [SCP Examples](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps_examples.html)
* [aws-samples/service-control-policy-examples](https://github.com/aws-samples/service-control-policy-examples)
* [Reducing Attack Surface with AWS Allowlisting](https://ramimac.me/aws-allowlisting)
* PrimeHarbor/Chris Farris [org-kickstart/policies](https://github.com/primeharbor/org-kickstart/tree/main/policies)
* [latacora/latacora-service-control-policies](https://github.com/latacora/latacora-service-control-policies)
* [asecure.cloud](https://asecure.cloud/l/scp/)
* ScaleSec: [terraform_aws_scp](https://github.com/ScaleSec/terraform_aws_scp)
* Ashish Rajan: [aws-scp-best-practice-policies](https://github.com/hashishrajan/aws-scp-best-practice-policies)
* [Summit Route, Scott Piper: AWS SCP Best Practices - Example SCPs](https://summitroute.com/blog/2020/03/25/aws_scp_best_practices/#example-scps)
* Ian Mckay's [List of expensive / long-term effect AWS IAM actions](https://gist.github.com/iann0036/b473bbb3097c5f4c656ed3d07b4d2222)
* Additional examples:

```terraform
# deny the usage of imdsv1
data "aws_iam_policy_document" "deny_imdsv1" {
  statement {
    sid    = "DenyIMDSv1"
    effect = "Deny"

    actions = [
      "*",
    ]

    resources = [
      "*",
    ]

    condition {
      test     = "NumericLessThan"
      variable = "ec2:RoleDelivery"
      values   = ["2.0"]
    }
  }
}
# deny creating public secrets
data "aws_iam_policy_document" "deny_public_secrets" {
  statement {
    sid    = "DenyPublicSecrets"
    effect = "Deny"

    actions = [
      "secretsmanager:PutResourcePolicy",
    ]

    resources = [
      "*",
    ]

    condition {
      test     = "Bool"
      variable = "secretsmanager:BlockPublicPolicy"
      values   = ["false"]
    }
  }
}
```

Visualization  

* [scpkit](https://github.com/aquia-inc/scpkit)
* Steampipe [aws_organizations_policy_target](https://hub.steampipe.io/plugins/turbot/aws/tables/aws_organizations_policy_target) + [Node/Edge Visualizations#](https://steampipe.io/docs/reference/mod-resources/graph#nodeedge-visualizations)

