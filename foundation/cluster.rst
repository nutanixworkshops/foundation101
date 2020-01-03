Cluster Create Options
======================

There are two options to bring a Nutanix Cluster to life after the initial node imaging.

-   Use the Foundation UI, by far the quickest and easiest route

-   Use the CLI with a command similar to this:

``cluster -s ip_addr_cvm1,ip_addr_cvm2,ip_addr_cvm3 create``

Where the **ip_addr_cvm** is the unique IP address of each CVM. In this example this will create a cluster in RF2, further syntax for detailed configuration can be applied.
