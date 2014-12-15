zfs_iscsi
=========

mount zfs for iscsi disk on boot 

FreeBSD 10.1 have a issue to mount zfs on iscsi disk  on boot. 
This is simple rc.d fix scrtip.

you can copy it in /usr/local/etc/rc.d/

EXAMPLE:

  /etc/iscsi.conf 
    ds {
	      TargetAddress   = 192.168.1.200
	      TargetName      = iqn.2000-01.com.synology:ds.target-1.be23ecdef5
    }
    
  /etc/rc.conf
    zfs_enable="YES"
    zfs_iscsi_enable="YES"  # zfs_iscsi 
    iscsi_flags="-n ds"
    iscsid_enable="YES"
    iscsictl_enable="YES"
    iscsictl_flags="-Aa"

