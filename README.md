# dragonchain-uvn-installer 

This project enables "easy mode" setup and installation of a Dragonchain Level 2 Unmanaged Verification Node

### Limitations:

Currently, the following limitations are in place for this script to function:
- Must be run on a Ubuntu linux installation (standard or server version)
    - Recommended server specs for the current Dragonchain release: 1 CPUs, 2GB RAM

### NOTE: IF YOUR NODE GOES UNHEALTHY ALL OF A SUDDEN, FOLLOW THE NEXT INSTRUCTIONS:

An issue with microk8s (not Dragonchain or our software) has been discovered that can cause nodes (especially those installed after approximately April 1st) to go into "unhealthy" status because they aren't able to process blocks.

If you run into this problem, SSH into your node and run the following command:

```wget https://raw.githubusercontent.com/Dragonchain-Community/dragonchain-uvn-installer/hotfix-certificates/update_certificates.sh && chmod u+x update_certificates.sh && sudo ./update_certificates.sh```
    
If, after running, you don't see all "1/1" and "Running" for the status of your pods, please try running the following command to check the status again:

```sudo kubectl get pods -n dragonchain```

If you still don't see all "1/1" and "Running," check in Telegram for support.

### To INSTALL a New Dragonchain Unmanaged Node:

- Clone the repo or download the **install_dragonchain_uvn.sh** file

    ```rm -f ./install_dragonchain_uvn.sh && wget https://raw.githubusercontent.com/Dragonchain-Community/dragonchain-uvn-installer/release-v3.2/install_dragonchain_uvn.sh```


- Make the script executable:

    ```chmod u+x install_dragonchain_uvn.sh```

- Run the script with sudo:

    ```sudo ./install_dragonchain_uvn.sh```

### To UPGRADE a Running Dragonchain Unmanaged Node:

- Clone the repo or download the **upgrade_dragonchain_uvn.sh** file

    ```rm -f ./upgrade_dragonchain_uvn.sh && wget https://raw.githubusercontent.com/Dragonchain-Community/dragonchain-uvn-installer/release-v3.2/upgrade_dragonchain_uvn.sh```


- Make the script executable:

    ```chmod u+x upgrade_dragonchain_uvn.sh```

- Run the script with sudo:

    ```sudo ./upgrade_dragonchain_uvn.sh```

### Coming features:
- Support for pre-built config files for easy automatic deployment

*Dragonchain-Community and this project are not affiliated with Dragonchain, Inc. or the Dragonchain Foundation*
