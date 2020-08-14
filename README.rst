
Munin-Node plugin to monitor ElectrumX and Groestlcoin
--------------------------------------------------

These Munin-Node plugins gather data from your running instance of
ElectrumX server and/or Groestlcoin daemon.

ElectrumX server:
    https://github.com/kyuupichan/electrumx

Groestlcoin daemon:
    https://github.com/groestlcoin/groestlcoin


Getting Started
---------------

Install munin and apache2.  For Ubuntu systems the commands are::

    sudo apt-get update
    sudo apt-get install munin apache2

The electrumx_bw plugin uses nethogs. To install it::

    sudo apt-get install nethogs

Once you have munin up and running, add the following files::

 /etc/munin/plugins/
    groestlcoin_blocks
    groestlcoin_bw
    groestlcoin_conn
    groestlcoin_diff
    groestlcoin_du
    groestlcoin_fee
    groestlcoin_mempool
    groestlcoin_mp
    groestlcoin_mp2
    groestlcoin_peer_versions
    groestlcoin_ticker
    groestlcoin_tx
    groestlcoin_vm
    electrumx_bw
    electrumx_caches
    electrumx_client_protocol
    electrumx_client_versions
    electrumx_connrate
    electrumx_err
    electrumx_io
    electrumx_lsof
    electrumx_mem
    electrumx_peers
    electrumx_peer_versions
    electrumx_reqcounts
    electrumx_ses
    electrumx_sub
    electrumx_tx
    electrumx_users

These plugins require configuration.
The configurations are in the following files added to your plugin-conf.d folder.::

 /etc/munin/plugin-conf.d/
    groestlcoin
    electrumx

You will need to edit /etc/munin/plugin-conf.d/groestlcoin.
*******************************************************

- Adjust the ``GROESTLCOIN_DATADIR`` environment to specify where to find your groestlcoin data directory.
- Adjust the ``GROESTLCOIN_CLI`` environment to specify where to find groestlcoin-cli.
- Adjust the ``ELECTRUMX_DATADIR`` environment to specify where to find your electrumx data directory.

You will need to edit /etc/munin/plugin-conf.d/electrumx.
*********************************************************

- Adjust the ``ELECTRUMX_RPC`` environment to specify where to find electrumx_rpc.py.

You will need to make the munin plugins executable.
***************************************************

The munin plugins must be marked as executable.
You can do so using this command::

    sudo chmod +x /etc/munin/plugins/*

After configuring the plugins, restart the munin-node service.

Versions
--------

These plugins are working with the following software versions::

 Operating System:   Ubuntu 18.04
 Munin-Node:         2.0.25
 ElectrumX:          1.11.0
 Groestlcoin Core:   2.19.1
