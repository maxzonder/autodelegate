## Autodelegate and status script with Telegram notifications

### 1. Install

```
cd $HOME
mkdir scripts

wget -O $HOME/scripts/telegram https://raw.githubusercontent.com/fabianonline/telegram.sh/master/telegram && \
chmod +x $HOME/scripts/telegram

wget -O $HOME/scripts/status_and_autodelegate_evmos.sh https://raw.githubusercontent.com/maxzonder/autodelegate/main/status_and_autodelegate_evmos.sh \
&& chmod +x $HOME/scripts/status_and_autodelegate_evmos.sh

cd scripts
wget -nc https://raw.githubusercontent.com/maxzonder/autodelegate/main/config_evmos.ini
 
```

### 2. Set vars in `config_evmos.ini`

EXAMPLE
```
PASS=12345678
KEY_NAME=WALLET_NAME
MONIKER=NODE_NAME
ADDRESS=evmos1... 
VALOPER=evmosvaloper1...
TG_CHAT_ID="34456xx7"
TG_TOKEN="21dfgdfgd1:AAHi9hjkghjkhgjkhjkhgjkhgjkhgjkY"
BINARY=evmosd
COIN=aphoton
COIN_DENOMED=photon
FEE=6000
DENOM=1000000000000000000
RPC_PORT=26657
CHAIN=evmos_9000-2
MIN_BALANCE=1000000000000000
```

### 3. Add task in cron

```
crontab -e
```
 
Will call every 1 hour 00 min

```
0 */1 * * *  /bin/bash /root/scripts/status_and_autodelegate_evmos.sh >> /var/log/status_and_autodelegate_evmos.log

```

#### To Update
```
wget -O $HOME/scripts/status_and_autodelegate_evmos.sh https://raw.githubusercontent.com/maxzonder/autodelegate/main/status_and_autodelegate_evmos.sh \
&& chmod +x $HOME/scripts/status_and_autodelegate_evmos.sh
```
