# Start a full node

# Things you will need:

- A unix host machine, with a fixed IP address
- The fixed IP address of the machine

## 1. Set up a host
These instructions target Ubuntu.

1.1. Set up a cloud service you have `ssh` access to. 
1.2. You'll want to use `screen` (or `tmux`) to persist the terminal session of the building. `screen -S build`, then you can rejoin the session with `screen -rd build`
1.3. Clone this repo: 

`git clone https://github.com/OLSF/libra.git`

1.4. Config dependencies: 

`cd </path/to/libra/source/> && . ol/util/setup.sh` 

For more details: (../devs/OS_dependencies.md)

1.5. Build the source and install binaries:

`cd </path/to/libra/source/> && make bins`

## 2. Catch-up to the network state, with a `fullnode`

You do not need an account for this step, you are simply syncing the database.

2.1. Restore from most recent backup in epoch-archive: `ol restore`

2.2. `libra-node --config $HOME/.0L/fullnode.node.yaml`

**You can start the next steps while your node is catching up**
