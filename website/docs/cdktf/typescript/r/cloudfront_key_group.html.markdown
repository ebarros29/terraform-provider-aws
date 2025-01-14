---
subcategory: "CloudFront"
layout: "aws"
page_title: "AWS: aws_cloudfront_key_group"
description: |-
  Provides a CloudFront key group.
---


<!-- Please do not edit this file, it is generated. -->
# Resource: aws_cloudfront_key_group

## Example Usage

The following example below creates a CloudFront key group.

```typescript
// DO NOT EDIT. Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
import { Construct } from "constructs";
import { Fn, Token, TerraformStack } from "cdktf";
/*
 * Provider bindings are generated by running `cdktf get`.
 * See https://cdk.tf/provider-generation for more details.
 */
import { CloudfrontKeyGroup } from "./.gen/providers/aws/cloudfront-key-group";
import { CloudfrontPublicKey } from "./.gen/providers/aws/cloudfront-public-key";
class MyConvertedCode extends TerraformStack {
  constructor(scope: Construct, name: string) {
    super(scope, name);
    const example = new CloudfrontPublicKey(this, "example", {
      comment: "example public key",
      encodedKey: Token.asString(Fn.file("public_key.pem")),
      name: "example-key",
    });
    const awsCloudfrontKeyGroupExample = new CloudfrontKeyGroup(
      this,
      "example_1",
      {
        comment: "example key group",
        items: [example.id],
        name: "example-key-group",
      }
    );
    /*This allows the Terraform resource name to match the original name. You can remove the call if you don't need them to match.*/
    awsCloudfrontKeyGroupExample.overrideLogicalId("example");
  }
}

```

## Argument Reference

This resource supports the following arguments:

* `comment` - (Optional) A comment to describe the key group..
* `items` - (Required) A list of the identifiers of the public keys in the key group.
* `name` - (Required) A name to identify the key group.

## Attribute Reference

This resource exports the following attributes in addition to the arguments above:

* `etag` - The identifier for this version of the key group.
* `id` - The identifier for the key group.

## Import

In Terraform v1.5.0 and later, use an [`import` block](https://developer.hashicorp.com/terraform/language/import) to import CloudFront Key Group using the `id`. For example:

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

Using `terraform import`, import CloudFront Key Group using the `id`. For example:

```console
% terraform import aws_cloudfront_key_group.example 4b4f2r1c-315d-5c2e-f093-216t50jed10f
```

<!-- cache-key: cdktf-0.20.0 input-0db0e51d4954b3fa9a11b3c80e65d4eec2e3dd9da0abaf0109fbb3ae52ac9582 -->