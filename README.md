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

## Resources

### Articles & Case Studies

### Scientific Literature & Theses

### Books

### Documentation & Knowledge Sources

### Education & Tutorials

### Forums & Community

### Lists & Landscapes

### Videos & Talks

### Standards, Specifications & Protocols

#### Graphics & Template Interchange

#### Newsroom, Automation & Control

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
