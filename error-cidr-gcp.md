**Prompt:**

*I'm trying to create a subnetwork in Google Cloud using Terraform, but I encountered the following error:*

```
Error creating Subnetwork: googleapi: Error 400: Invalid value for field 'resource.secondaryIpRanges[].ipCidrRange'. Must be a CIDR address range.
```

*I used the following IP CIDR ranges:*

- `primary_ip_cidr_range = "10.0.0.0/18"`
- `secondary_ip_cidr_range_1 = "10.0.1.0/14"`
- `secondary_ip_cidr_range_2 = "10.0.2.0/20"`

*When I used the following IP ranges, the configuration worked without issues:*

- `primary_ip_cidr_range = "10.0.0.0/18"`
- `secondary_ip_cidr_range_1 = "10.48.0.0/14"`
- `secondary_ip_cidr_range_2 = "10.52.0.0/20"`

*Can you explain why the first set of CIDR ranges caused the error, and why the second set worked? Additionally, can you guide me on how to choose valid and non-overlapping CIDR ranges for Google Cloud VPCs?*

