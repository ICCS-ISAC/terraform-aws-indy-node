<!-- BEGIN_TF_DOCS -->
## Requirements

No requirements.

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | n/a |
| <a name="provider_random"></a> [random](#provider\_random) | n/a |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_ebs_volume.data_volume](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ebs_volume) | resource |
| [aws_eip.public_client_ip](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/eip) | resource |
| [aws_eip.public_node_ip](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/eip) | resource |
| [aws_instance.indy_node](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance) | resource |
| [aws_internet_gateway.node_gateway](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/internet_gateway) | resource |
| [aws_network_interface.client_nic](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/network_interface) | resource |
| [aws_network_interface.node_nic](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/network_interface) | resource |
| [aws_network_interface_attachment.client_interface_attachment](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/network_interface_attachment) | resource |
| [aws_route.gateway_route](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/route) | resource |
| [aws_security_group.client_security_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group) | resource |
| [aws_security_group.node_security_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group) | resource |
| [aws_security_group_rule.client_security_group_rule_egress](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule) | resource |
| [aws_security_group_rule.client_security_group_rule_indy](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule) | resource |
| [aws_security_group_rule.node_security_group_rule_egress](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule) | resource |
| [aws_security_group_rule.node_security_group_rule_indy](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule) | resource |
| [aws_security_group_rule.node_security_group_rule_ssh](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule) | resource |
| [aws_subnet.client_subnet](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/subnet) | resource |
| [aws_subnet.node_subnet](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/subnet) | resource |
| [aws_volume_attachment.data_volume_attachment](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/volume_attachment) | resource |
| [aws_vpc.node_vpc](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpc) | resource |
| [random_id.node_seed](https://registry.terraform.io/providers/hashicorp/random/latest/docs/resources/id) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_ami_id"></a> [ami\_id](#input\_ami\_id) | AMI to use for the instance. | `any` | n/a | yes |
| <a name="input_application_name"></a> [application\_name](#input\_application\_name) | The name of the application. | `any` | n/a | yes |
| <a name="input_client_port"></a> [client\_port](#input\_client\_port) | The port, within the indy range of 9700 to 9799, on which the client interface will listen. | `string` | `"9702"` | no |
| <a name="input_data_volume_size"></a> [data\_volume\_size](#input\_data\_volume\_size) | Data EBS volume size | `any` | n/a | yes |
| <a name="input_ebs_delete_on_termination"></a> [ebs\_delete\_on\_termination](#input\_ebs\_delete\_on\_termination) | EBS delete on termination | `any` | n/a | yes |
| <a name="input_ebs_encrypted"></a> [ebs\_encrypted](#input\_ebs\_encrypted) | EBS is encrypted | `any` | n/a | yes |
| <a name="input_ebs_kms_key_id"></a> [ebs\_kms\_key\_id](#input\_ebs\_kms\_key\_id) | KMS key used to encrypt/decrypt EBS | `any` | n/a | yes |
| <a name="input_ebs_volume_type"></a> [ebs\_volume\_type](#input\_ebs\_volume\_type) | EBS volume type | `any` | n/a | yes |
| <a name="input_ec2_instance_type"></a> [ec2\_instance\_type](#input\_ec2\_instance\_type) | Type of instance ec2 | `any` | n/a | yes |
| <a name="input_environment"></a> [environment](#input\_environment) | The name of the environment. | `any` | n/a | yes |
| <a name="input_http_endpoint"></a> [http\_endpoint](#input\_http\_endpoint) | Whether the metadata service is available. Valid values include enabled or disabled. | `string` | `"enabled"` | no |
| <a name="input_http_tokens"></a> [http\_tokens](#input\_http\_tokens) | Whether or not the instance metadata service requires session tokens (IMDSv2). Valid values include 'optional' or 'required'. | `string` | `"required"` | no |
| <a name="input_iam_profile"></a> [iam\_profile](#input\_iam\_profile) | The IAM profile to attach to the ec2 instance. | `any` | `null` | no |
| <a name="input_instance_name"></a> [instance\_name](#input\_instance\_name) | The value to use for the Name tag of the EC2 instance | `any` | n/a | yes |
| <a name="input_node_port"></a> [node\_port](#input\_node\_port) | The port, within the indy range of 9700 to 9799, on which the node interface will listen. | `string` | `"9701"` | no |
| <a name="input_opt_ec2_tags"></a> [opt\_ec2\_tags](#input\_opt\_ec2\_tags) | Allows to add optional tags to EC2 vm's | `map(string)` | `{}` | no |
| <a name="input_root_volume_size"></a> [root\_volume\_size](#input\_root\_volume\_size) | Root EBS volume size | `any` | n/a | yes |
| <a name="input_ssh_key_name"></a> [ssh\_key\_name](#input\_ssh\_key\_name) | Name of the EC2 ssh public key to use to ssh in | `any` | n/a | yes |
| <a name="input_ssh_source_address"></a> [ssh\_source\_address](#input\_ssh\_source\_address) | The source IP address for SSH connections, in CIDR notation. | `any` | n/a | yes |
| <a name="input_subnet_client_cidr_block"></a> [subnet\_client\_cidr\_block](#input\_subnet\_client\_cidr\_block) | The cidr block to use for the client subnet. | `any` | n/a | yes |
| <a name="input_subnet_node_cidr_block"></a> [subnet\_node\_cidr\_block](#input\_subnet\_node\_cidr\_block) | The cidr block to use for the node subnet. | `any` | n/a | yes |
| <a name="input_use_elastic_ips"></a> [use\_elastic\_ips](#input\_use\_elastic\_ips) | The cidr block to use for the client subnet. | `bool` | n/a | yes |
| <a name="input_vpc_node_cidr_block"></a> [vpc\_node\_cidr\_block](#input\_vpc\_node\_cidr\_block) | VPC IP CIDR | `any` | n/a | yes |
| <a name="input_zone"></a> [zone](#input\_zone) | Availability zone where to deploy the VM | `any` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_node_info"></a> [node\_info](#output\_node\_info) | n/a |
<!-- END_TF_DOCS -->