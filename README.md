# NIX
Shell script to install a [NIX Ghostnode](http://www.nixplatform.io/) on a Linux server running Ubuntu 16.04.  
This will require a VPS, I use [Vultr](https://www.vultr.com/?ref=7310394).  I recommend using a $5 server.
This script will install **NIX Core 2.0.0**.
***

## Installation:
Log into the server using ssh (Putty for windows or terminal for Mac users) and run the following commands:
```
wget -q https://raw.githubusercontent.com/cryptosharks131/Ghostnode/master/nix_install.sh
bash nix_install.sh
```
***

## Desktop wallet setup

After the GN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows/Mac Wallet:
1. Open the NIX Core Wallet.
2. Go to RECEIVE and create a New 'G' Address: **GN1**
3. Send **40000** **NIX** to **GN1**.
4. Wait for 15 confirmations before starting the node.
5. Go to **Help -> "Debug window - Console"**
6. Type the following command: **ghostnode outputs**
7. Open ghostnode.conf from the following folder %appdata%\nix (windows) or ~/Library/Application Support/ (hidden folder for Mac users)
8. Add the following entry:
```
Alias Address Genkey TxHash Output_index
```
* Alias: **GN1**
* Address: **VPS_IP:6214**
* Genkey: **Ghostnode GenKey**
* TxHash: **First value from Step 6** 
* Output index:  **Second value from Step 6** It can be **0** or **1**
9. Click OK and exit the Wallet.
10. Open NIX Core Wallet, go to **Ghostnode Tab**.
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again.
10. Click **Start All** or **Start Alias**
11. If you are not able to see your **Ghostnode**, try to close and open your desktop wallet.
***

## Usage:
```
nix-cli getblockchaininfo
nix-cli getnetworkinfo
nix-cli ghostnode status
```
Also, if you want to check/start/stop **NIX** , run one of the following commands as **root**:
```
systemctl status NIX #To check the service is running.
systemctl start NIX #To start NIX service.
systemctl stop NIX #To stop NIX service.
systemctl is-enabled NIX #To check whetether NIX service is enabled on boot or not.
```
***

## Updating NIX
The first line (rm nix_update.sh) is not required the very first time you update the node and will return an error if you run it.  This is fine, continue with the update script.
```
rm nix_update.sh*
wget -q https://raw.githubusercontent.com/cryptosharks131/Ghostnode/master/nix_update.sh
bash nix_update.sh
```
***

## Donations:  

**NIX**: NMuG1vCmuwh7hg8Dcd28ovVnyj5n4arbWr  
**BTC**: 1FJvtLBszQgY2eKBawov48RwSYy2yqEvn1  
**ETH**: 0x39acE9917e25E2A04643d30319cF34449A72441B  
**LTC**: LR1Mmchr6Zz1vj51xecTiEdS1WHfJTVg5t
