!SLIDE bullets

<ul>
<li>Introduction</li>
<li>Basic CRUD</li>
<li>Schema Design</li>
<li><span class="current">Scaling Up</span></li>
</ul>

!SLIDE bullets incremental

# Scaling Up #

* Replication
* Replica Sets
* Auto-Sharding

!SLIDE bullets incremental

# Replication #

* One master
* Many slaves
* Slaves read a change log (opslog)

!SLIDE bullets incremental

# Replica Sets #

* A set of N nodes
* One master
* New master auto-elected
* Failover-friendly

!SLIDE bullets incremental

# Auto-Sharding #

* Shard data by key
* Over a number of replica sets
* Shards can be added anytime

!SLIDE center

## Auto-Sharding ##

![MongoDB Sharding](mongodb_sharding.png)
