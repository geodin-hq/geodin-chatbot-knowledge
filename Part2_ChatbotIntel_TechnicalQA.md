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

GeoDin Onsite is licensed per device per year (€495/device/year for existing GeoDin customers, €695/device/year standalone). A 1-month free trial with full functionality is available to all customers.

The licence is **bound to the device's hardware** and is validated online at each launch, with a rolling 30-day offline window. If a device is replaced or its hardware changes significantly (e.g., disk or memory swap), contact support@geodin.com to re-bind the licence to the new device.

### Q: What is GeoDin Ground?

GeoDin Ground is a **free plug-in for Autodesk Civil 3D** (available in the Autodesk App Store). It is the path forward as Autodesk retires its Geotechnical Modeler — built in roadmap collaboration with Autodesk (do not claim a formal Autodesk endorsement or designation).

Key features:
- Renders 3D borehole sticks (cylinders) in Civil 3D with colour-coded soil layers, metadata, and ground descriptions.
- Generates 3D surfaces and volumes from borehole data — visualize the subsurface as a 3D ground model.
- Virtual boreholes (virtual logs): insert synthetic boreholes to shape the ground model, test sensitivity, and identify areas needing more investigation. Three creation modes:
  - **Empty** — place the virtual log and type the layer stack by hand (e.g., to define a boundary condition).
  - **Nearest Borehole** — copies the layer sequence of the closest real borehole, which you then adjust.
  - **Surface Interpolation** — samples the currently generated ground model at the log's location to lock in its prediction as a constraint.
  Virtual logs are not persisted to the GeoDin database — they exist only in the current Civil 3D drawing.
- Volume/quantity calculations: intersect tunnel or excavation volumes with ground volumes to calculate cubic metres of each soil type for cost analysis.
- Access documents (PDFs, photos, reports) attached to boreholes directly from within Civil 3D.
- Works with Civil 3D 2025 and 2026 versions.

Civil 3D users do not need a GeoDin license to use GeoDin Ground — only the database managers need licenses.

### Q: What is the latest version? What's new?

- **GeoDin (desktop):** The current major version is **GeoDin 15** (15.x line). The setup supports direct upgrades from GeoDin 9.6 and 10 while keeping your system configuration; updates run in-app via System Configuration > Update GeoDin.
- **GeoDin Ground:** The current version is **v1.6.22.0** (24 June 2026, per the Autodesk Marketplace listing), compatible with **Civil 3D 2025, 2026, and 2027**. Earlier: v1.5.17 (September 2025) introduced **virtual logs** for customizing the ground model and better support for **Civil 3D in imperial mode**, plus accuracy improvements for complex or overlapping borehole data; v1.0.0 (June 2025) brought Civil 3D 2025/2026 compatibility.
- **GeoDin Onsite:** Updated continuously — the app checks for updates automatically at every launch and installs the latest version in one click. New versions always open data created in older versions (backward compatible); the reverse is not guaranteed, so teams should update together.

Full release notes for GeoDin Ground: https://docs.geodin.com/geodin-ground/support/release-notes

### Q: Which ground description standards does GeoDin Ground support in Civil 3D?

GeoDin Ground visualizes borehole data using these description standards:
- EN ISO 14688 / 14689
- ASTM D2487
- British Standard 5930
- Brazilian / Portuguese ABNT

If a borehole contains descriptions in multiple standards, the first alphabetically is used for visualization.

### Q: What databases can GeoDin Ground connect to, and does it work offline?

GeoDin Ground connects to both **file-based** GeoDin databases (MS Access .accdb) and **client-server** databases (PostgreSQL, Oracle, MS SQL Server). If GeoDin Core is installed on the same machine, existing database connections are discovered automatically; manual connections can also be configured.

Connectivity is only needed at import time. With a local file database, no network is needed at all. After import, all borehole data resides in the Civil 3D drawing and works fully offline. Data flow is one-way (read-only) — to get updated data, re-import from the database.

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

GeoDin offers a **fully native AGS workflow** for AGS 4.1.1 and AGS 4.0.4 — and is **officially listed by the AGS Committee** as AGS-compatible software (ags.org.uk/data-format/software/).

- **Dedicated AGS object type** (independent from the legacy G1 object type) covering **86 data types**, with comprehensive AGS dictionaries, fill patterns for geological layers, and map visualization built in.
- **AGS Importer** — guided 4-step process: configure AGS standard → select files → validate against AGS rules → import. Validation runs *before* data enters the database, catching formatting errors, missing fields, and rule violations upfront.
- **AGS Exporter** — guided 5-step process: select objects → choose standard (4.1.1 or 4.0.4) → fill in project and transmission details → validate → export. Every exported AGS file is fully validated.
- **Lifecycle:** import AGS → edit natively in the AGS object type (borehole logs, geological descriptions, lab results) → export validated AGS — no manual conversion to/from Excel or CSV.

The legacy G1 object type and G1 AGS Exporter remain available for projects that use that workflow. Both GeoDin (full import + export) and GeoDin Onsite (export only) are listed by the AGS Committee.

**Technical requirements:** The AGS Importer and Exporter are delivered as **plugins** installed from GeoDin's server (System side > Connecting). They require **GeoDin 15.4 or higher** and the **.NET 8 Desktop Runtime** (GeoDin prompts and links to the Microsoft download if missing). On a Microsoft Access database, the importer creates the required AGS tables automatically; on a client-server database (PostgreSQL, Oracle, MS SQL Server) the AGS object types must be registered once manually by creating an "AGS 4", "AGS 4 LBSG" and "AGS 4 PREM" object (requires table-creation permission). The importer can also **update existing data** from an uploaded AGS file.

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
- **gINT databases** via the built-in gINT converter, which converts the gINT **PROJECT**, **LITHOLOGY**, **POINT**, and **SAMPLING** groups into GeoDinML for import. If mandatory groups or parameters are missing, the converter reports exactly which ones need adjusting in the gINT file before conversion.
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

### Q: Does GeoDin support US State Plane coordinate systems?

Yes. GeoDin supports coordinate systems worldwide via EPSG codes, which include all US State Plane zones (e.g., NAD83 state plane systems). You select the coordinate system from the coordinate-system dictionary by its EPSG code — so if you know your zone by its Civil 3D-style code (e.g., MA83F), you look up the matching EPSG code once and can reuse it across projects. GeoDin can also transform borehole coordinates between systems (e.g., local grid to state plane, or Gauss-Krüger to UTM). For help identifying the right EPSG code for your state, the support team can assist.

### Q: What are the system requirements?

- **GeoDin Core:** Requires Windows 10/11 64-bit. For client-server backends, the matching 64-bit database client is needed (SQL Server Native Client/ODBC driver, PostgreSQL psqlODBC, or Oracle Instant Client). The AGS plugins additionally require GeoDin 15.4+ and the .NET 8 Desktop Runtime.
- **GeoDin Onsite:** Requires a Windows tablet, laptop, or desktop (Windows 10 or 11) plus the **.NET 8 runtime** — Onsite prompts and redirects to Microsoft's download page if it's missing. It is NOT available for iOS or Android.
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

### Q: Can I see boreholes from all my projects on one map?

Yes. Because GeoDin stores all projects in one centralized database (rather than one file per project, as in gINT), you can build a "master database" view: every borehole, CPT, and monitoring point your organization has ever logged, visible together on the built-in GIS map. Cross-project queries let you pull historical data into new work — for example, referencing nearby borings from past projects when scoping a new site — and report templates can combine objects from different projects. This is one of the main reasons firms move away from file-per-project tools.

### Q: Does GeoDin integrate with ArcGIS?

Yes — geodin.com/integrations/esri-arcgis describes the GeoDin–Esri workflow: plan investigations in ArcGIS (Living Atlas, historic boreholes); capture and manage data in GeoDin; then **move borehole data both ways with ArcGIS Pro** — import borehole locations from an ArcGIS Pro point feature class into GeoDin, or export GeoDin boreholes to ArcGIS Pro as fully attributed point features with coordinate integrity preserved, with finished GeoDin reports attachable to borehole points. In ArcGIS Pro, boreholes become 3D solids (multipatch) and soil layers become surfaces; models can be published to ArcGIS Online as web scenes for browser-based stakeholder review. The Civil 3D pathway (GeoDin Ground + ArcGIS for AutoCAD) remains available for BIM/CAD/GIS three-way workflows. [Team to verify: whether the ArcGIS Pro exchange is a live connector or a guided export/import workflow — do not promise a live API sync.]

In practice, GIS supports the geotechnical workflow in three ways: **planning site investigations** (using terrain, geology maps, and existing infrastructure to decide where to drill), **feeding historical borehole data** stored in ArcGIS Online or ArcGIS Enterprise into GeoDin, and **sharing results with stakeholders** — 3D borehole models, interpolated surfaces, and boring logs published to a web map that project managers and field teams open in a browser.

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

**File delivery modes (how data leaves the device):** Onsite supports two modes, configured per project:
1. **No delivery (default):** Data stays on the device until the user manually exports the .geodinml file (USB, email, shared drive).
2. **Shared network folder:** Onsite reads/writes a synced folder (OneDrive, Dropbox, Google Drive, or any sync service) — useful for field teams who want data pushed as soon as they reconnect.

**Form ownership model (Publish / Retrieve / Revoke):** A form behaves like a single piece of paper — it exists in one place at a time:
- **Publish** (as incomplete or final): sends the form to the shared folder; "Publish as final" hands it to the office.
- **Retrieve:** takes a form back from the shared folder onto the device.
- **Revoke:** pulls a finalised form back out (use with care).
This guarantees two people can't overwrite each other's edits.

### Q: Does GeoDin Onsite enforce standard-compliant data entry?

Yes. GeoDin Onsite includes the same dictionaries and standard-specific dropdown lists as GeoDin Core. When a standard is selected (e.g., ASTM), the app only shows valid options for soil descriptions, enforcing standard-compliant data entry in the field. Ground descriptions are auto-generated from the entered properties. It is described as a "foolproof system" that prevents data quality issues before they enter the workflow.

### Q: Can I print sample labels with QR codes?

Yes. GeoDin Onsite supports **portable field printing of QR-coded sample labels** using a compatible label printer. QR codes are automatically registered with unique identifiers linking to the correct sample ID, borehole, and project. Laboratories can scan the QR code to automatically identify the source project, location, and depth — providing full chain-of-custody traceability.

### Q: Can I customize the Onsite field forms?

Onsite forms are customizable, but not directly by end users — customization is provided as a service by the GeoDin team. This is because geotechnical standards in the background make user-level customization complex. You specify your needs, and GeoDin shapes the forms accordingly. Options include tabbed views vs. single-page layout, and custom test table configurations.

One exception is user-controlled: showing/hiding and reordering pages within a form (for example, hiding the SPT page if you don't log SPT readings) is done directly by the user via the form's page-management controls, set once per project — no service request needed for that specific case.

### Q: Does GeoDin Onsite protect against data loss or crashes?

Yes. Onsite has an optional automatic backup feature (off by default, enabled in Configuration → Backups) that takes timed snapshots of the form you're working on and keeps a configurable number of previous versions (default 10) — restorable any time via Tools → Restore backups. Separately, every form is saved automatically whenever it's closed or Onsite exits, so you don't need to press Save routinely.

### Q: How accurate is GPS capture in GeoDin Onsite?

It depends on the configured source (Configuration → GPS): a device's built-in GPS chip or an external Bluetooth receiver (including survey-grade RTK) gives high accuracy and works offline. The Windows-based IP/Wi-Fi fallback is available on any device but is only accurate to within a few kilometres — **not suitable for geotechnical fieldwork**, use only when nothing better is available. Manual coordinate entry is also supported. Captured positions convert automatically into your project's coordinate system (EPSG code).

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
- **BIM (IFC 4.3):** Ground models export to **IFC 4.3** via Civil 3D's IFC exporter (one-time layer→IFC classification mapping required). No direct IFC export from GeoDin itself.

### Q: Does GeoDin have an API?

Not yet. A **REST API** is planned and actively being developed, targeted for end of 2026. It will be HTTP-based web requests enabling third-party applications to pull geotechnical data directly from GeoDin without exporting to Excel/CSV. The GeoDin team is seeking early adopter input to shape API requirements.

In the meantime, data can be accessed via:
1. **Batch export** (Excel, CSV, AGS, Leapfrog format — available today).
2. **Direct SQL access** to the database (for advanced users).
3. **COM API** — GeoDin can act as a COM server, letting external applications (e.g., a GIS) control the GeoDin interface, run methods, and pull data or graphic images from the database. Documented for software developers at docs.geodin.com.
4. **Custom plug-ins** — external functions can be embedded into the GeoDin interface as method symbols, developed by the GeoDin team for specific client needs.

### Q: Does GeoDin support BIM/IFC?

Yes, via Civil 3D. GeoDin Ground generates **native Civil 3D surfaces and 3D solids**, so the ground model travels with your design when you export from Civil 3D to **IFC 4.3** for a BIM handoff — downstream BIM consumers receive the structure together with the ground beneath it. One-time setup required: in Civil 3D you map GeoDin layer types to IFC classifications and save the mapping in your project template, so every export is consistent. Without that mapping the geometry still exports, but classification metadata is generic. The export is driven by Civil 3D's own IFC exporter — there is no direct IFC export from GeoDin itself.

### Q: Does GeoDin integrate with geotechnical analysis tools like Rocscience (Slide, RS2), GeoStudio, or Plaxis?

There is no live, refreshable link to analysis packages today. The current pathway is data exchange: export your borehole data, cross sections, or ground-model geometry from GeoDin (Excel, CSV, DXF, AGS) or via the Civil 3D model built with GeoDin Ground, then bring it into your analysis tool. Many teams find the Civil 3D pathway already removes most of the manual rebuilding. GeoDin is a data management and visualization platform — it is designed to feed your existing analysis workflow, not replace it. If a specific analysis integration matters to your team, the GeoDin team welcomes that input for the roadmap.

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

### Q: What are GeoDin Ground's current limitations?

GeoDin Ground is deliberately scoped to ground visualisation inside Civil 3D. Current limitations (per the public roadmap page):
- **Import is one-way:** edits in Civil 3D never propagate back to the GeoDin database (by design, to protect the database).
- **Layer matching is by soil type only:** in complex stratigraphies, distinct layers of the same soil type may be connected; use virtual logs to constrain the interpolation.
- **No standards-compliant hatching in Civil 3D:** soil units show as layer colours; for report-quality cross sections with hatching, use GeoDin itself (11 hatching standards).
- **Not yet visualised in Civil 3D:** samples, classification test results, CPT detail, SPT values, and groundwater readings (all remain available in GeoDin and via attached documents).
- **No dedicated cross-section command yet** — use Civil 3D's native alignment/section tools.

Roadmap (directional, no committed dates): richer layer-matching inputs (geological age, genesis), a native cross-section command, expanded volumetric quantity calculations, and better merging of geophysics data.

### Q: Can GeoDin import PDF borehole logs?

Not yet. There is currently no automated PDF-to-data import capability. When data is only available as PDFs, manual data entry is required. However, **AI-based PDF borehole log digitization** is under development (proof of concept completed). GeoDin is seeking a client partner to co-develop this feature using real-world data.

### Q: Does GeoDin run on Mac or mobile?

No. GeoDin Core requires **Windows**. GeoDin Onsite requires **Windows 10 or 11** (not available for iOS or Android), and is designed for tablets and laptops rather than smartphones — full geotechnical logging (layers, samples, tests, well design) is too data-rich to work well on a six-inch phone screen. Rugged Windows tablets are the recommended field device. There is no Mac or Linux version.

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
