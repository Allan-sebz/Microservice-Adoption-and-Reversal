# Microservices Architecture: Industry Adoption and Strategic Reversals

A comprehensive analysis of how companies have adopted microservices architecture and why some have chosen to return to monoliths.

---

## 📋 Quick Answers

| Question | Answer |
|----------|--------|
| **How Netflix uses microservices** | 1,000+ services, Eureka for discovery, Hystrix for resilience, Chaos Monkey for testing, Open Connect CDN |
| **3 companies that shifted TO microservices** | WePay, Alight Solutions, Airbnb |
| **2 companies that shifted BACK to monoliths** | Amazon Prime Video, Uber |

---

## 1. 🎬 How Netflix Uses Microservices

### Background
Netflix began migrating from a monolith to microservices after a **database corruption in 2008** stopped DVD shipments for 3 days, costing millions.

### Current Architecture Scale
- **1,000+ microservices** running on AWS
- **100,000+ EC2 instances**
- **270+ million users** globally
- **Thousands of deployments daily**

### Key Microservices Components

| Component | Purpose | How It Works |
|-----------|---------|--------------|
| **Eureka** | Service Discovery | Services register themselves; others query to find them |
| **Hystrix** | Circuit Breaker | Prevents cascading failures by tripping "circuits" |
| **Chaos Monkey** | Resilience Testing | Randomly terminates production servers during business hours |
| **Open Connect** | Custom CDN | 10,000+ appliances inside ISP networks for fast streaming |

### Example: How Netflix Handles a Request
