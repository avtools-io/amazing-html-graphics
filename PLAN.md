# Amazing HTML Graphics — Research and Implementation Plan

> **Historical planning document.** Maintained in the repository to track completed audits and follow-up work.
>
> Target repository: <https://github.com/avtools-io/amazing-html-graphics>
>
> This plan is based on a research pass across the official EBU OGraf material, the current OGraf ecosystem, HTML-graphics products and projects, related standards/protocols, and the structure and maintenance files of [Amazing Digital Cinema](https://github.com/avtools-io/amazing-digital-cinema). Implementation should start only after this plan has been reviewed and approved.

## 1. Goal

Create **Amazing HTML Graphics**, a curated, vendor-inclusive list for three primary audiences:

1. **Broadcast and motion-picture technicians and engineers** — people who integrate, qualify, deploy, operate, or maintain graphics systems across studios, control rooms, production trucks, cloud production, editorial, finishing, and media pipelines. Their needs include interoperability, lifecycle/control APIs, newsroom and automation integration, fill/key and transport, browser/runtime behavior, deterministic rendering, security, monitoring, and operational reliability.
2. **Creative media professionals** — broadcast and motion designers, graphic designers, technical artists, editors, compositors, data-visualisation practitioners, and film/documentary creators who author, animate, adapt, and render data-driven graphics. Their needs include visual authoring, animation, typography, templates, maps/charts, Lottie/Rive/After Effects workflows, preview/validation, and live plus offline/NLE delivery.
3. **Media-focused software developers** — developers building OGraf Graphics, HTML graphics, editors, controllers, renderers, automation, plugins, browser hosts, and HTML-to-video systems. Their needs include specifications, schemas/types, Web Components, libraries, reference implementations, test tooling, performance/determinism guidance, security, and integration examples.

Secondary audiences include graphics operators, technical directors, newsroom and production-automation teams, educators, students, researchers, and technical decision-makers evaluating these workflows.

The list will focus on **HTML-based graphics used in live television and post-production**, with **EBU OGraf as its centre of gravity**, while also covering the wider web-graphics ecosystem that makes those workflows possible. Film, documentary, explainers, data visualisation, and other non-live/offline uses will be first-class targets rather than treated as out of scope.

Audience implications for curation:

- Every entry should help at least one primary audience **author, develop, integrate, operate, evaluate, test, or learn** professional HTML graphics.
- Descriptions should make the practical role clear instead of assuming that a product name or generic web capability explains its media relevance.
- Balance creative resources with engineering and operational material; the list must not become only a vendor catalogue, only a JavaScript-library directory, or only a design-inspiration gallery.
- Hosted software products and focused marketplaces are in scope, but standalone consulting agencies and single-company service listings are not; include reusable public resources they publish instead of advertising the company itself.
- Include both live/on-air and non-real-time/editorial needs, and avoid treating streaming overlays as the whole field.
- Prefer professional-media relevance, but do not require a product to be broadcast-exclusive when it materially enables OGraf, motion-picture, post-production, or data-driven graphics work.
- Keep explanations accessible across disciplines: define specialist broadcast terms for developers and browser/software terms for production practitioners.

The project should resemble Amazing Digital Cinema in editorial voice, layout, licensing, contribution workflow, and maintenance tooling, but use a taxonomy designed for HTML graphics rather than copying cinema categories.

## 2. Research findings that shape the list

### 2.1 OGraf's role

OGraf solves a narrower and more important problem than “graphics made with HTML” generally:

- It specifies a portable Graphic package represented by a `*.ograf.json` manifest, a JavaScript ES module exporting a Web Component, and local assets.
- It standardises the Graphic lifecycle and actions: `load()`, `dispose()`, `playAction()`, `stopAction()`, `updateAction()`, and `customAction()`.
- Non-real-time Graphics additionally expose `goToTime()` and `setActionsSchedule()`, which makes post-production, film, documentary, and deterministic offline rendering part of the specification rather than an afterthought.
- The manifest describes metadata, a JSON Schema/GDD-based data model, steps, action durations, thumbnails, and renderer requirements.
- Vendor extensions are allowed under `v_`-prefixed keys.
- The separate OGraf Server API is a REST API defined with OpenAPI between Controllers and rendering systems.
- OGraf deliberately separates Editors, Controllers, Servers, Renderers, and Graphics so products from different vendors can be combined.
- The historical **Graphics Data Definition (GDD)** project has been deprecated and incorporated into OGraf. It remains important as background and for older templates/tools.

The official repository currently describes Graphics v1 and Server API v1 as stable and production-ready. Older talks, editor documentation, and product pages may still call one or both “draft”; entries must use current official status and date historical material accurately.

### 2.2 Compatibility needs precise language

The research found several different meanings of “supports OGraf” or “supports HTML graphics”. The README must not collapse them into one claim:

1. **OGraf package author/exporter** — creates an OGraf manifest and compatible Web Component.
2. **OGraf package importer/renderer** — directly loads and executes an OGraf Graphic.
3. **OGraf controller/server** — implements the Graphics lifecycle and/or Server API.
4. **HTML/browser host** — can display the renderer URL from `ograf-server`, but does not necessarily understand an OGraf package itself.
5. **General web-native graphics system** — uses HTML/CSS/JavaScript but currently has no documented OGraf interchange.
6. **Output/conversion appliance** — turns a URL/browser composition into SDI, NDI, ST 2110, SRT, or a file.
7. **Adjacent control/data system** — triggers or supplies graphics through MOS, AMCP, REST, WebSocket, OSC, or another integration.

Descriptions will say exactly which relationship is documented. In particular:

- CasparCG, OBS Studio, and vMix can host the web renderer from `ograf-server`; this alone should not be described as direct/native OGraf package support.
- Singular.live and Viz Flowics are important web-native/HTML5 products, but no canonical public source was found establishing direct OGraf package support. They belong in the broader HTML-platform section, not the confirmed OGraf implementation section.
- Community sites and vendor claims are useful but will not override the EBU specification or a product's canonical documentation.

### 2.3 Confirmed and emerging OGraf ecosystem

The initial README should investigate and, where canonical documentation remains available, include the following.

#### Official specification and reference material

- [OGraf project site](https://ograf.ebu.io/).
- [ebu/ograf](https://github.com/ebu/ograf) specification repository, changelog, issues, JSON Schemas, Server API OpenAPI document, TypeScript definitions, and examples.
- [`ograf` npm package](https://www.npmjs.com/package/ograf) containing informative TypeScript definitions for the Graphics and Server APIs.
- [EBU HTML Graphics Working Group](https://tech.ebu.ch/groups/html-graphics).
- EBU's 2025 article and webinar slide deck introducing cross-platform HTML graphics.

#### Editors, authoring tools, and converters

- [DJ HTML Creator](https://djhtmlcreator.com/) — visual HTML/Lottie template authoring and OGraf export.
- [Eyevinn OGraf Template Editor](https://github.com/Eyevinn/ograf-editor) — open-source browser editor and package export.
- [Loopic](https://www.loopic.io/ograf) — commercial no-code HTML graphics editor with OGraf export.
- [NoaCG Studio](https://github.com/miwco/NoaCG-Studio) — open-source visual/code/AI-assisted authoring and multi-target export, including OGraf.
- [OGraf Studio](https://github.com/zerodensity/ograf-studio) — open-source visual editor, runtime, validation/export packages, and optional AI/MCP authoring.
- [StreamShapers Ferryman](https://github.com/Streamshapers/StreamShapers-Ferryman) and its After Effects OGraf Export extension — Lottie/After Effects to HTML/OGraf conversion.
- [rive-ograf-wrapper](https://github.com/cndgfxteam/rive-ograf-wrapper) — emerging Rive-to-OGraf converter; explicitly label its documented compliance and runtime limitations.

#### Development, testing, schemas, and validation

- [OGraf Devtool](https://github.com/SuperFlyTV/ograf-devtool) and hosted app.
- [OGraf Validator](https://github.com/Streamshapers/OGraf-Validator), hosted validator, and `@streamshapers/ograf-validator-core` npm package.
- [ograf.dev tools](https://ograf.dev/tools): package checker/runtime harness and schema explorer; identify the site as independent from EBU.
- [ograf-form](https://github.com/SuperFlyTV/ograf-form) Web Component/npm package for generating forms from OGraf/GDD schemas.
- [`ograf-graphics` agent skill](https://github.com/heretorecord/ograf-graphics-skill) for scaffolding and validating OGraf v1 packages.
- The official renderer-test Graphic and examples as conformance/development material.

#### Renderers, servers, controllers, and integrations

- [OGraf Simple Rendering System (`ograf-server`)](https://github.com/SuperFlyTV/ograf-server) — browser renderer, graphics management, Server API, and controller pages.
- [SPX Graphics](https://spxgraphics.com/software/integrations#ograf) / [SPX-GC](https://github.com/TuomoKu/SPX-GC) — documented OGraf rendering/control plus commercial Solo, Production, and Broadcast workflows.
- [H2R Graphics](https://h2r.graphics/docs/graphics/ograf/) — direct OGraf Graphic import and generated operator fields.
- [NetOn.Live LiveOS](https://www.neton.live/) — vendor-documented OGraf-compliant HTML graphics engine.
- [Erizos](https://docs.erizos.tv/) — changelog-documented OGraf support in addition to its HTML Composer path.
- [nxtedition/nxt-graphics](https://github.com/nxtedition/nxt-graphics) — OGraf host Graphic; also investigate nxtedition's editing-timeline integration.
- [DaVinci Resolve 21 and Fusion Studio 21](https://documents.blackmagicdesign.com/SupportNotes/DaVinci_Resolve_21_New_Features_Guide.pdf) — official OGraf/Lottie support for editorial and compositing; document beta/version caveats from official material only.
- [ograf-to-image-sequence-renderer](https://github.com/pjaspinski/ograf-to-image-sequence-renderer) — small non-real-time/offline renderer; label maturity.

#### Examples and community resources

- Official EBU examples.
- [Johan Nyman's OGraf graphics stash](https://github.com/nytamin/ograf-graphics).
- [ograf.dev](https://ograf.dev/) tutorials, interactive demos, package tools, and [ecosystem directory](https://ograf.dev/ecosystem); label as an independent community site.
- Before finalising the inventory, compare every project/tool linked from the ograf.dev ecosystem page with this list. Verify each against its canonical source, add strong missing entries, and record a specific exclusion reason for duplicates, unsupported claims, dead projects, or items outside scope.
- [ograf-dash.js](https://github.com/ryanmccartney/ograf-dash.js) as a small proof of concept for rendering OGraf over a DASH player.
- [LottiesForBroadcast](https://github.com/Streamshapers/LottiesForBroadcast) as Lottie/Ferryman/SPX/CasparCG examples.

Additional repositories found in the second pass need conservative placement:

- [CBC/Radio-Canada `mxl-hands-on`](https://github.com/cbcrc/mxl-hands-on) — Apache-2.0 workshop material containing an HTML5 keyer and OGraf teleprompter transported over MXL; list as an educational example, not a finished graphics product.
- [`ofxOGraf`](https://github.com/Jonathhhan/ofxOGraf) — MIT-licensed openFrameworks authoring/runtime addon with an OGraf v1 Web Component, native/Emscripten rendering, deterministic seeking, and an optional After Effects import path; mark as emerging and preserve its documented fidelity boundaries.
- [Keyframe Character Studio](https://github.com/ErtugrulAK/keyframe-character-studio) — MIT-licensed browser motion editor/live director with OGraf export tests; verify the released export path and maturity before inclusion.
- [`dom-compositor-proto`](https://github.com/timokorkalainen/dom-compositor-proto) — MIT-licensed headless DOM template editor/renderer prototype; include only if OGraf functionality is documented in a release or canonical README, not merely present on a development branch.
- [Resolve OGraf examples](https://github.com/mug-lab-3/resolve-ograf) — learning examples for Resolve's OGraf loader whose README explicitly says they are experimental and unsuitable for production.
- [Resolve Tools Public OGraf documentation](https://github.com/jdanna/Resolve_Tools_Public/tree/main/docs/OGraf%20HTML%20Templates) — unofficial developer notes and examples for Resolve/Fusion OGraf Titles; label as community documentation and cross-check against Blackmagic's official version-specific documentation.
- [AI Atelier](https://github.com/aiatelie/ai-atelie) — MIT-licensed, local-first HTML/JSX/CSS design tool containing an OGraf export service; include only after the export's packaging and lifecycle compliance are verified.

Emerging repositories found through GitHub should only be included after checking their canonical README, licence, releases/activity, and implemented OGraf behavior. Repository names, test filenames, roadmap documents, or generated claims alone are not sufficient evidence. Very small proofs of concept should be described as experimental examples rather than production systems.

### 2.4 Required and supplementary videos and talks

Include these user-specified videos under **Videos & Talks**:

- [OGraf](https://www.youtube.com/watch?v=gw2SnjeGW9Q) — OGraf EBU, 4:54.
- [OGraf: An Open Specification for HTML-Based Graphics](https://www.youtube.com/watch?v=6IMGzvxe1AY) — smpteconnect, 42:47.

The second pass also verified these focused demonstrations and tutorials:

- [Using OGraf with SPX and Loopic](https://www.youtube.com/watch?v=P6VEWyv7-P0) — SPX Graphics, 1:43.
- [everviz Maps in Erizos Studio | OGraf Open Broadcast Graphics Integration](https://www.youtube.com/watch?v=-S_gBYPyCiw) — everviz, 0:13.
- [Using an OGraf created with After Effects and StreamShapers Ferryman](https://www.youtube.com/watch?v=u4wruk2QTs0) — StreamShapers, 1:17.
- [Kickstart Day Pitch #8: HTML-Based Graphics for Multi-Platform Production](https://www.youtube.com/watch?v=3YZyWCjHK9U) — IBCShow, 5:33.
- [HTML Graphics with Rive and CasparCG (Tutorial)](https://www.youtube.com/watch?v=BnV55qu6vvg) — Aiden Wilson, 31:27.
- [SPX-GC Overview](https://www.youtube.com/watch?v=e5LTFC9MlOI) — Tuomo Kulomaa, 6:53.
- [SPX-GC: HTML Templates](https://www.youtube.com/watch?v=AdZATSBByng) — Tuomo Kulomaa, 5:03.
- [CasparCG HTML Templates - Part 2 - Basic Animated Lowerthird](https://www.youtube.com/watch?v=2oJaECoOPoQ) — Geert Verhoeff, 11:00.
- [Trying out Loopic to create a simple CasparCG Lower Third HTML Template](https://www.youtube.com/watch?v=gZRYTmngqLw) — Geert Verhoeff, 17:29.

Retain only videos that teach, demonstrate, or historically contextualise a concrete workflow; avoid promotional reels without technical value. Record title, channel, duration, publication date, and whether the content predates stable OGraf v1 during final verification. Also include the EBU webinar slide deck and a canonical recording/event page if available.

### 2.5 Related standards and protocols

The list needs a dedicated **Standards, Specifications & Protocols** area, split so readers can distinguish Graphic interchange from newsroom control, web foundations, and media transport.

#### OGraf and template/control specifications

- OGraf Graphics specification.
- OGraf Server API/OpenAPI definition.
- Legacy Graphics Data Definition (GDD), clearly marked deprecated/superseded by OGraf.
- CasparCG HTML Template/HTML Producer contract.
- Advanced Media Control Protocol (AMCP).
- SPX template definition, as a product-specific HTML-template format.

#### Newsroom, automation, discovery, and control

- [MOS Protocol](https://mosprotocol.com/) — Media Object Server protocol, including the widely deployed 2.8.5 material and WebSocket/WSS-oriented MOS 4.0. State explicitly that MOS exchanges newsroom objects/rundowns/status and does not itself define a portable HTML Graphic format.
- [`sofie-mos-connection`](https://github.com/Sofie-Automation/sofie-mos-connection) — JavaScript MOS implementation.
- AMWA NMOS family, especially IS-04 discovery/registration, IS-05 connection management, IS-07 events/tally, and IS-12 control/monitoring where relevant. Explain that NMOS manages IP-media infrastructure and control rather than defining HTML templates.
- Ember+ and OSC as adjacent control protocols where tools in the list actually use them.

#### Web platform foundations

- WHATWG HTML and Custom Elements/Web Components.
- ECMAScript modules.
- CSS, SVG, Canvas, WebGL, and Web Animations.
- JSON Schema 2020-12 and the GDD subset/extensions used by OGraf.
- OpenAPI.
- Web Fonts and relevant browser capability documentation.

#### Video, colour, safety, and outputs

- SMPTE ST 2110 suite, especially ST 2110-20 video/fill-key workflows; do not imply that ST 2110 defines graphics templates.
- NDI as a common graphics transport/output ecosystem.
- EBU R 95 safe areas for 16:9 SD/HD/UHD.
- EBU R 103 video signal tolerances.
- ITU-R BT.709, BT.2020, and BT.2100 where colour/HDR rendering is discussed.
- EBU R 143 cybersecurity recommendations as an optional operational resource for networked/cloud HTML graphics, not a graphics format.
- [SMPTE's free standards publication portal](https://pub.smpte.org/doc/) as the preferred canonical access point for relevant SMPTE documents.

Do **not** describe SMPTE ST 2019-1 as a general alpha-channel or fill/key standard: it defines the VC-3 Picture Compression and Data Stream Format. Include it only if a listed implementation has a specific, correctly sourced VC-3 dependency. Avoid padding the section with generic transport specifications unless a listed graphics product uses them materially.

### 2.6 Wider HTML-graphics products and projects

The broader list should include products with a demonstrable relationship to web-rendered graphics, even when they do not implement OGraf.

#### Web-native graphics platforms and services

Initial candidates:

- Dizplai live graphics.
- Ease Live interactive/player-side overlays.
- Grass Valley AMPP graphics/Live Producer X/Playout X.
- Grabyo Producer and supported HTML graphics integrations.
- LIGR for cloud/data-driven sports graphics.
- MXMZ editor/operator/NLE workflows.
- Overlays.uno and Poltergeist for browser-source streaming/event overlays.
- Singular.live, including client-side rendering and Recast/offline capture workflows.
- Viz Flowics, including data connectors, Control API, MOS Gateway, NDI/SDI integrations, and post-production recording workflows.
- Other products will be admitted only with a canonical page showing HTML, SVG, Canvas, Web Component, URL/browser-source, or equivalent web-runtime relevance.

#### Professional HTML renderers and output/key-fill systems

Initial candidates:

- AWS Elemental Live and MediaLive HTML5 motion overlays.
- Crystal Vision M-WEBKEY.
- Etere ETX/ETX-G HTML5/WebGL graphics.
- Lawo HOME Graphic Inserter.
- Medialooks MPlatform/MFormats HTML5 graphics plugin/SDK.
- RT Software Swift Engine and associated Swift authoring/newsroom products.
- SDI-Ware.
- Sienna GraphicArtist.
- Softron OnTheAir WebLink.
- Vindral Composer.
- Viz Connect Tetra.
- WebLinked (open source).
- keyfillwebview (open source).
- Videon LiveEdge Graphix, with edition/frame-rate limitations stated accurately.
- Aveco CGManager/Redwood WHITE where canonical documentation confirms HTML templates and renderer integration.

Products whose “HTML5” claim only means a browser-based control UI, rather than HTML-rendered output or templates, should not be put in this category.

#### Browser-capable production hosts

- OBS Studio Browser Source and `obs-browser`.
- vMix Web Browser input.
- Telestream Wirecast Web Page/Web Display source.
- LiveU Studio embedded webpage/HTML overlay support.
- Vizrt TriCaster/Vectar HTML Buffer/LiveLink workflows.
- mimoLive Web Browser Capture.
- CasparCG HTML Producer.

These entries should explain that browser hosting is not the same as OGraf package support.

#### Newsroom, automation, rundown, and data integration

- MOS itself and relevant open libraries.
- Cuez Automator/MOS Connector.
- Sofie TV Automation.
- SuperConductor.
- SVT Bridge.
- Yle Caspartool.
- Bitfocus Companion.
- Viz Flowics MOS Gateway.
- SPX Broadcast MOS/NRCS integrations.
- RT Software Swift News/Live.
- Relevant CasparCG clients and AMCP libraries.

Do not list generic NRCS products unless their graphics integration is documented and useful to this audience.

### 2.7 Reuse from Awesome Broadcasting

Review and carry over **every item** in Awesome Broadcasting's current **Animation, Graphics & Video Playout** section, but re-check the canonical source and place it according to its actual HTML-graphics relevance rather than copying it blindly:

- Aurena.
- Blender.
- Bridge.
- caspar-obs-client.
- CasparCG.
- ffplayout.
- Macadam, including its Electron/Sevruga HTML/CSS/SVG path.
- Nebula.
- NodeCG.
- OGraf.
- Open Playout Automation.
- ossia.
- Sofie TV Automation.
- SPX Graphics Controller.
- StreamShapers Ferryman.
- Studio TV Player.

Likely placement:

- Core HTML graphics: NodeCG, OGraf, SPX, Ferryman, CasparCG, Macadam.
- Control/automation: Bridge, caspar-obs-client, Nebula, Open Playout Automation, Sofie.
- Related animation/playout: Aurena, Blender, ffplayout, ossia, Studio TV Player.

Also review [Awesome NodeCG](https://github.com/nodecg/awesome-nodecg), CasparCG's related-projects page, and the EBU organisation's repositories for additional focused entries.

### 2.8 HTML authoring, animation, visualisation, and developer libraries

Create curated developer sections rather than treating “any JavaScript library” as relevant. Each entry must explain a concrete graphics use such as Web Component packaging, timeline animation, ticker/scoreboard rendering, data-driven charts/maps, responsive typography, deterministic capture, or template validation.

- **Web Components and component authoring:** native Custom Elements/Web Components, [Lit](https://lit.dev/), [Stencil](https://stenciljs.com/), and [FAST](https://fast.design/). Explain their relevance to OGraf's default-exported Web Component contract; do not imply that using one makes a component OGraf-compliant.
- **Animation and authored motion:** [GSAP](https://gsap.com/) with its PixiPlugin, Web Animations API, [Anime.js](https://animejs.com/), [Motion](https://motion.dev/), [Theatre.js](https://www.theatrejs.com/), [Lottie/lottie-web](https://github.com/airbnb/lottie-web), [dotLottie](https://dotlottie.io/), and [Rive](https://rive.app/). Distinguish authoring applications/formats from web runtimes. GSAP must be labelled free-to-use/source-available under its Standard No Charge License, not open source; PixiJS is MIT-licensed open source.
- **2D/3D rendering:** SVG, Canvas, [PixiJS](https://pixijs.com/), Three.js, and Babylon.js; include Fabric.js or Konva only where editor-building utility is described.
- **Data graphics and maps:** [D3](https://d3js.org/), [Vega-Lite](https://vega.github.io/vega-lite/), [Apache ECharts](https://echarts.apache.org/), [Chart.js](https://www.chartjs.org/), [MapLibre GL JS](https://maplibre.org/maplibre-gl-js/docs/), [Leaflet](https://leafletjs.com/), and [Turf](https://turfjs.org/) for election, sports, weather, explainer, and documentary graphics.
- **Typography and font handling:** [Fitty](https://rikschennink.github.io/fitty/) for fitting dynamic text, [opentype.js](https://opentype.js.org/) for font/path work, and the CSS Font Loading API for predictable readiness before playout or capture.
- **Validation and generated forms:** Ajv, JSON Forms, `ograf-form`, and the official OGraf/GDD schemas.
- **Testing and browser automation:** Playwright, Puppeteer, screenshot/visual-regression testing, and Chrome DevTools profiling where they are applied to Graphic lifecycle tests, transparent rendering, or offline capture.
- **Build and deployment:** Vite only in the context of an established graphics starter/boilerplate, not as a generic web-development listing.

Prefer a smaller explained set over exhaustive framework coverage. Verify each library's current licence from its canonical repository or package metadata; “free” and “open source” are not interchangeable.

### 2.9 Post-production, film, documentary, and HTML-to-video

This must be a substantive section because OGraf explicitly defines non-real-time rendering and the project is not broadcast-only.

#### Product/NLE workflows

- DaVinci Resolve 21/Fusion Studio 21 OGraf and Lottie support.
- SPX's Premiere Pro/NLE workflow.
- MXMZ's Premiere Pro panel and MAM integration.
- Singular Recast and documented alpha-recording workflows.
- Vizrt/Adobe and Flowics post-production workflows where the output is still relevant to HTML graphics.
- nxtedition's OGraf/HTML timeline integration.

#### Programmatic and offline browser rendering

Candidates:

- Remotion.
- Motion Canvas.
- HyperFrames.
- Cetus.
- html5-animation-video-renderer.
- puppeteer-capture.
- htmlrec.
- BeamToIX.
- render-d3-video.
- The small OGraf image-sequence renderer.

Descriptions should distinguish deterministic time/seek-based renderers from screen recording, and document alpha-capable outputs (such as image sequences, ProRes 4444, or WebM alpha) only when the project itself supports them.

#### Documentary/data-visualisation workflows

Include focused resources for browser-native charts, maps, timelines, election graphics, explainers, and repeatable data-driven video. D3/MapLibre/Observable-style tools can be useful here, but generic web-design galleries should remain out of scope. Add articles or case studies that actually describe data visualisation in documentary film or rendered-video workflows.

### 2.10 Education and design/operational guidance

Potential resource categories:

- OGraf tutorials and getting-started material.
- CasparCG HTML Template Guide and official HTML Producer documentation.
- SPX “How to create HTML graphics” and template documentation.
- Vizrt's HTML5 live-production guide.
- AWS's HTML5 motion-graphics walkthrough.
- Rive-to-CasparCG and Lottie/Ferryman workflows.
- `learn-html-gfx` if its content and maintenance pass final review.
- Browser rendering performance material from Chromium, including compositor-friendly `transform`/`opacity` animation and the limitations of `requestAnimationFrame` for frame accuracy.
- EBU R 95 safe-area guidance and accessibility/readability material.

Book candidates found in research can be included sparingly:

- *Broadcast Graphics On the Spot* for traditional broadcast design/workflow fundamentals.
- *Motion Graphics: Graphic Design for Broadcast and Film* for historical/design context.
- *Core HTML5 Canvas* and *Foundation HTML5 Animation with JavaScript* for browser-animation fundamentals, clearly labelled as general rather than OGraf-specific.

### 2.11 Scientific and professional literature

Create a dedicated **Scientific Literature & Theses** subsection, separate from vendor articles, documentation, and practitioner case studies. Seed it with the following source-verified candidates:

- [*Presentation Accuracy of the Web Revisited: Animation Methods in the HTML5 Era*](https://doi.org/10.1371/journal.pone.0109812) — peer-reviewed browser animation timing/accuracy research.
- [*A Survey of Digital Television Interactivity Technologies*](https://doi.org/10.3390/s22176542) — peer-reviewed context for interactive television delivery and standards.
- [*A Cross-Device and Cross-OS Benchmark of Modern Web Animation Systems*](https://doi.org/10.3390/jimaging12010045) — cross-platform animation performance research; verify final bibliographic metadata at implementation time.
- [*Titling for Live Streaming and File-Based Broadcast Workflows*](https://doi.org/10.5594/M001731) — SMPTE conference paper on data-driven titling across live and file-based outputs.
- [*Broadcast Media Creation as a Service*](https://doi.org/10.5594/JMI.2020.3024028) — SMPTE paper on cloud-hosted media creation architecture.
- [*Television Infographics as Orienting Response*](https://doi.org/10.1177/19312431211039500) — peer-reviewed study of attention and recall around television infographics.
- [Henri Johansson's 2025 thesis](https://urn.fi/URN:NBN:fi:amk-2025052918037) on Yle's SPX/CasparCG HTML5 graphics workflow.
- [Ismo Vaittinen's 2016 thesis](https://urn.fi/URN:NBN:fi:amk-2016060612041) on an open-source CasparCG graphics/video playout system.
- *TV Graphics Personalization Using In-Band Events* — relevant research on DASH event-driven overlays; use a stable publication record and do not invent a DOI if none can be verified.

Use DOI/publisher or institutional-repository links, include year and publication type, and avoid overstating conclusions beyond abstracts/full text. Put EBU presentations, vendor technical papers, implementation write-ups, and production examples in **Articles & Case Studies**, with disclosure when the source is also the vendor.

### 2.12 Forums and communities

Include active, focused support and practitioner channels, using durable landing pages rather than expiring invite URLs where possible:

- EBU OGraf [Issues](https://github.com/ebu/ograf/issues) and [Pull Requests](https://github.com/ebu/ograf/pulls).
- [ograf.dev](https://ograf.dev/) community resources.
- [CasparCG Forum](https://casparcgforum.org/) and [GitHub Discussions](https://github.com/CasparCG/server/discussions).
- NodeCG's official community/Discord link from the [NodeCG repository](https://github.com/nodecg/nodecg).
- SPX Graphics Discord through its durable [support page](https://spxgraphics.com/support/).
- [GSAP Forums/community](https://gsap.com/community/).
- [PixiJS GitHub Discussions](https://github.com/pixijs/pixijs/discussions/) and its official Discord link where exposed by the project.
- [Three.js Discourse](https://discourse.threejs.org/).
- [LottieFiles Forum](https://forum.lottiefiles.com/).
- Rive Discord through the official [Rive documentation](https://rive.app/docs/getting-started/introduction).
- [Remotion Discord](https://www.remotion.dev/discord).
- [Motion Canvas Discussions](https://github.com/motion-canvas/motion-canvas/discussions).
- [D3 community page](https://d3js.org/community), D3 GitHub Discussions, and Observable's forum where directly relevant.
- [MapLibre community/Slack page](https://maplibre.org/community/).

Verify activity and official affiliation immediately before inclusion. Describe `ograf.dev` as independent, distinguish issue trackers from discussion communities, and do not expose personal contact details.

### 2.13 Testing, performance, determinism, and security

Add focused operational/developer resources covering:

- Playwright and Puppeteer lifecycle/integration tests, frame capture, and browser-version pinning.
- Screenshot and visual-regression testing at target resolutions, device pixel ratios, alpha backgrounds, fonts, and representative data extremes.
- Chrome DevTools Performance/Rendering tooling and compositor-friendly `transform`/`opacity` guidance.
- CSS Font Loading API use and explicit asset/font readiness rather than timing playback from page load assumptions.
- Deterministic animation guidance: explicit timeline time, OGraf `goToTime()`, seeded randomness, mocked/frozen data and clocks, and the distinction between real-time `requestAnimationFrame()` playback and non-real-time frame stepping.
- [DOMPurify](https://github.com/cure53/DOMPurify), Content Security Policy, and Trusted Types for untrusted newsroom/operator data and remotely sourced HTML; explain that sanitisation, CSP, and Trusted Types solve different problems.
- Offline/self-contained package practices, dependency pinning, browser/runtime qualification, cache behavior, network failure handling, safe-area tests, and color/alpha output checks.

Keep this section browser-graphics-specific rather than becoming a general web-security or test-tool list. Never suggest inserting untrusted data through `innerHTML`, and avoid claiming deterministic or frame-accurate output without a documented time-control and capture model.

## 3. Proposed repository contents

The committed repository should initially contain:

```text
.
├── .gitignore
├── CONTRIBUTING.md
├── LICENSE.md
├── README.md
└── scripts
    ├── README.md
    ├── check-links.sh
    └── check-policies.json
```

Possible follow-up, only if wanted after the first version:

```text
.github/
└── workflows/
    └── links.yml
```

Do not add a package manager, site generator, application code, badges requiring third-party services, or copied vendor logos for the initial release. The repository's value is the carefully researched Markdown list.

`PLAN.md` was initially local but is now maintained in the repository at the maintainer's request.

## 4. README design

### 4.1 Proposed introduction

Adapt the successful Amazing Digital Cinema introduction rather than inventing a different voice:

- `# Amazing HTML Graphics`.
- One sentence explicitly naming broadcast and motion-picture technicians/engineers, creative media professionals, and media-focused software developers, including live, post, film, and documentary work.
- One sentence explaining coverage: design/authoring, data, templates, validation, control, rendering, compositing, playout, transport, offline rendering, standards, software, services, and learning resources.
- A bold invitation to contribute.
- The same non-technical contribution-guide pattern as Amazing Digital Cinema, using relative links where possible and the new repository's issue URL.
- An inspiration/attribution paragraph linking:
  - [Amazing Digital Cinema](https://github.com/avtools-io/amazing-digital-cinema), the direct blueprint;
  - [Awesome Broadcasting](https://github.com/ebu/awesome-broadcasting), especially Animation, Graphics & Video Playout;
  - the wider [Awesome](https://github.com/sindresorhus/awesome) project.
- Preserve the rationale for calling the list “Amazing”: it deliberately includes excellent commercial/non-open-source resources, unlike an open-source-only Awesome list.
- Add a short scope note: OGraf compatibility is called out explicitly, while plain HTML support must not be read as OGraf compliance.
- Add a compact classification legend for open-source, source-available, commercial, hosted/SaaS, open-core, freeware, and maturity/status qualifiers so readers do not have to infer licensing or deployment models from category placement.

### 4.2 Proposed table of contents and headings

```markdown
# Amazing HTML Graphics

- Contributors to This List
- OGraf
  - Official Specification & Governance
  - Graphics, Schemas & APIs
  - Editors & Exporters
  - Development & Validation
  - Renderers, Servers & Controllers
  - Examples & Templates
- Organizations & Communities
- Resources
  - Articles & Case Studies
  - Scientific Literature & Theses
  - Books
  - Documentation & Knowledge Sources
  - Education & Tutorials
  - Forums & Community
  - Lists & Landscapes
  - Videos & Talks
  - Standards, Specifications & Protocols
    - Graphics & Template Interchange
    - Newsroom, Automation & Control
    - Web Platform
    - Media Transport, Colour & Safety
  - Test Material & Examples
- Tools & Products
  - Authoring, Animation & Conversion
  - Web Components & Graphics Libraries
  - Data Visualization & Maps
  - Typography & Font Handling
  - Testing, Performance & Security
  - Open-source Graphics Systems
  - Commercial & Cloud Graphics Platforms
  - Browser-capable Production Hosts
  - Rendering, Key-Fill & Video Output
  - Newsroom, Rundown & Automation
  - Sports, Data & Audience Graphics
  - Post-production & NLE Integration
  - HTML-to-Video & Offline Rendering
  - Interactive & Player-side Graphics
  - Templates & Marketplaces
  - Related Animation, Graphics & Playout
```

During implementation, collapse headings that end up with fewer than two strong entries and avoid listing the same product repeatedly unless it has genuinely different resources (for example, SPX software versus SPX documentation/specification).

### 4.3 Entry format

Follow Amazing Digital Cinema:

```markdown
- [Resource](https://example.com/) – Short, factual description ending with a period.
```

Rules:

- Alphabetical within each category.
- Prefer canonical product docs/repository over resellers, press coverage, listicles, or mirrors.
- Exclude standalone consulting/service-company entries. This does not exclude hosted/SaaS software products, product support, integration documentation, or focused template/asset marketplaces.
- Begin every software/product entry's description with a compact, bold classification, for example `**Open source (MIT).**`, `**Commercial.**`, `**Commercial; hosted/SaaS.**`, `**Open core.**`, `**Freeware.**`, or `**Source available; free to use.**`. Combine labels when needed and verify exact licence language from a canonical source.
- Do not use “open source” for source-available/custom licences, no-charge proprietary software, public repositories without an open-source licence, or hosted products that merely expose APIs. If a repository has no asserted licence, say so or omit it.
- Mark archived, deprecated, experimental, beta, proof-of-concept, or unmaintained projects with a separate bold qualifier.
- Describe the OGraf relationship in prose using the compatibility levels in section 2.2; a classification label must never imply compliance.
- Documentation, standards, papers, videos, and communities do not need software-availability labels.
- Describe compatibility conservatively and link the page that proves it.
- Avoid superlatives and vendor marketing language.
- Avoid prices because they become stale; mention free/open-source/community editions only when stable and relevant.
- No unsupported “broadcast-grade”, “frame-accurate”, “native”, “any renderer”, or “production-ready” claims.
- Use “OGraf Graphic”/“Graphics” where referring to the specification's defined object; use ordinary lowercase “graphics” otherwise.
- Use en dashes consistently, as in the source project.

## 5. Supporting files adapted from Amazing Digital Cinema

### `CONTRIBUTING.md`

Reuse the existing concise guide and adapt it to require:

- relevance to HTML/web-based graphics in live, streaming, post-production, film, or documentary workflows;
- commercial entries are welcome;
- one resource entry per pull request (and recommend one logical entry commit rather than bundling unrelated additions);
- canonical links and short factual descriptions;
- precise evidence for OGraf compatibility;
- alphabetical placement;
- full-stop/period endings;
- no affiliate/referral links;
- archived/deprecated status disclosure.

### `LICENSE.md`

Use the same **Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)** licence as Amazing Digital Cinema. This is appropriate for a curated documentation/list project and keeps adapted material under the same terms.

### `.gitignore`

Start from the blueprint's minimal file (`.idea`) and only add editor/OS files that actually appear. Do not commit a `PLAN.md` ignore rule by default.

### `scripts/check-links.sh`

Copy the proven Amazing Digital Cinema link checker and make only project-specific changes:

- user agent: `Amazing-HTML-Graphics-Link-Checker/1.0`;
- temporary directory prefix: `ahg-link-check`;
- retain HEAD-to-range-GET fallback, retries, exponential backoff, redirect handling, per-host locking, parallel jobs, and policy-based exceptions.

### `scripts/check-policies.json`

Start clean rather than copying cinema-specific exceptions. Add only exact URL/status exceptions observed while checking this README. EBU `tech.ebu.ch` may need narrowly scoped 403 exceptions; YouTube may need link-check handling based on actual curl results.

### `scripts/README.md`

Adapt command examples and wording to Amazing HTML Graphics.

## 6. Implementation phases

### Phase 0 — Repository setup

1. Confirm branch choice. Recommendation: `main` for the new empty repository; use `master` only if matching Amazing Digital Cinema is more important.
2. Initialise Git in the current directory and add `git@github.com:avtools-io/amazing-html-graphics.git` as `origin` (the remote is private and currently empty).
3. Keep research scratch files local; `PLAN.md` is maintained in the repository.
4. Confirm no implementation files exist remotely before creating files.
5. Do not create implementation commits or push until this plan has been discussed, approved, and implementation is explicitly requested.

### Phase 1 — Build a source-backed inventory

1. Turn the candidate lists above into a working inventory with fields for category, canonical URL, organisation, role, licence/deployment type, OGraf relationship, maintenance status, evidence URL, and intended one-entry commit message.
2. Compare the inventory systematically with every project/tool on [ograf.dev/ecosystem](https://ograf.dev/ecosystem), then re-open every canonical page immediately before inclusion.
3. For OGraf compatibility, require one of:
   - official product documentation;
   - the product's canonical repository README/source;
   - an official vendor release note.
4. Check renamed/acquired/discontinued products and link current destinations where possible.
5. Reject SEO listicles, duplicate mirrors, empty repositories, generic overlay galleries, standalone consulting/service-company listings, and projects with no documented graphics functionality.
6. Apply an audience test to every candidate: record which primary audience it serves and what professional task it enables. Reject generic web/design tools whose relevance cannot be stated concretely in one short description.
7. Keep a short “not included / reason” scratch list during implementation so borderline entries are handled consistently; do not commit the scratch list unless requested.

### Phase 2 — Draft the OGraf core first

1. Write the introduction and scope warning.
2. Add the official specification, schemas, API, examples, and governance links.
3. Add confirmed editors/exporters, developer tools, validators, renderers/controllers, and post-production integrations.
4. Add the two required YouTube videos.
5. Add GDD history and distinguish it from current OGraf.
6. Verify that every statement about v1 status matches the current EBU repository, not an older webinar roadmap.

### Phase 3 — Add the wider HTML-graphics ecosystem

1. Import and re-verify all relevant Awesome Broadcasting entries requested above.
2. Add web-native platforms, open-source systems, browser hosts, key/fill renderers, automation, newsroom/MOS, and output products.
3. Add developer/animation/data libraries only where they materially support graphics workflows.
4. Add post-production, film/documentary, offline-render, and data-visualisation resources.
5. Place proprietary incumbent graphics platforms only when they have a documented HTML input/output/integration or provide necessary market context; do not turn the list into a generic catalogue of every character generator.

### Phase 3A — Refactor every Tools & Products subsection

Work through every subsection under [Tools & Products](README.md#tools--products) sequentially and autonomously. For each subsection:

1. Evaluate every existing entry against the audience and scope rules; remove entries that are generic, duplicative, weakly documented, or otherwise irrelevant.
2. Research the current ecosystem on the web and add missing tools or products only after verifying their relevance and classification from canonical sources.
3. Add all applicable bold relationship terms—**Authoring**, **Export**, **Import**, **Validation**, **Control**, **Rendering**, **Demonstration**, and **Integration**—to each entry. State OGraf explicitly only where canonical documentation confirms the relationship; otherwise the terms describe the resource's role in professional HTML graphics generally.
4. Validate every entry URL and inspect the destination content to confirm that it is live, canonical, genuine, and supports the description. Replace stale or indirect links and remove entries whose claims cannot be verified.
5. Recheck alphabetical order, concise factual wording, licence/deployment labels, maturity qualifiers, duplication across subsections, and the subsection's overall coherence.
6. Commit the complete refactor of that subsection as one focused commit before moving to the next subsection. This subsection-level refactor protocol is an explicit exception to the earlier one-entry-per-commit rule for new entries.

Do not pause for approval between subsections; continue until all Tools & Products subsections have been researched, refactored, committed, and validated.

### Phase 4 — Supporting project files

1. Adapt `CONTRIBUTING.md`.
2. Add the CC BY-SA `LICENSE.md`.
3. Adapt link-checking scripts and documentation.
4. Add minimal `.gitignore`.
5. Configure GitHub repository description/topics/homepage after content review, if desired.

Suggested repository description:

> A curated list of OGraf and HTML-based graphics resources for live production, post-production, film, and documentary workflows.

Suggested topics:

- `ograf`
- `html-graphics`
- `broadcast-graphics`
- `live-production`
- `post-production`
- `motion-graphics`
- `broadcasting`
- `curated-list`

### Phase 5 — Editorial and mechanical validation

1. Check Markdown headings and generated anchors against the hand-written TOC.
2. Check alphabetical ordering category by category.
3. Check every bullet for the agreed format and terminal period.
4. Search for duplicate URLs and duplicate products.
5. Search descriptions for stale/unsafe claims: `draft`, `native`, `first`, `only`, `all`, `any`, `frame-accurate`, `production-ready`, and version numbers.
6. Verify commercial/open-source labels and licences from canonical sources.
7. Verify OGraf entries against an independent renderer/tool where practical, but describe only documented capabilities.
8. Review the final diff and `git status` to ensure no research artefacts are included.
9. **At the very end, after content and commit-history work is complete, crawl every README URL with `./scripts/check-links.sh`.** Review every redirect and failure, correct moved or mistaken links from canonical sources, and add only narrow, documented exceptions for valid sites that reject automated checks.
10. Re-run the complete link crawl after corrections; the final run must pass before handoff or push.

### Phase 6 — Atomic commit protocol and history audit

This protocol applies throughout Phases 2–5 after implementation approval; commit entries as they are added rather than drafting a populated README and splitting it after the fact:

1. Before the first entry, create a small foundation commit containing the README introduction, scope/label legend, empty category structure, and table of contents, but **no resource entries**.
2. Add each README resource bullet in its **own commit**. One product, paper, video, standard, forum, or other list entry equals one commit; do not batch a category or vendor portfolio into a single commit.
3. Use clear imperative commit subjects such as `Add PixiJS`, `Add OGraf specification`, or `Add Henri Johansson thesis`. A commit may include only the minimal anchor/format adjustment needed for that entry.
4. Add each non-entry supporting file (`CONTRIBUTING.md`, `LICENSE.md`, `.gitignore`, and the link-checker files) in focused setup/tooling commits. These do not count as resource-entry commits.
5. While commits remain local and unpublished, amend the relevant entry commit when correcting its wording or placement. If rewriting is no longer safe, use a focused correction commit rather than mixing changes to unrelated entries.
6. Run formatting, ordering, and duplicate checks throughout. Run the full all-links crawl only at the final validation stage after the history is settled, then correct and re-run it before handoff. Do not collapse or squash the one-entry commits before push.
7. Before every commit, inspect the staged diff and run `git diff --cached --name-only`; ensure inventories, downloaded papers, and research scratch files are never staged.
8. Before push, audit history (for example with `git log --reverse --oneline`) and mechanically compare README resource bullets with entry commits so every entry has a traceable atomic commit.
9. Do not push any commit until the complete local history and content have been reviewed and the maintainer explicitly approves the push.

## 7. Quality bar / definition of done

The initial implementation is ready for review when:

- the README explicitly identifies broadcast and motion-picture technicians/engineers, creative media professionals, and media-focused software developers as its primary audiences;
- the README clearly explains what OGraf is and how it differs from generic HTML graphics;
- all currently well-documented OGraf editors, converters, validators, renderers, controllers, examples, and post-production integrations found in this research are represented;
- MOS is covered as a related newsroom/control protocol without being misrepresented as a Graphic format;
- both requested YouTube videos are included;
- all requested Awesome Broadcasting graphics/playout entries have been reviewed and either included in an appropriate section or called out in review notes with a specific exclusion reason;
- commercial products and non-open-source resources are present, consistent with the “Amazing” model;
- live broadcast, streaming, post-production, film, documentary, and offline HTML-to-video use cases are all visible in the taxonomy;
- descriptions are short, neutral, source-backed, and alphabetised;
- every software/product entry has an accurate availability/deployment classification, with maturity qualifiers where needed;
- scientific literature, practitioner/vendor case studies, and community support channels are clearly separated;
- testing guidance addresses browser automation, visual regression, font/asset readiness, deterministic time, and untrusted data;
- the contribution and licence files match the Amazing Digital Cinema blueprint;
- every README resource entry has one dedicated commit, supporting files have focused setup/tooling commits, and the entry commits have not been squashed together;
- the local link checker passes, apart from narrowly documented policy exceptions;
- no implementation commit has been made without approval;
- `PLAN.md` records the completed repository-wide link audit.

## 8. Decisions to confirm before implementation

1. **Default branch:** use modern `main` (recommended) or mirror Amazing Digital Cinema's `master`?
2. **Breadth of proprietary landscape:** include only systems with a documented HTML/web integration (recommended), or add a separate compact section for major proprietary non-HTML incumbents such as Viz Engine, Chyron PRIME, Ross XPression, Avid Maestro, Brainstorm, WASP3D, Pixotope, and Zero Density Reality?
3. **Emerging projects:** include small but relevant proofs of concept with explicit “experimental” wording (recommended), or require a minimum maturity threshold?
4. **Contributor section:** seed it with the creator's preferred name/link, use the GitHub contributors graph, or leave it ready for future names?
5. **Automation:** keep the blueprint's local link checker only for v1 (recommended), or add a scheduled/manual GitHub Actions link check?
6. **Film/documentary depth:** include the focused offline-render/data-visualisation set in the first release (recommended), or stage it as a second expansion after the OGraf/live ecosystem review?

## 9. Repository-wide link re-audit (2026-09-05)

This checklist supersedes the earlier audit. It inventories links across all tracked repository files, excluding only this checklist’s own repeated URLs to avoid a circular audit. For `PLAN.md`, the audited scope is the planning material above this section.

Checks performed:

- [x] Enumerated **273 distinct HTTP(S) targets** and **40 repository-relative or fragment targets**.
- [x] Ran the complete HTTP checker with redirects enabled and manually rechecked the one transient URN response.
- [x] Reviewed final redirect destinations and page title/heading content for destination correctness.
- [x] Verified GitHub repository and deep-path destinations.
- [x] Verified all YouTube destinations against oEmbed title/channel metadata.
- [x] Verified DOI and URN destinations against publication metadata.
- [x] Verified external fragments for the SPX OGraf, SPX NLE, and SPX template-definition sections.
- [x] Reviewed every narrowly scoped `scripts/check-policies.json` exception against canonical search results or page metadata.
- [x] Validated README table-of-contents fragments and repository-relative file targets locally.
- [x] Final automated result: **251 OK, 22 documented warnings, 0 dead**; destination review found no misdirected links.

Legend: **automatic** means the target completed successfully in the link checker; **manual exception** means the site rejected or failed the automated request but the destination was independently verified; **transient, rechecked** means a temporary failure immediately resolved on repeated requests.

### Repository-relative files and fragments

- [x] `README.md#tools--products` — PLAN.md:615 (Tools & Products).
- [x] `CONTRIBUTING.md` — README.md:9 (contribution guide).
- [x] `#ograf` — README.md:21 (OGraf).
- [x] `#official-specification--governance` — README.md:22 (Official Specification & Governance).
- [x] `#graphics-schemas--apis` — README.md:23 (Graphics, Schemas & APIs).
- [x] `#editors--exporters` — README.md:24 (Editors & Exporters).
- [x] `#development--validation` — README.md:25 (Development & Validation).
- [x] `#renderers-servers--controllers` — README.md:26 (Renderers, Servers & Controllers).
- [x] `#examples--templates` — README.md:27 (Examples & Templates).
- [x] `#organizations--communities` — README.md:28 (Organizations & Communities).
- [x] `#resources` — README.md:29 (Resources).
- [x] `#articles--case-studies` — README.md:30 (Articles & Case Studies).
- [x] `#scientific-literature--theses` — README.md:31 (Scientific Literature & Theses).
- [x] `#books` — README.md:32 (Books).
- [x] `#documentation--knowledge-sources` — README.md:33 (Documentation & Knowledge Sources).
- [x] `#education--tutorials` — README.md:34 (Education & Tutorials).
- [x] `#forums--community` — README.md:35 (Forums & Community).
- [x] `#lists--landscapes` — README.md:36 (Lists & Landscapes).
- [x] `#videos--talks` — README.md:37 (Videos & Talks).
- [x] `#standards-specifications--protocols` — README.md:38 (Standards, Specifications & Protocols).
- [x] `#graphics--template-interchange` — README.md:39 (Graphics & Template Interchange).
- [x] `#newsroom-automation--control` — README.md:40 (Newsroom, Automation & Control).
- [x] `#web-platform` — README.md:41 (Web Platform).
- [x] `#media-transport-colour--safety` — README.md:42 (Media Transport, Colour & Safety).
- [x] `#tools--products` — README.md:43 (Tools & Products).
- [x] `#authoring-animation--conversion` — README.md:44 (Authoring, Animation & Conversion).
- [x] `#web-components--graphics-libraries` — README.md:45 (Web Components & Graphics Libraries).
- [x] `#data-visualization--maps` — README.md:46 (Data Visualization & Maps).
- [x] `#typography--font-handling` — README.md:47 (Typography & Font Handling).
- [x] `#testing-performance--security` — README.md:48 (Testing, Performance & Security).
- [x] `#open-source-graphics-systems` — README.md:49 (Open-source Graphics Systems).
- [x] `#commercial--cloud-graphics-platforms` — README.md:50 (Commercial & Cloud Graphics Platforms).
- [x] `#browser-capable-production-hosts` — README.md:51 (Browser-capable Production Hosts).
- [x] `#rendering-key-fill--video-output` — README.md:52 (Rendering, Key-Fill & Video Output).
- [x] `#newsroom-rundown--automation` — README.md:53 (Newsroom, Rundown & Automation).
- [x] `#sports-data--audience-graphics` — README.md:54 (Sports, Data & Audience Graphics).
- [x] `#post-production--nle-integration` — README.md:55 (Post-production & NLE Integration).
- [x] `#html-to-video--offline-rendering` — README.md:56 (HTML-to-Video & Offline Rendering).
- [x] `#interactive--player-side-graphics` — README.md:57 (Interactive & Player-side Graphics).
- [x] `#templates--marketplaces` — README.md:58 (Templates & Marketplaces).

### HTTP and HTTPS targets

- [x] `https://about.grabyo.com/live-cloud-production/` — README.md:332; **automatic**.
- [x] `https://ajv.js.org/` — README.md:314; **automatic**.
- [x] `https://animejs.com/` — PLAN.md:296, README.md:267; **automatic**.
- [x] `https://aws.amazon.com/elemental-live/` — README.md:354; **automatic**.
- [x] `https://bitfocus.io/companion` — README.md:375; **automatic**.
- [x] `https://casparcg.com/` — README.md:324; **automatic**.
- [x] `https://casparcgforum.org/` — PLAN.md:382, README.md:177; **automatic**.
- [x] `https://cavalry.studio/docs/user-interface/menus/window-menu/render-manager/lottie-export/` — README.md:268; **automatic**.
- [x] `https://chrisryanouellette.gitbook.io/casparcg-html-template-guide` — README.md:160; **automatic**.
- [x] `https://community.rive.app/home` — README.md:188, scripts/check-policies.json:3; **manual exception**.
- [x] `https://creativecommons.org/licenses/by-sa/4.0/` — LICENSE.md:3; **automatic**.
- [x] `https://creativecommons.org/licenses/by-sa/4.0/legalcode` — LICENSE.md:5; **automatic**.
- [x] `https://cuez.app/products/automator/` — README.md:378; **automatic**.
- [x] `https://d3js.org/` — PLAN.md:298, README.md:293; **automatic**.
- [x] `https://d3js.org/community` — PLAN.md:392, README.md:179; **automatic**.
- [x] `https://developer.chrome.com/docs/devtools/performance/reference` — README.md:161; **automatic**.
- [x] `https://developer.mozilla.org/en-US/docs/Web/API/CSS_Font_Loading_API` — README.md:164; **automatic**.
- [x] `https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API` — README.md:163; **automatic**.
- [x] `https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_custom_elements` — README.md:165; **automatic**.
- [x] `https://developer.mozilla.org/en-US/docs/Web/Performance/Guides/Animation_performance_and_frame_rate` — README.md:162; **automatic**.
- [x] `https://discourse.threejs.org/` — PLAN.md:387, README.md:190; **automatic**.
- [x] `https://dizplai.com/live-graphics/` — README.md:331, scripts/check-policies.json:4; **manual exception**.
- [x] `https://djhtmlcreator.com/` — PLAN.md:82, README.md:79; **automatic**.
- [x] `https://docs.aws.amazon.com/elemental-live/latest/ug/how-to-insert-a-motion-overlay-with-html5.html` — README.md:130; **automatic**.
- [x] `https://docs.aws.amazon.com/medialive/latest/ug/feature-mgi.html` — README.md:355; **automatic**.
- [x] `https://docs.erizos.tv/` — PLAN.md:105; **automatic**.
- [x] `https://docs.erizos.tv/userguide/BasicConfig/` — README.md:100; **automatic**.
- [x] `https://docs.lottielab.com/export-and-hand-off/file-download/lottie-json-download` — README.md:272; **automatic**.
- [x] `https://docs.mapbox.com/mapbox-gl-js/guides/get-started/` — README.md:299; **automatic**.
- [x] `https://docs.spxgraphics.com/` — README.md:173; **automatic**.
- [x] `https://docs.spxgraphics.com/Documentation/Graphic+Templates/Formats/HTML` — README.md:166; **automatic**.
- [x] `https://docs.spxgraphics.com/Documentation/Graphic+Templates/Formats/HTML#Template+Definition` — README.md:220; **automatic**.
- [x] `https://docs.spxgraphics.com/Documentation/Graphic+Templates/Graphics+Creation/Overview` — README.md:134; **automatic**.
- [x] `https://documents.blackmagicdesign.com/SupportNotes/DaVinci_Resolve_21_New_Features_Guide.pdf` — PLAN.md:107, README.md:99; **automatic**.
- [x] `https://doi.org/10.1177/19312431211039500` — PLAN.md:369, README.md:146, scripts/check-policies.json:5; **manual exception**.
- [x] `https://doi.org/10.1371/journal.pone.0109812` — PLAN.md:364, README.md:145; **automatic**.
- [x] `https://doi.org/10.3390/jimaging12010045` — PLAN.md:366, README.md:140, scripts/check-policies.json:6; **manual exception**.
- [x] `https://doi.org/10.3390/s22176542` — PLAN.md:365, README.md:141, scripts/check-policies.json:7; **manual exception**.
- [x] `https://doi.org/10.5594/JMI.2020.3024028` — PLAN.md:368, README.md:142; **automatic**.
- [x] `https://doi.org/10.5594/M001731` — PLAN.md:367, README.md:147; **automatic**.
- [x] `https://dotlottie.io/` — PLAN.md:296, README.md:269; **automatic**.
- [x] `https://dotlottie.io/spec/` — README.md:218; **automatic**.
- [x] `https://drafts.csswg.org/css-font-loading/` — README.md:238; **automatic**.
- [x] `https://echarts.apache.org/` — PLAN.md:298, README.md:291; **automatic**.
- [x] `https://example.com/` — PLAN.md:513; **automatic**.
- [x] `https://fabricjs.com/` — README.md:281; **automatic**.
- [x] `https://fast.design/` — PLAN.md:295, README.md:282; **automatic**.
- [x] `https://flourish.studio/product/data-visualization/` — README.md:296; **automatic**.
- [x] `https://forum.lottiefiles.com/` — PLAN.md:388, README.md:182; **automatic**.
- [x] `https://github.com/CasparCG/help/wiki/AMCP-Protocol` — README.md:224; **automatic**.
- [x] `https://github.com/CasparCG/help/wiki/Related-Projects` — README.md:196; **automatic**.
- [x] `https://github.com/CasparCG/server/discussions` — PLAN.md:382, README.md:178; **automatic**.
- [x] `https://github.com/ErtugrulAK/keyframe-character-studio` — PLAN.md:123, README.md:81; **automatic**.
- [x] `https://github.com/Eyevinn/ograf-editor` — PLAN.md:83, README.md:80; **automatic**.
- [x] `https://github.com/Jonathhhan/ofxOGraf` — PLAN.md:122, README.md:104; **automatic**.
- [x] `https://github.com/Lawo/ember-plus` — README.md:225; **automatic**.
- [x] `https://github.com/SVT/bridge` — README.md:376; **automatic**.
- [x] `https://github.com/Sofie-Automation/Sofie-TV-automation` — README.md:382; **automatic**.
- [x] `https://github.com/Sofie-Automation/sofie-mos-connection` — PLAN.md:168, README.md:381; **automatic**.
- [x] `https://github.com/Streampunk/macadam` — README.md:362; **automatic**.
- [x] `https://github.com/Streamshapers/LottiesForBroadcast` — PLAN.md:117, README.md:114; **automatic**.
- [x] `https://github.com/Streamshapers/OGraf-Validator` — PLAN.md:93, README.md:94; **automatic**.
- [x] `https://github.com/Streamshapers/StreamShapers-Ferryman` — PLAN.md:87, README.md:86; **automatic**.
- [x] `https://github.com/SuperFlyTV/SuperConductor` — README.md:383; **automatic**.
- [x] `https://github.com/SuperFlyTV/ograf-devtool` — PLAN.md:92, README.md:91; **automatic**.
- [x] `https://github.com/SuperFlyTV/ograf-form` — PLAN.md:95, README.md:92; **automatic**.
- [x] `https://github.com/SuperFlyTV/ograf-server` — PLAN.md:101, README.md:106; **automatic**.
- [x] `https://github.com/TuomoKu/SPX-GC` — PLAN.md:102; **automatic**.
- [x] `https://github.com/Yleisradio/caspartool` — README.md:384; **automatic**.
- [x] `https://github.com/a-bentofreire/beamtoix` — README.md:403; **automatic**.
- [x] `https://github.com/aDifferentJT/keyfillwebview` — README.md:360; **automatic**.
- [x] `https://github.com/aiatelie/ai-atelie` — PLAN.md:127, README.md:78; **automatic**.
- [x] `https://github.com/airbnb/lottie-web` — PLAN.md:296, README.md:271; **automatic**.
- [x] `https://github.com/alexey-pelykh/puppeteer-capture` — README.md:408; **automatic**.
- [x] `https://github.com/avtools-io/amazing-digital-cinema` — PLAN.md:7, PLAN.md:451, README.md:11; **automatic**.
- [x] `https://github.com/avtools-io/amazing-html-graphics` — PLAN.md:5; **automatic**.
- [x] `https://github.com/avtools-io/amazing-html-graphics/issues` — README.md:9; **automatic**.
- [x] `https://github.com/bramstein/fontfaceobserver` — README.md:309; **automatic**.
- [x] `https://github.com/cbcrc/mxl-hands-on` — PLAN.md:121, README.md:111; **automatic**.
- [x] `https://github.com/centricular/gstcefsrc` — README.md:359; **automatic**.
- [x] `https://github.com/cndgfxteam/rive-ograf-wrapper` — PLAN.md:88, README.md:85; **automatic**.
- [x] `https://github.com/cure53/DOMPurify` — PLAN.md:406, README.md:316; **automatic**.
- [x] `https://github.com/dtinth/html5-animation-video-renderer` — README.md:404; **automatic**.
- [x] `https://github.com/ebu/awesome-broadcasting` — PLAN.md:452, README.md:11, README.md:194; **automatic**.
- [x] `https://github.com/ebu/ograf` — PLAN.md:75, README.md:65; **automatic**.
- [x] `https://github.com/ebu/ograf/blob/main/v1/specification/docs/Specification.md` — README.md:70; **automatic**.
- [x] `https://github.com/ebu/ograf/blob/main/v1/specification/docs/Specification_Server_API.md` — README.md:73; **automatic**.
- [x] `https://github.com/ebu/ograf/issues` — PLAN.md:380, README.md:180; **automatic**.
- [x] `https://github.com/ebu/ograf/pulls` — PLAN.md:380; **automatic**.
- [x] `https://github.com/ebu/ograf/tree/main/v1/examples` — README.md:112; **automatic**.
- [x] `https://github.com/ebu/ograf/tree/main/v1/specification/json-schemas` — README.md:71; **automatic**.
- [x] `https://github.com/ebu/ograf/tree/main/v1/typescript-definitions` — README.md:74; **automatic**.
- [x] `https://github.com/garris/BackstopJS` — README.md:315; **automatic**.
- [x] `https://github.com/heretorecord/ograf-graphics-skill` — PLAN.md:96, README.md:93; **automatic**.
- [x] `https://github.com/heygen-com/hyperframes` — README.md:405; **automatic**.
- [x] `https://github.com/jaskie/PlayoutAutomation` — README.md:379; **automatic**.
- [x] `https://github.com/jdanna/Resolve_Tools_Public/tree/main/docs/OGraf%20HTML%20Templates` — PLAN.md:126, README.md:116; **automatic**.
- [x] `https://github.com/mapbox/pixelmatch` — README.md:318; **automatic**.
- [x] `https://github.com/michalramus/caspar-obs-client` — README.md:377; **automatic**.
- [x] `https://github.com/midrender/revideo` — README.md:411; **automatic**.
- [x] `https://github.com/miwco/NoaCG-Studio` — PLAN.md:85, README.md:83; **automatic**.
- [x] `https://github.com/motion-canvas/motion-canvas/discussions` — PLAN.md:391, README.md:184; **automatic**.
- [x] `https://github.com/mug-lab-3/resolve-ograf` — PLAN.md:125, README.md:117; **automatic**.
- [x] `https://github.com/nodecg/awesome-nodecg` — PLAN.md:289, README.md:195; **automatic**.
- [x] `https://github.com/nodecg/nodecg` — PLAN.md:383, README.md:185; **automatic**.
- [x] `https://github.com/nxtedition/nxt-graphics` — PLAN.md:106, README.md:103; **automatic**.
- [x] `https://github.com/nytamin/ograf-graphics` — PLAN.md:113, README.md:113; **automatic**.
- [x] `https://github.com/observablehq/plot` — README.md:301; **automatic**.
- [x] `https://github.com/pixijs/pixijs/discussions/` — PLAN.md:386, README.md:186; **automatic**.
- [x] `https://github.com/pjaspinski/ograf-to-image-sequence-renderer` — PLAN.md:108, README.md:105; **automatic**.
- [x] `https://github.com/plotly/plotly.js` — README.md:302; **automatic**.
- [x] `https://github.com/reearth/kamishibai` — README.md:406; **automatic**.
- [x] `https://github.com/russellsamora/render-d3-video` — README.md:410; **automatic**.
- [x] `https://github.com/ryanmccartney/ograf-dash.js` — PLAN.md:116, README.md:115; **automatic**.
- [x] `https://github.com/sindresorhus/awesome` — PLAN.md:453, README.md:11; **automatic**.
- [x] `https://github.com/stoatworks-labs/weblinked` — README.md:327; **automatic**.
- [x] `https://github.com/suitougreentea/denocg` — README.md:325; **automatic**.
- [x] `https://github.com/superflytv/GraphicsDataDefinition` — README.md:69; **automatic**.
- [x] `https://github.com/timokorkalainen/dom-compositor-proto` — PLAN.md:124; **automatic**.
- [x] `https://github.com/zerodensity/ograf-studio` — PLAN.md:86, README.md:84; **automatic**.
- [x] `https://gsap.com/` — PLAN.md:296, README.md:270; **automatic**.
- [x] `https://gsap.com/community/` — PLAN.md:385, README.md:181; **automatic**.
- [x] `https://h2r.graphics/` — README.md:101; **automatic**.
- [x] `https://h2r.graphics/docs/graphics/ograf/` — PLAN.md:103, README.md:171; **automatic**.
- [x] `https://help.shotstack.io/en/articles/16312767-migrating-from-the-html-asset-to-html5` — README.md:412; **automatic**.
- [x] `https://helpx.adobe.com/animate/desktop/interactivity/creating-publishing-html5-canvas-document.html` — README.md:266, scripts/check-policies.json:26; **manual exception**.
- [x] `https://html.spec.whatwg.org/multipage/canvas.html` — README.md:235; **automatic**.
- [x] `https://html.spec.whatwg.org/multipage/custom-elements.html` — README.md:239; **automatic**.
- [x] `https://json-schema.org/draft/2020-12` — README.md:242; **automatic**.
- [x] `https://jsonforms.io/` — README.md:317; **automatic**.
- [x] `https://keepthescore.com/scoreboard-overlay/` — README.md:388; **automatic**.
- [x] `https://konvajs.org/` — README.md:283; **automatic**.
- [x] `https://lawo.com/products/home-graphic-inserter/` — README.md:361; **automatic**.
- [x] `https://leafletjs.com/` — PLAN.md:298, README.md:298; **automatic**.
- [x] `https://link.springer.com/book/10.1007/978-1-4302-3666-5` — README.md:154; **automatic**.
- [x] `https://lit.dev/` — PLAN.md:295, README.md:284; **automatic**.
- [x] `https://lottie.github.io/lottie-spec/` — README.md:219; **automatic**.
- [x] `https://lottiefiles.com/` — README.md:423, scripts/check-policies.json:8; **manual exception**.
- [x] `https://maplibre.org/community/` — PLAN.md:393, README.md:183; **automatic**.
- [x] `https://maplibre.org/maplibre-gl-js/docs/` — PLAN.md:298, README.md:300; **automatic**.
- [x] `https://medialooks.com/plugins/hmtl5` — README.md:363; **automatic**.
- [x] `https://mimolive.com/user-manual/sources-input/screen-sources/web-browser-capture/` — README.md:344; **automatic**.
- [x] `https://mosprotocol.com/` — PLAN.md:167, README.md:226; **automatic**.
- [x] `https://motion.dev/` — PLAN.md:296, README.md:273; **automatic**.
- [x] `https://motionarray.com/` — README.md:424, scripts/check-policies.json:9; **manual exception**.
- [x] `https://motioncanvas.io/` — README.md:407; **automatic**.
- [x] `https://ndi.video/for-developers/ndi-sdk/` — README.md:257; **automatic**.
- [x] `https://obscoreboard.com/use-cases/sports-overlays-for-broadcasters/` — README.md:390; **automatic**.
- [x] `https://obsproject.com/kb/browser-source` — README.md:345; **automatic**.
- [x] `https://ograf.dev/` — PLAN.md:114, PLAN.md:381; **automatic**.
- [x] `https://ograf.dev/ecosystem` — PLAN.md:114, PLAN.md:586, README.md:197; **automatic**.
- [x] `https://ograf.dev/tools` — PLAN.md:94, README.md:95; **automatic**.
- [x] `https://ograf.dev/tutorials` — README.md:172; **automatic**.
- [x] `https://ograf.ebu.io/` — PLAN.md:74, README.md:5; **automatic**.
- [x] `https://openlibrary.org/books/OL8662465M/Motion_Graphics` — README.md:155; **automatic**.
- [x] `https://opensoundcontrol.stanford.edu/spec-1_0.html` — README.md:231; **automatic**.
- [x] `https://opentype.js.org/` — PLAN.md:299, README.md:310; **automatic**.
- [x] `https://overlays.uno/` — README.md:334; **automatic**.
- [x] `https://pandainteractive.com/product` — README.md:417; **automatic**.
- [x] `https://pixijs.com/` — PLAN.md:297, README.md:285; **automatic**.
- [x] `https://playwright.dev/` — README.md:319; **automatic**.
- [x] `https://poltergeist.cc/` — README.md:335; **automatic**.
- [x] `https://pptr.dev/` — README.md:320; **automatic**.
- [x] `https://pub.smpte.org/doc/` — PLAN.md:189, README.md:258; **automatic**.
- [x] `https://rikschennink.github.io/fitty/` — PLAN.md:299, README.md:308; **automatic**.
- [x] `https://rive.app/` — PLAN.md:296, README.md:274; **automatic**.
- [x] `https://rive.app/docs/community/marketplace-overview` — README.md:425; **automatic**.
- [x] `https://rive.app/docs/getting-started/introduction` — PLAN.md:389; **automatic**.
- [x] `https://rtsw.co.uk/all-products/swift-engine/` — README.md:364; **automatic**.
- [x] `https://sdiware.video/` — README.md:365; **automatic**.
- [x] `https://search.worldcat.org/title/61711466` — README.md:152, scripts/check-policies.json:21; **manual exception**.
- [x] `https://smartpanelapp.com/features` — README.md:337; **automatic**.
- [x] `https://softron.tv/products/play/ontheair-weblink` — README.md:367; **automatic**.
- [x] `https://spec.openapis.org/oas/latest.html` — README.md:243; **automatic**.
- [x] `https://specs.amwa.tv/is-04/` — README.md:227; **automatic**.
- [x] `https://specs.amwa.tv/is-05/` — README.md:228; **automatic**.
- [x] `https://specs.amwa.tv/is-07/` — README.md:229; **automatic**.
- [x] `https://specs.amwa.tv/is-12/` — README.md:230; **automatic**.
- [x] `https://spxgraphics.com/software/integrations#ograf` — PLAN.md:102, README.md:107; **automatic**.
- [x] `https://spxgraphics.com/software/more#nle` — README.md:399; **automatic**.
- [x] `https://spxgraphics.com/store/` — README.md:426; **automatic**.
- [x] `https://spxgraphics.com/support/` — PLAN.md:384, README.md:189; **automatic**.
- [x] `https://stenciljs.com/` — PLAN.md:295, README.md:286; **automatic**.
- [x] `https://streamshapers.com/docs` — README.md:167; **automatic**.
- [x] `https://studiosupport.liveu.tv/hc/en-us/articles/17094646501659-Web-Page` — README.md:343; **automatic**.
- [x] `https://support.ecamm.com/en/articles/3323618-using-overlays` — README.md:342; **automatic**.
- [x] `https://support.flowics.com/en/articles/15393380-what-is-viz-flowics` — README.md:338; **automatic**.
- [x] `https://support.singular.live/hc/en-us/articles/360055456751-Using-Singular-in-Post-Production-for-Windows` — README.md:135, scripts/check-policies.json:10; **manual exception**.
- [x] `https://support.telestream.net/s/article/Wirecast-Web-Display` — README.md:348; **automatic**.
- [x] `https://support.xsplit.com/en/article/webpage-1y1l6v/` — README.md:349; **automatic**.
- [x] `https://tagboard.com/modern-interactive-graphics-system/` — README.md:392; **automatic**.
- [x] `https://tc39.es/ecma262/multipage/ecmascript-language-scripts-and-modules.html` — README.md:240; **automatic**.
- [x] `https://tech.ebu.ch/groups/html-graphics` — PLAN.md:77, README.md:64, scripts/check-policies.json:11; **manual exception**.
- [x] `https://tech.ebu.ch/news/2025/04/ograf-the-ebu%27s-open-spec-for-cross-platform-graphics-integration` — README.md:131, scripts/check-policies.json:12; **manual exception**.
- [x] `https://tech.ebu.ch/publications/r095` — README.md:253, scripts/check-policies.json:13; **manual exception**.
- [x] `https://tech.ebu.ch/publications/r103` — README.md:251, scripts/check-policies.json:14; **manual exception**.
- [x] `https://tech.ebu.ch/publications/r143` — README.md:252, scripts/check-policies.json:15; **manual exception**.
- [x] `https://tech.ebu.ch/publications/webinar-ograf-html-graphics-spec` — README.md:133, scripts/check-policies.json:16; **manual exception**.
- [x] `https://threejs.org/` — README.md:287; **automatic**.
- [x] `https://toolsonair.com/usermanuals/justplaylivepro2026/2-13-html-based-graphic-templates-2026.html` — README.md:368; **automatic**.
- [x] `https://turfjs.org/` — PLAN.md:298, README.md:303; **automatic**.
- [x] `https://urn.fi/URN:NBN:fi:amk-2016060612041` — PLAN.md:371, README.md:144; **transient, rechecked**.
- [x] `https://urn.fi/URN:NBN:fi:amk-2025052918037` — PLAN.md:370, README.md:143; **automatic**.
- [x] `https://vega.github.io/vega-lite/` — PLAN.md:298, README.md:304; **automatic**.
- [x] `https://videohive.net/category/after-effects-project-files/broadcast-packages` — README.md:427, scripts/check-policies.json:17; **manual exception**.
- [x] `https://vindral.com/composer/` — README.md:370; **automatic**.
- [x] `https://w3c.github.io/trusted-types/dist/spec/` — README.md:245; **automatic**.
- [x] `https://web.classx.it/products-liveboard` — README.md:356; **automatic**.
- [x] `https://www.adobe.com/products/aftereffects.html` — README.md:265, scripts/check-policies.json:27; **manual exception**.
- [x] `https://www.amwa.tv/` — README.md:121; **automatic**.
- [x] `https://www.aveco.com/en/download/22/cg-manager` — README.md:353, scripts/check-policies.json:25; **manual exception**.
- [x] `https://www.babylonjs.com/` — README.md:280; **automatic**.
- [x] `https://www.casparcg.com/docs/wiki/media/html-templates` — README.md:217; **automatic**.
- [x] `https://www.casparcg.com/docs/wiki/server/producers/html-producer` — README.md:159; **automatic**.
- [x] `https://www.chartjs.org/` — PLAN.md:298, README.md:292; **automatic**.
- [x] `https://www.crystalvision.tv/wp/wp-content/uploads/2022/09/m-webkeymanual.pdf` — README.md:357; **automatic**.
- [x] `https://www.datawrapper.de/features` — README.md:294; **automatic**.
- [x] `https://www.easelive.tv/` — README.md:416; **automatic**.
- [x] `https://www.ebu.ch/` — README.md:122, scripts/check-policies.json:18; **manual exception**.
- [x] `https://www.etere.com/DocView/8818/Etere-ETX-Graphics-Capabilities-with-HTML5.aspx` — README.md:358; **automatic**.
- [x] `https://www.everviz.com/` — README.md:295; **automatic**.
- [x] `https://www.flowics.com/data-driven-graphics/` — README.md:393; **automatic**.
- [x] `https://www.grassvalley.com/products/ampp/playout-x/` — README.md:333; **automatic**.
- [x] `https://www.hbbtv.org/` — README.md:241; **automatic**.
- [x] `https://www.highcharts.com/products/maps/` — README.md:297; **automatic**.
- [x] `https://www.informit.com/store/core-html5-canvas-graphics-animation-and-game-development-9780132761611` — README.md:153; **automatic**.
- [x] `https://www.itu.int/rec/R-REC-BT.2020` — README.md:254; **automatic**.
- [x] `https://www.itu.int/rec/R-REC-BT.2100` — README.md:255; **automatic**.
- [x] `https://www.itu.int/rec/R-REC-BT.709` — README.md:256; **automatic**.
- [x] `https://www.khronos.org/webgl/` — README.md:247; **automatic**.
- [x] `https://www.ligrsystems.com/what-is-ligr` — README.md:389; **automatic**.
- [x] `https://www.loopic.io/ograf` — PLAN.md:84, README.md:82; **automatic**.
- [x] `https://www.mxmz.com/products/nle-mam` — README.md:397; **automatic**.
- [x] `https://www.neton.live/` — PLAN.md:104, README.md:102, scripts/check-policies.json:22; **manual exception**.
- [x] `https://www.nodecg.dev/` — README.md:326; **automatic**.
- [x] `https://www.npmjs.com/package/ograf` — PLAN.md:76, README.md:72, scripts/check-policies.json:19; **manual exception**.
- [x] `https://www.remotion.dev/` — README.md:409; **automatic**.
- [x] `https://www.remotion.dev/discord` — PLAN.md:390, README.md:187; **automatic**.
- [x] `https://www.researchgate.net/publication/319442826_TV_Graphics_Personalization_Using_In-Band_Events` — README.md:148, scripts/check-policies.json:20; **manual exception**.
- [x] `https://www.rossvideo.com/resources/ross-university/xpression-mos-html5-plugin/` — README.md:380; **automatic**.
- [x] `https://www.sienna-tv.com/ndi/graphicartist.html` — README.md:366; **automatic**.
- [x] `https://www.singular.live/` — README.md:336; **automatic**.
- [x] `https://www.singular.live/recast` — README.md:398; **automatic**.
- [x] `https://www.smpte.org/` — README.md:123; **automatic**.
- [x] `https://www.smpte.org/standards/st2110` — README.md:259; **automatic**.
- [x] `https://www.sportbuff.com/` — README.md:418; **automatic**.
- [x] `https://www.spx.graphics/spx-graphics-helps-upgrade-finnish-lottery-production` — README.md:132; **automatic**.
- [x] `https://www.statsperform.com/products/opta-graphics/` — README.md:391; **automatic**.
- [x] `https://www.streamlayer.io/` — README.md:419; **automatic**.
- [x] `https://www.streamshapers.com/ae-extension/` — README.md:87; **automatic**.
- [x] `https://www.svgator.com/help/export-and-file-formats/lottie-support-in-svgator` — README.md:275; **automatic**.
- [x] `https://www.theatrejs.com/` — PLAN.md:296, README.md:276; **automatic**.
- [x] `https://www.videonlabs.com/liveedge-graphix` — README.md:369; **automatic**.
- [x] `https://www.vizrt.com/ebooks/your-guide-to-html5-graphics-for-live-productions/` — README.md:136; **automatic**.
- [x] `https://www.vizrt.com/products/tricaster-family/` — README.md:346; **automatic**.
- [x] `https://www.vizrt.com/products/viz-connect-tetra/tech-specs/` — README.md:371; **automatic**.
- [x] `https://www.vmix.com/help29/WebBrowser.html` — README.md:347; **automatic**.
- [x] `https://www.w3.org/` — README.md:124; **automatic**.
- [x] `https://www.w3.org/Style/CSS/` — README.md:237; **automatic**.
- [x] `https://www.w3.org/TR/CSP3/` — README.md:236; **automatic**.
- [x] `https://www.w3.org/TR/SVG2/` — README.md:244; **automatic**.
- [x] `https://www.w3.org/TR/web-animations-1/` — README.md:246; **automatic**.
- [x] `https://www.youtube.com/watch?v=-S_gBYPyCiw` — PLAN.md:141, README.md:206; **automatic**.
- [x] `https://www.youtube.com/watch?v=2oJaECoOPoQ` — PLAN.md:147, README.md:201; **automatic**.
- [x] `https://www.youtube.com/watch?v=3YZyWCjHK9U` — PLAN.md:143, README.md:203; **automatic**.
- [x] `https://www.youtube.com/watch?v=6IMGzvxe1AY` — PLAN.md:136, README.md:208; **automatic**.
- [x] `https://www.youtube.com/watch?v=AdZATSBByng` — PLAN.md:146, README.md:209; **automatic**.
- [x] `https://www.youtube.com/watch?v=BnV55qu6vvg` — PLAN.md:144, README.md:202; **automatic**.
- [x] `https://www.youtube.com/watch?v=P6VEWyv7-P0` — PLAN.md:140, README.md:207; **automatic**.
- [x] `https://www.youtube.com/watch?v=e5LTFC9MlOI` — PLAN.md:145, README.md:210; **automatic**.
- [x] `https://www.youtube.com/watch?v=gZRYTmngqLw` — PLAN.md:148, README.md:204; **automatic**.
- [x] `https://www.youtube.com/watch?v=gw2SnjeGW9Q` — PLAN.md:135, README.md:205; **automatic**.
- [x] `https://www.youtube.com/watch?v=u4wruk2QTs0` — PLAN.md:142, README.md:211; **automatic**.
