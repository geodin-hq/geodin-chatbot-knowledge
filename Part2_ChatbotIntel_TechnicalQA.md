# Part 2 — Technical Q&A

> Chatbot Intel: Frequently asked technical questions and answers for the GeoDin website chatbot.
> Source: GeoDin Transcript Knowledge, GeoDin Docs, Competitor Context files.
> Last updated: 2026-03-16

---

## THE GEODIN PRODUCT SUITE

### Q: What is GeoDin? What does it do?

GeoDin is a geotechnical data management software for collecting, storing, processing, visualizing, and reporting geotechnical and environmental ground investigation data. It is not just a logging tool — it is a full data management, visualization, and lab test processing platform.

The suite consists of three integrated applications:
1. **GeoDin Core** — the main platform for database creation, data entry, analysis, reporting, and GIS mapping.
2. **GeoDin Onsite** — a touchscreen-native field data collection app for Windows tablets that digitizes paper field forms.
3. **GeoDin Ground** — a free plug-in for Autodesk Civil 3D that visualizes subsurface data in 3D within the design environment.

Together they provide a complete field-to-design workflow: data collected in the field flows into the central database, gets processed and analyzed, generates reports, and feeds into 3D models in Civil 3D.

### Q: What is GeoDin Core?

GeoDin Core is the main platform where you create and manage your geotechnical databases. It handles:
- Data entry and import (Excel, CSV, AGS, gINT, ODBC, and more).
- Soil/rock description using 11+ international standards.
- Lab and field test data storage (60+ pre-built test tables).
- Report generation: borehole logs, CPT plots, cross sections, particle size distribution curves, tabular reports, and maps.
- Built-in GIS mapping with OpenStreetMap, shape file support, WMS layers, heat maps, and contour lines.
- Data export in PDF, DXF, CSV, Excel, AGS, Leapfrog, shapefile, and other formats.

### Q: What is GeoDin Onsite?

GeoDin Onsite is a field data collection app that replaces paper drilling logs. It runs on **Windows tablets and laptops** (Windows 10 or 11 required — it is not available for iOS or Android).

Key features:
- Touchscreen-native interface that digitally replicates traditional paper field forms.
- Standard-compliant data entry — dictionaries enforce correct soil descriptions per the selected geotechnical standard.
- Works **offline for up to 30 days** without internet connectivity.
- QR code sample label printing for full chain-of-custody traceability from field to lab.
- GPS coordinate capture.
- Photography and field observations.
- Data export as XML (GeoDinML format) for import into GeoDin Core.

GeoDin Onsite is included free with any GeoDin subscription.

### Q: What is GeoDin Ground?

GeoDin Ground is a **free plug-in for Autodesk Civil 3D** (available in the Autodesk App Store). It is the designated replacement for Autodesk's Geotech Modeller (which is being retired).

Key features:
- Renders 3D borehole sticks (cylinders) in Civil 3D with colour-coded soil layers, metadata, and ground descriptions.
- Generates 3D surfaces and volumes from borehole data — visualize the subsurface as a 3D ground model.
- Virtual boreholes: create synthetic boreholes to shape the ground model, test sensitivity, and identify areas needing more investigation.
- Volume/quantity calculations: intersect tunnel or excavation volumes with ground volumes to calculate cubic metres of each soil type for cost analysis.
- Access documents (PDFs, photos, reports) attached to boreholes directly from within Civil 3D.
- Works with Civil 3D 2025 and 2026 versions.

Civil 3D users do not need a GeoDin license to use GeoDin Ground — only the database managers need licenses.

---

## DATA & STANDARDS

### Q: What geotechnical standards does GeoDin support?

GeoDin supports **11+ international geotechnical standards** for soil description and classification:
- ASTM D2487/D2488 (English and Spanish)
- British Standard (BS5930, Eurocode 7)
- EN ISO 14688/14689 (English and German)
- DIN (Germany)
- ABNT (Brazil/Portuguese)
- NEN (Netherlands)
- ISO GOST (Russia)
- Turkish, Chilean, South American standards
- Additional standards available on request

Multiple ground description standards can coexist within the same database simultaneously. International teams can work in their preferred language and deliver in the client's required language.

### Q: What AGS support does GeoDin have?

GeoDin supports **AGS export** for versions 4.0.4 and 4.1.1. The AGS object type has a dedicated table structure that mimics AGS file groups and headers, allowing direct import of AGS files. Full AGS compatibility (including AGS as a native object type with AGS group naming and the ability to import AGS data directly into the G1 object type) is planned for H1 2026.

### Q: What test types are included?

Over **60+ pre-built geotechnical test tables** are included, covering both in-situ and laboratory tests:
- Water content, Atterberg limits, particle size distribution
- SPT (with country-specific variants for US, Japan, UK, Brazil)
- Triaxial tests (all types), oedometer
- Pocket penetrometer, torvane, field/lab vane
- Unit weight classification, undrained shear strength
- Dilatometer (Marchetti), fall cone
- Rock quality (TCR/SCR/RQD)
- CPT data (cone resistance, sleeve friction, water pressure)
- And many more

If a test type is not included (e.g., Menard pressuremeter, environmental/chemical analysis, Proctor), users can create **custom test tables** with their own parameters, formulas, and validation rules — or GeoDin's consulting team can create them.

### Q: What languages does GeoDin support?

GeoDin supports **8 languages**: English, German, French, Italian, Spanish, Portuguese, Turkish, and Russian. Switching the interface language automatically translates dictionary values. Users can work in one language and deliver reports in another (e.g., work in French, deliver in German or Portuguese).

### Q: How does GeoDin handle soil descriptions?

GeoDin uses a structured approach: you select a geotechnical standard (e.g., ASTM), then for each soil layer you choose the ground type, principal soil type, secondary soil type, and additional properties from standard-specific dropdown lists. The system **auto-generates a standard-compliant text description** from the entered properties.

Properties include: plasticity, colour (Munsell chart available), carbonate content, grain unit, interbedding type, undrained shear strength, USCS group symbol, and more. Each soil type has an associated fill pattern (hatch) for borehole logs and cross sections.

---

## DATA IMPORT & EXPORT

### Q: What data can I import into GeoDin?

GeoDin supports importing:
- **General borehole data** (name, coordinates, depths, drilling method) from Excel, CSV, or text files — batch import for multiple boreholes at once.
- **Sample data** (recovery depths, sampling method, tube type) from Excel, CSV, or text files.
- **Measurement/lab test data** from Excel, CSV, or text files into any test table.
- **Data sequences** (CPT, seismic, measure-while-drilling) from CSV, text/ASCII, Excel, LAS, GEF, and GF files.
- **AGS files** directly into the AGS object type.
- **gINT databases** via the built-in gINT converter.
- **GeoDin Onsite field data** via GeoDinML (XML) import.
- **GIS data**: shape files, GeoJSON, geo-referenced JPEG, WMS services, grid files.
- **ODBC connections** to external data sources.

Import configurations can be saved as ICF files and reused for future imports.

### Q: Can I batch import layer/ground description data?

Currently, ground/layer description data **cannot be batch imported** in the G1 object type through the UI. Layer data must be entered manually or via SQL scripts. This is a known limitation and the **top-priority feature request** in development. Workaround options: use the AGS object type (which supports bulk import), or copy borehole log properties between boreholes.

### Q: What formats can I export?

Supported export formats include:
- **PDF** (continuous, individual per page, or per borehole/object)
- **DXF** (AutoCAD drawing exchange format)
- **CSV** and **Excel** (for data tables and sequences)
- **AGS** (versions 4.0.4 and 4.1.1)
- **Leapfrog-compatible format** (via dedicated export button)
- **Shapefiles** (for GIS integration)
- **PNG** and **EMF** (image/vector formats for layouts)
- **GeoDinML (XML)** for data exchange
- Access database zip files via "Publish and Export"

### Q: Can I export data to Leapfrog?

Yes. GeoDin has a **dedicated Leapfrog export button** that formats borehole data (coordinates, depths, soil descriptions) into the table structure expected by Leapfrog. This is implemented as a custom SQL-based publication method.

---

## DATABASE & DEPLOYMENT

### Q: What database does GeoDin use?

GeoDin supports two database types:
1. **Microsoft Access** (.accdb/.mdb) — single file, easy to share, maximum size 2 GB (recommended practical limit ~1 GB). Best for small to medium projects.
2. **Client-server SQL databases** (PostgreSQL, Oracle, MS SQL Server) — no practical size restriction, can hold hundreds of gigabytes. Best for larger organizations and multi-user collaboration.

### Q: Can multiple people work on the same database?

Yes. Multiple users can collaborate on the same database simultaneously. With client-server SQL databases, latency is low and concurrent editing generally causes no issues unless two users edit the exact same field at the same time. With Access databases, concurrent editing works but with slightly higher latency.

### Q: Can GeoDin work offline?

Yes. GeoDin Core can run completely offline on a laptop with a local Access database on the local hard drive, isolated from any external network. GeoDin Onsite works offline for up to 30 days without internet connectivity.

### Q: What are the system requirements?

- **GeoDin Core:** Requires a Windows operating system.
- **GeoDin Onsite:** Requires Windows 10 or Windows 11 (it is NOT available for iOS or Android).
- **GeoDin Ground:** Requires Autodesk Civil 3D 2025 or 2026 (versions 2024 and earlier are not supported).

### Q: How do I install GeoDin?

GeoDin offers two installation modes:
1. **Express installation** (recommended for first-time users) — installs everything on a single computer, includes demo databases.
2. **Custom installation** — supports single-user local installation or network installation for multi-user centralized deployment.

For larger organizations, a centralized server installation is recommended: configuration (dictionaries, object types, templates) is shared across all users and changes apply automatically.

---

## REPORTING & VISUALIZATION

### Q: What reports can GeoDin generate?

GeoDin includes **200+ pre-made templates** for:
- Borehole log reports (with graphic logs, soil descriptions, test results, well design, groundwater, legend)
- CPT classification plots (Robertson)
- Particle size distribution curves
- Parameter-vs-depth charts (any parameter from the database)
- Cross sections (with layer connections, hatch patterns, overlaid test data)
- Tabular/summary reports
- Map deliverables with title blocks, logos, and legends

All templates are customizable. Users can modify existing templates or create new ones from scratch. Templates are interactive — drag a different borehole onto a template and it updates automatically with that borehole's data.

### Q: Can I create custom report templates?

Yes. GeoDin has a full **template editor** with:
- Object frames that connect database data to the layout.
- Dynamic text using macros that pull data from the connected borehole.
- Drawing layers for organizing graphic elements.
- Data sequence elements for parameter-vs-depth charts.
- SQL queries as data sources.
- Layout snippets for reusing headers, footers, and logos across templates.

Templates are stored in the database and shared across the team. GeoDin also offers a custom template creation consulting service at EUR 250/hour.

### Q: How do cross sections work?

Cross sections are created using a dedicated tool:
1. Select or import a section line (straight, polyline, or imported from Civil 3D alignment).
2. Project boreholes onto the section line.
3. Manually connect layers between boreholes using the "Join Layers" command.
4. Overlay additional data: CPT plots, lab results, sample markers, and more.

Cross sections support 11 international standards for geological hatchings. Templates can be saved and regenerated with new borehole data. Cross-section lines can be displayed on the GIS map with click-to-open functionality.

### Q: Can I generate 3D models?

Yes, using **GeoDin Ground** inside Autodesk Civil 3D. It generates:
- 3D borehole sticks with colour-coded soil layers.
- TIN surfaces connecting matching layers between neighbouring boreholes.
- 3D volumes between surfaces.
- Virtual boreholes for model refinement.
- Volume calculations for cost analysis (e.g., cubic metres of each soil type in a tunnel path).

For report-quality 2D cross sections with standard-compliant hatching, use GeoDin Core.

---

## GIS & MAPPING

### Q: Does GeoDin have built-in GIS?

Yes. GeoDin has a **built-in GIS map** that uses OpenStreetMap as the base map. Capabilities include:
- Plot boreholes and CPT locations with customizable symbols and markers.
- Import and display shape files, GeoJSON, geo-referenced images, and WMS layers.
- Generate elevation contour lines.
- Create heat maps from database parameters using SQL queries.
- Display cross-section lines on the map with click-to-open previews.
- "Mini graphics" — small borehole log previews displayed as markers on the map.
- Map export with branded title blocks, logos, and legends.

### Q: Does GeoDin integrate with ArcGIS?

Yes, through two paths:
1. **Via Civil 3D:** GeoDin data flows from GeoDin Ground through Civil 3D into ArcGIS using the free ArcGIS for AutoCAD plug-in. Boreholes can be published as feature layers in ArcGIS Online with attached borehole logs.
2. **Direct integration (planned):** GeoDin and Esri are actively developing a direct integration to move data into ArcGIS Online without requiring Civil 3D. Timeline is potentially end of 2026 or early 2027.

### Q: Does GeoDin work with QGIS?

Yes. GeoDin has a **QGIS plugin** available in the QGIS plugin library. GeoDin Core also has a built-in QGIS engine for GIS modelling capabilities.

---

## FIELD DATA COLLECTION (GEODIN ONSITE)

### Q: How does field-to-office data flow work?

1. Field crew collects data on a Windows tablet using GeoDin Onsite.
2. Data is saved locally on the device (works offline for up to 30 days).
3. When ready, field data is exported as an XML file (GeoDinML format) to a central network folder, OneDrive, or USB.
4. Office engineers import the XML file into GeoDin Core using the GeoDinML Importer plug-in.
5. The import auto-populates general data, depths, ground descriptions, sample tables, and field test measurements.

Office engineers do not need to re-enter field logs — the data flows directly from the field into the database with full traceability.

### Q: Does GeoDin Onsite enforce standard-compliant data entry?

Yes. GeoDin Onsite includes the same dictionaries and standard-specific dropdown lists as GeoDin Core. When a standard is selected (e.g., ASTM), the app only shows valid options for soil descriptions, enforcing standard-compliant data entry in the field. Ground descriptions are auto-generated from the entered properties. It is described as a "foolproof system" that prevents data quality issues before they enter the workflow.

### Q: Can I print sample labels with QR codes?

Yes. GeoDin Onsite supports **portable field printing of QR-coded sample labels** using a compatible label printer. QR codes are automatically registered with unique identifiers linking to the correct sample ID, borehole, and project. Laboratories can scan the QR code to automatically identify the source project, location, and depth — providing full chain-of-custody traceability.

### Q: Can I customize the Onsite field forms?

Onsite forms are customizable, but not directly by end users — customization is provided as a service by the GeoDin team. This is because geotechnical standards in the background make user-level customization complex. You specify your needs, and GeoDin shapes the forms accordingly. Options include tabbed views vs. single-page layout, and custom test table configurations.

---

## INTEGRATIONS

### Q: What software does GeoDin integrate with?

- **Autodesk Civil 3D:** Native integration via GeoDin Ground plug-in (free). 3D borehole visualization, ground modelling, virtual boreholes, volume calculations.
- **Leapfrog (Seequent/Bentley):** Dedicated export button for Leapfrog-compatible data.
- **ArcGIS:** Via Civil 3D pathway today; direct integration in development.
- **QGIS:** Plugin available in the QGIS plugin library.
- **gINT:** Built-in converter for migrating gINT databases.
- **Excel:** Full import/export with configurable column mapping.
- **AGS:** Import and export support.
- **CAD (DXF):** Export for AutoCAD and similar software.
- **BIM (IFC 4.3):** Ground data will be part of the IFC 4.3 standard via Civil 3D (planned).

### Q: Does GeoDin have an API?

Not yet. A **REST API** is planned and actively being developed, targeted for end of 2026. It will be HTTP-based web requests enabling third-party applications to pull geotechnical data directly from GeoDin without exporting to Excel/CSV. The GeoDin team is seeking early adopter input to shape API requirements.

In the meantime, data can be accessed via:
1. **Batch export** (Excel, CSV, AGS, Leapfrog format — available today).
2. **Direct SQL access** to the database (for advanced users).
3. **Custom plug-ins** developed by the GeoDin team for specific client needs.

### Q: Does GeoDin support BIM/IFC?

GeoDin ground data will be part of the **IFC 4.3 standard** for BIM. Currently, IFC export is not directly available from GeoDin, but Civil 3D can produce IFC 4.3 geotechnical strata and borehole data after import from GeoDin Ground. IFC classification mapping in Civil 3D must be set up manually. Full native IFC 4.3 support is planned.

---

## CUSTOMIZATION

### Q: Can I create custom test tables?

Yes. Users can create custom measurement data tables ("data types") via System > Data Types. Custom tables support:
- User-defined parameters (which become columns).
- Formulas for calculated columns with conditional logic.
- Validation criteria (flagging out-of-range values).
- Visibility conditions.

Custom tables are local to your installation and are not overwritten by GeoDin updates. Creating a new test table is described as "not a very big workload." Built-in test tables (60+) cannot be edited (for cross-installation compatibility), but you can create new custom ones alongside them.

### Q: Can I add my own calculation formulas?

Yes. GeoDin has a built-in calculation engine with **several hundred standard analytical equations**. You can also add your own proprietary formulas — they are stored in the database and shared only within your team. GeoDin does not have access to your custom formulas. Formulas support conditional logic (if-then) and chaining (parameter B from A, then C from B).

### Q: Can I customize dictionaries (lookup lists)?

Yes. Dictionaries (e.g., investigation methods, soil types, sampling methods, coordinate systems) can be extended by adding new entries. However, editing a dictionary sets a timestamp that prevents it from receiving automatic updates from future GeoDin distributions. For important modifications (soil types, investigation methods), it is recommended to communicate changes to GeoDin support.

---

## KNOWN LIMITATIONS (HONEST ANSWERS)

### Q: Can GeoDin import PDF borehole logs?

Not yet. There is currently no automated PDF-to-data import capability. When data is only available as PDFs, manual data entry is required. However, **AI-based PDF borehole log digitization** is under development (proof of concept completed). GeoDin is seeking a client partner to co-develop this feature using real-world data.

### Q: Does GeoDin run on Mac or mobile?

No. GeoDin Core requires **Windows**. GeoDin Onsite requires **Windows 10 or 11** (not available for iOS or Android). There is no Mac or Linux version.

### Q: Does GeoDin do liquefaction analysis or advanced geotechnical analysis?

No. Liquefaction analysis and advanced geotechnical analysis (like those performed in GeoStudio) are out of scope. GeoDin is a data management and visualization platform, not a geotechnical analysis/design tool.

### Q: Does GeoDin have data versioning?

No built-in data versioning at the individual borehole level. There is no explicit mechanism to store older vs. newer data. Workarounds include naming sequences differently, creating a second version of the same location, or using "update data sequences" (which overwrites previous data).

### Q: Can GeoDin do statistical analysis across boreholes?

Not currently. Proper statistical evaluation on curves (e.g., finding maximum/minimum values across boreholes, cross-borehole statistical analysis) is not possible in GeoDin. This type of analysis would need to be performed in external tools using exported data.

---

## Gaps & Review Notes

- **iOS/Android Onsite version** — frequently asked by prospects. Confirm there are no plans or if this is on a long-term roadmap.
- **Mac support** — confirm if there is any roadmap for macOS or web-based access.
- **REST API timeline** — the "end of 2026" target comes from October 2025 transcripts. Verify if this has been updated.
- **AGS full compatibility** — "H1 2026" target for full AGS support. Verify current status.
- **AASHTO classification** — "Q1 2026" target. Verify if delivered.
- **Cross sections in Civil 3D** — "end of Q1 / early Q2 2026" target. Verify if released.
- **PDF digitization** — confirm whether a client partner has been found for co-development.
- **Web-based version / SaaS** — no mention of a web-based GeoDin in any source. If prospects ask about this, the chatbot needs a clear answer.
- **Data migration effort estimates** — no specific timelines for how long a gINT migration typically takes. Would be useful for setting expectations.
- **Environmental test types** — the document notes that environmental/chemical analysis tables are not standard. Clarify what is needed for environmental projects and what must be configured.
