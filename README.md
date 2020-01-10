# Analysis_of_MANET_Routing_Protocols
Comaparison of different types of MANET Routing Protocols using NS3 Simulator.

# Abstract :

Basically, here we are comparing the various MANET Routing Protocols based on certain performance metrics like Throughput, Packet Delay Ratio, End to End Delay, Number of Packets Dropped, Jitter, etc using Ns3 Simulator.

# Routing Protocols :

In MANET routing protocol should be capable to handle a very large number of nodes with limited resources. The main issue associate with the routing protocol involves being appeared and disappeared of nodes in various locations. It is necessary to reduce routing message overhead despite the increasing number of nodes. Another important issue is to keeping the routing table small, reason being increasing the routing table affects the control packets sent in the network and in turn affects large link overheads. 

Routing protocol needs to have following qualities to be effective: distributed operation, loop freedom, demand based operation, proactive operation, security and unidirectional link support. Distributed operation means that any node can enter or leave whenever they want. Loop-freedom is to prevent overhead created during sending information uselessly. Demand based operation is to decrease traffic and use bandwidth resources more efficiently. Proactive operation is used when they require enough bandwidth and energy resources. Security is the most important factor for any communication. 

Routing protocol is categorized on the basis of how and when route are discovered, but both select the shortest path to the destination. 

A- Proactive Routing Protocols 

Proactive routing protocols are also known as Table-driven routing protocol uses link-state routing algorithms which floods link information about its neighbors frequently. This type of protocol keeps and maintains up-to-date routing information between every pair of nodes by sending control message periodically in network. One of the main advantages of this protocol is that routes are ready to use when needed. The major drawback of proactive routing protocols includes the overhead of flooding route. There are various proactive routing protocols present for MANET like DSDV, OLSR, and WRP etc. 

  OPTIMIZED LINK STATE ROUTING PROTOCOL (OLSR)

Optimized Link State Routing Protocol is based on link state algorithm. Being a proactive routing protocol, it has an advantage of having the route immediately available within the standard routing table when needed. Due to optimization nature minimum flooding duplication occurs in highly connected network. Each node in the network selects a set of neighboring nodes to retransmit the packets and this set of nodes is called multipoint relays of that node. Instead of pure flooding the OLSR protocol employs Multipoint Relay (MPR) in network to reduce the possible overhead, flooding of broadcast and time interval for control message transmission. Only MPRs forward the control packets in such a way that information should reach entire network and these MPRs are responsible for declaring LS information. Each node periodically broadcasts a list of its one hop neighbors to select the MPRs with the help of hello message. Route calculations are done by MPR from source to destination node. OLSR supports three mechanisms: neighbor sensing, efficient flooding of control traffic and sufficient topology information. 

OLSR uses two types of control message: Hello and Topology Control (TC). Hello messages are used to find the information about the link status and node’s neighbors while TC messages are used for broadcasting information about own advertised neighbors includes at least the MPR selector list. 

  DISTANCE SEQUENCED DISTANCE VECTOR (DSDV) 

The DSDV routing protocol is a proactive routing protocol based on the Bellman-Ford routing algorithm that provides solution for shortest path between two nodes. In addition it introduces new feature i.e. sequence number for each routing table entry of entire network to avoid the formation of routing loops. Routing table is updated periodically throughout the network to maintain consistency in the table. To maintain the up-to-date view of the network, the tables are exchanged at regular interval of time. In order to reduce the amount of information carried during the broadcasting the routing information packets, two types of message are defined.

One carry all the available routing information is called full dump and other types i.e. incremental dump carries information that has changed since the last full dump. A full dump requires multiple Network Protocol Data Units (NPDU) while the incremental dump requires only one to fit in all information. While receiving the information packet from another node, node compares the sequence number with the available sequence number for the entry, and updates the entry with the new sequence number if the sequence number is larger or smaller. If the information arrives with the same sequence number, metric entry will be required. 

In this protocol the updates lead to high control overhead during high mobility due to broken links. Another drawback is that node has to wait for a table update message initiated by the same destination node in order to obtain information about a particular destination node.  

B. Reactive Routing Protocols 

Reactive or on-demand routing protocols were designed to reduce overheads present in proactive protocols by maintaining information. It uses distance-vector routing algorithm and establishes the route to given destination only when a node request it by initiating route discovery process. This protocols work on route discovery and route maintenance mechanism. Reactive routing protocols have drawback of delay in finding routes to new destination. There are number of reactive routing protocols available in MANET [14] like DSR, AODV, TORA and LMR etc. 

 AD-HOC ON DEMAND DISTANCE VECTOR ROUTING (AODV)

The AODV routing protocol is a reactive protocol that means routes are established whenever needed. It is based on On-demand mechanism of route discovery and route maintenance, plus the use of hop-by-hop routing and sequence number. Routing table consists of the information about the next hop to the destisequence number received from the destination. This protocol supports two phase: route discovery, route maintenance; and data forwarding. Route discovery is done by broadcasting the RREQ message to its neighbors with the requested destination sequence number, which prevents looping problem. Neighbors reply with the RREP packets while having corresponding route otherwise forward RREQ packets to their neighbors. While noticed the breakage of the route the node sends RERR message to the neighbors. It uses the HELLO message periodically to inform the neighbor that link to the host is alive. While receiving the HELLO message node updates the lifetime of the node information in the routing table. Being a flat routing protocol, AODV protocol does not need any central administrative system to handle the routing process. It also reduces the control traffic message overhead at the cost of increased latency in finding new routes. 

 DYNAMIC SOURCE ROUTING (DSR)

DSR is a reactive protocol based on source routing concept that requires each packet to carry the full address (every hop in the route) from source to destination. It is based on On-demand mechanism of route discovery and route maintenance. An advantage of DSR protocol is that nodes can store multiple routes in their route cache. Source node can check its route cache for a valid route before initiating route discovery, and if a valid route is found there is no need for route discovery. On the other hand, if a node does not have such a route, it initiates route discovery by broadcasting a RREQ packet. The RREQ packet contains the address of the destination along with address of source, a route record field and a unique identification number. Once the RREQ reaches either the destination or a node that knows a route to destination, it responds with a RREP along with the reverse of the route collected by the RREQ. A failed link is detected by either actively monitoring acknowledgements or passively running in promiscuous mode, overhearing that packet is forwarded by neighboring node. The failed link is notified to the source node with RERR packet. The source node can use other known route to destination node or the process of route discovery is initiated again to find new route to destination. Another thing is to be noted that it does not require hello message exchanges, therefore nodes can enter sleep node to conserve their power. Also saves a considerable amount of bandwidth in the network. 

# Performance Metrics :

A. Throughput :

It measures how well the network can constantly provide data to the destination. It is derived in Mbps. For achieving better performance it should be high. 

B. Packet Delivery Ratio 

The ratio of the number of data packets delivered to the destination nodes and the number of data packets sent by source nodes. The performance would be better when it is high. 

C. End to end delay 

The average time interval between the generation of packets in a source node and successfully delivery of it in a destination node. The performance would be better when it is low. 

D. Number of Packets dropped 

The number of data packets that is not successfully delivered to the destination during transmission.

E. Jitter 

It describes standard deviation of packet delay between all nodes. 

# Results :

1- Throughput VS Number of Nodes

In this particular bar graph we observe that as the number of nodes are increased though we observe a push in throughput in all protocols, we find that DSR is boosted a bit more when compared to rest. We don’t see much rise in case of OLSR. In DSDV we can observe a stillness when nodes are increased from 5 to 10, but a slight rise from 10 to 15 nodes. AODV shows a constant rise in throughput as we increase the number of nodes. 

2- Throughput VS Node Mobility

This graph depicts throughput of all the protocols considered at various mobility values of the nodes, In case of OLSR we can observe a slight increase in the Throughput when mobility changed from 10mps to 20mps,but from 20mps to 30mps we can observe a decrease in the throughput. We can see that DSDV gives a constant rise right from 10mps to 30mps.DSR gives almost the same throughput in all cases. AODV is slightly peculiar here and gives a  rise in throughput from 10mps to 20mps ,and a fall from 20mps to 30mps.

3- Delay VS Number of Nodes

This graph gives information about End to End delay as we vary number of nodes. We see decrement in all the three cases. But the decrement in AODV is rapid when compared with DSDV and DSR.DSDV has highest end to end delay in all the cases.

4- Average Delay VS Node Mobility

This particular bar graph visualizes change in Average delay with node speed. We see that in case of 10mps DSDV has highest average delay and the same continues even when node speed is increased to 20mps ,but in 30mps case it happens that DSDV is less than AODV in terms of Average delay.

5- Jitter VS Number of Nodes

Jitter in the all the cases more for DSDV.Then comes OLSR followed by AODV. But we can observe a  decrement in jitter by increasing number of nodes.

6- Average Jitter VS Node Mobility

Average jitter is  also almost same as average delay .In 20mps we observe  highest jitter.In all the other cases we see DSDV is dominant with respect to Jitter

7- Average PDR VS Node Mobility

Though we observe a decrement in Average PDR, we observe that OLSR is dominant in all the cases. DSDV comes next but in 30mps and 20mps we see DSDV is less than AODV.

8- Average PDR VS Number of Nodes

PDR  remains almost constant in the all the cases for OLSR and also DSDV ,but in case of AODV we can observe an increment when we increase nodes from 5 to 15.In all the cases PDR  dominates for OLSR protocol.

# CONCLUSION:

Thus comparison of various MANET routing protocols  OLSR , AODV, DSDV, DSR is done with by taking into consideration many metrics like PDR, Jitter, Throughput, Delay and Average Jitter, Average Delay, Average PDR by changing number of nodes and their speeds. We faced problem while calculating Delay of various protocols. It is pertaining to NS3 and in the process of resolving it and calculating we had a slight variation from theoretical aspects of the comparison only in delay. Future work can be done by analyzing various other protocols in both Reactive and Proactive types.

