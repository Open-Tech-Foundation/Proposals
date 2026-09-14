# Proposal 0002: Fair Domain Name Registration and Transfer Policy

**Status:** Draft  
**Version:** 1.0  
**Created:** 2026-09-14

---

## Executive Summary

Domain names are globally unique identifiers within the Domain Name System (DNS). Once a domain name is registered, the same name cannot be independently registered by another party for the duration of that registration.

This exclusivity is technically necessary for DNS to function.

However, the same exclusivity enables a secondary business model in which large quantities of desirable domain names can be acquired without an intention to use them, held for extended periods, and later offered to prospective users at prices substantially above ordinary registration and renewal costs.

At sufficient scale, this creates a cycle of:

```text
Bulk Acquisition
      ↓
Warehousing
      ↓
Reduced Public Availability
      ↓
Premium Resale
      ↓
Transfer / Auction
      ↓
Reacquisition
```

This proposal defines this structural pattern as the **Domain Registration Abuse Lifecycle**.

The proposal does not seek to prohibit legitimate domain ownership, long-term registration, multi-domain operation, ordinary domain transfers, or reasonable periods of non-use.

Instead, it proposes structural safeguards intended to reduce the economic incentives and infrastructure that enable industrial-scale speculative domain warehousing.

The principal safeguards are:

1. restrictions on speculative premium pricing for domain-only resale;
2. monthly and annual limits on domain acquisition, including new registrations and ownership transfers;
3. separation of registrar transfer services from speculative aftermarket services;
4. a minimum six-month holding period before beneficial ownership may change; and
5. public re-release of expired domains rather than preferential speculative allocation.

These measures are intended to preserve the ordinary domain lifecycle:

```text
Register
→ Use
→ Renew
→ Transfer
→ Relinquish
```

while discouraging:

```text
Bulk Acquire
→ Warehouse
→ Create Scarcity
→ Demand Premium
→ Flip / Auction
→ Reacquire
→ Repeat
```

---

## 1. Intent

The intent of this proposal is to preserve domain names primarily as **usable Internet identifiers**, rather than allowing access to desirable names to become dominated by speculative accumulation.

The proposal is based on a simple distinction:

> Registering and controlling a domain is necessary for using the Internet's naming system. Systematically acquiring large quantities of names primarily to withhold them from future users and extract scarcity-driven resale premiums is not necessary for the operation of that system.

A registrant may legitimately hold an unused domain for many reasons, including:

- future projects;
- infrastructure;
- email;
- APIs;
- testing;
- migration;
- security;
- redirects;
- brand protection; or
- other lawful purposes.

This proposal therefore does **not** attempt to determine whether a domain is sufficiently active, whether it hosts a website, or whether its use is sufficiently productive.

Instead, it addresses the economic and registration mechanisms that make large-scale speculative accumulation attractive.

The objective is:

> **Preserve registration. Preserve renewal. Preserve legitimate transfer. Reduce industrial-scale speculative warehousing.**

---

## 2. Terminology

For the purposes of this proposal:

### Domain Acquisition

A **domain acquisition** occurs when a person or controlling entity obtains beneficial control of a domain through either:

1. registration of an available domain; or
2. transfer of beneficial ownership of an already registered domain.

### Beneficial Owner

A **beneficial owner** is the person or controlling entity that ultimately exercises control over a domain registration.

Changing registrars, accounts, technical contacts, or service providers without changing ultimate control does not constitute a change of beneficial ownership.

### Domain-Only Resale

A **domain-only resale** is a transaction in which the principal asset being sold is the right to control the domain registration itself.

The sale of a business, software product, trademark, website, customer base, intellectual property, or other independent asset is outside this definition merely because a domain accompanies that transaction.

### Domain Warehousing

For this proposal, **domain warehousing** means systematic accumulation and retention of domain names primarily for future speculative resale rather than ordinary use.

### Speculative Premium

A **speculative premium** is a resale price substantially derived from the scarcity created by prior registration and the prospective buyer's willingness to pay for the domain name itself, rather than ordinary registration, renewal, transfer, or administrative costs.

---

## 3. Domain Registration Abuse Lifecycle

This proposal uses the term **Domain Registration Abuse Lifecycle** for a specific structural pattern.

It does not mean that every unused domain, multi-domain registrant, or domain transfer constitutes abuse.

The lifecycle begins when desirable names are systematically acquired primarily because future users may eventually want them.

### 3.1 Primary Lifecycle

```text
Available Domain
      ↓
Automated / Bulk Acquisition
      ↓
Domain Warehousing
      ↓
Domain Becomes Unavailable to Other Prospective Registrants
      ↓
Premium Listing / Brokerage / Auction
      ↓
Scarcity-Driven Domain-Only Resale
      ↓
Ownership Transfer
      ↓
Potential Further Speculation
```

The registrant does not necessarily create the underlying demand for the name.

Instead, economic value may be captured because exclusive registration prevents another party from obtaining that same name through ordinary registration.

### 3.2 Expiration Recycling Lifecycle

A second path occurs when a warehoused domain is abandoned or expires:

```text
Domain Warehousing
      ↓
Expiration
      ↓
Aftermarket Auction / Preferential Acquisition
      ↓
New Speculative Registrant
      ↓
Domain Warehousing
      ↓
Premium Resale
```

Under this lifecycle, an abandoned domain may move directly from one speculative holder to another without meaningfully returning to ordinary public registration.

### 3.3 Lifecycle Interventions

This proposal addresses multiple stages rather than relying upon a single restriction.

| Lifecycle Stage | Proposed Intervention |
| --- | --- |
| Bulk acquisition | Monthly and annual acquisition limits |
| Transfer-based accumulation | Incoming ownership transfers count as acquisitions |
| Rapid flipping | Minimum six-month holding period |
| Scarcity monetization | Domain-only resale price restriction |
| Registrar-supported speculation | No registrar-facilitated premium aftermarket |
| Expiration recycling | Return expired domains to ordinary public availability |
| Multiple-account circumvention | Common-control enforcement |

---

## 4. Problem Statement

The domain-registration model generally allows an available domain to be obtained by the first eligible registrant that successfully requests it and continues satisfying registration and renewal requirements.

This model works naturally when domains are acquired for use.

The same mechanism, however, permits a participant to:

1. identify large quantities of potentially desirable names;
2. register them before prospective users require them;
3. maintain the registrations without productive use;
4. advertise them through aftermarket platforms;
5. demand scarcity-driven prices substantially above ordinary registration costs;
6. transfer successful speculative acquisitions for profit; and
7. repeat the process at scale.

Modern automation can further reduce the cost of identifying and acquiring potentially desirable names.

At sufficient scale, the participant is no longer merely selecting a domain for future use. The participant is accumulating portions of a globally unique namespace in anticipation of future demand.

This proposal considers the resulting **systematic speculative withholding of domain registration rights** to be a domain-allocation problem worthy of policy consideration.

---

## 5. Existing Policies and Distinction

Existing domain-name policies already address several forms of abusive registration behavior.

This proposal does not seek to replace those mechanisms.

Instead, it addresses a related but distinct structural problem: **large-scale speculative acquisition, warehousing, premium resale, and recycling of domain registration rights.**

### 5.1 Uniform Domain Name Dispute Resolution Policy

The Uniform Domain Name Dispute Resolution Policy (UDRP) addresses certain abusive registrations involving trademark rights.

Among the circumstances considered evidence of bad faith is registration undertaken primarily for the purpose of selling a domain to the owner of the corresponding trademark, or a competitor, for consideration exceeding documented domain-related costs.

This addresses an important category of speculative registration: **cybersquatting involving trademark rights**.

The present proposal addresses a broader structural case.

A generic or otherwise lawful domain may be acquired without infringing another party's trademark and nevertheless be held purely in anticipation of extracting a substantial premium from an unknown future user.

The distinction is:

```text
UDRP

Trademark Rights
      ↓
Bad-Faith Registration / Use
      ↓
Domain Dispute Resolution
```

versus:

```text
This Proposal

Large-Scale Speculative Acquisition
      ↓
Warehousing
      ↓
Scarcity Monetization
      ↓
Structural Registration Safeguards
```

These approaches are complementary.

---

### 5.2 Existing Transfer Policy

Existing domain-transfer policies contain temporary restrictions under certain circumstances.

For example, ICANN policy includes 60-day restrictions associated with certain newly registered domains, inter-registrar transfers, and Changes of Registrant.

Those restrictions principally concern **transfer integrity and security**.

The six-month holding period proposed by this document has a different purpose.

It concerns **beneficial ownership stability** and seeks to discourage rapid speculative flipping.

Therefore:

```text
Existing Transfer Restrictions
      ↓
Transfer Security
      ↓
Protection Against Unauthorized Transfers
```

while:

```text
Proposed Six-Month Holding Period
      ↓
Beneficial Ownership Stability
      ↓
Reduction of Rapid Speculative Flipping
```

A registrar-to-registrar transfer in which beneficial ownership remains unchanged would not restart the proposed six-month holding period.

---

### 5.3 Expired Registration Recovery Policy

Existing expiration policies provide important protections to registrants whose registrations expire.

These include notification, renewal, restoration, and Redemption Grace Period mechanisms.

This proposal preserves those protections.

The public re-release requirement proposed here begins **only after all applicable renewal, grace, redemption, and recovery opportunities have concluded**.

The distinction is:

```text
Existing Expiration Policy
      ↓
Protect Existing Registrant
      ↓
Allow Recovery
```

followed, after final release, by:

```text
This Proposal
      ↓
Ordinary Public Availability
      ↓
Normal Registration Rules
```

The proposal must not be interpreted as shortening or eliminating existing registrant recovery protections.

---

### 5.4 Domain Tasting and Add Grace Period Restrictions

Internet governance has previously addressed another form of large-scale speculative registration known as **domain tasting**.

Domain tasting exploited registration grace mechanisms by allowing large quantities of domains to be registered, evaluated, and unwanted registrations rapidly deleted with limited financial exposure.

Policy and economic changes were introduced to substantially reduce the practice.

Domain tasting and domain warehousing are nevertheless different behaviors.

```text
Domain Tasting

Bulk Register
      ↓
Evaluate
      ↓
Delete Unwanted Domains
      ↓
Recover / Avoid Much of the Cost
```

The lifecycle addressed by this proposal is:

```text
Domain Warehousing

Acquire
      ↓
Retain
      ↓
Restrict Availability
      ↓
Wait for Future Demand
      ↓
Demand Premium
```

The historical response to domain tasting demonstrates an important policy principle:

> Registration behavior can be influenced by changing the economic and operational mechanisms that make large-scale speculation attractive.

This proposal applies that principle to long-term speculative warehousing.

---

### 5.5 Existing Recognition of Warehousing and Speculation

Domain warehousing and speculation are not newly discovered concepts.

ICANN's Registrar Accreditation Agreement framework expressly contemplates Consensus Policies concerning principles for domain allocation and prohibitions on warehousing or speculation by registries or registrars.

This proposal does not therefore claim to introduce the concept of domain-name speculation.

Its intended contribution is different.

Existing provisions principally contemplate particular registry or registrar conduct and other defined registration abuses.

This proposal develops a broader **registrant-level lifecycle framework** addressing:

```text
Acquisition
→ Warehousing
→ Premium Monetization
→ Transfer
→ Expiration
→ Reacquisition
```

and proposes corresponding safeguards at each stage.

---

## 6. Policy Gap

Existing mechanisms primarily address particular concerns:

| Existing Mechanism | Primary Concern |
| --- | --- |
| UDRP | Trademark-based abusive registration |
| Transfer Policy | Secure and authorized transfers |
| Expiration / recovery policies | Protection of existing registrants |
| Add Grace Period restrictions | Domain tasting |
| Registry / registrar contractual provisions | Defined registry and registrar conduct |

This proposal addresses:

| Proposed Mechanism | Primary Concern |
| --- | --- |
| Monthly and annual acquisition limits | Large-scale accumulation |
| Incoming transfers counted as acquisitions | Secondary-market accumulation |
| Domain-only resale restrictions | Scarcity-driven speculative profit |
| No registrar premium aftermarket | Institutional facilitation of speculation |
| Six-month ownership holding period | Rapid flipping |
| Public re-release after expiration | Speculative recycling |
| Common-control enforcement | Circumvention |

No single restriction is expected to solve the problem independently.

The proposal treats speculative warehousing as a **lifecycle**.

---

## 7. Scope

### 7.1 In Scope

This proposal concerns the domain registration right itself.

It applies to:

- new domain registrations;
- acquisition of registered domains;
- beneficial-ownership transfers;
- domain-only resale;
- registrar-operated aftermarket services;
- domain auctions;
- expired-domain allocation;
- acquisition-rate limits; and
- circumvention of those limits.

### 7.2 Out of Scope

This proposal does not regulate the value or sale of:

- businesses;
- companies;
- trademarks;
- websites;
- source code;
- software;
- hosting infrastructure;
- customer relationships;
- content;
- independent intellectual property; or
- other assets transferred together with a business.

A business containing a domain may be sold at any mutually agreed price.

The restrictions concern the **domain registration right itself**.

---

# 8. Policy Requirements

## 8.1 Domain-Only Resale Pricing

A registered domain **MUST NOT** be offered through participating domain-registration infrastructure at an unrestricted speculative premium solely because another party desires the registered name.

A conforming policy implementation **MUST** establish a reasonable maximum domain-only transfer price.

That limit should be derived from objective costs such as:

- current ordinary registration price;
- current ordinary renewal price;
- documented transfer costs; and
- reasonable administrative costs.

The permitted price **MUST NOT** be determined primarily by:

- bidding;
- speculative aftermarket valuation;
- perceived future demand;
- the identity of a prospective buyer; or
- the prospective buyer's willingness to pay.

This restriction applies exclusively to the domain registration right.

It **MUST NOT** establish a price ceiling for independent assets accompanying a domain.

---

## 8.2 Monthly and Annual Acquisition Limits

Domain acquisition **MUST** be subject to both monthly and annual limits.

An initial implementation should evaluate limits such as:

```text
Maximum acquisitions per month: 50
Maximum acquisitions per year:  200
```

These values are policy starting points rather than immutable constants and should be evaluated against real registration data.

An acquisition includes:

```text
New Registration
       OR
Incoming Beneficial-Ownership Transfer
```

For example:

```text
30 new registrations
+ 20 incoming ownership transfers
= 50 acquisitions
```

Renewing a domain already under the same beneficial ownership **MUST NOT** count as a new acquisition.

Moving a domain between registrars while maintaining the same beneficial owner **MUST NOT** count as a new acquisition.

The following similarly **MUST NOT** count as acquisitions when beneficial ownership remains unchanged:

- nameserver changes;
- DNS changes;
- technical-contact changes;
- account migration; and
- infrastructure-provider changes.

---

## 8.3 No Registrar-Facilitated Speculative Aftermarket

Registrars **MAY** provide infrastructure for transferring domain registrations between parties.

Registrars **MAY** support individual and bulk technical transfers.

However, conforming registrars and registries **MUST NOT** operate or directly facilitate services whose principal purpose is speculative premium resale of already registered domain names.

This includes:

- premium aftermarket listings;
- speculative domain auctions;
- bidding systems;
- premium domain brokerage;
- domain-only "make an offer" marketplaces; and
- systems in which registrar compensation increases according to speculative resale value.

Registrars **MAY** charge ordinary:

- registration fees;
- renewal fees;
- transfer fees;
- escrow fees; and
- reasonable administrative fees.

The governing principle is:

> **Transfer infrastructure is permitted. Speculative marketplace infrastructure is not.**

Private parties may independently arrange a lawful transfer subject to the pricing, acquisition, and holding-period requirements of this policy.

---

## 8.4 Minimum Six-Month Holding Period

A newly acquired domain **MUST** remain under the same beneficial ownership for a minimum of **six months** before ordinary transfer to another beneficial owner.

The holding period begins when:

1. an available domain is registered; or
2. beneficial ownership of an existing domain changes.

Following a legitimate ownership transfer, a new six-month holding period begins for the acquiring owner.

The holding period **MUST NOT** restart solely because of:

- renewal;
- registrar-to-registrar transfer;
- nameserver changes;
- DNS configuration changes;
- technical account migration; or
- other changes that do not alter beneficial ownership.

Narrow exceptions **MAY** exist for:

- inheritance;
- court orders;
- insolvency;
- corporate mergers or acquisitions;
- organizational restructuring without meaningful change in ultimate control; and
- other legally required transfers.

Exceptions **SHOULD** be narrowly defined to prevent their use as ordinary speculative-transfer mechanisms.

Existing transfer-security restrictions remain independently applicable.

---

## 8.5 Public Re-Release of Expired Domains

Existing registrants **MUST** retain all applicable expiration, renewal, grace, redemption, and recovery protections.

This proposal does not seek to weaken those protections.

After those protections have concluded and a registration is finally released, the domain **SHOULD** return to ordinary public registration availability.

A conforming registrar, registry, or affiliated aftermarket provider **MUST NOT** receive preferential rights to convert the released domain into a speculative premium auction before ordinary public availability.

The intended lifecycle is:

```text
Registered
    ↓
Expiration
    ↓
Renewal / Grace / Redemption / Recovery
    ↓
Final Release
    ↓
Ordinary Public Availability
```

rather than:

```text
Registered
    ↓
Expiration
    ↓
Registrar / Affiliate Auction
    ↓
Premium Acquisition
    ↓
Warehousing
```

A newly released domain remains subject to the ordinary acquisition limits defined by this policy.

---

# 9. Anti-Circumvention

Acquisition limits **MUST NOT** operate solely on a per-account basis.

Otherwise:

```text
Account A → 200 domains
Account B → 200 domains
Account C → 200 domains
...
```

would trivially defeat the policy.

Where legally and technically feasible, limits should therefore apply to the actual registrant or controlling entity.

Creating additional registrar accounts **MUST NOT** independently multiply an entity's acquisition allowance.

Similarly, distributing acquisitions among multiple registrars **MUST NOT**, by itself, create additional acquisition capacity.

Implementations **SHOULD** develop privacy-preserving mechanisms for identifying common control.

Beneficial-ownership information collected for enforcement **SHOULD NOT** be made publicly accessible merely because it is used for acquisition-limit enforcement.

The objective is to prevent circumvention, not to eliminate registrant privacy.

---

# 10. Legitimate Multi-Domain Ownership

Owning many domains is not inherently abusive.

Organizations may legitimately operate large domain portfolios for:

- products;
- services;
- geographic deployments;
- languages;
- infrastructure;
- email;
- APIs;
- security;
- testing;
- migration;
- redirects; or
- brand protection.

For this reason, the proposal primarily limits the **rate of new acquisition**, rather than imposing an absolute lifetime portfolio ceiling.

A registrant that legitimately accumulates domains over many years may therefore continue maintaining those registrations.

Existing domains **MUST NOT** become non-conforming merely because a registrant's total portfolio exceeds the annual acquisition allowance.

Renewal remains distinct from acquisition.

---

# 11. No Website-Usage Requirement

This proposal intentionally does **not** require a registrant to prove that a domain hosts an active website.

A legitimate domain may exist exclusively for:

- email;
- APIs;
- private infrastructure;
- redirects;
- security;
- development;
- testing; or
- future deployment.

Furthermore, a website-usage requirement would be trivial to circumvent through automatically generated placeholder content.

The proposal therefore regulates **acquisition and speculative-market mechanisms**, not website content.

Registries and registrars should not be required to determine whether a website is sufficiently useful or legitimate.

---

# 12. Relationship to Existing Domain Policy

This proposal should be understood as an extension of an existing Internet-governance principle:

> When characteristics of the registration system create strong incentives for harmful large-scale registration behavior, policy may modify those incentives without eliminating ordinary registration.

Historical intervention against domain tasting provides a useful precedent.

The response did not require authorities to inspect every website and determine whether its registrant had a worthy purpose.

Instead, policy changed the mechanism that made large-scale speculative behavior economically attractive.

This proposal follows the same philosophy.

It does not:

- require proof of website use;
- prohibit large existing portfolios;
- prohibit legitimate domain transfers;
- replace trademark-dispute mechanisms;
- eliminate renewal rights;
- eliminate expiration-recovery protections; or
- prohibit legitimate long-term domain ownership.

Instead, it targets the mechanisms sustaining the **Domain Registration Abuse Lifecycle**.

---

# 13. Benefits

## 13.1 Fairer Access

Desirable domain names have a greater opportunity to remain accessible to prospective users rather than being systematically accumulated in advance.

## 13.2 Reduced Bulk Warehousing

Monthly and annual acquisition limits increase the operational cost of industrial-scale accumulation.

## 13.3 Reduced Rapid Flipping

The six-month holding period reduces incentives to acquire domains primarily for immediate resale.

## 13.4 Reduced Speculative Incentive

Restrictions on domain-only premium pricing reduce the financial incentive to acquire enormous portfolios solely in anticipation of rare high-value sales.

## 13.5 Neutral Registration Infrastructure

Registrars remain registration and transfer providers without simultaneously having an incentive to increase scarcity-driven aftermarket prices.

## 13.6 Fairer Expiration

Domains that are genuinely relinquished can return to ordinary public registration instead of automatically entering another speculative cycle.

## 13.7 Preservation of Legitimate Ownership

Existing registrants retain the ability to renew and maintain legitimately controlled domains.

## 13.8 Preservation of Transferability

Domains remain transferable when legitimate ownership changes are necessary.

## 13.9 No Content Policing

Registries and registrars do not need to determine whether websites are sufficiently active, valuable, or productive.

---

# 14. Trade-Offs and Implementation Challenges

This proposal deliberately introduces restrictions into a currently flexible market and therefore creates implementation challenges.

### 14.1 Identity and Common Control

Cross-registrar acquisition limits require a mechanism for determining whether apparently separate registrations share common control.

Such mechanisms must balance enforceability with privacy.

### 14.2 Legitimate High-Volume Registrants

Some organizations legitimately acquire many domains.

Future implementations may therefore require narrowly defined exemptions or elevated acquisition allowances for demonstrable operational needs.

Such exemptions must not become a general mechanism for speculative portfolio accumulation.

### 14.3 Private Price-Cap Circumvention

Parties could attempt to disguise domain premiums as payments for unrelated services or assets.

No policy can completely eliminate private circumvention.

Enforcement should therefore focus on domain-registration infrastructure and clearly attributable domain-only transactions rather than attempting to regulate every private commercial agreement.

### 14.4 Defining Objective Transfer Costs

A domain-only resale ceiling requires a transparent method for calculating permitted registration, renewal, transfer, escrow, and administrative costs.

This mechanism should be developed separately and periodically reviewed.

### 14.5 Different TLD Governance Models

Generic TLDs, country-code TLDs, sponsored TLDs, and other namespaces may operate under different authorities and contractual structures.

Implementation may therefore vary while preserving the principles established by this proposal.

---

# 15. Conformance

A registry, registrar, or domain-registration ecosystem conforms to this policy when all requirements applicable to its role are satisfied.

At minimum:

1. domain-only resale must not use unrestricted speculative premium pricing;
2. new registrations and incoming beneficial-ownership transfers must count toward acquisition limits;
3. both monthly and annual acquisition limits must exist;
4. renewals must not count as new acquisitions;
5. same-owner registrar transfers must not count as new acquisitions;
6. registrars must not operate or directly facilitate speculative premium aftermarket services;
7. newly acquired domains must remain under the same beneficial ownership for at least six months, except for narrowly defined legitimate exceptions;
8. existing expiration and recovery protections must be preserved;
9. finally released domains should return to ordinary public registration rather than preferential speculative allocation;
10. acquisition limits must contain reasonable anti-circumvention mechanisms; and
11. implementations must not require a public website as proof of legitimate domain use.

---

# 16. Adoption Considerations

The domain-registration ecosystem is distributed across:

- registries;
- registrars;
- ICANN;
- country-code domain authorities;
- resellers;
- registrants;
- hosting providers; and
- other participants.

No single actor necessarily controls the entire lifecycle.

Adoption may therefore occur incrementally.

Registrars can stop operating speculative aftermarket services.

Registries can establish allocation and expiration rules.

Domain authorities can establish holding-period and acquisition policies.

Broader coordination can enable cross-registrar acquisition-limit enforcement.

The numerical limits proposed by this document should be evaluated against real-world registration data before broad deployment.

The initial suggested values:

```text
50 acquisitions per month
200 acquisitions per year
```

are intended as starting points for policy evaluation.

The fundamental principle is more important than the exact numbers:

> Ordinary domain acquisition should remain practical while industrial-scale speculative accumulation becomes economically and operationally unattractive.

---

# 17. Intended Contribution and Novelty

This proposal does **not** claim that domain speculation, warehousing, transfer restrictions, expiration allocation, or registration abuse have never previously been recognized or discussed.

They have.

Existing domain governance already contains mechanisms addressing:

- cybersquatting;
- trademark disputes;
- domain tasting;
- expiration recovery;
- transfer security; and
- certain forms of registry or registrar warehousing and speculation.

The intended contribution of this proposal is the treatment of **large-scale speculative domain warehousing as a complete lifecycle-level allocation problem**.

The proposal links:

```text
Bulk Acquisition
        ↓
Warehousing
        ↓
Reduced Availability
        ↓
Scarcity Monetization
        ↓
Transfer / Flipping
        ↓
Expiration / Aftermarket Recycling
        ↓
Reacquisition
```

and introduces corresponding interventions:

```text
Acquisition Limits
        ↓
Resale Restrictions
        ↓
Aftermarket Restrictions
        ↓
Holding Period
        ↓
Public Re-Release
        ↓
Anti-Circumvention
```

The novelty claimed by this proposal is therefore **not that every individual mechanism is unprecedented**.

Its contribution is the coordinated policy framework and the explicit identification of the **Domain Registration Abuse Lifecycle** as the target of those interventions.

---

# 18. Conclusion

The exclusivity of domain registration is technically necessary.

A globally resolvable domain name must identify one registration at a given point in time.

**Speculative scarcity is not technically necessary.**

When the registration ecosystem permits unrestricted bulk acquisition, long-term warehousing, premium domain-only pricing, registrar-operated speculative marketplaces, rapid flipping, and preferential recycling of expired domains, these mechanisms can reinforce one another.

The result is the **Domain Registration Abuse Lifecycle**:

```text
Bulk Acquire
→ Warehouse
→ Reduce Availability
→ Monetize Scarcity
→ Transfer / Auction
→ Reacquire
→ Repeat
```

This proposal seeks to interrupt that lifecycle while preserving:

```text
Register
→ Use
→ Renew
→ Transfer
→ Relinquish
```

It does not attempt to determine who deserves a particular domain.

It does not attempt to determine whether a website is useful.

It does not prohibit legitimate domain ownership.

It does not prohibit long-term registration.

It does not prohibit legitimate transfers.

Its objective is narrower:

> **Keep the domain-registration system open for registration and legitimate transfer while reducing structural incentives for large-scale speculative control of globally unique names.**

A fair domain-registration system should enable long-term legitimate control of domain names without making systematic speculative withholding one of the most profitable ways to participate in the namespace.

---

## References

The policy concepts and existing mechanisms discussed in this proposal should be considered alongside the current versions of:

- ICANN Uniform Domain Name Dispute Resolution Policy (UDRP)
- ICANN Transfer Policy
- ICANN Expired Registration Recovery Policy (ERRP)
- ICANN Add Grace Period Limits Policy
- ICANN Registrar Accreditation Agreement (RAA)
- applicable registry agreements and TLD-specific registration policies

Where this proposal conflicts with an existing mandatory policy, implementation would require the appropriate policy-development, contractual, or regulatory process rather than unilateral non-compliance with existing obligations.