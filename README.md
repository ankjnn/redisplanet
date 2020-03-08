# Redisplanet - An Ultimate Redis Hands-On Labs

## Redis Open Source

### Installation
- Linux
  - [Installing Redis Open Source on Ubuntu 18.04](https://github.com/collabnix/redis/blob/master/install/ubuntu/18.04/README.md)<br>
  - [Starting Redis Server](https://github.com/collabnix/redis/tree/master/install/ubuntu/18.04#starting-redis-server)<br>
  - [Shutting down Redis Server](https://github.com/collabnix/redis/tree/master/install/ubuntu/18.04#shutting-down-redis)<br>
  - [How to change Redis Port](https://github.com/collabnix/redis/tree/master/install/ubuntu/18.04#how-to-change-redis-server-port)<br>

- Windows
- MacOS
- Docker
  - [Redis on Docker Swarm](http://collabnix.com/getting-started-with-redis-inside-docker-container-in-2-minutes/)
  - [Getting Started with Redis + Docker + Go](https://github.com/collabnix/redisplanet/blob/master/docker/Getting_Started_with_Docker-Redis-Go.md#getting-started-with-docker--redis--go)
- Kubernetes
   - Cloud
     - GKE
       -  [Setting up 3 Node Redis Cluster on GKE](https://github.com/collabnix/redis/blob/master/kubernetes/gke/README.md#setting-up-multi-node-redis-cluster-on-google-cloud-engine)<br>
   - Minikube
     - [How to run Redis Cluster on Kubernetes? ](https://github.com/collabnix/redisplanet/blob/master/kubernetes/redis-ruby-k8s/README.md#how-to-run-redis-cluster-on-kubernetes ) 

- IoT
  - [Redis running inside Docker Container on Jetson Nano](http://collabnix.com/running-redis-inside-docker-container-on-jetson-nano/)
  
- Monitoring
  - [Visualize Redis Open Source using Rebrow](https://collabnix.com/visualize-redis-open-source-using-rebrow/)
  
  
## Redis Configuration File

- [Everything You Want to Know about Redis.conf](https://github.com/collabnix/redisplanet/blob/master/Redis-conf/README.md)

## Redis Enterprise Software

### Installation

 - Linux
   - [Installing Redis Enterprise on Ubuntu Linux](https://collabnix.github.io/redisplanet/ee/install/)
 - Windows
 - MacOS
   - [3 Node Redis Enterprise Cluster using Docker Desktop for Mac](http://collabnix.com/3-node-redis-enterprise-cluster-using-docker-desktop/)
 - Docker
   - [Setting up Redis Enterprise Software on Docker](https://github.com/collabnix/redis/blob/master/docker/README.md)<br>
   - [Installing RedisInSight & Connect to Redis Enterprise Software](https://github.com/collabnix/redis/blob/master/docker/README.md#running-redinsight)<br>
   - [3 Node Active-Active Redis Enterprise Cluster for Developers using Docker Desktop](http://collabnix.com/3-node-redis-enterprise-cluster-using-docker-desktop/)
   
## Redis OSS Vs Redis Enterprise

# RedisLabs Vs Redis OSS 

| Redis OSS       | RedisLabs       | 
| ------------- |:-------------:|
|   Leading OSS in-memory database platform, supporting any high performance operational, analytics or hybrid use case            |  The OSS home and commercial provider of Redis Enterprise technology, platform, products and services          |  

# Redis OSS


## Standalone Redis

| Redis OSS       | RedisLabs       | 
| ------------- |:-------------:|
|   No Concept of sharding           |            |  
|   No automatic Failover           |            | 
|   No Scability         |            | 
|   No Multitenancy           |            | 
|   Manual & Complex Operation           |            | 
|   Relaxed (Multiple Replicas) Consistency           |            | 
|   Single instance performance for writes           |            | 
|   Single instance performance for writes           |            | 


## [Redis Sentinel](https://redis.io/topics/sentinel)

| Redis OSS     | RedisLabs      | 
| ------------- |:-------------:|
|   No Scability            |            |  
|   No HA (Yes, but can take comparable long)          |            | 
|   Built-in HA and automatic failover        |            | 
|   Doesn't support standard clients, Sentinel discovery mechanism instead          |            | 
|   Hard to operate          |            | 
|   No Multitenancy          |            | 
|   Relaxed (1 master + 2 replicas)         |            | 
|   Complex+, manual           |            | 


## [Redis OSS Cluster](https://redis.io/topics/cluster-tutorial)

| Redis OSS     | RedisLabs      | 
| ------------- |:-------------:|
|   Built-in HA and automatic failover           |            |  
|   Hash­based sharding (and hash tags)          |            | 
|   No support for multi­key operations      |            | 
|   Doesn't support standard clients, OSS Cluster client required         |            | 
|   Hard to operate        |            | 
|   Scalable        |            | 
|   Lower Performance       |            | 
|   Scalable        |            | 
| Performance dependent on the number of connections per shard |    |
| Each client needs to connect to each shard | |


## Redis OSS VS Redis Enterprise Software

| Feature | Redis OSS Cluster    | Redis Enterprise      | 
| -----------| ------------- |-------------|
| Scability     |                                 Yes     |       Fully Automated   |  
|  HA           | Built-in HA, manual intervention may be required    |       Fully automated                  | 
|  Performance  |                       Lower (Performance dependent on the number of connections per shard)                 |   Up to x2 base, Stable            | 
|  Multitenancy |                        None                 |       Yes                          | 
| Consistency   |                  Relaxed (2 replicas per master shard)       |    Tunable                         | 
| Operations    |             Complex++, manual                 |     Minimal, automated             | 
| Sharding      |                                         | Automatic resharding when increasing the shard count |
| Sharding      |                                         | Increasing the shard count leads to a balanced state |
| Proxy         |                                         | Built-in Proxy for connection multiplexing and command re-pipelining |
| Failover      |                                         | Automatic failover and failure recovery (Watchdogs, Supervisor, ...)|
| Sharding    |     Hash-based sharding (and hash tags)                   | Hash based sharding (and hash tags) |
| Multikey Operations |  No support for multi­key operations | Support for several multikey operations (i.e. MSET/MGET) |
| Clients for Database    |  Doesn't support standard clients, OSS Cluster client required     |   Supports standard clients for standard clustered databases |
|                         |       |  Node-based quorum, 1 replica per master shard, doesn't allow to read from replicas |



### Redis Data Structure
- [Hashes](https://github.com/collabnix/redis/blob/master/datastructure/hashes/README.md)
  - [HSET](https://github.com/collabnix/redis/blob/master/datastructure/hashes/README.md#hset)
  - [HGET](https://github.com/collabnix/redis/blob/master/datastructure/hashes/README.md#hget)
  - [HINCRBY](https://github.com/collabnix/redis/blob/master/datastructure/hashes/README.md#hincrby)
  - [HGETALL](https://github.com/collabnix/redis/blob/master/datastructure/hashes/README.md#hgetall)
  
### Redis Technology Stack 

  - [TBD]()
  

### Redis Ready Solution 

  - [TBD]()




 
