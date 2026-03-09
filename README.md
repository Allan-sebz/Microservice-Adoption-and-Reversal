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
User opens Netflix app

Eureka discovers available services

API Gateway routes to appropriate services

Each service (recommendations, catalog, playback) handles its part

If any service fails, Hystrix provides fallback

Chaos Monkey ensures system can survive random failures


### Results
- ✅ 95% of traffic served in under 100ms
- ✅ 99.99% availability
- ✅ Can deploy thousands of times daily

---

## 2. 🏢 3 Companies That Shifted TO Microservices

### Company 1: WePay (FinTech)

**Before (Monolith):**
- PHP application with MySQL
- Monthly deployments taking 3-5 days
- 30 developers on same codebase

**Why They Changed:**
- Slow deployments blocking features
- Scaling entire app for load on specific features
- Payment failures affecting entire platform

**After (Microservices):**
- Multiple services in Java, Scala, Python
- Database per service (PostgreSQL, Cassandra, MongoDB)
- Deployments multiple times daily

**Results:**
| Metric | Before | After |
|--------|--------|-------|
| Deploy Time | 3-5 days | 15-30 minutes |
| Features/Week | 2 | 8-10 |
| Availability | 99.5% | 99.99% |

---

### Company 2: Alight Solutions (Enterprise Benefits)

**Before (Monolith):**
- COBOL and mainframe systems from 1980s
- 10+ million lines of legacy code
- Quarterly releases

**Why They Changed:**
- Features took 12-18 months to deliver
- Fortune 100 clients needed customizations
- Couldn't find COBOL developers

**After (Microservices):**
- 20+ autonomous teams
- Kubernetes on AWS
- Kafka for event streaming
- Services for enrollment, eligibility, pricing, claims, tax

**Results:**
- ✅ Feature delivery: 12-18 months → 2-4 weeks
- ✅ 35 million users supported
- ✅ Modern tech stack attracts talent

---

### Company 3: Airbnb (Travel)

**Before (Monolith):**
- Ruby on Rails
- 300+ developers on same codebase
- Tests took 6+ hours

**Why They Changed:**
- Daily merge conflicts
- Any change could break any feature
- Had to scale entire app for search load

**After (Microservices):**
| Service | Technology | Scale |
|---------|------------|-------|
| Listing | Java + Spring | 10M+ listings |
| Search | Elasticsearch | 100M+ searches/day |
| Pricing | Python + ML | Real-time pricing |
| Booking | Scala + Akka | Concurrent bookings |
| Payment | Java + Kafka | 1M+ transactions/day |

**Current Scale:**
- 1,200+ services
- 50,000+ containers
- 2,500+ daily deployments

---

## 3. 🔄 2 Companies That Shifted BACK to Monoliths

### Company 1: Amazon Prime Video

**Original Microservices Architecture:**
