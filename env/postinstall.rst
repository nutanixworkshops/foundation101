VMware vSphere & MS Hyper-V
===========================

These two hypervisors require specific configuration updates either directly on the host or in the management layer, i.e. VMware's vCenter or MS System Center Virtual Machine Manager (SCVMM). If the documentation isn't followed the Nutanix Cluster may not perform as expected in certain scenarios. Fear not, the steps that need to be followed are located with the Support Portal.

VMware Deployments
+++++++++++++++++++

Topics that are covered off include the vSphere HA/DRS settings, Admission Control Policy and disabling SIOC. And of course, don't forget to configure Prism with the VMware vCenter details.

-   Search for the **vSphere Administration Guide for Acropolis** in the Support Portal, or click this link `vSphere Guide`_.

-   If the customer is planning multiple HA/DRS clusters on a single Nutanix Cluster make sure **you've read** the `caveats`_ KB article 7256.

.. _vSphere Guide: https://portal.nutanix.com/#/page/docs/details?targetId=vSphere-Admin6-AOS-v55:vSphere-Admin6-AOS-v55

.. _caveats: https://portal.nutanix.com/#/page/kbs/details?targetId=kA00e0000009CFWCA2


Microsoft Hyper-V Deployments
+++++++++++++++++++++++++++++

Topics that are covered off include the Active Directory Domain Join, Configuring Failover Cluster and connecting to SCVMM.

- Search for the **Hyper-V Administration for Acropolis** in the Support Portal, or click this link `Hyper-V Guide`_.

.. _Hyper-V Guide: https://portal.nutanix.com/#/page/docs/details?targetId=HyperV-Admin-AOS-v511:HyperV-Admin-AOS-v511
