# 🚀 Enterprise EIGRP WAN Network Implementation Project

## 📌 Project Overview

This project focuses on designing and implementing an enterprise-level WAN topology using Cisco networking technologies to simulate a scalable, resilient, and highly available multi-branch enterprise network.

The topology was designed with redundant WAN connectivity between a Headquarters (HQ) region and multiple branch offices using EIGRP dynamic routing, VRRP gateway redundancy, Equal-Cost Load Balancing (ECMP), and Unequal-Cost Load Balancing using Variance.

The project demonstrates enterprise WAN concepts including redundancy, failover, intelligent path selection, routing convergence, and high availability.

---

# 🌐 Enterprise Topology Overview

The enterprise WAN topology consists of:

* 🏢 1 Headquarters Region (Bangalore)
* 🏢 3 Branch Offices

  * Kolkata
  * Assam
  * Delhi
* 🌍 Multiple ISP Transit Routers
* 🔄 Redundant WAN Connectivity
* ⚡ Dual Routers at each site for High Availability

---

# 🛠 Technologies & Concepts Implemented

* ✅ EIGRP Dynamic Routing
* ✅ EIGRP Neighbor Formation & DUAL Analysis
* ✅ Equal-Cost Load Balancing (ECMP)
* ✅ Unequal-Cost Load Balancing using Variance
* ✅ WAN Redundancy & Automatic Failover
* ✅ VRRP First-Hop Redundancy
* ✅ Gateway Failover Mechanisms
* ✅ Branch-to-Branch Communication
* ✅ HQ-to-Branch Communication
* ✅ WAN Path Selection & Metric Manipulation
* ✅ Enterprise Routing Verification & Troubleshooting
* ✅ Feasible Successor & Successor Route Analysis

---

# 🧰 Tools & Technologies Used

* Cisco IOS
* EVE-NG
* Wireshark
* EIGRP
* VRRP
* DUAL Algorithm
* Variance Command

---

# ⚙️ Features Successfully Implemented

## 🔹 Dynamic Routing using EIGRP

Configured EIGRP AS 100 across HQ routers, branch routers, and ISP routers to dynamically exchange routes and establish enterprise-wide communication.

---

## 🔹 Equal-Cost Load Balancing (ECMP)

Implemented Equal-Cost Multi-Path routing where traffic was automatically load balanced across redundant WAN paths with equal metrics.

---

## 🔹 Unequal-Cost Load Balancing using Variance

Implemented variance-based unequal-cost load balancing by manipulating EIGRP metrics using interface delay values and feasible successor analysis.

---

## 🔹 WAN Redundancy & Automatic Failover

Simulated ISP failures by shutting down WAN interfaces and verified automatic failover and route reconvergence using EIGRP.

---

## 🔹 VRRP Gateway Redundancy

Configured VRRP between branch routers and HQ routers to provide seamless default gateway failover and eliminate single points of failure.

---

# 🔍 Verification & Troubleshooting

The following verification and troubleshooting commands were used throughout the project:

```cisco
show ip route
show ip eigrp neighbors
show ip eigrp topology
show vrrp
show ip interface brief
ping
traceroute
```

The project included:

* EIGRP neighbor verification
* Routing table analysis
* Failover testing
* Load balancing verification
* VRRP master/backup validation
* WAN redundancy testing

---

# 📂 Project Structure

```text
# 📂 Project Structure

enterprise-eigrp-wan-project/
│
├── README.md
├── LICENSE
│
├── topology/
│   ├── topology-diagram.png
│   └── EIGRP_Enterprise_IP_Assignment_Plan.txt
│
├── configs/
│   ├── HQ/
│   ├── Branch1/
│   ├── Branch2/
│   ├── Branch3/
│   └── ISPs/
│
├── reports/
│   ├── Enterprise_EIGRP_Project_Report.pdf
│   └── Professional_Config_Guide.pdf
│
└── screenshots/
    ├── eigrp-neighbors.png
    ├── eigrp-topology-table.png
    ├── vrrp-master-backup.png
    ├── failover-test.png
    ├── traceroute-test.png
    └── unequal-cost-load-balancing.png
```

```

---

# 📚 Key Learning Outcomes

* Deep understanding of EIGRP routing behavior
* Successor & feasible successor route analysis
* Equal-Cost & Unequal-Cost Load Balancing
* WAN failover and reconvergence
* VRRP first-hop redundancy
* Enterprise WAN architecture design
* Practical routing troubleshooting methodologies

---

# 🚀 Future Improvements

Possible future enhancements include:

* EIGRP Authentication
* ACL-based traffic filtering
* GRE/IPSec VPN integration
* Network Automation
* QoS & Traffic Engineering
* SD-WAN concepts

---

# ✅ Project Conclusion

This project successfully demonstrated enterprise-level WAN implementation using EIGRP and VRRP with redundancy, failover, load balancing, and high availability concepts.

The implementation provided strong hands-on exposure to practical enterprise networking, routing behavior, troubleshooting, and resilient WAN design principles.
