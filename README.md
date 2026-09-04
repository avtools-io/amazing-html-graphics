# Amazing HTML Graphics

A curated list for broadcast and motion-picture technicians and engineers, creative media professionals, and media-focused software developers working with HTML graphics and [EBU OGraf](https://ograf.ebu.io/) across live production, streaming, post-production, film, and documentary workflows.

It covers authoring, animation, data visualisation, templates, validation, control, rendering, compositing, playout, transport, offline rendering, standards, software, services, research, and learning resources.

**Contributions are welcome.** You do not need to know Git to suggest a resource: read the [contribution guide](CONTRIBUTING.md), open an [issue](https://github.com/avtools-io/amazing-html-graphics/issues), or submit one focused pull request per entry.

This list is inspired by [Amazing Digital Cinema](https://github.com/avtools-io/amazing-digital-cinema), the direct blueprint for its editorial style and maintenance workflow; [Awesome Broadcasting](https://github.com/ebu/awesome-broadcasting), especially its Animation, Graphics & Video Playout section; and the wider [Awesome](https://github.com/sindresorhus/awesome) project. It is called “Amazing” because useful commercial and non-open-source resources are welcome alongside open-source projects.

HTML or browser support does not by itself mean OGraf compatibility. Entries describe whether a resource authors, imports, renders, controls, or demonstrates OGraf; merely hosting an OGraf renderer URL is identified separately.

Software and product descriptions begin with availability/deployment labels: **Open source** includes a verified licence where practical; **Source available** is not necessarily open source; **Commercial** covers proprietary products and services; **Hosted/SaaS**, **Open core**, and **Freeware** provide additional context. Qualifiers such as **Experimental**, **Beta**, **Archived**, and **Deprecated** indicate maturity rather than licensing.

## Contents

- [Contributors to This List](#contributors-to-this-list)
- [OGraf](#ograf)
  - [Official Specification & Governance](#official-specification--governance)
  - [Graphics, Schemas & APIs](#graphics-schemas--apis)
  - [Editors & Exporters](#editors--exporters)
  - [Development & Validation](#development--validation)
  - [Renderers, Servers & Controllers](#renderers-servers--controllers)
  - [Examples & Templates](#examples--templates)
- [Organizations & Communities](#organizations--communities)
- [Resources](#resources)
  - [Articles & Case Studies](#articles--case-studies)
  - [Scientific Literature & Theses](#scientific-literature--theses)
  - [Books](#books)
  - [Documentation & Knowledge Sources](#documentation--knowledge-sources)
  - [Education & Tutorials](#education--tutorials)
  - [Forums & Community](#forums--community)
  - [Lists & Landscapes](#lists--landscapes)
  - [Videos & Talks](#videos--talks)
  - [Standards, Specifications & Protocols](#standards-specifications--protocols)
    - [Graphics & Template Interchange](#graphics--template-interchange)
    - [Newsroom, Automation & Control](#newsroom-automation--control)
    - [Web Platform](#web-platform)
    - [Media Transport, Colour & Safety](#media-transport-colour--safety)
- [Tools & Products](#tools--products)
  - [Authoring, Animation & Conversion](#authoring-animation--conversion)
  - [Web Components & Graphics Libraries](#web-components--graphics-libraries)
  - [Data Visualization & Maps](#data-visualization--maps)
  - [Typography & Font Handling](#typography--font-handling)
  - [Testing, Performance & Security](#testing-performance--security)
  - [Open-source Graphics Systems](#open-source-graphics-systems)
  - [Commercial & Cloud Graphics Platforms](#commercial--cloud-graphics-platforms)
  - [Browser-capable Production Hosts](#browser-capable-production-hosts)
  - [Rendering, Key-Fill & Video Output](#rendering-key-fill--video-output)
  - [Newsroom, Rundown & Automation](#newsroom-rundown--automation)
  - [Sports, Data & Audience Graphics](#sports-data--audience-graphics)
  - [Post-production & NLE Integration](#post-production--nle-integration)
  - [HTML-to-Video & Offline Rendering](#html-to-video--offline-rendering)
  - [Interactive & Player-side Graphics](#interactive--player-side-graphics)
  - [Templates, Marketplaces & Services](#templates-marketplaces--services)
  - [Related Animation, Graphics & Playout](#related-animation-graphics--playout)

## Contributors to This List

<!-- Contributors will be added here. -->

## OGraf

### Official Specification & Governance

- [EBU HTML Graphics Working Group](https://tech.ebu.ch/groups/html_graphics) – The EBU group coordinating the open, interoperable HTML graphics work that includes OGraf.
- [EBU OGraf repository](https://github.com/ebu/ograf) – The canonical specification repository, including versioned documents, schemas, examples, changelogs, and public issue tracking.

### Graphics, Schemas & APIs

- [Graphics Data Definition](https://github.com/superflytv/GraphicsDataDefinition) – **Deprecated.** The predecessor data-description project incorporated into OGraf; useful for historical GDD templates and tools.
- [OGraf Graphics specification](https://github.com/ebu/ograf/blob/main/v1/specification/docs/Specification.md) – The normative v1 package, manifest, Web Component, lifecycle, action, and non-real-time rendering requirements.
- [OGraf JSON Schemas](https://github.com/ebu/ograf/tree/main/v1/specification/json-schemas) – Normative JSON Schemas for validating OGraf manifests and Graphics data definitions.
- [OGraf npm package](https://www.npmjs.com/package/ograf) – **Open source (MIT).** Informative TypeScript definitions for the OGraf Graphics and Server APIs.
- [OGraf Server API](https://github.com/ebu/ograf/blob/main/v1/specification/docs/Specification_Server_API.md) – The REST/OpenAPI contract between Controllers and rendering systems.
- [OGraf TypeScript definitions](https://github.com/ebu/ograf/tree/main/v1/typescript-definitions) – **Open source (MIT).** Informative lifecycle, action, manifest, and Server API types maintained with the specification.

### Editors & Exporters

- [AI Atelier](https://github.com/aiatelie/ai-atelie) – **Open source (MIT). Experimental OGraf support.** A local-first, agent-assisted HTML/JSX/CSS design environment with an OGraf export service.
- [DJ HTML Creator](https://djhtmlcreator.com/) – **Commercial.** Visual HTML and Lottie graphics authoring with OGraf package export.
- [Eyevinn OGraf Template Editor](https://github.com/Eyevinn/ograf-editor) – **Open source (MIT).** Browser-based visual editor with animation, data binding, preview, validation, and OGraf import/export.
- [Keyframe Character Studio](https://github.com/ErtugrulAK/keyframe-character-studio) – **Open source (MIT). Experimental.** Browser motion-design sequencer and live director with an emerging OGraf export path.
- [Loopic](https://www.loopic.io/ograf) – **Commercial; hosted/SaaS.** No-code HTML graphics editor with OGraf export and integrations for live graphics workflows.
- [NoaCG Studio](https://github.com/miwco/NoaCG-Studio) – **Open source (AGPL-3.0).** Visual, code, and AI-assisted motion graphics authoring with multi-target export including OGraf.
- [OGraf Studio](https://github.com/zerodensity/ograf-studio) – **Open source (AGPL-3.0).** Visual OGraf editor with runtime, validation, export, and optional AI/MCP-assisted authoring packages.
- [Rive OGraf Wrapper](https://github.com/cndgfxteam/rive-ograf-wrapper) – **Source available; no licence asserted. Experimental.** Web application that converts Rive files into OGraf Graphics with documented runtime limitations.
- [StreamShapers Ferryman](https://github.com/Streamshapers/StreamShapers-Ferryman) – **Open source (AGPL-3.0).** Converts Lottie JSON and After Effects exports into HTML templates and OGraf packages.
- [StreamShapers OGraf Export](https://www.streamshapers.com/ae-extension/) – **Commercial; announced.** After Effects extension combining Lottie preflight, rendering, embedded Ferryman configuration, and OGraf export; the vendor says availability is planned for summer 2026.

### Development & Validation

- [OGraf Devtool](https://github.com/SuperFlyTV/ograf-devtool) – **Open source (MIT).** Local and hosted harness for loading Graphics, exercising lifecycle methods, updating data, and checking behavior.
- [OGraf Form](https://github.com/SuperFlyTV/ograf-form) – **Open source (MIT).** Web Component and npm package that generates operator forms from OGraf/GDD schemas.
- [OGraf Graphics Skill](https://github.com/heretorecord/ograf-graphics-skill) – **Open source (MIT).** Agent skill for scaffolding, packaging, and validating OGraf v1 Graphics.
- [OGraf Validator](https://github.com/Streamshapers/OGraf-Validator) – **Open source (MIT).** Web validator and reusable core package for checking OGraf package structure and manifests.
- [ograf.dev Tools](https://ograf.dev/tools) – Independent browser-based package checker, runtime harness, and schema explorer for OGraf development.

### Renderers, Servers & Controllers

- [DaVinci Resolve and Fusion Studio](https://documents.blackmagicdesign.com/SupportNotes/DaVinci_Resolve_21_New_Features_Guide.pdf) – **Commercial; free edition available.** Version 21 introduced OGraf and Lottie support for editorial and compositing; verify version-specific requirements before deployment.
- [Erizos](https://docs.erizos.tv/userguide/BasicConfig/) – **Commercial; hosted/SaaS.** Cloud production system with changelog-documented OGraf support alongside its HTML Composer workflow.
- [H2R Graphics](https://h2r.graphics/) – **Commercial; free edition available.** Live graphics application that directly imports OGraf Graphics and generates operator fields from their data schema.
- [NetOn.Live LiveOS](https://www.neton.live/) – **Commercial.** Software-defined production platform with a vendor-documented OGraf-compliant HTML graphics engine.
- [nxt-graphics](https://github.com/nxtedition/nxt-graphics) – **Source available; no licence asserted.** An OGraf host Graphic used in nxtedition editing and timeline workflows.
- [ofxOGraf](https://github.com/Jonathhhan/ofxOGraf) – **Open source (MIT). Experimental.** openFrameworks authoring and runtime addon with native/Emscripten rendering, deterministic seeking, and an OGraf v1 Web Component.
- [OGraf image-sequence renderer](https://github.com/pjaspinski/ograf-to-image-sequence-renderer) – **Open source (MIT). Experimental.** Small non-real-time renderer that saves an OGraf Graphic as a sequence of images.
- [OGraf Simple Rendering System](https://github.com/SuperFlyTV/ograf-server) – **Open source (MIT).** Reference-oriented browser renderer, graphics manager, Server API implementation, and controller interface.
- [SPX Graphics](https://www.spx.graphics/ograf) – **Open source (MIT); commercial editions available.** SPX-GC and associated products provide documented OGraf rendering and control for live and production workflows.

### Examples & Templates

- [CBC/Radio-Canada MXL Hands-on](https://github.com/cbcrc/mxl-hands-on) – **Open source (Apache-2.0).** Workshop material containing an HTML5 keyer and OGraf teleprompter transported over MXL.
- [EBU OGraf examples](https://github.com/ebu/ograf/tree/main/v1/examples) – Reference Graphics and test material maintained with the official specification.
- [Johan Nyman's OGraf Graphics](https://github.com/nytamin/ograf-graphics) – **Open source (MIT).** A community collection of OGraf example Graphics and experiments.
- [Lotties for Broadcast](https://github.com/Streamshapers/LottiesForBroadcast) – **Source available; no licence asserted.** Example Lottie animations and templates for Ferryman, SPX, and CasparCG workflows.
- [OGraf over dash.js](https://github.com/ryanmccartney/ograf-dash.js) – **Source available; no licence asserted. Proof of concept.** Demonstrates an OGraf overlay rendered over a dash.js video player.
- [Resolve OGraf Developer Documentation](https://github.com/jdanna/Resolve_Tools_Public/tree/main/docs/OGraf%20HTML%20Templates) – **Source available; no licence asserted. Community documentation.** Unofficial Resolve OGraf integration notes, starter templates, and examples.
- [Resolve OGraf Examples](https://github.com/mug-lab-3/resolve-ograf) – **Source available; licence unclear. Experimental.** Learning examples for Resolve OGraf Titles whose author explicitly advises against production use.

## Organizations & Communities

- [Advanced Media Workflow Association](https://www.amwa.tv/) – Develops the open NMOS specifications used to discover, connect, and control professional IP-media systems.
- [European Broadcasting Union](https://www.ebu.ch/) – Public-service media alliance responsible for OGraf and many broadcast technology recommendations.
- [Society of Motion Picture and Television Engineers](https://www.smpte.org/) – Professional association and standards body for motion-imaging technology.
- [World Wide Web Consortium](https://www.w3.org/) – Develops web standards and community material underlying interoperable browser graphics.

## Resources

### Articles & Case Studies

- [AWS HTML5 Motion Overlay Walkthrough](https://docs.aws.amazon.com/elemental-live/latest/ug/how-to-insert-a-motion-overlay-with-html5.html) – Shows how AWS Elemental Live burns a continuously published HTML5 motion overlay into encoded outputs.
- [EBU's Open Spec for Cross-Platform Graphics Integration](https://tech.ebu.ch/news/2025/04/ograf-the-ebu%27s-open-spec-for-cross-platform-graphics-integration) – Introduces OGraf goals, architecture, and multi-platform live and post-production use cases.
- [NEP Finland LiveOS and SPX Case Study](https://www.spx.graphics/spx-graphics-helps-upgrade-finnish-lottery-production) – Vendor case study describing integrated HTML5 graphics for Lotto and Eurojackpot productions.
- [OGraf Webinar Slide Deck](https://tech.ebu.ch/publications/webinar-ograf-html-graphics-spec) – EBU presentation explaining the HTML graphics specification, packaging, APIs, and intended workflows.
- [SPX: How to Create HTML Graphics](https://docs.spxgraphics.com/Documentation/Graphic%2BTemplates/Overview) – Compares custom HTML, Lottie/After Effects, Loopic, and Rive authoring approaches for broadcast graphics.
- [Using Singular in Post Production](https://support.singular.live/hc/en-us/articles/360055456751-Using-Singular-in-Post-Production-for-Windows) – Vendor workflow for recording browser-rendered graphics with transparency for Premiere Pro or After Effects.
- [Vizrt's Guide to HTML5 Graphics](https://www.vizrt.com/ebooks/your-guide-to-html5-graphics-for-live-productions/) – Vendor guide to browser-rendered graphics in live production; treat performance and business claims as vendor-authored.

### Scientific Literature & Theses

- [A Cross-Device and Cross-OS Benchmark of Modern Web Animation Systems](https://doi.org/10.3390/jimaging12010045) – Peer-reviewed benchmark of modern web animation approaches across devices and operating systems.
- [A Survey of Digital Television Interactivity Technologies](https://doi.org/10.3390/s22176542) – Peer-reviewed survey providing technical context for interactive television delivery and standards.
- [Broadcast Media Creation as a Service](https://doi.org/10.5594/JMI.2020.3024028) – SMPTE paper on cloud-hosted, GPU-enabled media creation architecture.
- [Henri Johansson's HTML5 Broadcast Graphics Thesis](https://www.theseus.fi/bitstream/10024/891614/2/Johansson_Henri.pdf) – 2025 thesis examining Yle workflows built around SPX, CasparCG, HTML, CSS, and JavaScript.
- [Ismo Vaittinen's CasparCG Thesis](https://www.theseus.fi/bitstream/10024/113413/1/Vaittinen_Ismo.pdf) – 2016 thesis on an open-source graphics and video playout system for live production.
- [Presentation Accuracy of the Web Revisited](https://doi.org/10.1371/journal.pone.0109812) – Peer-reviewed study of timing accuracy among HTML5-era browser animation methods.
- [Television Infographics as Orienting Response](https://doi.org/10.1177/19312431211039500) – Peer-reviewed eye-tracking study of attention and recall around television infographics.
- [Titling for Live Streaming and File-Based Broadcast Workflows](https://doi.org/10.5594/M001731) – SMPTE conference paper on reusable, data-driven titling across live and file-based outputs.
- [TV Graphics Personalization Using In-Band Events](https://www.researchgate.net/publication/319442826_TV_Graphics_Personalization_Using_In-Band_Events) – Research on event-driven HTML overlays synchronized with MPEG-DASH playback; no paper-specific DOI is asserted here.

### Books

- [Broadcast Graphics on the Spot](https://search.worldcat.org/title/61711466) – Practical broadcast and post-production graphics techniques using Photoshop and After Effects.
- [Core HTML5 Canvas](https://www.informit.com/store/core-html5-canvas-graphics-animation-and-game-development-9780132761611) – General Canvas graphics and animation reference applicable to custom browser graphics.
- [Foundation HTML5 Animation with JavaScript](https://link.springer.com/book/10.1007/978-1-4302-3666-5) – General JavaScript animation fundamentals for Canvas and browser-based motion.
- [Motion Graphics: Graphic Design for Broadcast and Film](https://openlibrary.org/books/OL8662465M/Motion_Graphics) – Design and historical context for motion graphics across broadcast and film.

### Documentation & Knowledge Sources

- [CasparCG HTML Producer](https://github.com/CasparCG/server/wiki/HTML-Producer) – Technical notes for the Chromium-based CasparCG HTML producer.
- [CasparCG HTML Template Guide](https://chrisryanouellette.gitbook.io/casparcg-html-template-guide) – Community guide to the CasparCG HTML template lifecycle, data updates, and authoring patterns.
- [Chrome DevTools Performance Reference](https://developer.chrome.com/docs/devtools/performance/reference) – Reference for recording and interpreting browser rendering, scripting, layout, paint, and frame performance.
- [MDN Animation Performance](https://developer.mozilla.org/en-US/docs/Web/Performance/Guides/Animation_performance_and_frame_rate) – Explains the browser rendering waterfall and why transform/opacity animations often avoid layout and paint.
- [MDN Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API) – Reference for scriptable 2D and WebGL drawing used by many HTML graphics runtimes.
- [MDN CSS Font Loading API](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Font_Loading_API) – Reference for explicitly loading and checking fonts before playout or offline capture.
- [MDN Custom Elements](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_custom_elements) – Guide to defining the custom elements used as the packaging boundary for OGraf Graphics.
- [SPX HTML Template Format](https://docs.spxgraphics.com/Documentation/Graphic%2BTemplates/Formats/HTML) – Documents SPX HTML/CSS/JavaScript templates, template definitions, and operator fields.
- [StreamShapers Documentation](https://streamshapers.com/docs) – Documentation and tutorials covering Ferryman, After Effects, OGraf, CasparCG, SPX, and HTML templates.

### Education & Tutorials

- [H2R OGraf Import Guide](https://h2r.graphics/docs/graphics/ograf/) – Explains importing an OGraf Graphic and mapping its data schema to H2R operator controls.
- [ograf.dev Tutorials](https://ograf.dev/tutorials) – Independent step-by-step OGraf examples with interactive previews.
- [SPX Knowledge Base](https://docs.spxgraphics.com/) – Documentation for installing, authoring, controlling, and deploying SPX HTML graphics.

### Forums & Community

- [CasparCG Forum](https://casparcgforum.org/) – Community support forum for CasparCG playout, HTML templates, clients, and integrations.
- [CasparCG GitHub Discussions](https://github.com/CasparCG/server/discussions) – Development and usage discussions attached to the CasparCG Server repository.
- [D3 Community](https://d3js.org/community) – Official routes to D3 help, examples, discussions, and the Observable community.
- [EBU OGraf Issues](https://github.com/ebu/ograf/issues) – Public specification questions, proposals, bug reports, and implementation discussions.
- [GSAP Community](https://gsap.com/community/) – Official support forums and community resources for GSAP animation.
- [LottieFiles Forum](https://forum.lottiefiles.com/) – Community support for Lottie authoring, rendering, formats, and integrations.
- [MapLibre Community](https://maplibre.org/community/) – Official community page linking project meetings, Slack, and contributor channels.
- [Motion Canvas Discord](https://github.com/motion-canvas/motion-canvas/discussions) – Official chat community for Motion Canvas code-driven animation.
- [NodeCG Community](https://github.com/nodecg/nodecg#community) – Official repository section linking the NodeCG Discord and support channels.
- [PixiJS Discussions](https://github.com/pixijs/pixijs/discussions/) – Official discussion board for PixiJS rendering and development questions.
- [Remotion Discord](https://www.remotion.dev/discord) – Official community chat for React-based video generation.
- [Rive Community](https://community.rive.app/home) – Official discussion and support community for Rive authoring, runtimes, and integrations.
- [SPX Graphics Support](https://spxgraphics.com/support/) – Support page linking SPX documentation, GitHub, and its public Discord community.
- [Three.js Discourse](https://discourse.threejs.org/) – Official forum for Three.js rendering, shaders, animation, and tooling.

### Lists & Landscapes

- [Awesome Broadcasting](https://github.com/ebu/awesome-broadcasting) – Curated open-source broadcasting resources, including Animation, Graphics & Video Playout.
- [Awesome NodeCG](https://github.com/nodecg/awesome-nodecg) – **Archived.** Community list of NodeCG bundles, utilities, examples, and resources.
- [CasparCG Related Projects](https://github.com/CasparCG/help/wiki/Related-Projects) – Community-maintained index of clients, templates, libraries, and tools around CasparCG.
- [ograf.dev Ecosystem](https://ograf.dev/ecosystem) – Independent directory of OGraf specifications, editors, controllers, renderers, post-production integrations, tools, templates, and services.

### Videos & Talks

- [CasparCG HTML Templates: Basic Animated Lower Third](https://www.youtube.com/watch?v=2oJaECoOPoQ) – Geert Verhoeff, 11:00 — builds a basic animated lower third for CasparCG.
- [HTML Graphics with Rive and CasparCG](https://www.youtube.com/watch?v=BnV55qu6vvg) – Aiden Wilson, 31:27 — tutorial for controlling a Rive animation in a CasparCG HTML template.
- [HTML-Based Graphics for Multi-Platform Production](https://www.youtube.com/watch?v=3YZyWCjHK9U) – IBCShow, 5:33 — Kickstart pitch that provides historical context for interoperable HTML graphics work.
- [Loopic CasparCG Lower Third](https://www.youtube.com/watch?v=gZRYTmngqLw) – Geert Verhoeff, 17:29 — creates a simple CasparCG lower third with Loopic.
- [OGraf](https://www.youtube.com/watch?v=gw2SnjeGW9Q) – OGraf EBU, 4:54 — concise overview of the specification and workflow.
- [OGraf Maps in Erizos Studio](https://www.youtube.com/watch?v=-S_gBYPyCiw) – everviz, 0:13 — short demonstration of an OGraf map in Erizos Studio.
- [OGraf with SPX and Loopic](https://www.youtube.com/watch?v=P6VEWyv7-P0) – SPX Graphics, 1:43 — demonstrates moving a Loopic-authored OGraf Graphic into SPX.
- [OGraf: An Open Specification for HTML-Based Graphics](https://www.youtube.com/watch?v=6IMGzvxe1AY) – smpteconnect, 42:47 — detailed technical presentation of OGraf.
- [SPX-GC HTML Templates](https://www.youtube.com/watch?v=AdZATSBByng) – Tuomo Kulomaa, 5:03 — introduces the structure and use of SPX HTML templates.
- [SPX-GC Overview](https://www.youtube.com/watch?v=e5LTFC9MlOI) – Tuomo Kulomaa, 6:53 — overview of the open-source SPX Graphics Controller.
- [Using an After Effects OGraf with Ferryman](https://www.youtube.com/watch?v=u4wruk2QTs0) – StreamShapers, 1:17 — demonstrates an After Effects-to-OGraf workflow with Ferryman.

### Standards, Specifications & Protocols

#### Graphics & Template Interchange

- [CasparCG HTML Template Interface](https://github.com/CasparCG/help/wiki/Template-Host-Commands) – The JavaScript host commands and callbacks used to control CasparCG HTML templates; it is not an OGraf package format.
- [dotLottie Specification](https://dotlottie.io/spec/) – Defines an archive format for bundling one or more Lottie animations with metadata and assets.
- [Lottie Animation Format](https://lottie.github.io/lottie-spec/) – Community specification for portable vector animation data rendered by Lottie runtimes.
- [SPX Template Definition](https://docs.spxgraphics.com/Documentation/Graphic%2BTemplates/Template%2BDefinition) – Product-specific metadata and data-field contract for SPX templates; it is distinct from OGraf.

#### Newsroom, Automation & Control

- [Advanced Media Control Protocol](https://github.com/CasparCG/help/wiki/AMCP-Protocol) – CasparCG command protocol used by many graphics controllers and automation systems.
- [Ember+](https://github.com/Lawo/ember-plus) – Open control protocol and implementation resources used in broadcast systems; it does not define graphics templates.
- [MOS Protocol](https://mosprotocol.com/) – Newsroom object, rundown, status, and control protocol; MOS does not itself define a portable HTML Graphic.
- [NMOS IS-04](https://specs.amwa.tv/is-04/) – Discovery and registration for networked media nodes, devices, sources, flows, senders, and receivers.

#### Web Platform

#### Media Transport, Colour & Safety

## Tools & Products

### Authoring, Animation & Conversion

### Web Components & Graphics Libraries

### Data Visualization & Maps

### Typography & Font Handling

### Testing, Performance & Security

### Open-source Graphics Systems

### Commercial & Cloud Graphics Platforms

### Browser-capable Production Hosts

### Rendering, Key-Fill & Video Output

### Newsroom, Rundown & Automation

### Sports, Data & Audience Graphics

### Post-production & NLE Integration

### HTML-to-Video & Offline Rendering

### Interactive & Player-side Graphics

### Templates, Marketplaces & Services

### Related Animation, Graphics & Playout
