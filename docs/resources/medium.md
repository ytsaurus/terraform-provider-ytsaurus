---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "ytsaurus_medium Resource - ytsaurus"
subcategory: ""
description: |-
  Different media types (HDD, SDD, RAM) are logically combined into special entities referred to as media.
  More information:
  https://ytsaurus.tech/docs/en/user-guide/storage/media
---

# ytsaurus_medium (Resource)

Different media types (HDD, SDD, RAM) are logically combined into special entities referred to as media.

More information:
https://ytsaurus.tech/docs/en/user-guide/storage/media



<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `name` (String) YTsaurus medium name.

### Optional

- `acl` (Attributes List) A list of ACE records. More information: https://ytsaurus.tech/docs/en/user-guide/storage/access-control. (see [below for nested schema](#nestedatt--acl))
- `config` (Attributes) The medium options. (see [below for nested schema](#nestedatt--config))
- `disk_family_whitelist` (List of String) A list of disk_families allowed for the medium.

### Read-Only

- `id` (String) ObjectID in the YTsaurus cluster, can be found in an object's @id attribute.

<a id="nestedatt--acl"></a>
### Nested Schema for `acl`

Required:

- `action` (String) Either allow (allowing entry) or deny (denying entry).
- `permissions` (Set of String) A list of access types also called permissions.
Supported permissions:
  - read - Means reading a value or getting information about an object or its attributes
  - write - Means changing an object's state or its attributes
  - use - Applies to accounts, pools, and bundles and means usage (that is, the ability to insert new objects into the quota of a given account, run operations in a pool, or move a dynamic table to a bundle)
  - administer - Means changing the object access descriptor
  - create - Applies only to schemas and means creating objects of this type
  - remove - Means removing an object
  - mount - Means mounting, unmounting, remounting, and resharding a dynamic table
  - manage - Applies only to operations (not to Cypress nodes) and means managing that operation or its jobs
- `subjects` (Set of String) A list of names of subjects (users or groups) to which the entry applies.

Optional:

- `inheritance_mode` (String) The inheritance mode of this ACE, by default.
Can be:
  - object_only - The object_only value means that this entry affects only the object itself
  - object_and_descendants - The object_and_descendants value means that this entry affects the object and all its descendants, including indirect ones
  - descendants_only - The descendants_only value means that this entry affects only descendants, including indirect ones. 
  - immediate_descendants_only - The immediate_descendants_only value means that this entry affects only direct descendants (sons)


<a id="nestedatt--config"></a>
### Nested Schema for `config`

Optional:

- `max_erasure_replicas_per_rack` (Number) Maximum number of erasure chunk replicas to store in a rack.
- `max_journal_replicas_per_rack` (Number) Maximum number of journal chunk replicas to store in a rack.
- `max_regular_replicas_per_rack` (Number) Maximum number of regular chunk replicas to store in a rack.
- `max_replicas_per_rack` (Number) Maximum number of replicas to store in a rack.
- `max_replication_factor` (Number) Maximum replication factor for the medium.
- `prefer_local_host_for_dynamic_tables` (Boolean) Prefer to store dynamic table data on local disks.


