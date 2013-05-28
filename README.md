Munin plugin for Solr 4+ multicore
==================================

Installation
------------

    cd /usr/share/munin/plugins/
    sudo wget https://raw.github.com/hiroki23/munin-solr4-multicore/master/solr4_multicore_
    sudo chmod 755 solr4_multicore_

**Change the shebang line** (#!/usr/local/bin/ruby) .  

    sudo vi solr4_multicore_

(You can check ruby path by `which ruby` command.)

Create a symbolic link like this:

    sudo ln -s /usr/share/munin/plugins/solr4_multicore_ /etc/munin/plugins/solr4_multicore_999thPcRequestTime

Restart munin-node.

    sudo /etc/init.d/munin-node restart

### QUERYHANDLER

You can get

* avgRequestsPerSecond
* 5minRateReqsPerSecond
* 15minRateReqsPerSecond
* avgTimePerRequest
* medianRequestTime
* 75thPcRequestTime
* 95thPcRequestTime
* 99thPcRequestTime
* 999thPcRequestTime
* errors
* timeouts

etc, by creating symbolic links just like example above.

See QUERYHANDLER section at admin/mbeans URL like:

    http://localhost:8983/solr/[Core name]/admin/mbeans?stats=true

### CACHE

You can get

* queryResultCache
* documentCache
* fieldValueCache
* filterCache

See CACHE section at admin/mbeans URL like:

    http://localhost:8983/solr/[Core name]/admin/mbeans?stats=true

