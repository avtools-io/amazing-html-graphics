# Amazing HTML Graphics

A curated resource list primarily for broadcast engineers, software developers, and systems integrators who build and maintain graphics systems. It also serves motion designers, graphics operators, and post-production professionals who create and deliver graphics.

Centered on [EBU OGraf](https://ograf.ebu.io/), the list covers HTML-based graphics across live broadcast, streaming, post-production, film, and documentary workflows.

Coverage follows the graphics workflow—from authoring, animation, and data visualisation through template packaging, validation, control, rendering, compositing, playout, and delivery—and extends to post-production and offline rendering. The list also brings together relevant standards, tools and products, research, case studies, documentation, and training.

**Contributions are welcome.** Suggest a resource by [opening an issue](https://github.com/avtools-io/amazing-html-graphics/issues)—no Git experience is required. To contribute directly, read the [contribution guide](CONTRIBUTING.md) and submit one focused pull request per resource entry.

Amazing HTML Graphics follows the model of [Amazing Digital Cinema](https://github.com/avtools-io/amazing-digital-cinema) and draws inspiration from [Awesome Broadcasting](https://github.com/ebu/awesome-broadcasting) and the wider [Awesome](https://github.com/sindresorhus/awesome) project. Some Awesome lists focus exclusively on open-source projects.

Professional HTML graphics spans a broader ecosystem: open standards, open-source software, commercial and hosted products, marketplaces, research, education, communities, and production knowledge. To reflect this scope while respecting open-source-only Awesome lists, this project is called “Amazing” rather than “Awesome.”

**How to read the entries.** Inclusion means that a resource is relevant to professional HTML graphics; it does not imply OGraf support. When an OGraf relationship is documented, the description identifies its role, such as **authoring**, **export**, **import**, **validation**, **control**, **rendering**, or **demonstration**. Loading an OGraf renderer URL through a browser source is treated as **integration**, not direct OGraf support.

Software and product entries use bold labels to describe availability, delivery, and maturity. **Open source** includes a verified licence where practical; **Source available** does not imply an open-source licence. **Commercial**, **Hosted/SaaS**, **Open core**, and **Freeware** describe availability or delivery, while **Experimental**, **Beta**, **Archived**, and **Deprecated** describe maturity.

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
  - [Templates & Marketplaces](#templates--marketplaces)
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
- [NMOS IS-05](https://specs.amwa.tv/is-05/) – Connection management for establishing media flows between NMOS senders and receivers.
- [NMOS IS-07](https://specs.amwa.tv/is-07/) – Event and tally transport for production applications.
- [NMOS IS-12](https://specs.amwa.tv/is-12/) – Control protocol for discovering and manipulating device capabilities.
- [Open Sound Control](https://opensoundcontrol.stanford.edu/spec-1_0.html) – Network control message format used by some graphics and show-control tools.

#### Web Platform

- [Canvas 2D](https://html.spec.whatwg.org/multipage/canvas.html) – WHATWG definition of the immediate-mode 2D drawing surface used by browser graphics.
- [Content Security Policy](https://www.w3.org/TR/CSP3/) – Browser policy for restricting executable and fetched content in graphics that consume remote or untrusted data.
- [CSS](https://www.w3.org/Style/CSS/) – W3C specifications and working-group material for layout, styling, transforms, masking, and animation.
- [CSS Font Loading](https://drafts.csswg.org/css-font-loading/) – API specification for controlling and observing font loading.
- [Custom Elements](https://html.spec.whatwg.org/multipage/custom-elements.html) – WHATWG lifecycle and registration model underlying the Web Components exported by OGraf Graphics.
- [ECMAScript Modules](https://tc39.es/ecma262/multipage/ecmascript-language-scripts-and-modules.html) – JavaScript module semantics used by OGraf entry points and modern graphics applications.
- [JSON Schema 2020-12](https://json-schema.org/draft/2020-12) – Schema vocabulary on which OGraf Graphic data definitions are based.
- [OpenAPI Specification](https://spec.openapis.org/oas/latest.html) – HTTP API description format used by the OGraf Server API definition.
- [Scalable Vector Graphics](https://www.w3.org/TR/SVG2/) – Vector graphics format widely used for resolution-independent broadcast artwork and animation.
- [Trusted Types](https://w3c.github.io/trusted-types/dist/spec/) – DOM injection-sink controls that complement sanitisation and Content Security Policy.
- [Web Animations](https://www.w3.org/TR/web-animations-1/) – Timing and animation model exposed through CSS animations/transitions and the Web Animations API.
- [WebGL](https://www.khronos.org/webgl/) – Browser API for GPU-accelerated 2D and 3D rendering.

#### Media Transport, Colour & Safety

- [EBU R 103](https://tech.ebu.ch/publications/r103) – Video signal tolerance recommendations relevant to legal broadcast graphics output.
- [EBU R 143](https://tech.ebu.ch/publications/r143) – Cybersecurity recommendations for media vendors and systems, relevant to networked graphics deployments.
- [EBU R 95](https://tech.ebu.ch/publications/r095) – Safe-area recommendations for 16:9 television production across SD, HD, and UHD.
- [ITU-R BT.2020](https://www.itu.int/rec/R-REC-BT.2020) – UHDTV picture parameters and wide-colour-gamut primaries.
- [ITU-R BT.2100](https://www.itu.int/rec/R-REC-BT.2100) – HDR television image parameters for PQ and HLG workflows.
- [ITU-R BT.709](https://www.itu.int/rec/R-REC-BT.709) – HDTV picture characteristics and colourimetry commonly targeted by broadcast graphics.
- [NDI](https://ndi.video/for-developers/ndi-sdk/) – Commercial IP video ecosystem commonly used to carry rendered graphics and alpha-capable workflows.
- [SMPTE Public Standards](https://pub.smpte.org/doc/) – Free canonical access portal for published SMPTE standards and engineering documents.
- [SMPTE ST 2110](https://www.smpte.org/standards/st2110) – Professional Media over Managed IP suite used for uncompressed video and fill/key transport; it does not define graphics templates.

## Tools & Products

### Authoring, Animation & Conversion

- [Adobe After Effects](https://www.adobe.com/products/aftereffects.html) – **Commercial; subscription.** **Authoring, export, integration.** Motion-design and compositing application used with Bodymovin/Lottie export and third-party OGraf conversion workflows.
- [Adobe Animate](https://helpx.adobe.com/animate/desktop/interactivity/creating-publishing-html5-canvas-document.html) – **Commercial; subscription.** **Authoring, export.** Motion-graphics application that creates and publishes HTML5 Canvas documents driven by CreateJS.
- [Anime.js](https://animejs.com/) – **Open source (MIT).** **Authoring, rendering.** JavaScript animation engine for DOM, SVG, and JavaScript objects.
- [Cavalry](https://cavalry.studio/docs/user-interface/menus/window-menu/render-manager/lottie-export/) – **Commercial; free edition available.** **Authoring, export.** Procedural 2D motion-design application with documented Lottie JSON export and compatibility limits.
- [dotLottie](https://dotlottie.io/) – **Open source ecosystem.** **Import, export, rendering, integration.** Format, tools, and runtimes for packaged Lottie animations, themes, state machines, and web playback.
- [GSAP](https://gsap.com/) – **Source available; free to use under the Standard No Charge License.** **Authoring, rendering, integration.** Timeline animation toolkit for DOM, SVG, Canvas, and PixiJS graphics.
- [Lottie-web](https://github.com/airbnb/lottie-web) – **Open source (MIT).** **Import, export, rendering.** Web renderer and After Effects Bodymovin exporter for JSON vector animations.
- [Lottielab](https://docs.lottielab.com/export-and-hand-off/file-download/lottie-json-download) – **Commercial; hosted/SaaS with free tier.** **Authoring, export, rendering.** Browser-based motion-design tool with Lottie JSON export, hosted playback, and interactive animation features.
- [Motion](https://motion.dev/) – **Open source (MIT).** **Authoring, rendering, integration.** Web animation library for JavaScript, React, Vue, and browser-native animation APIs.
- [Rive](https://rive.app/) – **Commercial authoring; open-source runtimes.** **Authoring, export, rendering, integration.** Interactive vector-animation editor, state-machine format, and web runtimes.
- [SVGator](https://www.svgator.com/help/export-and-file-formats/lottie-support-in-svgator) – **Commercial; hosted/SaaS.** **Authoring, export.** Browser-based SVG animation editor with SVG export and a documented beta Lottie export path.
- [Theatre.js](https://www.theatrejs.com/) – **Open source (Apache-2.0).** **Authoring, control, rendering, integration.** Visual animation and sequencing environment for JavaScript, Three.js, and React projects.

### Web Components & Graphics Libraries

- [Babylon.js](https://www.babylonjs.com/) – **Open source (Apache-2.0).** **Rendering, integration.** WebGL/WebGPU 3D engine for browser-rendered virtual sets, explainers, and motion graphics.
- [Fabric.js](https://fabricjs.com/) – **Open source (MIT).** **Authoring, rendering, integration.** Interactive Canvas object model for building browser graphics editors and compositors.
- [FAST](https://www.fast.design/) – **Open source (MIT).** **Authoring, integration.** Standards-based Web Component libraries and tooling applicable to OGraf component authoring.
- [Konva](https://konvajs.org/) – **Open source (MIT).** **Authoring, rendering, integration.** Canvas framework for interactive 2D scene graphs and graphics-editor interfaces.
- [Lit](https://lit.dev/) – **Open source (BSD-3-Clause).** **Authoring, integration.** Lightweight library for standards-based Web Components, directly applicable to OGraf Graphic entry components.
- [PixiJS](https://pixijs.com/) – **Open source (MIT).** **Rendering, integration.** GPU-accelerated 2D engine for performant, data-driven browser graphics, with GSAP integration through PixiPlugin.
- [Stencil](https://stenciljs.com/) – **Open source (MIT).** **Authoring, integration.** Compiler and toolchain for reusable standards-based Web Components.
- [Three.js](https://threejs.org/) – **Open source (MIT).** **Rendering, integration.** WebGL/WebGPU 3D library for real-time browser graphics and data visualisation.

### Data Visualization & Maps

- [Apache ECharts](https://echarts.apache.org/) – **Open source (Apache-2.0).** **Authoring, rendering, integration.** Canvas/SVG charting library for explainers, elections, weather, and sports data.
- [Chart.js](https://www.chartjs.org/) – **Open source (MIT).** **Authoring, rendering, integration.** Canvas charting library for animated, responsive data graphics.
- [D3](https://d3js.org/) – **Open source (ISC).** **Authoring, rendering, integration.** Low-level toolkit for binding data to DOM, SVG, and Canvas visualisations.
- [Datawrapper](https://www.datawrapper.de/features) – **Commercial; hosted/SaaS with free tier.** **Authoring, export, integration.** No-code charts, maps, and tables with responsive embeds and static image, PDF, and SVG export options.
- [everviz](https://www.everviz.com/) – **Commercial; hosted/SaaS.** **Authoring, export, integration.** No-code charts and maps platform with broadcast integrations including documented OGraf output.
- [Flourish](https://flourish.studio/product/data-visualization/) – **Commercial; hosted/SaaS with free public tier.** **Authoring, export, rendering, integration.** Animated data-visualisation and storytelling platform with web embeds and plan-dependent video export.
- [Highcharts](https://www.highcharts.com/products/maps/) – **Commercial; free non-commercial use.** **Authoring, rendering, integration.** JavaScript charting and mapping libraries for interactive and animated data graphics.
- [Leaflet](https://leafletjs.com/) – **Open source (BSD-2-Clause).** **Authoring, rendering, integration.** Lightweight interactive mapping library for location-based graphics.
- [Mapbox GL JS](https://docs.mapbox.com/mapbox-gl-js/guides/get-started/) – **Commercial; source available.** **Authoring, rendering, integration.** WebGL vector-map library for animated and data-driven geographic graphics using Mapbox services.
- [MapLibre GL JS](https://maplibre.org/maplibre-gl-js/docs/) – **Open source (BSD-3-Clause).** **Authoring, rendering, integration.** GPU-accelerated vector maps for animated geographic and data-driven graphics.
- [Observable Plot](https://github.com/observablehq/plot) – **Open source (ISC).** **Authoring, rendering, integration.** Concise JavaScript grammar for layered, exploratory SVG and HTML data visualisations.
- [Plotly.js](https://github.com/plotly/plotly.js) – **Open source (MIT).** **Authoring, rendering, integration.** Declarative JavaScript library for interactive statistical, scientific, and geographic charts.
- [Turf](https://turfjs.org/) – **Open source (MIT).** **Authoring, integration.** Geospatial analysis functions for preparing and transforming map data in JavaScript.
- [Vega-Lite](https://vega.github.io/vega-lite/) – **Open source (BSD-3-Clause).** **Authoring, rendering, integration.** Declarative grammar for repeatable, data-driven statistical graphics.

### Typography & Font Handling

- [Fitty](https://rikschennink.github.io/fitty/) – **Open source (MIT).** **Rendering, integration.** Fits dynamic text into its container for unpredictable names, headlines, and scores.
- [Font Face Observer](https://github.com/bramstein/fontfaceobserver) – **Open source (BSD-3-Clause).** **Validation, integration.** Promise-based library for detecting when web fonts have loaded before graphics are played or captured.
- [opentype.js](https://opentype.js.org/) – **Open source (MIT).** **Authoring, rendering, integration.** Parses and manipulates OpenType fonts and glyph paths in the browser.

### Testing, Performance & Security

- [Ajv](https://ajv.js.org/) – **Open source (MIT).** JSON Schema validator suitable for OGraf manifests, data, and generated operator forms.
- [BackstopJS](https://github.com/garris/BackstopJS) – **Open source (MIT).** Browser screenshot regression testing for graphics at controlled viewports and states.
- [DOMPurify](https://github.com/cure53/DOMPurify) – **Open source (Apache-2.0 OR MPL-2.0).** DOM-only sanitizer for untrusted operator, newsroom, and remote HTML data.
- [JSON Forms](https://jsonforms.io/) – **Open source (MIT).** Schema-driven form framework applicable to graphics data-entry and control interfaces.
- [Playwright](https://playwright.dev/) – **Open source (Apache-2.0).** Browser automation for lifecycle tests, screenshots, data extremes, and repeatable render checks.
- [Puppeteer](https://pptr.dev/) – **Open source (Apache-2.0).** Chrome automation API used for testing, screenshots, and HTML-to-video capture workflows.

### Open-source Graphics Systems

- [CasparCG](https://casparcg.com/) – **Open source (GPL-3.0).** Graphics and video playout server with a Chromium HTML producer controlled through AMCP.
- [NodeCG](https://www.nodecg.dev/) – **Open source (MIT).** Node.js framework for browser-rendered broadcast graphics, dashboards, shared data, and operator control.
- [WebLinked](https://github.com/stoatworks-labs/weblinked) – **Open source (MIT).** CEF URL renderer with DeckLink/AJA SDI, NDI, OMT, fullscreen, HTTP, and OSC outputs.

### Commercial & Cloud Graphics Platforms

- [Dizplai](https://www.dizplai.com/) – **Commercial; hosted/SaaS.** Cloud live graphics, audience engagement, and data integration platform.
- [Grabyo Producer](https://about.grabyo.com/live-cloud-production/) – **Commercial; hosted/SaaS.** Browser-based live production platform with HTML graphics and third-party graphics integrations.
- [Grass Valley AMPP](https://www.grassvalley.com/products/cloud-based-workflows/ampp/) – **Commercial; hosted and deployable services.** Cloud production and playout platform with HTML5 graphics applications.
- [Overlays.uno](https://overlays.uno/) – **Commercial; hosted/SaaS.** Browser-source overlay creation and control for streaming and live events.
- [Poltergeist](https://poltergeist.cc/) – **Commercial; hosted/SaaS.** Collaborative browser dashboard for remotely controlling OBS Browser Source overlays.
- [Singular.live](https://www.singular.live/) – **Commercial; hosted/SaaS.** Cloud authoring and client-side rendering platform for data-driven HTML graphics.
- [Viz Flowics](https://support.flowics.com/en/articles/15393380-what-is-viz-flowics) – **Commercial; hosted/SaaS.** Cloud-native HTML5 graphics with data connectors, APIs, MOS, and broadcast output integrations.

### Browser-capable Production Hosts

- [LiveU Studio](https://www.liveu.tv/products/create/liveu-studio) – **Commercial; hosted/SaaS.** Cloud production switcher capable of using webpages as overlay sources.
- [mimoLive Browser Capture](https://mimolive.com/user-manual/sources-input/screen-sources/web-browser-capture/) – **Commercial.** macOS live-production source that renders webpages and browser overlays.
- [OBS Studio Browser Source](https://obsproject.com/kb/browser-source) – **Open source (GPL-2.0).** CEF-based source for loading local or remote HTML graphics; it can host an OGraf server renderer URL but does not import OGraf packages.
- [TriCaster](https://www.vizrt.com/products/tricaster/) – **Commercial.** Live-production systems with HTML/browser graphics workflows through HTML Buffer and LiveLink integrations.
- [vMix Web Browser Input](https://www.vmix.com/help28/WebBrowser.html) – **Commercial.** Chromium webpage input for HTML overlays; hosting a renderer URL is not direct OGraf package support.
- [Wirecast](https://support.telestream.net/s/article/Wirecast-Web-Display) – **Commercial.** Live-production application with web page and web display sources for browser graphics.

### Rendering, Key-Fill & Video Output

- [Aveco CGManager](https://www.aveco.com/en/) – **Commercial.** Broadcast graphics management and playout integration with HTML template workflows.
- [AWS Elemental Live](https://aws.amazon.com/elemental-live/) – **Commercial.** On-premises live encoder that can burn continuously published HTML5 motion overlays into outputs.
- [AWS Elemental MediaLive](https://aws.amazon.com/medialive/) – **Commercial; hosted/SaaS.** Managed live encoding service with HTML5 motion-overlay support.
- [Crystal Vision M-WEBKEY](https://crystalvision.tv/products/m-webkey.html) – **Commercial.** Hardware web-page keyer providing SDI fill/key and composited output.
- [Etere ETX](https://www.etere.com/) – **Commercial.** Channel-in-a-box and graphics engine supporting HTML5/WebGL graphics.
- [gstcefsrc](https://github.com/centricular/gstcefsrc) – **Open source (LGPL-2.1).** GStreamer source element wrapping CEF to turn HTML and JavaScript pages into video and audio streams; it is a building block rather than an OGraf server.
- [keyfillwebview](https://github.com/aDifferentJT/keyfillwebview) – **Source available; no licence asserted. Experimental.** Small browser renderer targeting separate key and fill output.
- [Lawo HOME Graphic Inserter](https://lawo.com/products/home-graphic-inserter/) – **Commercial.** HTML5 graphics insertion application for HOME-based IP production workflows.
- [Medialooks HTML5 Graphics](https://support.medialooks.com/hc/en-us/articles/360000210892-HTML5-graphics) – **Commercial.** Chromium-based HTML graphics plugin for the MPlatform and MFormats SDKs.
- [RT Software Swift Engine](https://rtsw.co.uk/products/swift-engine/) – **Commercial.** HTML5 broadcast graphics renderer for live, newsroom, and channel-branding workflows.
- [SDI-Ware](https://sdiware.video/) – **Commercial.** Software for rendering HTML graphics to professional video outputs.
- [Sienna GraphicArtist](https://www.sienna-tv.com/ndi/graphicartist.html) – **Commercial.** NDI-oriented HTML5 graphics authoring and rendering system.
- [Softron OnTheAir WebLink](https://softron.tv/products/ontheair-weblink) – **Commercial.** Renders webpages to broadcast video with fill-and-key output options.
- [Videon LiveEdge Graphix](https://videonlabs.com/liveedge-graphix) – **Commercial.** Edge HTML graphics insertion for live streams; verify edition and frame-rate limits for the intended deployment.
- [Vindral Composer](https://vindral.com/products/composer) – **Commercial; hosted/SaaS.** Browser-based graphics compositor for low-latency live-stream overlays.
- [Viz Connect Tetra](https://www.vizrt.com/products/viz-connect-tetra/) – **Commercial.** Broadcast connectivity appliance that can turn supported graphics sources into SDI or IP outputs.

### Newsroom, Rundown & Automation

- [Bitfocus Companion](https://bitfocus.io/companion) – **Open core.** Button-surface control and automation system with modules for graphics, streaming, and playout products.
- [Bridge](https://github.com/SVT/bridge) – **Source available; no licence asserted.** Extensible SVT control client for real-time graphics systems.
- [caspar-obs-client](https://github.com/michalramus/caspar-obs-client) – **Open source (MIT).** Python GUI coordinating CasparCG playback and OBS Studio scene transitions.
- [Cuez Automator](https://www.cuez.app/automator) – **Commercial; hosted/SaaS.** Rundown-driven automation with graphics and MOS connector workflows.
- [Sofie MOS Connection](https://github.com/Sofie-Automation/sofie-mos-connection) – **Open source (MIT).** TypeScript implementation of MOS communications for newsroom and automation integrations.
- [Sofie TV Automation](https://github.com/Sofie-Automation/Sofie-TV-automation) – **Open source (MIT).** Rundown and device automation system with MOS and graphics integrations.
- [SuperConductor](https://github.com/SuperFlyTV/SuperConductor) – **Source available; licence unclear.** Desktop playout client controlling CasparCG, OBS, vMix, ATEM, OSC, and HTTP devices.
- [Yle Caspartool](https://github.com/Yleisradio/caspartool) – **Source available; no licence asserted.** Browser controller for CasparCG HTML template graphics playout.

### Sports, Data & Audience Graphics

- [LIGR](https://www.ligrsystems.com/) – **Commercial; hosted/SaaS.** Automated, data-driven sports graphics platform for live streams and broadcast feeds.
- [Viz Flowics Data Connectors](https://www.flowics.com/data-connectors) – **Commercial; hosted/SaaS.** Connectors for sports, weather, finance, elections, and social data used in HTML5 graphics.

### Post-production & NLE Integration

- [MXMZ](https://www.mxmz.com/products/nle-mam) – **Commercial.** HTML graphics authoring and operation with Premiere Pro panel and media-asset-management workflows.
- [Singular Recast](https://www.singular.live/recast) – **Commercial; free utility.** Windows application for rendering Singular graphics to NDI and recording transparent files for NLE/compositing use.
- [SPX Adobe Premiere Pro Workflow](https://docs.spxgraphics.com/Documentation/Renderer/Workflows/Adobe%2BPremiere%2BPro) – **Commercial workflow.** Uses SPX-rendered graphics in Adobe Premiere Pro and other file-based finishing paths.

### HTML-to-Video & Offline Rendering

- [BeamToIX](https://github.com/a-bentofreire/beamtoix) – **Open source (MIT).** Frame-by-frame web animation framework with deterministic rendering and video-generation tooling.
- [HTML5 Animation Video Renderer](https://github.com/dtinth/html5-animation-video-renderer) – **Source available; no licence asserted. Experimental.** Captures HTML5 animation frame by frame for high-quality video encoding.
- [Motion Canvas](https://motioncanvas.io/) – **Open source (MIT).** TypeScript and Canvas-based system for programmatic, timeline-controlled motion graphics and video.
- [Puppeteer Capture](https://github.com/alexey-pelykh/puppeteer-capture) – **Open source (MIT).** Puppeteer plugin for capturing browser pages to video.
- [Remotion](https://www.remotion.dev/) – **Source available; free for qualifying use.** React-based framework and rendering stack for programmatic video generation.
- [render-d3-video](https://github.com/russellsamora/render-d3-video) – **Open source (MIT). Experimental.** Utility for rendering D3 browser animations to video.

### Interactive & Player-side Graphics

- [Ease Live](https://www.easelive.tv/) – **Commercial; hosted/SaaS.** Interactive, player-side sports and broadcast overlays delivered across viewing devices.
- [HbbTV](https://www.hbbtv.org/) – Hybrid broadcast/broadband specifications and ecosystem for interactive television applications and synchronized web experiences.

### Templates & Marketplaces

- [LottieFiles](https://lottiefiles.com/) – **Commercial; hosted/SaaS with free tier.** Lottie asset marketplace, editor, optimizer, testing tools, and hosted services.
- [SPX Graphics Store](https://spxgraphics.com/store/) – **Commercial marketplace.** Ready-made SPX HTML graphics templates and design services.
- [VideoHive Broadcast Packages](https://videohive.net/category/after-effects-project-files/broadcast-packages) – **Commercial marketplace.** After Effects broadcast packages that may serve as source artwork for supported conversion workflows.

### Related Animation, Graphics & Playout

- [Aurena](https://github.com/thaytan/aurena) – **Source available; licence unclear.** Network-distributed media playback system.
- [ffplayout](https://github.com/ffplayout/ffplayout) – **Open source (GPL-3.0).** FFmpeg- and Rust-based broadcast playout from folders and playlists.
- [Macadam](https://github.com/Streampunk/macadam) – **Open source (Apache-2.0).** Node.js bindings for Blackmagic devices, with Electron and Sevruga paths for HTML/CSS/SVG graphics output.
- [Nebula](https://github.com/nebulabroadcast) – **Open source (GPL-3.0).** Media asset management and broadcast automation ecosystem.
- [Open Playout Automation](https://github.com/jaskie/PlayoutAutomation) – **Open source (GPL-2.0).** CasparCG-based master-control-room playout and automation system.
- [ossia score](https://ossia.io/) – **Open source (GPL-3.0).** Interactive intermedia sequencer for time-based audiovisual and show-control work.
- [Studio TV Player](https://github.com/jaskie/StudioTVPlayer) – **Open source (GPL-3.0).** Studio clip player with SDI, NDI, and MPEG-TS outputs.
