# VMs on ESXi controlling HOWTO

----

This text describes how to control VMs on ESX by vSphere CLI without vCenter.

----

Download [vSphere CLI][1] and install it to a host which is IP reachable to the ESXi to be controlled.

On the host, open the console then run *vmware-cmd* to

- list up the path to VM configuration file for all VMs.

		C:\>vmware-cmd -H 10.0.0.1 -U root -P pass4root -l

  the output will be like this.

		/vmfs/volumes/4b0cb567-f988aa4b-d96d-002421a9b4be/cent6-1/cent6-1.vmx
		:
		<snip>

- power on the specified VM.

		C:\>vmware-cmd -H 10.0.0.1 -U root -P pass4root /vmfs/volumes/4b0cb567-f988aa4b-d96d-002421a9b4be/cent6-1/cent6-1.vmx start

- power off the specified VM.

		C:\>vmware-cmd -H 10.0.0.1 -U root -P pass4root /vmfs/volumes/4b0cb567-f988aa4b-d96d-002421a9b4be/cent6-1/cent6-1.vmx stop

- get power status of the specified VM.

		C:\>vmware-cmd -H 10.0.0.1 -U root -P pass4root /vmfs/volumes/4b0cb567-f988aa4b-d96d-002421a9b4be/cent6-1/cent6-1.vmx getstate

[1]: https://developercenter.vmware.com/web/dp/tool/vsphere_cli/6.0

| Date			| Issued by			| Description	|
|:-				|:-					|:-				|
| 2016.03.24	| miyamoto KAZuyuki	|1st issue		|
