# Part 1: Value Proposition & Personas

> Chatbot knowledge base for GeoDin website.
> Generated: 2026-03-16

---

## 1. What GeoDin Is

GeoDin is a geotechnical data management software suite built by geotechnical engineers. It provides a unified platform to collect, store, process, visualize, and report geotechnical and geological data across the entire project lifecycle -- from field data collection through database management to design integration.

### The GeoDin Suite consists of three integrated products:

- **GeoDin (Core):** The central desktop platform for creating geodatabases, managing borehole and test data, running geotechnical calculations, generating reports, and ensuring standards compliance.
- **GeoDin Onsite (free with subscription):** A Windows-based field data collection app that digitizes paper-based logging with real-time validation, QR sample labeling, and seamless import into GeoDin Core.
- **GeoDin Ground (free):** An Autodesk Civil 3D plugin that visualizes subsurface data directly inside the design environment, enabling geotechnical-to-civil design collaboration.

### Key facts:

- 30+ years of development history (founded ~1995 in Berlin, Germany)
- Owned by Fugro, a global geo-data company with 11,000+ employees across 60 countries
- Used in 15,000+ geotechnical projects across 38+ countries
- Supports 11 international geotechnical standards (ASTM, DIN, BS 5930, EN ISO, GOST, NEN, ABNT, and others)
- Available in 7+ languages (English, German, French, Italian, Spanish, Portuguese, Turkish, Russian)
- Official Autodesk strategic AEC partner (Gold Partnership)
- Free 30-day trial, no credit card required

---

## 2. Core Value Proposition

### The problem GeoDin solves:

Geotechnical data is one of the biggest contributors to cost overruns and design rework in infrastructure projects. An estimated one-third of infrastructure failures are attributed to insufficient ground data in the design process. Yet geotechnical data is commonly managed through fragmented workflows -- scattered Excel files, static PDFs, legacy software with proprietary formats, and paper field logs that must be manually re-entered.

### What GeoDin delivers:

- **Single source of truth:** One centralized database for all geotechnical data across projects, replacing fragmented files and spreadsheets.
- **Full data ownership:** Customers control where data is stored (on-premises, company network, or cloud). GeoDin never accesses, hosts, or resells customer data.
- **End-to-end workflow:** Field collection (Onsite) to database management (Core) to design visualization (Ground) -- one connected pipeline with no data re-entry.
- **Standards compliance built in:** Automatic enforcement of 11+ international geotechnical standards at every step, from field entry through reporting.
- **Interoperability:** Open data philosophy with export to AGS, Leapfrog, Civil 3D, ArcGIS, QGIS, Excel, CSV, DXF, shapefiles, and more. Not a closed ecosystem.
- **Data longevity:** Data stored in standard SQL databases (PostgreSQL, Oracle, MS SQL Server, or MS Access). Users retain access to their data regardless of licensing status.

---

## 3. Target Personas

### 3.1 Geotechnical Consultant

**Role:** Works in geotechnical engineering and consulting with 17+ years of experience. Industries: infrastructure, environmental projects, mining, large-scale construction. Balances office-based analysis and on-site investigation. Daily tools: geotechnical software, GIS tools, borelog analysis tools, PDF reports, project management software.

**What matters most:**
- Provide expert geotechnical insights to project teams and clients
- Ensure data accuracy, consistency, and compliance with regional standards
- Help stakeholders interpret complex geotechnical data for decision-making
- Digitize geotechnical reports efficiently to reduce time spent on manual processes
- Ensure site investigations are properly documented and accessible
- Reliable formulas and calculations with full transparency (no black-box approach)

**How GeoDin addresses their pain points:**
- 60+ preconfigured geotechnical test tables (Atterberg limits, SPT, CPT, triaxial, shear strength, permeability, particle size distribution, and more) with automated calculations
- 200+ preconfigured report templates for borehole logs, CPT plots, cross-sections, and tabular reports
- Auto-generated ground descriptions that are standard-compliant based on entered properties
- Full visibility on all formulas -- users can inspect, verify, and add custom formulas
- Multi-standard support: work in ASTM for a US project and DIN for a German project within the same database
- Built-in gINT converter for migrating legacy data without starting from scratch
- Cross-section tool with both freehand and automatic layer boundary construction
- Data stored once, reused across multiple report types and visualizations

---

### 3.2 Geotechnical Project Manager

**Role:** Works in project planning and construction management with 18+ years of experience. Industries: infrastructure, real estate development, large-scale civil projects. Mostly office-based but frequently in contact with engineers and field teams. Point of contact between client/asset owners and downstream deliverables. Daily tools: project management software, budgeting tools, dashboards, geotechnical reports.

**What matters most:**
- Ensure that geotechnical data is reliable and actionable for project planning
- Reduce delays and cost overruns by having early risk assessments
- Make sure the team follows data security and regional compliance
- Access customizable, easy-to-read geotechnical reports
- Increase trust in geotechnical insights by improving clarity and consistency
- Efficient collaboration between geotechnical, design, and environmental teams
- Cost control and predictable workflows

**How GeoDin addresses their pain points:**
- Single centralized database eliminates version control issues and data silos; one database can hold multiple projects with tens of thousands of boreholes
- Cross-project querying enables portfolio-level analysis without manual merging
- Standards compliance is enforced automatically, not dependent on individual user discipline
- Full data traceability from field collection through to final deliverable
- Floating/network licenses reduce cost: buy N licenses, share across a larger team with N concurrent users
- Transparent pricing with no hidden add-ons; GeoDin Onsite and Ground included at no extra cost
- Demonstrated at scale: SuedLink project (700 km, 3,600+ boreholes, 5 companies sharing one database)

---

### 3.3 IT / Data Manager

**Role:** Manages software deployment, database infrastructure, data security, and integration with the organization's broader technology stack. Responsible for data residency and compliance.

**What matters most:**
- Data security, residency, and privacy compliance
- Flexible deployment options (on-premises vs. cloud)
- Integration with existing enterprise systems (CAD, GIS, CDE)
- Scalable database architecture
- Minimal vendor lock-in

**How GeoDin addresses their pain points:**
- Full customer-controlled data residency: deploy on-premises (own network), private cloud, or Azure -- GeoDin does not host or access customer data
- Standard SQL database backends: PostgreSQL, Oracle, MS SQL Server, or MS Access -- no proprietary data formats
- Client-server databases support unlimited size (hundreds of GB) and concurrent multi-user access
- Can run completely offline on a local machine (suitable for defense/high-security environments)
- Data remains accessible regardless of licensing continuation -- no vendor lock-in on your own data
- Integration ecosystem: Autodesk Civil 3D, ArcGIS/QGIS, Leapfrog, AGS format, plus CSV/Excel/DXF/shapefile exports
- REST API under active development (targeted late 2026) for external system integration
- Windows-based deployment (Windows 10/11); minimal hardware requirements (1 GHz processor, 1 GB RAM)
- Two licensing models: single-user (device-bound) and network/floating (concurrent sessions)

---

### 3.4 Lab Manager

**Role:** Manages laboratory testing workflows, receives field samples, performs geotechnical tests, and returns results to the project database.

**What matters most:**
- Clear sample identification and traceability
- Efficient data entry for test results
- Accurate, validated calculations
- Integration between field sample records and lab test results

**How GeoDin addresses their pain points:**
- QR-coded sample labels printed in the field (via GeoDin Onsite) provide full chain-of-custody traceability from field to lab -- scan the QR code to identify project, location, depth, and sample type
- 50+ preconfigured test tables with automated calculations and built-in validation rules
- Calculated fields shown in distinct color with fully transparent formulas; no black-box results
- Custom test tables can be created for non-standard tests or local variants
- Sample status tracking: Scheduled, Executed, Completed
- Parent-child sample relationships supported (sub-samples/specimens linked to parent samples)

---

### 3.5 Civil Engineer

**Role:** Works in structural and infrastructure design with 15+ years of experience. Industries: public works, transportation, urban development. Mostly office-based but collaborates with geotechnical teams. Daily tools: CAD software, GIS, PDF reports, engineering simulations.

**What matters most:**
- Receive accurate geotechnical insights to make design decisions
- Work with a modern and flexible reporting system
- Ensure data security and regional compliance
- Choose customizable report layouts to fit different projects
- Reduce the learning curve of new tools for faster adoption
- Access to subsurface data without leaving the design environment

**How GeoDin addresses their pain points:**
- GeoDin Ground is a free Civil 3D plugin that displays borehole data, lithological layers, CPT results, and samples directly in the 3D design model
- Eliminates the traditional workflow of emailing multi-hundred-page PDF geotechnical reports; designers connect directly to the GeoDin database
- Virtual Logs feature: click anywhere in the Civil 3D model to explore subsurface information without drilling
- Color-coded borehole sticks grouped by ground units for clear visual interpretation
- Adjustable surfaces and volumes between boreholes for layer interaction analysis
- Volumetric calculations: intersect tunnel or road volumes with ground layers to estimate quantities of each soil type for cost analysis
- Attached documents (PDFs, photos, reports) accessible directly from within Civil 3D
- Replaces Autodesk's retired Geotechnical Modeler with more functionality

---

### 3.6 Environmental Consultant

**Role:** Manages environmental monitoring data (groundwater, soil contamination), conducts site characterizations, and produces compliance reports. Works with environmental boring logs and monitoring data.

**What matters most:**
- Structured management of monitoring data over time (groundwater levels, contaminant concentrations)
- Standards-compliant reporting
- Ability to visualize spatial distribution of environmental data
- Integration with GIS tools for spatial analysis and stakeholder communication

**How GeoDin addresses their pain points:**
- Supports environmental use cases: site characterization, groundwater monitoring, soil sampling, delineation of spills, historic fill delineation
- Water level monitoring data stored with date/time, depth, and multiple parameters for piezometer records
- Thematic maps with embedded GIS tools, WMS/TMS support, and export to common GIS formats (SHP, KML, GML, GeoJSON)
- Export to ArcGIS (feature layers with borehole log attachments) and QGIS (dedicated plugin available)
- Cross-project database enables long-term environmental monitoring across multiple campaigns
- Multi-standard compliance ensures regulatory reporting requirements are met
- Real-world deployment example: Doha water monitoring system with live data streaming to GeoDin databases

---

### 3.7 Geotechnical Field Operator

**Role:** Works in geotechnical site investigations with 10+ years of experience. Work environment is either in the field or office-based, often working with borehole data and ground assessments. Daily tools: borehole logs, geotechnical software, PDFs, GIS tools.

**What matters most:**
- Ensure accurate and consistent geotechnical data for project planning
- Efficiently digitize borelog data and minimize manual data entry
- Work seamlessly across multiple projects and locations
- Have access to safe and secure data storage
- Make sure data can be used in calculations for risk assessment
- Works offline in areas without connectivity
- Quick sample labeling and tracking

**How GeoDin addresses their pain points:**
- GeoDin Onsite replicates familiar paper forms as digital interfaces on Windows tablets
- Touchscreen or keyboard input; designed for field conditions
- Full offline capability for up to 30 days without internet
- Real-time data validation: checks data types, completeness, and enforces conditional rules during entry
- QR code sample label printing with portable Bluetooth-compatible printers (e.g., Zebra) -- prevents sample mix-ups from field to lab
- GPS coordinate capture built in
- Photo capture linked directly to data records
- Standard-compliant soil description dictionaries enforce correct entry at the source -- described as a "foolproof system"
- Data flows directly into GeoDin Core, eliminating manual re-entry by office staff

---

### 3.8 GIS Specialist

**Role:** Manages spatial data, creates maps, and integrates geotechnical data with broader spatial datasets for project-wide visualization and stakeholder communication.

**What matters most:**
- Interoperability with GIS platforms (ArcGIS, QGIS)
- Ability to export geotechnical data in standard spatial formats
- Spatial context for borehole and monitoring data
- Web map integration

**How GeoDin addresses their pain points:**
- Export to SHP, KML, GML, GeoJSON, and MDB/ACCDB for direct use in ArcGIS and QGIS
- Dedicated QGIS plugin available in the QGIS plugin library
- Data can flow from GeoDin through Civil 3D into ArcGIS Online as feature layers with borehole log attachments
- Built-in thematic mapping with WMS and TMS support for web map overlays
- Support for raster and vector data (TIFF, JPG, ECW, SHP)
- Import of shapefiles and GeoJSON for spatial reference
- Direct integration with Esri ArcGIS under active development (planned late 2026/early 2027)

---

## 4. Industries and Use Cases

GeoDin serves multiple industries, each with specific data management needs:

- **Infrastructure projects:** Rail, road, bridge, and tunnel construction requiring subsurface data integrated with civil design
- **Environmental monitoring:** Groundwater monitoring, soil contamination tracking, and regulatory compliance reporting
- **Land reclamation:** Managing geotechnical data for land development and remediation projects
- **Tunnel monitoring:** Subsurface characterization and ongoing monitoring for tunneling operations
- **Transportation:** Highway and rail projects, departments of transportation (DOT) data management
- **Marine/ports:** Port infrastructure and offshore geotechnical data (growing market, especially in US)
- **Construction/contracting:** Estimating quantities of unsuitable soils and pavement thicknesses during pre-construction bidding

---

## 5. Competitive Positioning Summary

GeoDin positions itself as an alternative to:

- **gINT (Bentley):** Being phased out (support extended to Dec 2028 with limited support). GeoDin offers a dedicated gINT converter and centralized database vs. gINT's per-project file approach.
- **OpenGround (Bentley):** GeoDin offers customer-controlled data residency, free Civil 3D integration (vs. expensive limited licenses), cross-section generation, and more responsive support.
- **BoreDM:** GeoDin positions as more mature and feature-rich with 30 years of development.
- **Geotechnical Modeler (Autodesk, retired):** GeoDin Ground is its designated replacement with greater functionality.

Key differentiators across all competitors:
- Full data ownership and customer-controlled residency
- Free Civil 3D plugin (GeoDin Ground) and free field app (GeoDin Onsite) included
- 30+ years of domain expertise backed by Fugro's global geotechnical credibility
- 11+ international standards supported in a single platform
- Transparent pricing displayed on website; no hidden costs
- Open interoperability philosophy vs. closed ecosystems

---

## Gaps & Review Notes

1. **Environmental consultant persona depth:** The sources confirm GeoDin supports environmental use cases (groundwater monitoring, contamination delineation, site characterization) but lack detail on specific environmental test types, contaminant tracking features, or regulatory frameworks supported. If environmental consulting is a significant market segment, this persona section would benefit from more specific capability detail (e.g., which environmental standards are supported, what contaminant data types exist).

2. **Lab Manager workflow completeness:** The sources explicitly note that lab workflow (scheduling, status tracking, automated distribution to lab teams) is a known gap. The persona section reflects what GeoDin can do today, but the chatbot should be aware that lab management is not a core strength and prospects with heavy lab workflow needs may find it insufficient.

3. ~~**Pricing details may change**~~ **RESOLVED:** Verified pricing as of 2026-03-16: Individual License €2,394.70/$2,011, Professional (shared) License €3,395/$2,850, Educational €100. GeoDin Onsite: €695 standalone or €495 ecosystem discount. Standard Onboarding: €1,200 (3h training + 1h follow-up). Custom training/consulting: case-by-case.

4. **GIS Specialist persona:** This persona was inferred from the feature set (QGIS plugin, ArcGIS export, thematic mapping) rather than being explicitly called out as a target user in any source. Verify whether GIS specialists are a meaningful buying persona or whether GIS features are primarily used by geotechnical engineers themselves.

5. **Government/public authority persona missing:** The sources mention German ministries, municipalities (Berlin, Hanover), and US DOTs as users, but no dedicated persona was created for government buyers. If public sector procurement is a key channel, consider adding a persona covering their specific needs (contractual data handover requirements, long-term data archiving, standardization mandates).

6. **Academic/education persona missing:** An educational license is available at €100 for accredited institutions. If this is a meaningful market, a persona could be added.

7. **Mining industry:** GeoDin mentions mining applications in passing but no detail was found on specific mining-oriented features or workflows. If mining is a target vertical, this needs expansion.

8. **New UI (Beta design mode):** A completely reimagined UI is announced for first half 2026. The chatbot should be aware of this to manage expectations about the current interface, which is acknowledged as having legacy UX friction points.

9. **US market specifics:** North American sales and support are handled exclusively through Symetri (partner). The chatbot should know whether to direct US prospects to Symetri or to GeoDin directly.

10. **Mobile platform limitation:** GeoDin Onsite is Windows-only (not iOS or Android). This is a frequent question topic -- the chatbot must be clear about this to avoid misleading prospects who expect a mobile app.
