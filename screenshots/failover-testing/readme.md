
# 🔄 EIGRP Unequal-Cost Load Balancing & Automatic Failover Analysis

## 📌 Initial EIGRP Behavior — Equal-Cost Load Balancing

Initially, BRANCH_2_R1 had two equal-cost paths to reach the HQ network `10.0.1.0/24` through:

* ISP_3 → `172.16.17.1`
* ISP_4 → `172.16.18.1`

Since both paths had identical EIGRP metrics, EIGRP installed both routes as successor routes in the routing table. This resulted in Equal-Cost Multi-Path (ECMP) load balancing, where traffic was automatically distributed across both WAN links.

The routing table confirmed:

* `2 successors`
* Same feasible distance (FD)
* Both paths actively participating in load balancing

This demonstrated EIGRP’s native equal-cost load balancing capability in a redundant WAN environment.

---

# ⚙️ Metric Manipulation using Delay

To simulate Unequal-Cost Load Balancing, the delay on the `FastEthernet1/0` interface connected toward ISP_4 was increased using:

```cisco id="6v4u8h"
interface f1/0
delay 100
```

Increasing the interface delay increased the composite EIGRP metric for the ISP_4 path.

After modifying the delay:

* The path through ISP_3 (`172.16.17.1`) became the preferred successor route
* The ISP_4 path (`172.16.18.1`) remained as a feasible successor
* Only one route was installed in the routing table

The EIGRP topology table showed:

* Different feasible distances
* Different total delay values
* One active successor route
* One feasible backup route

This demonstrated how EIGRP selects the best path based on composite metrics derived from bandwidth and delay.

---

# 🚀 Enabling Unequal-Cost Load Balancing using Variance

To allow both paths to participate in forwarding despite having different metrics, the following EIGRP variance command was configured:

```cisco id="1w4g8q"
router eigrp 100
variance 2
```

After applying the variance multiplier:

* Both routes were reinstalled into the routing table
* Traffic could now be load balanced across unequal-cost paths
* The lower metric path remained the primary successor
* The higher metric path was accepted because it satisfied the feasibility condition and fell within the variance multiplier range

The routing table confirmed:

* `2 successor routes`
* Different metric values
* Active unequal-cost load balancing behavior

This demonstrated EIGRP’s advanced traffic engineering capability using the variance feature.

---

# 🔄 Automatic WAN Failover Demonstration

To test WAN resiliency and failover, the ISP_4 path was intentionally brought down.

Immediately after the failure:

* EIGRP detected neighbor loss with `172.16.18.1`
* DUAL reconverged automatically
* Traffic switched to the remaining ISP_3 path (`172.16.17.1`)
* Connectivity to the HQ network remained uninterrupted

Traceroute verification confirmed:

* Automatic path switchover
* Successful failover operation
* Continued end-to-end reachability

This demonstrated:

* Fast EIGRP convergence
* Automatic failover
* High availability
* Enterprise WAN resiliency

---

# ✅ Key Outcomes

✔ Successfully implemented Equal-Cost Load Balancing (ECMP)
✔ Successfully demonstrated Unequal-Cost Load Balancing using Variance
✔ Performed metric manipulation using interface delay
✔ Verified successor & feasible successor route behavior
✔ Demonstrated automatic EIGRP failover and reconvergence
✔ Validated enterprise WAN redundancy and resiliency mechanisms
