# Example: Technical Decision - Support Tool Selection

This example shows how to document a technical implementation decision using the full template.

---

# Decision: Select Zendesk Over Intercom for Client Support Platform

**Date:** 2025-11-20
**Context:** Support Operations
**Participants:** Ash, Client Technical Team
**Status:** Active (Review: After 3 months usage)

---

## Decision Made

Implement Zendesk as primary support platform rather than Intercom or Help Scout.

---

## Why This Decision?

### Problem
Client needs professional support platform to scale from 50 to 300+ customers. Current email-based support doesn't provide:
- Ticket tracking and SLAs
- Team collaboration features
- Reporting and analytics
- Self-service knowledge base

### Options Considered
1. **Intercom**
   - Pros: Modern UI, strong messaging/chat, good for product-led growth
   - Cons: Expensive at scale, limited reporting, primarily chat-focused

2. **Zendesk** ✅ **CHOSEN**
   - Pros: Industry standard, robust reporting, excellent ticket management, scales well
   - Cons: Steeper learning curve, less modern UI, higher upfront cost

3. **Help Scout**
   - Pros: Simple, affordable, good for small teams
   - Cons: Limited automation, basic reporting, may need to migrate later

### Rationale
- Zendesk designed for scaling from 100 to 10,000+ customers
- Advanced workflow automation (critical for tiered support model)
- Comprehensive reporting for CX metrics tracking
- Strong integration ecosystem (Slack, Jira, Salesforce)
- Industry standard - easier to hire support staff familiar with platform

---

## Trade-offs Accepted

**Not getting:**
- Modern, consumer-friendly chat interface
- Lower initial cost
- Simple setup and configuration

**Gaining:**
- Enterprise-grade ticket management
- Advanced analytics and reporting
- Scalable automation capabilities
- Long-term platform stability

---

## Implementation Impact

**Affects:**
- Migration: Move 200+ historical tickets and conversations
- Training: Team needs 2-3 weeks to reach proficiency
- Integration: Connect with Slack, CRM, monitoring tools
- Process: Rebuild workflows and automation in new platform

**Action Items:**
- [x] Purchase Zendesk Suite Professional license
- [ ] Configure ticket routing and SLA policies
- [ ] Migrate historical data from Gmail
- [ ] Train support team on Zendesk workflows
- [ ] Build knowledge base and help center
- [ ] Set up reporting dashboards

---

## Review Criteria

**Revisit if:**
- Team adoption below 80% after 2 months
- Support costs exceed $200/agent/month
- Reporting doesn't provide needed CX metrics

**Success metrics:**
- Average first response time under 2 hours
- Ticket resolution time reduced by 30%
- Customer satisfaction score 4.2+/5.0
- Team reports feeling more productive

**Scheduled review:** February 20, 2026

---

## Related Decisions
- Influences: Support team hiring requirements, knowledge base strategy
- Related to: Tiered support model implementation

---

## Notes
If client scales beyond 1,000 customers, may need Zendesk Enterprise plan for advanced features. Current Suite Professional should handle growth to 500 customers.

---

**Learning:** This example shows how technical tool decisions benefit from documenting the trade-offs and review criteria. Notice the focus on both cost and team adoption - important for support platform selection.
