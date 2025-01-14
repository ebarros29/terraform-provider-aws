---
subcategory: "Network Manager"
layout: "aws"
page_title: "AWS: aws_networkmanager_vpc_attachment"
description: |-
  Terraform resource for managing an AWS Network Manager VPC Attachment.
---


<!-- Please do not edit this file, it is generated. -->
# Resource: aws_networkmanager_vpc_attachment

Terraform resource for managing an AWS Network Manager VPC Attachment.

## Example Usage

### Basic Usage

```typescript
// DO NOT EDIT. Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
import { Construct } from "constructs";
import { Token, TerraformStack } from "cdktf";
/*
 * Provider bindings are generated by running `cdktf get`.
 * See https://cdk.tf/provider-generation for more details.
 */
import { NetworkmanagerVpcAttachment } from "./.gen/providers/aws/networkmanager-vpc-attachment";
class MyConvertedCode extends TerraformStack {
  constructor(scope: Construct, name: string) {
    super(scope, name);
    new NetworkmanagerVpcAttachment(this, "example", {
      coreNetworkId: Token.asString(awsccNetworkmanagerCoreNetworkExample.id),
      subnetArns: [Token.asString(awsSubnetExample.arn)],
      vpcArn: Token.asString(awsVpcExample.arn),
    });
  }
}

```

## Argument Reference

The following arguments are required:

* `coreNetworkId` - (Required) The ID of a core network for the VPC attachment.
* `subnetArns` - (Required) The subnet ARN of the VPC attachment.
* `vpcArn` - (Required) The ARN of the VPC.

The following arguments are optional:

* `options` - (Optional) Options for the VPC attachment.
* `tags` - (Optional) Key-value tags for the attachment. If configured with a provider [`defaultTags` configuration block](https://registry.terraform.io/providers/hashicorp/aws/latest/docs#default_tags-configuration-block) present, tags with matching keys will overwrite those defined at the provider-level.

### options

* `applianceModeSupport` - (Optional) Indicates whether appliance mode is supported.
  If enabled, traffic flow between a source and destination use the same Availability Zone for the VPC attachment for the lifetime of that flow.
  If the VPC attachment is pending acceptance, changing this value will recreate the resource.
* `ipv6Support` - (Optional) Indicates whether IPv6 is supported.
  If the VPC attachment is pending acceptance, changing this value will recreate the resource.

## Attribute Reference

This resource exports the following attributes in addition to the arguments above:

* `arn` - The ARN of the attachment.
* `attachmentPolicyRuleNumber` - The policy rule number associated with the attachment.
* `attachmentType` - The type of attachment.
* `coreNetworkArn` - The ARN of a core network.
* `edgeLocation` - The Region where the edge is located.
* `id` - The ID of the attachment.
* `ownerAccountId` - The ID of the attachment account owner.
* `resourceArn` - The attachment resource ARN.
* `segmentName` - The name of the segment attachment.
* `state` - The state of the attachment.
* `tagsAll` - A map of tags assigned to the resource, including those inherited from the provider [`defaultTags` configuration block](https://registry.terraform.io/providers/hashicorp/aws/latest/docs#default_tags-configuration-block).

## Import

In Terraform v1.5.0 and later, use an [`import` block](https://developer.hashicorp.com/terraform/language/import) to import `aws_networkmanager_vpc_attachment` using the attachment ID. For example:

```typescript
// DO NOT EDIT. Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
import { Construct } from "constructs";
import { TerraformStack } from "cdktf";
class MyConvertedCode extends TerraformStack {
  constructor(scope: Construct, name: string) {
    super(scope, name);
  }
}

```

Using `terraform import`, import `aws_networkmanager_vpc_attachment` using the attachment ID. For example:

```console
% terraform import aws_networkmanager_vpc_attachment.example attachment-0f8fa60d2238d1bd8
```

<!-- cache-key: cdktf-0.20.0 input-cc1d154d9a55335caf00aadaab7fbce5215f86bb670f30c6fb7dce2d8c50b3ac -->