VM running on unRAID.  
 - 12 CPU Cores  
 - 16 GB RAM  
 - 25 GB VDisk  
 - Ethernet Adapters:  
    - vlan  0: 00:00:00:25:00:13  
    - vlan 11: 00:00:00:25:10:13  
    - vlan 31: 00:00:00:25:30:13  
    (had to manually add scripts to connect the extra adapters: https://unix.stackexchange.com/questions/597407/centos-8-network-card-disconnected-on-boot)  


Centos Stream 8  
 - installed cifs-utils  
 - installed docker (https://docs.docker.com/engine/install/centos/, had to use --allowerasing to have it uninstall conflicting packages.)  
 - installed docker_compose (https://docs.docker.com/compose/install/)  

 - map drives in /etc/fstab  
   - created /root/sheebo-server.smb.cred with the username and password for the container_vm_user on unRAID.  
   - Added to fstab:  
      //sheebo-server.sheehantebo.com/nvme1_500/containers    /mnt/sheebo-server/containers        cifs    credentials=/root/sheebo-server.smb.cred,iocharset=utf8$
      //sheebo-server.sheehantebo.com/Media                   /mnt/sheebo-server/Media             cifs    credentials=/root/sheebo-server.smb.cred,iocharset=utf8$
      //sheebo-server.sheehantebo.com/Nextcloud-Data          /mnt/sheebo-server/Nextcloud-Data    cifs    credentials=/root/sheebo-server.smb.cred,iocharset=utf8$
 
 - installed Portainer (https://github.com/portainer/portainer-compose)  
 
