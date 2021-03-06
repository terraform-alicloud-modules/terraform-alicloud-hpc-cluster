Terraform Module for creating ECS HPC cluster on Alibaba Cloud.

terraform-alicloud-hpc-cluster
=====================================================================

English | [简体中文](README-CN.md)

This module is used to create a Hpc Cluster under Alibaba Cloud.

These types of resources are supported:

* [alicloud_ecs_hpc_cluster](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/ecs_hpc_cluster)
* [alicloud_instance](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/instance)

## Usage

```hcl
module "example" {
  source                     = "terraform-alicloud-modules/hpc-cluster/alicloud"
  #alicloud_ecs_hpc_cluster
  create_cluster             = true
  cluster_name               = "tf-name"
  #alicloud_instance
  create_instance            = true
  availability_zone          = "cn-hangzhou-k"
  instance_name              = "tf-test-name"
  security_group_ids         = ["sg-123456xxx"]
  vswitch_id                 = "vsw-123456xxx"
  instance_type              = "ecs.sccg7.32xlarge"
  system_disk_category       = "cloud_efficiency"
  system_disk_name           = "tf-system_disk_name"
  system_disk_description    = "system_disk_description"
  image_id                   = "centos_7_9_uefi_x64_20G_scc_20210727.vhd"
  internet_max_bandwidth_out = 50
  data_disks  = {
    name        = "data_disks_name"
    size        = 120
    category    = "cloud_efficiency"
    description = "tf-test-description"
    encrypted   = true
  }
}
```

## Examples

* [complete example](https://github.com/terraform-alicloud-modules/terraform-alicloud-hpc-cluster/tree/main/examples/complete)

## Notes

* This module using AccessKey and SecretKey are from `profile` and `shared_credentials_file`. If you have not set them
  yet, please install [aliyun-cli](https://github.com/aliyun/aliyun-cli#installation) and configure it.

## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | > = 0.13.0 |
| <a name="requirement_alicloud"></a> [alicloud](#requirement\_alicloud) | > = 1.116.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_alicloud"></a> [alicloud](#provider\_alicloud) | > = 1.116.0 |

## Submit Issues

If you have any problems when using this module, please opening
a [provider issue](https://github.com/aliyun/terraform-provider-alicloud/issues/new) and let us know.

**Note:** There does not recommend opening an issue on this repo.

## Authors

Created and maintained by Alibaba Cloud Terraform Team(terraform@alibabacloud.com).

## License

MIT Licensed. See LICENSE for full details.

## Reference

* [Terraform-Provider-Alicloud Github](https://github.com/aliyun/terraform-provider-alicloud)
* [Terraform-Provider-Alicloud Release](https://releases.hashicorp.com/terraform-provider-alicloud/)
* [Terraform-Provider-Alicloud Docs](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs)
