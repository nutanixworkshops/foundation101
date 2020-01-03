Check the Build
===============

**BEFORE you log in to Prism the customer must accept EULA, NEVER should the SE undertake this**

With the cluster now up and running review the Events, run an NCC and check all is functioning correctly. You may find some warnings from NCC relating to network speeds, these can be ignored when using a 1GbE network. Once the cluster reports to be healthy it's ready to be gracefully shutdown.

But, before turning everything off check the IPMI IP settings are correct and apply VLANs to the NICs if they are required.

Setting a VLAN on the IPMI
++++++++++++++++++++++++++

A quick and easy way to set the VLAN tag. There is a command line equivalent but only a few clicks are needed through the UI.

-   Use a web browser and connect to the first IPMI IP address

-   Log in with ADMIN / ADMIN

-   Locate the network configuration and enter the VLAN number

-   Network connectivity to the web page will be lost once the settings have been saved

-   Repeat for all hosts

Setting a VLAN on the CVM and AHV hosts
+++++++++++++++++++++++++++++++++++++++

To apply a VLAN to the CVM use this script and syntax:

-   Use SSH with the root username and password and connect the AHV host, **not** the CVM

-   Then SSH to the CVM using the nutanix username and password and local IP of 192.168.5.254

-   Now run the command **change_cvm_vlan 125** (this will apply VLAN 125, replace with your desired number)

-   Now type in **sudo service network restart** to restart the network


To apply a VLAN to the AHV hosts follow these simple steps:

-   Use SSH with the root username and password and connect the AHV host

-   Now type in **ovs-vsctl set port br0 tag=125** (this will apply VLAN 125, replace with your desired number)

-   Assuming you can still connect to the host given that you've just applied a VLAN use this command to confirm **ovs-vsctl list port br0**


More information about the `change_cvm_vlan`_ script can be reviewed in the Prism Web Console Guide.

.. _change_cvm_vlan: https://portal.nutanix.com/#/page/docs/details?targetId=AHV-Admin-Guide-v511:ahv-cvm-assign-to-vlan-t.html

More information about `changing the AHV VLAN`_ tag is documented in the Prism Web Console Guide.

.. _changing the AHV VLAN: https://portal.nutanix.com/#/page/docs/details?targetId=AHV-Admin-Guide-v511:ahv-vlan-setup-ahv-t.html


Graceful shutdown
+++++++++++++++++

For **AHV hosts** only. If you're unsure of how to shut down vSphere & Hyper-V hosts head to the **Hypervisor Post Tasks** section and review the hypervisor specific Acropolis guides.

-   SSH from your computer to one of the CVMs

-   Type in ``cluster stop`` and confirm the shutdown

-   Type in ``cvm_shutdown -P`` and repeat this command on the remaining CVMs

-   Confirm the CVMs are now off by 'pinging' each them from your computer

-   SSH from your computer to the AHV command line of the first host

-   Type in ``shutdown -h now``

-   Repeat for all the AHV hosts

-   The hosts can now be powered off


More information about `AHV host shutdown`_ can be read in the Prism Web Console Guide.

.. _AHV host shutdown: https://portal.nutanix.com/#/page/docs/details?targetId=AHV-Admin-Guide-v511:ahv-node-shutdown-ahv-t.html

More information about the cvm_shutdown command can be read in the `KB article 3270`_.

.. _KB article 3270: https://portal.nutanix.com/#/page/kbs/details?targetId=kA0320000004H2NCAU
