# Rapids Masternode Setup Guide

This guide assumes that you will setup so called COLD Masternode, where the server process is running on a remote Linux system (usually a rented VPS), and your funds are kept safely in your local offline wallet.
Local wallet (collateral transfer)

# Local wallet (collateral transfer)
First, you need to make a transaction collateral of exactly 10000000 (10Million) coins. It should be kept untouched to receive masternode rewards.

* Start the Brixcoin wallet and wait for it to complete the blockchain synchronisation.
* Open Menu → **Receiving addresses**... and create a new address with label MN1 (or any one you like). Copy this address to the clipboard.
* Send exactly 10000000 (10Million) RPD coins in a single transaction to the account address you generated in the previous step. This may be sent from another wallet, or from funds already held in your current wallet.
* Wait for at least 1 transaction confirmation.
* Go to Help/Tools → Debug console and type the following command: masternode outputs
* This command should print a collateral transaction hash and index, usually 0 or 1.
* Keep this info at hand and proceed to the remote VPS setup.

# Remote VPS (masternode setup)
You have to find a Linux server which runs 24/7/365 and has a real IP address accessible from the outside. While it is possible to run it at home, the best way is to rent a VPS from a VPS provider. There are many providers, but we recommend AWS which provides VPS starting from as low as $5.85 USD/month. To simplify the setup we provide an install script which runs on Ubuntu Linux version 16.04, 17.10 or 18.04 and automates most of the setup for you. You should have a root user access with a password, and log in to the VPS using any ssh client (on Windows it could be putty, kitty or something similar).

Copy and paste the following commands to the root command prompt on Linux:

`wget -N https://github.com/RapidsOfficial/Rapids/raw/master/contrib/masternodes/rapids_masternode_install.sh`

`bash rapids_masternode_install.sh`

The script will check if it runs on a supported Ubuntu version, update your system, install necessary libraries, install Rapids software, configure it as a cold masternode daemon and ask you for your masternode private key. If you don't have one yet, just press Enter, and a new key will be generated for you.

Then you should have a script output similar to this one:

IMAGE GOES HERE

The most important thing is the green line with the data you have to put into your local wallet. So let's go back to it to finalise the setup.
