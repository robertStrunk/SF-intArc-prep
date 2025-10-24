# Salesforce Certified Integration Architect Study Plan (v1.1)
## Complete Guide for 2025 Exam Alignment

---

## 📋 Exam Overview

| **Attribute** | **Details** |
|---------------|-------------|
| **Exam Format** | 60 multiple-choice/multiple-select questions |
| **Duration** | 105 minutes (1 hour 45 minutes) |
| **Passing Score** | 67% |
| **Cost** | $400 USD (retake $200) |
| **Delivery** | Online or onsite proctored |
| **Recommended Experience** | 2+ years of integration design with Salesforce |
| **Exam Code** | Plat-Arch-204 (verify on Trailhead for updates) |

**Tip:** The exam includes emphasis on **event-driven architecture**, **non-functional requirements**, and **integration governance**.

---

## 🎯 Exam Domains & Weightings

| **Domain** | **Weight** | **Study Time** |
|-------------|-------------|----------------|
| 1. Evaluate Current System Landscape | 8% | 1 week |
| 2. Evaluate Business Needs | 11% | 1–2 weeks |
| 3. Translate Needs to Integration Requirements | 22% | 2–3 weeks |
| 4. Design Integration Solutions | 28% | 3–4 weeks |
| 5. Build Solution | 23% | 2–3 weeks |
| 6. Maintain Integration | 8% | 1 week |

**Total Study Duration: 10–14 weeks (recommended)**

---

## 🔍 Domain 1: Evaluate the Current System Landscape (8%)

### Focus
- Evaluate hybrid/multi-cloud architectures
- Assess data residency and compliance (GDPR, CCPA, etc.)
- Understand integration governance and API lifecycle

### What the Examiner Tests
- Accurately document system dependencies and data flow
- Identify existing protocols and where Salesforce fits

### Key Topics
- API lifecycle awareness (Design → Publish → Secure → Monitor → Retire)
- API governance tools (MuleSoft API Manager, External Services)

### Hands-On Practice
- [ ] Create an integration inventory with API endpoints and dependencies
- [ ] Document data residency zones and compliance impact

---

## 💡 Domain 2: Evaluate Business Needs (11%)

### Focus
- Translate **non-functional requirements (NFRs)** into measurable architecture goals
- Assess organizational governance and ownership of integrations

### Key Topics
**Non-Functional Requirements (NFRs):**
- Performance SLAs (latency, throughput, availability)
- Scalability and elasticity
- Security & compliance requirements
- Observability: logging, tracing, monitoring
- Maintainability and cost efficiency

### Hands-On Practice
- [ ] Create NFR matrix (SLA, RTO/RPO, load expectation)
- [ ] Map business ownership for each integration layer

---

## ⚙️ Domain 3: Translate Needs to Integration Requirements (22%)

### Focus
- Integration governance and strategy
- Data volume and performance planning
- Authentication and security updates

### Key Topics
**Integration Governance Checklist:**
- Centralized API inventory
- Version control standards
- Security token rotation policy
- Integration ownership and documentation process

**LDV Handling:**
- Bulk API 2.0 + Async Apex + Platform Events for scalable data flow
- Staggered scheduling and throttling

**Authentication & Security:**
- External Credentials and Principal Mappings
- Cross-Org Connect for multi-org authentication
- Scoped OAuth and API Shield (MuleSoft)

### Hands-On Practice
- [ ] Configure External Credentials and test org-to-org integration
- [ ] Implement data sync using Bulk + CDC hybrid
- [ ] Design governance documentation for an enterprise integration

---

## 🧩 Domain 4: Design Integration Solutions (28%)

### Focus
- Event-driven architectures (CDC, Platform Events, Async APIs)
- Resilience, monitoring, and error recovery
- Trade-off analysis between APIs, middleware, and event bus

### Key Topics
**Event Replay and Recovery**
- Replay IDs for CDC / Platform Events
- Dead Letter Queues (DLQ)
- Durable Subscribers for mission-critical events

**Advanced Event-Driven Design:**
- Mixed event + API approach (e.g., event triggers ETL or async job)
- Outbox pattern for transactionally safe event publishing

**Error & Resilience:**
- Correlation IDs for tracing across systems
- Idempotent design and retry policies
- Structured error responses (JSON error codes)

**API Gateway / Security Layer Design**
- WAF, rate limits, IP whitelisting
- Centralized authentication (OAuth 2.0 + mutual TLS)

### Hands-On Practice
- [ ] Configure durable subscriptions in CDC
- [ ] Implement DLQ pattern for failed Platform Events
- [ ] Add correlation IDs and trace logs to callout chain
- [ ] Use MuleSoft to enforce API rate limiting

---

## 🧠 Domain 5: Build Solution (23%)

### Focus
- Build with resilience: retries, fallbacks, caching, circuit breakers
- Manage API versions and backward compatibility
- Implement CI/CD for integration deployments

### Key Topics
**CI/CD & Deployment Strategies:**
- Use Metadata API or SFDX for controlled releases
- Maintain multiple API versions concurrently
- Implement integration smoke tests

**Retry & Recovery Frameworks:**
- Use Queueable + Platform Events for async retries
- Implement exponential backoff retry logic

**Security:**
- Leverage External Credentials and Named Credentials together
- Monitor OAuth token lifecycles and rotation policies

### Hands-On Practice
- [ ] Build resilient integration with Queueable + Event retry
- [ ] Implement versioned Apex REST service (v1 → v2)
- [ ] Create CI/CD pipeline for deploying integration changes

---

## 🧭 Domain 6: Maintain Integration (8%)

### Focus
- Continuous monitoring & observability
- Integration health dashboards and alerts

### Key Topics
**Monitoring Framework:**
- Health check APIs for integrations
- Synthetic monitoring (scheduled test integrations)
- API analytics (latency, volume, error trends)
- Integration audit trail for compliance

**Maintenance Governance:**
- Quarterly API key rotation
- Logging retention & masking policies
- Automated alerting via Slack/PagerDuty

### Hands-On Practice
- [ ] Build an Integration Health Dashboard in Salesforce
- [ ] Implement Platform Event alerts → Slack notifications
- [ ] Simulate outage and confirm circuit breaker triggers

---

## 🧱 Integration Scenarios

### Real-World Design Exercises

1. **Retail Order Sync** → Platform Events + Bulk API (resilient, async)
2. **ERP Pricing Update** → Salesforce Connect (data virtualization)
3. **Payment Gateway** → REST (Request-Reply, low latency)
4. **Data Warehouse Feed** → ETL (Batch Data Sync + LDV controls)
5. **Mobile App Integration** → OAuth 2.0 + REST Composite API

Each should include:
- Pattern used
- Chosen APIs
- Error handling design
- Trade-offs (speed, complexity, cost)

---

## 📈 Integration Governance & Lifecycle

| **Phase** | **Description** | **Example Tools** |
|------------|------------------|------------------|
| **Design** | Define APIs, security, and SLAs | Anypoint Design Center |
| **Publish** | Register API specs | MuleSoft Exchange |
| **Secure** | Apply policies (OAuth, rate limits) | API Manager, Named Credentials |
| **Monitor** | Log metrics, alert on anomalies | Event Monitoring, Splunk |
| **Retire** | Deprecate old APIs, document successors | DevOps / Release Notes |

**Best Practices:**
- Central ownership (Integration COE)
- API catalog & documentation
- Consistent versioning (v1, v2, etc.)

---

## 🧩 Non-Functional Requirements Framework

| **Category** | **Metric** | **Example Target** |
|---------------|------------|-------------------|
| **Latency** | Response time | < 2s (real-time) |
| **Throughput** | Transactions per sec | 100+ TPS |
| **Availability** | Uptime | 99.9% |
| **Security** | Compliance | SOC2, GDPR |
| **Maintainability** | Mean Time to Repair (MTTR) | < 4 hours |

---

## ⚡ Quick Reference

**Patterns:**
- **Event Replay**: CDC + durable subscription
- **Hybrid Batch/Event**: Batch job triggers async Platform Event for downstream sync
- **API Gateway Pattern**: Central entry for multi-system orchestration

**Common Mistakes to Avoid:**
- Forgetting DLQs or replay IDs in event architecture
- Overusing synchronous callouts for large data
- Ignoring token rotation in OAuth flows
- Missing governance around API versioning

---

## ✅ Pre-Exam Checklist

**1 Week Before Exam:**
- [ ] Reviewed all integration patterns (esp. event-driven)
- [ ] Memorized NFR metrics and SLAs
- [ ] Practiced scenario-based trade-offs
- [ ] Understood External Credentials setup

**Day Before:**
- [ ] Review governance, LDV, and CDC nuances
- [ ] Skim Platform Event retention and replay behavior
- [ ] Rest and relax — exam tests understanding, not recall

---

## 📘 References (2025)

- Salesforce Certified Platform Integration Architect Exam Guide (Plat-Arch-204)
- Salesforce Architect Decision Guides (Integration, API, Event-Driven)
- MuleSoft Anypoint Platform Documentation
- Trailhead: “External Credentials”, “API Management”, “Event Monitoring”
- Salesforce Integration Patterns & Best Practices Whitepaper

---

**Document Version: 1.1**  
**Last Updated:** October 2025  
**Maintainer:** Robert Strunk

