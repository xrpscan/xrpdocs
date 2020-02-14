Validator
=========

We run a XRPL validator at ``aloha.xrpscan.com`` that's included in 
`Ripple's <https://vl.ripple.com>`_ and `Coil's <https://vl.coil.com>`_ 
recommended node list (UNL). Our node's validation key is::

  nHDB2PAPYqF86j9j3c6w1F1ZqwvQfiWcFShZ9Pokg9q4ohNDSkAz

Validator's properties:

#. Long history of availability and agreement: `aloha.xrpscan.com 
   <https://xrpscan.com/validator/nHDB2PAPYqF86j9j3c6w1F1ZqwvQfiWcFShZ9Pokg9q4ohNDSkAz>`_ 
#. High I/O NVMe SSD disks in RAID configuration.
#. Dedicated server that only runs ``rippled`` and ``sshd``.
#. Connected to the internet backbone via 1 GBit/s connection.
#. Peers with several highly trusted ``XRPL`` hubs.
#. Geographically located in a commercial datacenter near Helsinki, Finland.
#. CentOS 7 with regular OS updates. 
#. Timely and coordinated ``rippled`` upgrades.
#. Independently operated - Not affiliated with Ripple, Inc.

.. note:: The API service that powers `xrpscan.com <https://xrpscan.com/>`_ runs
  a separate stock ``rippled`` node that's completely isolated from the validating node.

Contact operator
----------------

There are several ways to contact the node operator. For transparency, we're
happy to answer any questions related to the validating node. :ref:`contact_us`
