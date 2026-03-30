# Part 2: GeoDin Product Suite Overview

> Chatbot knowledge base — structured reference for AI-assisted responses.
> Last updated: 2026-03-16

---

## 1. GeoDin Core

### What It Is
GeoDin Core is the central desktop platform for geotechnical data management. It serves as the single source of truth for all project geodata — storing, processing, validating, visualizing, and reporting borehole and geotechnical test data. It is a Windows-based application with 30+ years of development history, originally built by geotechnical engineers.

### Key Capabilities
- **Geodatabase creation:** Build structured databases containing projects, boreholes, samples, test results, well designs, water levels, and data sequences (CPT, SPT, etc.)
- **Data hierarchy:** Database > Project(s) > Object(s). A single database can hold dozens of projects and tens of thousands of boreholes.
- **Standards compliance:** Supports 11+ international geotechnical standards out-of-the-box: ASTM, BS 5930, DIN, EN ISO, NEN, ABNT, GOST, KA5, ONORM, and others. Auto-generates standard-compliant ground descriptions from entered soil properties.
- **60+ pre-built test types:** Water content, Atterberg limits, SPT, triaxial, oedometer, particle size distribution, CPT, RQD, and many more. Each test table includes automated calculations with visible formulas (no black box).
- **Custom test tables:** Users or GeoDin consultants can create additional measurement data types for tests not in the standard distribution.
- **Reporting and visualization:** 200+ pre-made layout templates for borehole logs, cross sections, CPT classification plots, parameter-vs-depth charts, tabular reports, and thematic maps. All templates are customizable.
- **Cross sections:** Create geological cross sections by projecting boreholes onto section lines, with manual layer connections, standard-compliant hatching, and overlay of CPT/SPT/lab data.
- **Built-in GIS map:** Embedded map environment with OpenStreetMap base tiles, shapefile support, WMS/TMS layers, heat maps, elevation/contour data, and mini-graphic borehole previews.
- **Data import:** Supports XLS, XLSX, CSV, TXT, MDB, ACCDB, SHP, LAS, GeoJSON, GML, and ODBC connections. Includes a dedicated gINT migration/converter tool.
- **Data export:** PDF (single, per-object, or continuous), DXF, PNG, EMF, CSV, XLSX, AGS (4.0.4, 4.1.1), Leapfrog, SHP, GML, KML, JSON, XML, HTML.
- **AGS export:** Three-click conversion to AGS format for delivery to platforms like OpenGround or Plaxis.
- **Calculation engine:** Built-in library of several hundred standard geotechnical equations. Companies can store proprietary formulas shared only within their team.
- **Multi-language:** Interface and data output in 8 languages (English, German, French, Italian, Spanish, Portuguese, Turkish, Russian). Users can work in one language and deliver in another.
- **SQL queries and publication methods:** Write custom SQL to fetch, reformat, and export data. Publication methods are reusable SQL-based export configurations.
- **Document management:** Attach PDFs, photos, videos, and other files directly to boreholes in the database.
- **QGIS plugin:** Available in the QGIS plugin library for pulling GeoDin data into QGIS.

### Who Uses It
- Geotechnical consultants preparing borehole logs and reports
- Environmental firms managing groundwater or soil contamination data
- Construction companies requiring subsurface models
- Government agencies and ministries needing standardized, audit-ready data
- Project managers overseeing multi-company, multi-project geotechnical programs

---

## 2. GeoDin Onsite

### What It Is
GeoDin Onsite is a field data collection application for Windows tablets, laptops, and desktops. It digitizes traditional paper-based field logging, replacing handwritten forms with validated digital entry while maintaining the familiar paper-form layout. It is included with a GeoDin subscription at no additional cost.

### Key Capabilities
- **Digital paper forms:** Touchscreen-native interface that replicates traditional driller paper forms. Supports both touchscreen and keyboard input.
- **Real-time validation:** Checks data types, completeness, and enforces conditional rules based on the selected geotechnical standard. Prevents non-compliant data from being captured.
- **Standard-compliant field logging:** Uses the same 11+ international standards and dictionaries as GeoDin Core. Soil descriptions are auto-generated from entered properties using the same builder approach as the desktop application.
- **QR code sample tracking:** Prints labels with QR codes (project ID, borehole ID, depth, sample type) via compatible mobile printers (e.g., Zebra, Bluetooth or wired). Maintains chain of identification from field to lab.
- **Photo integration:** Capture and embed sample/site photographs directly into data entries.
- **GPS integration:** Automatically logs device GPS coordinates during data capture.
- **Offline operation:** Works without internet for up to 30 days. Data saved locally and uploaded when connectivity is restored.
- **Supported field tests:** SPT, rock core recording (SCR/RQD), and other in-situ tests. Does not cover the full 60+ lab test types available in GeoDin Core.
- **Data exchange:** Exports data as XML files (GeoDinML/GODML format). Can deliver to a central network folder or OneDrive.
- **Form customization:** Customizable by GeoDin as a service (not end-user configurable) due to the complexity of underlying geotechnical standards.

### Who Uses It
- Drilling crews and field engineers logging boreholes on-site
- Sampling teams managing sample identification and chain of custody
- Engineering companies that want to eliminate paper field logs and transcription errors
- Subcontractors who receive Onsite licences from their clients

---

## 3. GeoDin Ground

### What It Is
GeoDin Ground is a free Autodesk Civil 3D plugin that visualizes subsurface geotechnical data directly within the Civil 3D design environment. It bridges the gap between geotechnical data and infrastructure design. Available on the Autodesk App Store at no cost. GeoDin is Autodesk's strategic AEC partner and the designated replacement for Autodesk's retiring Geotechnical Modeler.

### Key Capabilities
- **3D borehole visualization:** Renders boreholes as 3D cylinders ("borehole sticks") in Civil 3D, colour-coded by soil layer/ground unit, with metadata annotations and ground descriptions.
- **Surface and volume generation:** "Draw Surfaces and Volumes" connects matching layers between neighbouring boreholes, generates TIN surfaces, and fills 3D volumes. Layers absent in a neighbouring borehole taper to zero thickness (lens modelling).
- **Virtual boreholes:** Insert virtual boreholes to shape the ground model, test sensitivity, and identify areas needing more investigation. Can be created empty, by copying a nearby borehole, or interpolated from the existing model.
- **Document access:** Open borehole logs, sample photos, and PDFs attached in GeoDin directly from within Civil 3D — no need to switch to GeoDin Core.
- **Volume/quantity calculations:** Calculate cubic metres of soil/rock types along infrastructure paths for cost analysis and optimization.
- **No GeoDin licence required for viewers:** Civil 3D plugin users do not need a GeoDin licence. Only the team members who manage and curate the database need licences.
- **Data types visualized:** Borehole data, lithological layers, sample data, CPT data, 60+ geotechnical test types.
- **ArcGIS integration path:** Borehole data can flow from GeoDin through Civil 3D into ArcGIS Online via the ArcGIS for AutoCAD plugin, published as feature layers with attached logs.
- **IFC/BIM pathway:** Civil 3D can produce IFC 4.3 geotechnical strata and borehole data after import from GeoDin Ground (manual classification mapping required).
- **Compatibility:** Civil 3D 2025 and 2026. Versions 2024 and earlier are not supported.
- **Sample dataset included:** A demo dataset is bundled with the app for exploration.

### Who Uses It
- Civil and design engineers who need ground visibility within their CAD environment
- Geotechnical engineers sharing subsurface data with design teams
- Infrastructure project teams (roads, tunnels, bridges, rail) needing subsurface context for design decisions
- BIM coordinators incorporating geotechnical data into project models

---

## 4. How the Three Products Work Together

### End-to-End Data Flow

```
Field (Onsite) --> Office (Core) --> Design (Ground)
```

1. **Field collection (GeoDin Onsite):** Drillers and field crews capture borehole data on Windows tablets using validated digital forms. Data is standard-compliant from the moment of entry. Samples are labelled with QR codes for traceability. GPS coordinates are recorded automatically.

2. **Data transfer (Onsite to Core):** Field data is exported as GeoDinML (XML) files and imported into GeoDin Core via the GeoDinML Importer plugin. Import auto-populates general data, depths, ground descriptions, sample tables, and field test measurements. Two workflow options:
   - Start from scratch on the tablet (Onsite creates the project)
   - Pre-create an empty project in Core and export a settings template for the field team

3. **Office processing (GeoDin Core):** Office engineers receive field data already structured and validated. They add lab test results, run calculations, create cross sections, generate borehole log reports, perform QA/QC, and produce deliverables — all from the same database.

4. **Design visualization (GeoDin Ground):** Design engineers open the same GeoDin database (or a copy) in Civil 3D via the Ground plugin. Boreholes appear as 3D objects in the design environment. Engineers generate ground surfaces, volumes, and virtual boreholes to inform infrastructure design. Attached documents (logs, photos) are accessible without leaving Civil 3D.

### Key Integration Points
- **Shared dictionaries:** Onsite uses the same dictionaries, standards, and drop-down values as Core, ensuring field data matches office expectations exactly.
- **Shared database:** Core and Ground read from the same database. If both are on the same machine, databases appear automatically in both applications.
- **One-way data flow to Civil 3D:** Data transfer from GeoDin to Civil 3D is read-only. Once imported, borehole data resides in the Civil 3D drawing with no backward connection.
- **No automatic sync:** The Onsite-to-Core import requires manual XML file transfer and import. There is no live sync between applications.

---

## 5. Key Technical Facts

### Deployment Model
- **Three deployment options:**
  1. **Local:** Database on the user's machine (Access file). Fully offline-capable.
  2. **On-premises:** Client-server database on company network (PostgreSQL, Oracle, or MS SQL Server). Most common configuration for larger organizations.
  3. **Cloud-hosted:** Customer's own cloud infrastructure (e.g., Azure) or GeoDin-hosted servers. Cost is separate from licence.
- **Installation:** Windows-based (Windows 10/11). Two modes: centralized server installation (shared config, recommended for teams) or local per-device installation.
- **GeoDin does not host data by default.** Customers choose where their data lives. GeoDin has no access to customer data.

### Database Technology
- **File-based:** Microsoft Access (.accdb/.mdb). Max 2 GB (practical limit ~1 GB). One file per project recommended. Easy to share by copying the file.
- **Client-server:** PostgreSQL, Oracle, MS SQL Server. No practical size limit. Multiple projects per database. Concurrent multi-user editing supported.
- **Cloud databases (e.g., Azure) are supported** — the customer decides the hosting location.
- **Multi-user:** Multiple users can work on the same database simultaneously. Concurrent editing on different boreholes/fields works without issues.

### Data Ownership and Sovereignty
- Full data ownership by the customer. Data remains accessible regardless of licence continuation.
- Customer-controlled data residency (key differentiator vs. some competitors).
- Used by government agencies and ministries of defence requiring data behind their own security layers.

### Standards Supported
- 11+ international geotechnical standards: ASTM, BS 5930, DIN 4022/23, DIN EN ISO 14688/89, DIN 4943, SEP1/SEP3, DIN EN ISO 22475, NEN, ONORM, GOST, KA5
- AGS export: versions 4.0.4 and 4.1.1
- Both GeoDin (import + export) and GeoDin Onsite (export) are officially listed on the AGS website (ags.org.uk/data-format/software/) as AGS-compatible software

### Integrations
| Integration | Type | Notes |
|---|---|---|
| Autodesk Civil 3D | Plugin (GeoDin Ground) | Free. Strategic Autodesk AEC partnership. Replacement for Geotechnical Modeler. |
| Leapfrog | Export | Dedicated export via SQL-based publication method |
| QGIS | Plugin | Available in QGIS plugin library |
| ArcGIS | Via Civil 3D | Boreholes published as feature layers via ArcGIS for AutoCAD plugin |
| gINT | Import/migration | Built-in converter tool for migrating gINT databases |
| OpenGround | Export (AGS) | AGS export for data delivery |
| BoreDM | Alternative | GeoDin positions as alternative |

### Licensing & Pricing (as of March 2026)

| License | EUR | USD |
|---|---|---|
| Individual License (single device) | €2,394.70/year | $2,011/year |
| Professional/Network License (floating/concurrent) | €3,395/year | $2,850/year |
| Educational License | €100/year | $100/year |

- **GeoDin Ground:** Free with any licence. Civil 3D users who only consume data need no GeoDin licence.
- **GeoDin Onsite:** €695/device/year standalone, or €495/device/year with ecosystem discount (existing GeoDin customers). Per-device pricing (not per-user) — designed for shared field tablets. Volume discounts from 6+ devices (contact sales). Free trial available.
- **Free 30-day trial** of GeoDin Core available. No credit card required. Trial can be extended on request.
- **Standard Onboarding:** €1,200 — includes 3-hour beginner training (online, up to 5 attendees) + 1-hour follow-up Q&A within 2 weeks.
- **Custom Training & Consulting:** Case-by-case pricing (contact sales). Covers advanced features, multi-site deployments, enterprise integrations.

### System Requirements
- Processor: 1 GHz or higher
- RAM: 1 GB minimum
- OS: Windows 10 or Windows 11
- GeoDin Ground requires Autodesk Civil 3D 2025 or 2026

### Scale
- Used in 14,000+ geotechnical projects across 38+ countries
- Demonstrated with projects containing 3,600+ location objects covering 700 km with 5 companies collaborating
- Team of ~30 people; parent company Fugro (~10,000-11,000 employees globally)

---

## Gaps & Review Notes

1. **GeoDin Core vs. GeoDin Desktop naming:** The transcript sources use both "GeoDin Core" and "GeoDin Desktop" interchangeably in places, while the marketing pages use just "GeoDin" for the main product. The chatbot should know whether these are the same product or if there is a distinction. The sources suggest they are the same, but this should be confirmed.

2. ~~**Onsite pricing as standalone**~~ **RESOLVED:** GeoDin Onsite is priced per device/year: €695 standalone or €495 with ecosystem discount (existing GeoDin customers). Volume discounts from 6+ devices. Status is marked as "Draft (in development)" in the pricing document — confirm whether this is now live.

3. **Number of supported languages:** Sources variously state 7 languages (marketing page lists English, German, French, Italian, Spanish, Portuguese, Turkish) and 8 languages (transcript mentions "8 languages: German, French, Russian, Spanish, English, Portuguese, and 2 others"). The exact list should be reconciled — specifically whether Russian, Italian, and Turkish are all supported, and what the remaining language(s) might be.

4. **Project count discrepancy:** The overview page says "14,000 geotechnical projects" while the transcript says "15,000 geo projects." The chatbot should use the more conservative/official figure or the latest confirmed number.

5. **GeoDin Ground as standalone viewer:** One source mentions "GeoDin Ground is also available as a standalone free app for viewing 3D borehole visualizations" (separate from Civil 3D). This is mentioned only once and should be verified — is there a standalone Ground viewer, or does it strictly require Civil 3D?

6. **REST API timeline:** Sources reference a REST API planned for end of 2026 (from October 2025 context). As of March 2026, there is no update on whether this timeline holds. The chatbot should not promise API availability without current confirmation.

7. **Internal vs. External product versions:** The transcript mentions an "Internal version" (for Fugro/Focal, more data types and layouts) and an "External version" (for external clients, fewer). Planned unification has no timeline. This could cause confusion if a visitor asks about specific test types that exist only in the internal version.

8. **Onsite test coverage:** Onsite supports "a subset of tests" (SPT, SCR/RQD, and other in-situ tests) but not the full 60+ lab tests. The exact list of supported field tests in Onsite is not enumerated in the sources.

9. **gINT converter completeness:** The migration tool currently imports locations, coordinates, and general data. Sample data and measurement data import is still being developed. The chatbot should set appropriate expectations about migration scope.

10. ~~**Consulting/training pricing currency**~~ **RESOLVED:** Standard Onboarding is €1,200. Custom training/consulting is case-by-case (contact sales).

11. **Minimum system requirements seem very low:** 1 GHz processor and 1 GB RAM are listed on the features page, but these seem like legacy minimums. Practical requirements for larger projects likely differ. Consider adding recommended specs.

12. **Direct Esri integration (without Civil 3D):** Multiple sources mention this is under active development (potentially end of 2026 or early 2027) but it does not exist yet. The chatbot should not present this as a current capability.
