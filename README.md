# Awesome-Multi-Entity-Subsidiary-Management

# Awesome Multi-Entity & Subsidiary Management

> A curated list of top Multi-Entity and Subsidiary Management platforms — both SaaS/Hosted commercial ERP and accounting suites and open-source alternatives for managing multiple legal entities, intercompany transactions, and consolidated reporting.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [NetSuite OneWorld](#netsuite-oneworld)
  - [SAP S/4HANA Multi-Company](#sap-s4hana-multi-company)
  - [Microsoft Dynamics 365 Multi-Company](#microsoft-dynamics-365-multi-company)
  - [Oracle Fusion Cloud Multi-Org](#oracle-fusion-cloud-multi-org)
  - [Sage Intacct Multi-Entity](#sage-intacct-multi-entity)
- [Open-Source Software](#-open-source-software)
  - [Tryton](#tryton)
  - [Akaunting](#akaunting)
  - [LedgerSMB](#ledgersmb)
  - [Bizuno](#bizuno)
  - [Django Ledger](#django-ledger)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Multi-Entity and Subsidiary Management platforms. These are not open-source but are included as reference points for feature comparison.

### NetSuite OneWorld
**Type:** Cloud ERP with hierarchical subsidiary consolidation
NetSuite OneWorld manages a hierarchical structure of separate legal entities (subsidiaries) organized as a tree that rolls up to a root parent, with a limit of **250 subsidiaries** per account (elimination subsidiaries and inactive subsidiaries do not count toward this limit) [citation:14]. Each subsidiary represents a separate company, with the country defined on the subsidiary record determining the NetSuite edition and tax nexus. Consolidated reporting allows viewing data from multiple subsidiaries on supported reports, with the Subsidiary Context field showing "(Consolidated)" options. Consolidated reports use the Consolidated Exchange Rates table to translate child subsidiary amounts to the parent's base currency, and financial statements include a Cumulative Translation Adjustment (CTA) account to balance multi-currency consolidations [citation:4]. Intercompany transactions require elimination subsidiaries and elimination journal entries to maintain balanced consolidated financials [citation:14].
**Best for:** Mid-market to enterprise organizations needing proven multi-subsidiary consolidation with intercompany elimination and multi-currency translation.

### SAP S/4HANA Multi-Company
**Type:** Enterprise ERP with company code and cross-company processing
SAP S/4HANA manages multiple independent companies through **company codes**, where business transactions are always entered and processed at the company code level [citation:12]. Cross-company code processing enables scenarios like centralized procurement and payment, where individual company codes enter their own invoices while a central company code pays them; clearing entries are automatically posted between participating company codes to record receivables and payables [citation:7]. Cross-company code make-to-order processing allows costs to be collected on a controlling object in one company code while revenue is updated in another, with internal invoices settling the difference [citation:2].
**Best for:** Large enterprises needing deep cross-company code clearing, centralized payment, and intercompany profitability analysis.

### Microsoft Dynamics 365 Multi-Company
**Type:** Enterprise ERP with legal entity isolation and cross-company data sharing
Dynamics 365 Finance uses **legal entities** (companies) as the primary organizational unit, with the ability to add new legal entities after dual-write setup without unlinking environments [citation:3]. **Cross-company data sharing** allows selected tables and fields to be shared across companies using duplicate record or master company policies, with limits of 300 companies and 2 million records per table for duplicate sharing [citation:8]. Financial consolidation supports single-level consolidation, eliminations, minority interest, multiple charts of accounts, different fiscal calendars, and multiple reporting currencies, with source companies remaining the owners of their data [citation:13].
**Best for:** Microsoft-centric enterprises needing flexible data sharing policies and multi-company financial consolidation with diverse fiscal calendars.

### Oracle Fusion Cloud Multi-Org
**Type:** Enterprise cloud ERP with multi-organization access control
Oracle Fusion Cloud supports multi-organization structures through **reference organizations** and centralized security governance. Organizations can govern item security using the definition organization while automatically extending the same access model to associated reference organizations, simplifying administration and improving data consistency across shared product data [citation:1]. This security inheritance applies across Product Management interfaces, search, structures, categories, relationships, integrations, and reporting. Policy-based access control allows granular management of user groups and actions across compartments [citation:6].
**Best for:** Oracle-centric enterprises needing centralized security governance across multiple reference organizations with inherited access models.

### Sage Intacct Multi-Entity
**Type:** Cloud accounting with dimensional multi-entity reporting
Sage Intacct provides multi-entity management with dimensional reporting, allowing transactions to be tagged by entity, department, location, or project. It supports consolidated financial statements across entities with automatic elimination entries and multi-currency translation. Positioned for mid-market organizations wanting flexible, multi-dimensional visibility without the complexity of a full ERP.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Multi-Entity and Subsidiary Management tools. The open-source ecosystem spans **modular ERP platforms with multi-company support**, **accounting applications with multi-company features**, and **framework-level accounting engines**.

### Tryton
**Stack:** Python / PostgreSQL | **License:** GPL-3.0
Tryton is a modular open-source ERP with native **multi-company support** through its Company Module, which allows the business using Tryton to be represented as a single company or multiple companies, recording which employees belong to which companies and their organizational structure [citation:18][citation:24]. Key characteristics include:
- **Modular architecture** covering accounting, sales, inventory, manufacturing, and projects [citation:10]
- **Access rules** applied at the model, action, field, button, and record levels according to user-group membership [citation:10]
- **Three-tier architecture** with an application server, PostgreSQL database, and web or desktop clients [citation:10]
- **Self-hosting or provider-hosted** options available, with a Docker image containing server, modules, and web client [citation:10]

**Trade-off:** The release series is supported for one year (except major versions, which receive five years of long-term support), and on-premises use requires managing the Tryton server and PostgreSQL database [citation:10].
**Best for:** Organizations wanting a modular, genuinely open-source ERP with native multi-company support and granular access controls, accepting the operational overhead of self-hosting.

### Akaunting
**Stack:** PHP / Laravel / MySQL | **License:** GPL-3.0 (core)
Akaunting is a free, open-source online accounting software for small businesses, freelancers, and entrepreneurs, with **multi-user and multi-company support** [citation:16]. Key features include double-entry bookkeeping, invoice and bill management, financial reporting (profit & loss, balance sheet, tax summaries), and document management. It is self-hosted for complete data privacy and control, with a modern interface built on Laravel.
**Best for:** Small businesses and accountants managing multiple clients needing a free, self-hosted accounting solution with multi-company support, accepting a narrower feature set than full ERP platforms.

### LedgerSMB
**Stack:** Perl / PostgreSQL | **License:** GPL-2.0
LedgerSMB is an open-source ERP and accounting application with a notable multi-company feature: **concurrent logins into multiple companies on a single browser** through separate URLs for each company, enabling users to work across multiple tabs or windows [citation:21][citation:27]. It covers the full order-to-cash and procure-to-pay cycle, including quotations, sales and purchase orders, invoicing, payments, inventory, projects, fixed assets, budgeting, and bank reconciliation.
**Best for:** SMBs and accounting teams needing a proven open-source accounting system with the ability to work across multiple companies simultaneously in one browser session.

### Bizuno
**Stack:** PHP / WordPress / MySQL | **License:** Open Source (WordPress plugin)
Bizuno is an open-source ERP/accounting/CRM plugin for WordPress, evolved from PhreeBooks (open-source ERP since 2007) [citation:5]. It supports **multiple warehouses, locations, or even separate businesses from one secure Bizuno instance**, with built-in audit trails, process documentation, and customizable quality reports. It includes US tax calculation via API and integrations with USPS, FedEx, and UPS for real-time quotes, labels, and tracking [citation:5].
**Best for:** WordPress-based businesses wanting an integrated ERP/accounting solution with multi-business support, accepting the WordPress dependency.

### Django Ledger
**Stack:** Python / Django | **License:** MIT (per project)
Django Ledger is a double-entry accounting engine for Django applications, with **multi-tenancy support** as a core feature . It provides a high-level API, hierarchical chart of accounts, financial statements (income statement, balance sheet, cash flow), purchase orders, sales orders, bills, invoices, and financial ratio calculations. It integrates with Django Admin and includes built-in Entity Management UI, making it suitable for developers building multi-entity accounting into their applications.
**Best for:** Django developers wanting to embed multi-tenant accounting capabilities into their applications, accepting the framework-specific dependency and library-level integration.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Multi-Entity Model | Consolidation | Self-Hosted | Best For |
|----------|---------|-------|-------------------|---------------|-------------|----------|
| **NetSuite OneWorld** | Proprietary | Cloud | Hierarchical subsidiaries | ✅ CTA + eliminations | ❌ | Mid-market multi-subsidiary |
| **SAP S/4HANA** | Proprietary | Cloud/On-prem | Company codes | ✅ Cross-company clearing | (On-prem) | Large enterprise intercompany |
| **Dynamics 365** | Proprietary | Cloud | Legal entities | ✅ Multi-calendar/currency | ❌ | Microsoft-centric enterprises |
| **Oracle Fusion** | Proprietary | Cloud | Reference organizations | ✅ Inherited security | ❌ | Oracle-centric enterprises |
| **Tryton** | GPL-3.0 | Python/Postgres | Multiple companies | (Via modules) | ✅ | Modular OSS ERP |
| **Akaunting** | GPL-3.0 | PHP/Laravel | Multiple companies | (Check) | ✅ | SMB multi-client accounting |
| **LedgerSMB** | GPL-2.0 | Perl/Postgres | Multiple companies | (Check) | ✅ | Concurrent multi-company browser |
| **Bizuno** | Open Source | PHP/WordPress | Multiple businesses | (Check) | ✅ | WordPress ERP |
| **Django Ledger** | MIT | Python/Django | Multi-tenant | (Check) | ✅ (Library) | Django embedded accounting |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Multi-Entity or Subsidiary Management tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source.

**Note on the open-source ecosystem:** The multi-entity management space is **dominated by commercial ERP platforms** because consolidation, intercompany elimination, and multi-currency translation are complex accounting requirements that demand mature, audited systems. **NetSuite OneWorld** provides the most documented subsidiary hierarchy model with CTA accounts and elimination subsidiaries [citation:4][citation:14]. **SAP S/4HANA** and **Dynamics 365** offer deep cross-company code processing and data sharing policies for large enterprises [citation:7][citation:8]. On the open-source side, **Tryton** is the most complete ERP with native multi-company support and granular access controls [citation:10][citation:18], while **Akaunting** and **LedgerSMB** provide multi-company accounting for smaller organizations [citation:16][citation:21]. **Django Ledger** is notable as a library for developers wanting to embed multi-tenant accounting into their own applications . No open-source project fully replicates NetSuite's subsidiary consolidation with automatic elimination and multi-book accounting, but Tryton and LedgerSMB cover the core multi-company workflow for self-hosted deployments.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
