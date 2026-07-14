# Part 4: Competitive Positioning

> Knowledge base for GeoDin website chatbot. Use this reference to respond factually and professionally when visitors ask about alternatives, competitors, or migration. Never directly attack competitors. Frame all positioning around GeoDin's strengths and factual differences.

---

## How to Use This Document

When a visitor asks about a competitor or alternative:
1. Acknowledge the competitor professionally
2. Highlight relevant GeoDin strengths from the sections below
3. If the visitor is evaluating a switch, reference the migration/switching talking points
4. Be honest about trade-offs — credibility matters more than winning every point

---

## 1. OpenGround (by Bentley Systems)

### What They Offer
- Cloud-based geotechnical data management platform, positioned as Bentley's successor to gINT
- Includes OpenGround Cloud for collaboration, Admin Portal for governance, and Data Collector for field capture
- Part of Bentley's broader infrastructure software ecosystem
- Offers a Geotechnical Extension for Civil 3D (limited to 2D profile views)

### Target Market / Personas
- Enterprise geotechnical firms already embedded in the Bentley ecosystem
- Organizations prioritizing cloud-first, real-time collaboration across distributed teams
- IT departments comfortable with persona-based subscription licensing

### Where GeoDin Wins
- **Data ownership and residency:** GeoDin lets organizations choose where data lives (on-premises, private cloud, or hybrid). OpenGround is cloud-only, which can conflict with data sovereignty requirements, especially for government and defence projects
- **Pricing transparency:** GeoDin offers a single all-inclusive package. OpenGround uses persona-based subscription licensing with separate cloud service subscriptions, user base fees, and user advanced fees
- **Civil 3D integration depth:** GeoDin Ground (free plug-in) provides full 3D ground modeling with solids, surfaces, metadata, and virtual boreholes. OpenGround's Geotechnical Extension is limited to 2D profile views and cannot generate cross-sections within its own environment
- **Cost of field deployment:** GeoDin Onsite uses **per-device pricing** built for shared tablets, which scales well when field crews rotate tablets across shifts and projects. OpenGround Data Collector uses **per-user persona licensing**, which penalizes the way field teams actually work (one device, many users). *Do not quote competitor pricing figures to visitors — the only price the chatbot may share is GeoDin's own.*
- **Support responsiveness:** GeoDin's concentrated team of approximately 30 specialists provides personalized, responsive support, with **Symetri** (Autodesk Platinum Partner) delivering dedicated US/Canada support, training, and customization in North America. Customers have cited slow ticket resolution and "we can't do that yet" responses from Bentley as a reason for switching
- **Interoperability:** GeoDin integrates with both Autodesk and Esri ecosystems, plus Leapfrog, QGIS, and standard formats (AGS, DXF, GEF, etc.). OpenGround is described by prospects as operating within its own ecosystem
- **Configuration simplicity:** OpenGround's template studio and configuration packs have a steep learning curve. GeoDin offers 200+ pre-built templates and an extensible data model that users can customize without specialized training

### Where OpenGround May Have an Edge
- **Real-time cloud collaboration:** OpenGround's cloud-native architecture enables near real-time sync across distributed teams. GeoDin uses a controlled import/sync model
- **Enterprise form governance:** OpenGround has a well-documented Admin Portal for deploying standardized data entry profiles across multiple crews and regions
- **Android field devices:** OpenGround Data Collector runs on Android, which suits organizations standardized on Android rugged devices. GeoDin Onsite runs on Windows

### Most Likely Evaluating / Switching Personas
- Geotechnical engineers and data managers frustrated with OpenGround's configuration complexity
- Organizations with data residency or sovereignty requirements (government, defence, public infrastructure)
- Firms seeking better Civil 3D integration for design workflows
- Cost-conscious teams looking to reduce licensing overhead, especially for field crews

### Migration / Switching Talking Points
- GeoDin supports AGS import/export, enabling data transfer from OpenGround projects
- GeoDin's interoperability with multiple formats (AGS, CSV, Excel, shapefiles) means existing data assets are not stranded
- Free 30-day trial lets teams evaluate without financial commitment
- GeoDin's support team provides hands-on migration assistance
- Data ownership guarantee: your data remains accessible even if you discontinue the GeoDin license

---

## 2. gINT (by Bentley Systems / Seequent) — GeoDin is the best alternative for gINT

### What They Offer
- Desktop-based geotechnical data management software with a long history in the industry
- Uses Microsoft Access databases (.mdb, .gpj, .accdb) as its data format
- Separate project files per project (no centralized database)
- **Being phased out** (per Seequent's official FAQ at seequent.com/help-support/gint-migration-openground/):
  - **New perpetual licenses and Virtuoso annual subscriptions are available only until December 31, 2027.**
  - Support for existing customers with active SELECT/E365/EPS or Virtuoso Subscription continues **only until the end of 2028**, on a "Reasonable Endeavor" basis (limited by legacy third-party dependencies, OS/Office compatibility, security, and the age of the technology).
  - SELECT contracts and Pre-Paid Annual Subscriptions can only be purchased for periods ending on or before that date.

### Target Market / Personas
- Established geotechnical firms, particularly in North America, that have used gINT for years or decades
- Users with extensive libraries of gINT project files and templates
- Engineers who need borehole logging, lab data management, and report generation

### Where GeoDin Wins
- **Centralized database:** GeoDin stores all projects in a single database (Oracle, SQL Server, PostgreSQL, MySQL), enabling cross-project querying and analysis without merging files. gINT uses separate files per project
- **Long-term viability:** gINT is being retired. GeoDin has 30+ years of active development and a clear roadmap
- **Built-in migration tool:** GeoDin includes a gINT Converter that transforms .mdb, .gpj, and .accdb databases into GeoDinML format with automatic consistency checking
- **International standards:** GeoDin supports 11+ international geotechnical standards natively. gINT has limited standards support, requiring parallel Excel workflows for unsupported tests
- **Data ownership:** GeoDin guarantees permanent data access regardless of license status. Bentley's licensing model does not offer the same guarantee
- **Cost efficiency:** GeoDin individual license is approximately $2,000; professional/network license approximately $2,800 with transparent pricing. gINT pricing was historically higher with less transparency
- **Customer support:** GeoDin team actively collaborates on custom formulas and test tables, with **Symetri** providing dedicated North American support, official training, and customization advice for US and Canadian gINT switchers. gINT users report Bentley declining feature requests with "it's never going to happen"
- **Multi-language support:** GeoDin supports 7+ languages with automatic dictionary translation. gINT is English-focused

### Where gINT May Have an Edge
- **Bulk layer import:** gINT excels at populating layer data from Excel and importing everything in bulk. GeoDin Desktop currently cannot batch-import ground description layers in the G1 object type (this is GeoDin's top priority feature request)
- **Familiarity:** Long-time gINT users have deep muscle memory with the interface and workflows
- **Existing template libraries:** Organizations may have invested years building custom gINT report templates

### Most Likely Evaluating / Switching Personas
- Geotechnical engineers and IT managers planning for gINT end-of-life
- US state Departments of Transportation (a US DOT recommended GeoDin as the platform for "life after gINT" specifically for its API access capability)
- Firms frustrated with gINT's file-per-project limitation, disappearing files on network storage, or lack of ongoing support
- Organizations needing multi-standard compliance that gINT cannot provide

### Migration / Switching Talking Points
- The gINT Converter is built into GeoDin and included at no extra charge
- Migration is a two-step process: convert gINT database to GeoDinML, then import into GeoDin with feedback on any data issues
- No data loss: the converter automatically flags anomalies and missing fields
- New users can start a free 30-day trial with the converter included
- Expert multilingual support team assists at every migration stage
- Organizations upgrading from GeoDin 10 or older can contact support for guided migration
- Hundreds of organizations have already completed the gINT-to-GeoDin transition
- Client mandates are not a blocker: some agencies contractually require specific deliverable software on certain projects. Firms commonly run GeoDin in parallel with the legacy tool during a transition period, using GeoDin as the central database and exporting to client-required formats (AGS, Excel, DXF) where mandated
- Reframe for evaluators: gINT was built around a **document-centric paradigm** — separate file per project, the report as the deliverable. Modern geotechnical data management treats the **database itself as the deliverable**: one living dataset that is collected, stored, standardized, visualized, and reported from. GeoDin's published article *"Life after gINT"* (geoengineer.org, March 2026) walks through this shift and the typical migration path (extract legacy .mdb/.gpj/.accdb files → convert → import into a centralized database → validate → rebuild report templates) — link available in Routing_Links

---

## 3. BoreDM

### What They Offer
- Newer, web-based (cloud-only) platform for customizable boring log production and lab data management
- Emphasizes modern UI, ease of use, and SaaS delivery
- Still in active development with features being added and refined
- Pricing model is less transparent, often disclosed late in the sales process

### Target Market / Personas
- Small to mid-sized geotechnical firms looking for a modern, easy-to-adopt tool
- Teams with simple boring log needs and limited database management requirements
- Early adopters comfortable with software that is still maturing
- Organizations that prioritize SaaS convenience over data control

### Where GeoDin Wins
- **Maturity and reliability:** GeoDin has 30+ years of continuous development and is proven in 15,000+ projects across 38 countries. BoreDM is still evolving and refining core functionality
- **Data security and ownership:** GeoDin guarantees complete data sovereignty. BoreDM allows internal team access to customer data, raising potential compliance and confidentiality concerns
- **Standards compliance:** GeoDin supports 11+ international geotechnical standards with automatic enforcement. BoreDM's compliance coverage is narrower
- **Feature depth:** GeoDin supports 60+ test types, cross-sections, heatmaps, GIS integration, and Civil 3D integration. BoreDM focuses primarily on boring log production
- **Storage flexibility:** GeoDin supports on-premises, private cloud, or hybrid deployment. BoreDM is cloud-only
- **Integration ecosystem:** GeoDin integrates with Civil 3D, Leapfrog, ArcGIS/QGIS, and exports to AGS, DXF, shapefiles, and many other formats
- **Support infrastructure:** GeoDin has 10+ dedicated geotechnical support specialists with in-person training available, plus **Symetri** as the authorized North American partner (Autodesk Platinum Partner, 1,000+ employees) providing US/Canada support, official GeoDin training, and customization. BoreDM's support infrastructure is still developing
- **Transparent pricing:** GeoDin's all-inclusive pricing is published on geodin.com. BoreDM's pricing is often unclear until late in evaluation

### Where BoreDM May Have an Edge
- **Modern UI/UX:** BoreDM has a contemporary web interface that may feel more intuitive for users accustomed to modern SaaS applications
- **Low barrier to entry:** As a cloud-only SaaS tool, BoreDM requires no local installation or database setup
- **Speed for simple use cases:** For organizations with basic boring log needs and limited test types, BoreDM can be faster to get started with

### Most Likely Evaluating / Switching Personas
- Firms that adopted BoreDM but found its feature set insufficient as project complexity grew
- Organizations concerned about data privacy after learning BoreDM's internal access policies
- Teams needing Civil 3D integration, international standards compliance, or advanced visualization that BoreDM cannot provide
- Growing firms that started with simple logging needs but now require a full data management platform

### Migration / Switching Talking Points
- GeoDin supports import from common formats (Excel, CSV, AGS, Access) that BoreDM data can be exported to
- Free 30-day trial with no credit card required
- GeoDin's 10-step onboarding framework and in-person training ensure a smooth transition
- Data remains the customer's property even if they later discontinue GeoDin
- Transparent, published pricing allows direct cost comparison

---

## 4. Geotechnical Modeler (Retired/Legacy — by Autodesk)

### What They Offer
- Was a Civil 3D extension for viewing geotechnical data within the Autodesk design environment
- Has been end-of-lifed and retired by Autodesk
- Provided basic subsurface data visualization within Civil 3D

### Target Market / Personas
- Civil 3D users who needed basic geotechnical data visualization within their design environment
- Infrastructure designers who wanted subsurface context without leaving Autodesk

### Where GeoDin Wins
- **Direct replacement path:** GeoDin Ground is the path forward as Autodesk retires Geotechnical Modeler — built in roadmap collaboration with Autodesk, which selected Fugro/GeoDin as a strategic AEC partner because geotechnical data management requires specialized domain expertise. (Do not claim a formal Autodesk endorsement or designation — none has been announced.)
- **More functionality:** GeoDin Ground already exceeds the capabilities of Geotechnical Modeler, including full 3D ground modeling, virtual boreholes, strata solids, volumetric calculations, and metadata-rich visualization
- **Database-backed, not file-based:** Geotechnical Modeler was essentially a file importer — it visualized CSV/AGS files with no persistent geotechnical data management behind it. GeoDin Ground reads directly from a live GeoDin database, so models update from the single source of truth instead of fragile file exports. Database management is GeoDin's core business
- **Free availability:** GeoDin Ground is a free plug-in available on the Autodesk App Store. No GeoDin license is required for Civil 3D users to view data
- **Autodesk Gold Partnership:** Fugro holds a Gold Partnership with Autodesk, announced at Autodesk University 2024
- **Active development:** GeoDin Ground has shipped regular releases (v1.0.0 in June 2025, v1.5.17 in September 2025 adding virtual logs and Civil 3D imperial-mode support, v1.6.22.0 in June 2026 with Civil 3D 2027 compatibility) with planned features including cross-section generation in Civil 3D, geophysics visualization, and groundwater surfaces
- **Complete ecosystem:** Unlike Geotechnical Modeler which was only a viewer, GeoDin provides the full pipeline from field data collection (Onsite) through database management (Core) to design visualization (Ground)

### Where Geotechnical Modeler Had an Edge
- **None currently relevant:** The product is retired. There is no active alternative to compare against

### Most Likely Evaluating / Switching Personas
- Civil 3D users who lost access to Geotechnical Modeler and need a replacement
- Infrastructure designers looking for better subsurface data visibility in their design environment
- AEC firms wanting to integrate geotechnical data into BIM workflows

### Migration / Switching Talking Points
- GeoDin Ground is free and available on the Autodesk App Store
- No GeoDin license required for Civil 3D users — install and connect to any GeoDin database
- GeoDin Ground is the path forward for geotechnical data in Civil 3D as Autodesk retires Geotechnical Modeler — built in roadmap collaboration with Autodesk and distributed free on the Autodesk App Store
- Works with Civil 3D 2025 and 2026 versions
- Virtual boreholes allow "drilling" anywhere in the 3D model to explore subsurface conditions without physical investigation

---

## 5. Aldoa

### What They Offer
- Cloud-first SaaS platform focused on field-to-report workflow optimization for geotechnical and materials testing
- Mobile-first design (iOS, Android, Web) optimized for technician speed and productivity
- Core strength is rapid report generation from field data
- Includes business workflow integrations (billing, scheduling)
- Primarily US-market oriented with ASTM/AASHTO focus

### Target Market / Personas
- Materials testing firms in the US market
- Technician-heavy organizations prioritizing speed of report delivery
- Small to mid-sized geotechnical firms with high job turnover and fast project cycles
- Report-driven business models where the deliverable is the PDF, not a long-term database

### Where GeoDin Wins
- **Data as a strategic asset:** GeoDin treats field data as a long-term asset that feeds databases, design workflows, and future projects. Aldoa treats field data primarily as an input for reports
- **Database-first architecture:** GeoDin captures data into a structured, standards-compliant geodatabase. Aldoa's primary output is client-ready reports
- **Design integration:** GeoDin integrates natively with Civil 3D, GIS tools (ArcGIS, QGIS), and Leapfrog. Aldoa has no design ecosystem integration
- **International standards:** GeoDin supports 11+ geotechnical standards for cross-border projects. Aldoa focuses on ASTM/AASHTO
- **Data validation depth:** GeoDin Onsite performs schema-based, contextual validation with extensive cross-field logic. Aldoa performs form-level validation
- **Long-term data reuse:** GeoDin enables portfolio analysis, historical querying, and cross-project insights. Aldoa does not support these use cases
- **Sample traceability:** GeoDin provides QR-coded end-to-end sample tracking from field through lab to database. Aldoa tracks samples via forms and photos
- **Data ownership and storage flexibility:** GeoDin offers on-premises, private cloud, or hybrid storage. Aldoa is cloud-hosted SaaS with less sovereignty flexibility
- **Scale and longevity:** GeoDin is proven in multi-decade infrastructure projects across 38 countries. Aldoa targets shorter project cycles

### Where Aldoa May Have an Edge
- **Speed and technician UX:** Aldoa is optimized for rapid field data entry on phones and tablets with a mobile-first design. Getting data to a report is faster
- **Multi-platform field devices:** Aldoa runs on iOS, Android, and Web. GeoDin Onsite is Windows-only
- **Business workflow tools:** Aldoa includes billing and scheduling integrations that GeoDin does not offer
- **Lower learning curve for basic use:** For simple field logging and report generation, Aldoa requires less setup and training
- **Report generation speed:** Aldoa produces client-ready PDFs directly from field data without requiring a separate database/reporting workflow

### Most Likely Evaluating / Switching Personas
- Firms outgrowing Aldoa's report-first approach as they take on larger, more complex infrastructure projects
- Organizations that need design integration (Civil 3D, GIS) and realize Aldoa cannot provide it
- Companies expanding internationally and needing multi-standard compliance beyond ASTM/AASHTO
- Public infrastructure owners or consultants working on long-term projects where data reuse and audit trails are critical

### Migration / Switching Talking Points
- GeoDin supports import from standard formats that Aldoa data can be exported to
- The two tools serve different strategic purposes: if field data is becoming a long-term asset rather than just a report input, GeoDin is the right next step
- GeoDin Onsite at €495/device/year (per-device, not per-user) scales better than Aldoa's per-user/month model when field tablets are shared across crews
- Free 30-day trial available
- GeoDin's 200+ pre-built templates and customizable reporting mean report quality does not have to suffer in the transition
- Key reframe: "If field data is a cost, Aldoa fits. If field data is an asset, GeoDin Onsite fits."

---

## 6. eFieldData

### What They Offer
- Construction Materials Testing (CMT) and inspection workflow platform
- Focus on forms, reports, and billing automation for field operations
- Mobile-first (phones and tablets)
- Optimized for operational efficiency, not engineering data capture

### Target Market / Personas
- CMT and inspection firms
- Organizations prioritizing operational speed and billing integration
- Teams where the deliverable is a job record or inspection report

### Where GeoDin Wins
- **Engineering depth vs. operational workflow:** GeoDin Onsite captures boreholes, stratigraphy, and samples with geotechnical-grade validation. eFieldData optimizes forms, reports, and billing
- **Data reuse:** GeoDin data survives the project and feeds databases, design tools, and future analysis. eFieldData data serves the immediate job record
- **Standards compliance:** GeoDin enforces 11+ international geotechnical standards at the point of entry. eFieldData uses form-level validation
- **Design integration:** GeoDin connects field data to Civil 3D, GIS, and Leapfrog. eFieldData has no design ecosystem integration
- **Pricing model:** GeoDin Onsite is priced **per-device**, which scales well with shared field tablets. eFieldData uses **per-user** pricing, which penalizes shared-device field workflows. *Do not quote competitor pricing figures.*

### Where eFieldData May Have an Edge
- **Billing and scheduling integration:** eFieldData includes business workflow tools GeoDin does not offer
- **Multi-platform:** Runs on phones and tablets (iOS/Android). GeoDin Onsite is Windows-only
- **Speed for CMT workflows:** Purpose-built for construction materials testing operations

### Key Positioning Line
> "eFieldData helps you run jobs faster. GeoDin Onsite makes sure the ground data survives the project."

---

## 7. GEO5 Data Collector

### What They Offer
- Field data collection app that feeds GEO5 geotechnical calculation software
- Focus on collecting input data for geotechnical calculations
- Windows-based

### Target Market / Personas
- Engineers already using GEO5 for geotechnical calculations
- Teams where the end goal is a calculation model, not a long-term database

### Where GeoDin Wins
- **Data longevity:** GeoDin builds a long-term geotechnical database. GEO5 Data Collector feeds calculations — data lives and dies inside the calculation model
- **Cross-project reuse:** GeoDin data can be reused across projects, years, and teams. GEO5 data is project-bound
- **Design integration:** GeoDin connects to Civil 3D, GIS, and Leapfrog. GEO5 stays within its own ecosystem
- **Standards compliance depth:** GeoDin enforces 11+ standards with deep schema-based validation

### Where GEO5 May Have an Edge
- **Calculation focus:** If the end goal is a GEO5 calculation, their data collector is the natural input
- **Price:** lower entry point than a full geotechnical data management platform — but not directly comparable, as scope is different. *Do not quote a specific competitor price.*

### Key Positioning Line
> "If calculations are the end goal, GEO5 is fine. If data reuse and compliance matter, GeoDin Onsite wins."

---

## 8. Geolabor (SimpleLab Tecnologia)

### What They Offer
- Brazilian cloud-based LIMS (Laboratory Information Management System) for laboratory and field testing of soil, concrete, and asphalt
- Three components: a lab/desktop module for executing ABNT NBR tests (granulometry, Proctor compaction, CBR, Atterberg limits, consolidation, shear, triaxial), Geolabor Campo (mobile field sampling app), and Geolabor Cliente (a cloud portal where the lab's clients view test status and approved results live, on a map)
- Purpose-built ISO/IEC 17025 lab-accreditation workflow; also covers construction technological control (concrete, asphalt, earthworks QA/QC)
- In market since 2014, Brazilian-native (PT-BR), with established references in Brazilian mining and construction

### Target Market / Personas
- Accredited commercial testing laboratories in Brazil
- Lab-centric firms whose primary deliverable is approved test results delivered to clients
- Organizations that prioritize a polished client-facing results portal

### Where GeoDin Wins
- **Whole-of-ground vs. lab-first (the category reframe):** Geolabor grew outward from the lab bench — the lab is the system. In GeoDin, the lab is one object type inside the system of record for the *entire* ground-data lifecycle: boreholes/sondagem, CPT/CPTu, rock core, instrumentation and monitoring, environmental, and lab tests in one queryable database. Field and lab data are unified, not reconciled by hand across two systems
- **International standards and interoperability:** GeoDin runs multiple standards (ABNT, ASTM, BS, DIN, EN ISO) in one database and exports validated AGS 4.0.4 / 4.1.1 (mapping to AGS4 Brasil v1.0). Geolabor is focused on Brazilian standards, with documented exports via CSV, PDF, and BI feeds
- **Native pipe into the design and analysis stack:** GeoDin feeds Autodesk Civil 3D via GeoDin Ground (aligned with Brazil's BIM Geotécnico direction), Leapfrog, and ArcGIS/QGIS. Lab data becomes modelling-ready source data, not a PDF attachment
- **Data ownership and residency:** GeoDin runs on the customer's own database — on-premises, private cloud, or offline. Geolabor is vendor-hosted cloud SaaS
- **Portfolio scale and reporting depth:** cross-project querying at enterprise scale plus 200+ pre-built report templates

### Where Geolabor May Have an Edge
- **Client-facing live results portal:** Geolabor Cliente lets a lab's customers watch test status and approved results arrive in real time on a dashboard/map. This is a genuinely strong capability — acknowledge it honestly. *The chatbot must not claim GeoDin matches this portal; if a visitor's core need is a live client-results portal, route them to sales for a current-capability conversation*
- **ISO/IEC 17025 accreditation workflow** purpose-built for accredited labs
- **Construction technological control breadth** (concrete/asphalt/earthworks QA/QC) beyond pure geotech
- **Brazilian-native:** PT-BR product, local standards depth, mature local user community

### Most Likely Evaluating / Switching Personas
- Brazilian consultancies and asset owners whose ground data spans field investigation *and* lab, and who want one source of truth instead of a lab silo plus a separate field system
- Firms working with international clients who need AGS or multi-standard interoperability
- Teams feeding Leapfrog, Civil 3D, or GIS who need modelling-ready data rather than CSV/PDF exports

### Migration / Switching Talking Points
- The two products can be framed as answering different questions: Geolabor manages the lab; GeoDin is the system of record for the whole ground. Some organizations evaluate them for different layers of the same workflow
- GeoDin imports CSV and Excel, so existing lab datasets are not stranded
- GeoDin supports Portuguese (interface and support), and Fugro Brasil uses GeoDin operationally with Brazilian standards (NSPT, CPT)
- Free 30-day trial, no credit card required

### Key Positioning Line
> "Geolabor is a strong lab system. The real question is whether your whole ground data — sondagem, CPT, instrumentation, lab, environmental — lives in one queryable source of truth that feeds your design and analysis tools, or whether the lab is one silo and the field is another."

---

## 9. Leapfrog (by Seequent / Bentley)

### What They Offer
- Dedicated 3D geological modelling software with advanced implicit modelling, widely used for subsurface visualization
- Collaboration and model sharing require Central, a separate add-on product
- Part of the Seequent portfolio (owned by Bentley Systems)

### How GeoDin Relates to Leapfrog
Leapfrog is primarily a **modelling tool**, not a geotechnical data management platform — so the two are often complementary rather than direct rivals.

- **Interoperability, not lock-in:** GeoDin has a dedicated Leapfrog export button that formats borehole data into the structure Leapfrog expects. Teams that model in Leapfrog can keep doing so with GeoDin as the database behind it
- **Modelling inside Civil 3D:** For teams in the Autodesk ecosystem, GeoDin Ground provides 3D ground modelling (borehole sticks, surfaces and volumes, virtual boreholes) directly inside Civil 3D — no separate modelling package or export step needed
- **Cost model:** Leapfrog requires its own licensing, and collaboration adds Central as a separate product. GeoDin Ground is a free Civil 3D plug-in. *Do not quote competitor pricing figures — describe the model only.*
- **Single source of truth:** GeoDin keeps the live database as the system of record; models are regenerated from current data rather than maintained as separate file-based projects

### Where Leapfrog Has an Edge
- **Modelling depth:** Leapfrog's implicit 3D geological modelling is more advanced than GeoDin Ground's current surfaces/volumes approach. For complex standalone geological modelling, it remains a strong dedicated tool — and GeoDin exports to it

### Migration / Switching Talking Points
- Teams don't have to choose: GeoDin manages the data and exports to Leapfrog whenever a Leapfrog model is needed
- For Civil 3D-based design workflows, GeoDin Ground can cover much of the day-to-day 3D ground-model need without leaving the design environment

---

## Summary Comparison Table

| Dimension | GeoDin | OpenGround | gINT | BoreDM | Aldoa | eFieldData | GEO5 Data Collector | Geolabor |
|---|---|---|---|---|---|---|---|---|
| **Status** | Active, 30+ years | Active | Retiring (Dec 2028) | Active, early stage | Active | Active | Active | Active, ~10 years (Brazil) |
| **Core purpose** | Field-to-design ecosystem | Cloud collaboration | Desktop geodata mgmt | Modern boring logs | Field-to-report speed | CMT & inspection ops | Feed GEO5 calculations | Lab/LIMS & construction QC |
| **Data mindset** | Long-term asset | Cloud-managed | File-based | Cloud-managed | Operational input | Job record | Calculation input | Lab results & client reporting |
| **Deployment** | On-prem / cloud / hybrid | Cloud-only | Desktop (Access) | Cloud-only | Cloud-only (SaaS) | Cloud-only | Windows | Cloud-only (SaaS) |
| **Data ownership** | Full customer control | Vendor-hosted cloud | Local files | Vendor access possible | Vendor-hosted | Vendor cloud | Local files | Vendor-hosted cloud |
| **International standards** | 11+ standards | Limited | Limited | Narrow | ASTM/AASHTO | Form-level | Limited | Brazilian (ABNT/NBR) focus |
| **Civil 3D integration** | Native 3D (free plug-in) | 2D profiles only (paid) | None | None | None | None | None | None published |
| **Field data collection** | Onsite (per-device, Windows) | Data Collector (per-user, Android) | None | N/A | Mobile-first (iOS/Android/Web) | Mobile (iOS/Android) | Windows | Mobile field app (Campo) |
| **Pricing model** | Per-device (Onsite) / per-license (Core) | Persona subscriptions + cloud fees | Legacy | Less transparent | Per-user SaaS | Per-user/month | Per-user/license | *Do not quote.* |
| **Approx. Core license (GeoDin only — do not quote competitor figures)** | €2,394.70 individual / €3,395 network | *Persona-based subscription + cloud fees — do not quote.* | Legacy (no new sales) | *Do not quote.* | *Do not quote.* | N/A | N/A | *Do not quote.* |
| **Approx. field app cost (GeoDin only — do not quote competitor figures)** | €495 (ecosystem) / €695 (standalone) per-device/year | *Per-user persona licensing — do not quote figures.* | N/A | N/A | *Per-user SaaS — do not quote figures.* | *Per-user — do not quote figures.* | *Do not quote.* | *Do not quote.* |
| **Scales well in field** | Yes (shared devices) | No (per-user) | N/A | N/A | No (per-user) | No (per-user) | Neutral | Not documented |
| **gINT migration tool** | Yes (built-in converter) | Partial (Bentley ecosystem) | N/A | No | No | No | No | No |
| **Multi-language** | 7+ languages | Limited | English-focused | Limited | English (US) | Limited | Limited | Portuguese (PT-BR) |
| **Database architecture** | Centralized SQL (Oracle, PostgreSQL, SQL Server) | Cloud database | File-per-project | Cloud | Cloud | Cloud | Local | Cloud |
| **Offline capability** | Full (30-day validation) | After initial sign-in | Full | Requires connection | Requires connection | Partial | Yes | Not documented |
| **Data reuse across projects** | Yes (core value) | Limited (ecosystem-bound) | No (file-per-project) | Limited | Limited | Limited | No | Lab-scoped |

---

## General Competitive Principles for the Chatbot

1. **Never disparage a competitor by name.** Instead, describe GeoDin's strengths in the relevant area.
2. **Be honest about trade-offs.** If a visitor has a need where a competitor genuinely excels (e.g., Aldoa for rapid mobile reporting, OpenGround for real-time cloud collaboration), acknowledge it and explain what GeoDin offers in that area.
3. **Lead with the visitor's need, not the competitor's weakness.** Ask what problem they are trying to solve, then show how GeoDin addresses it.
4. **Migration is not disruptive.** Always emphasize that GeoDin has proven migration paths, built-in converters (for gINT), and standard format support.
5. **Data ownership is a differentiator, not an attack.** When discussing data control, frame it as "GeoDin gives you choice" rather than "competitor X locks you in."
6. **Free trial removes risk.** Always mention the 30-day free trial with no credit card required.
7. **Credibility anchors:** 30+ years of development, 15,000+ projects, 38 countries, Autodesk Gold Partnership, clients like Arcadis, Siemens, CDM Smith, and TenneT.
8. **The system-of-record reframe.** When a visitor weighs GeoDin against a tool that wins on a single feature (mobile speed, modern UI, a results portal), acknowledge the feature honestly, then reframe around GeoDin's strength: "If the deliverable is the point, a focused tool can fit. If the ground data itself is the point — reused across projects, teams, and decades — you want a system of record you own." Useful follow-up question: where should the data live, and who should control it in ten years? Always frame this as GeoDin's strength, never as the competitor's flaw.

---

## Gaps & Review Notes

### OpenGround
- **Pricing data is approximate.** The ~$999/user/year figure comes from a single UK public procurement note. Actual pricing varies by contract and region. Consider verifying current pricing or removing the specific figure if it risks being inaccurate.
- **OpenGround Data Collector platform coverage is uncertain.** Source materials focus on Android; it may also support iOS or web access. Worth verifying.
- **OpenGround's roadmap is not covered.** Bentley may have announced new features or integrations that close some of the gaps described here. This section should be reviewed periodically.

### gINT
- **End-of-life date.** The sources reference "sunset date pushed back to 2027" in one place and "support extended only until December 31, 2028" in another. The chatbot currently uses the December 2028 date from the most recent LinkedIn post. This should be verified against Bentley's official communications.
- **BS standards support for GeoDin.** One source says BS standards support is "coming soon" — verify whether this has shipped as of March 2026.

### BoreDM
- **Data is the thinnest of all competitors.** The comparison file reads more like a positioning document than a detailed feature comparison. Specific BoreDM features, pricing tiers, supported test types, and integration capabilities are not detailed in any source. Consider conducting a fresh competitive review or requesting updated intelligence.
- **BoreDM's internal data access claim** (that their team can access customer data) should be verified. If this has changed, the positioning should be updated.
- **No information on BoreDM's market traction,** customer base size, or recent product updates.

### Geotechnical Modeler
- **This section is solid** since the product is retired and GeoDin Ground is the replacement path (no formal Autodesk endorsement — see Central_Reference §5 override). No gaps identified.

### Aldoa
- **Comparison is field-collection focused.** The source document (GeoDin Onsite vs. Aldoa) covers field data collection in depth but does not address Aldoa's full platform capabilities (e.g., lab management, enterprise features, integrations beyond billing/scheduling).
- ~~**Aldoa's pricing is not documented.**~~ **PARTIALLY RESOLVED:** Estimated at ~€300-600/user/year from competitive cheat sheet. Still approximate — verify against current Aldoa pricing.
- **Aldoa's market presence and customer base** are not detailed beyond "strong adoption in US market." Specific customer references or market share data would strengthen this section.
- **Aldoa's standards support** may extend beyond ASTM/AASHTO. Worth verifying.

### Geolabor
- **Live client-results portal parity is an open question.** Geolabor's standout feature is its client-facing portal showing live test status/results. Confirm GeoDin's current capability and roadmap before the chatbot implies parity — until confirmed, the chatbot must not claim GeoDin matches it and should route portal-centric prospects to sales.
- **Geolabor's AGS support is unverified.** Documented exports are CSV / PDF / BI feeds. Do not assert that Geolabor lacks AGS; instead state positively that GeoDin's AGS workflow is native and validated.
- Intelligence dates from June 2026 Brazil tech demos. Review as the Brazil go-to-market matures.

### General
- ~~**Leapfrog (Seequent/Bentley)** appears in the competitive positioning transcripts but is not one of the five requested competitors. Some visitors may ask about Leapfrog. Consider adding a brief section or note for chatbot reference.~~ **RESOLVED (2026-06):** Section 9 (Leapfrog) added with complementary-tool framing.
- **SoilCloud** — appears on prospect shortlists alongside GeoDin and OpenGround (e.g., port-infrastructure evaluations). If asked, position on GeoDin's maturity and longevity (30+ years, 15,000+ projects) without commenting on SoilCloud's features — detailed comparison data is not available.
- **HoleBASE** — occasionally mentioned as an interim tool between gINT and OpenGround. No detailed comparison exists; respond with GeoDin's own strengths and offer a conversation with the team.
- **All competitor information should be reviewed quarterly** to catch product changes, pricing updates, and new feature releases. Sources are dated primarily from late 2025 and early 2026.
