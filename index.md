---
layout: default
title: "An Empirically Grounded Reference Architecture for Software Supply Chain Metadata Management"
description: "An SoK paper that gives SCM2 a vocabulary and an architecture, built from 11 industry and academic frameworks and validated against 5 tools."
---

<section class="hero">
  <div class="hero-inner">
    <p class="venue-badge">
      <span class="venue-name">EASE 2024</span>
      <span class="venue-sep">·</span>
      <span>28th International Conference on Evaluation and Assessment in Software Engineering</span>
      <span class="venue-sep">·</span>
      <span>pp. 38–47</span>
      <span class="venue-sep">·</span>
      <span>2024</span>
    </p>

    <h1 class="paper-title">An Empirically Grounded Reference Architecture for Software Supply Chain Metadata Management</h1>
    <p class="paper-subtitle">A vocabulary and architecture for managing software supply chain metadata across its life cycle.</p>

    <p class="authors">
      <span><strong>Nguyen Khoi Tran</strong><sup>1</sup></span>
      <span class="dot">·</span>
      <span><strong>Samodha Pallewatta</strong><sup>1</sup></span>
      <span class="dot">·</span>
      <span><strong>M. Ali Babar</strong><sup>1,2</sup></span>
    </p>

    <p class="affiliations">
      <sup>1</sup> CREST, The University of Adelaide, Australia &nbsp;
      <sup>2</sup> Cyber Security Cooperative Research Centre, Australia
    </p>

    <div class="hero-actions">
      <a class="btn btn-primary" href="{{ '/assets/pdf/main.pdf' | relative_url }}">⬇ Download PDF</a>
      <a class="btn btn-ghost" href="https://doi.org/10.1145/3661167.3661212" rel="noopener">View on ACM Digital Library ↗</a>
    </div>
  </div>
</section>

<section class="section section--alt">
  <div class="container">
    <h2>TL;DR</h2>
    <p>
      Software supply chain attacks have grown <strong>742% in three years</strong>. To defend against them,
      organisations need trustworthy, machine-readable visibility into every artefact's life cycle, which
      we call <em>software supply chain metadata</em>. Practitioners have no comprehensive vocabulary or
      architectural blueprint to navigate the design space of <strong>SCM2</strong> (Software Supply Chain
      Metadata Management) systems. This paper provides one. We contribute an <strong>empirically grounded
      Reference Architecture</strong> combining a domain model and an architectural blueprint, synthesised from
      <strong>11 SSC security frameworks</strong> and validated by mapping <strong>5 prominent SSC security
      tools</strong> onto it.
    </p>
  </div>
</section>

<section class="section">
  <div class="container">
    <h2>At a glance</h2>
    <div class="stat-grid">
      <div class="stat">
        <div class="stat-value">11</div>
        <div class="stat-label">SSC security frameworks analysed</div>
      </div>
      <div class="stat">
        <div class="stat-value">331</div>
        <div class="stat-label">digital note cards from the analysis</div>
      </div>
      <div class="stat">
        <div class="stat-value">13</div>
        <div class="stat-label">functional containers in the blueprint</div>
      </div>
      <div class="stat">
        <div class="stat-value">5</div>
        <div class="stat-label">SSC security tools mapped for evaluation</div>
      </div>
    </div>
  </div>
</section>

<section class="section section--alt">
  <div class="container">
    <h2>How we built the RA</h2>
    <p>
      We followed Galster and Avgeriou's empirically grounded Reference Architecture design methodology.
      We combined an <strong>industry-driven</strong> foundation (13 reports and standards such as SLSA,
      SCITT, SCVS, SSF) with <strong>peer-reviewed</strong> academic inputs (4 articles), unified through
      a <em>hybrid design strategy</em>. We extracted information via document analysis into
      <strong>331 digital note cards</strong>, organised them into a knowledge graph in Obsidian, and
      consolidated them into the domain model and architectural blueprint. To establish validity we
      mapped five widely-used SSC security solutions — <em>Scribe, Chainguard Enforce, Anchore, Snyk,
      and FOSSA</em> — onto the proposed RA.
    </p>
    <figure class="figure">
      <img src="{{ '/assets/figures/methodology_overview.png' | relative_url }}" alt="Six-step methodology for constructing the empirically grounded Reference Architecture for SSC Metadata life cycle management">
      <figcaption>
        The six-step methodology: determine RA type, determine design strategy, data acquisition, RA construction, enabling variability, and evaluation.
      </figcaption>
    </figure>
  </div>
</section>

<section class="section">
  <div class="container">
    <h2>The SCM2 domain model</h2>
    <p>
      The first half of the RA is a <strong>domain model</strong> that organises every concept relevant to
      SSC metadata into four clusters: the <em>SSC activities</em> that create and consume metadata,
      the <em>SSC artefacts</em> that the metadata describes, the <em>SSC metadata actors</em> who act
      on it, and the taxonomic relationships among SSC metadata types themselves (SBOM, provenance,
      attestation, transparent statements, VEX). Together these clusters give architects and
      stakeholders a common vocabulary for figuring out what their organisation actually needs to know
      about its software supply chain.
    </p>
    <figure class="figure">
      <img src="{{ '/assets/figures/SSC_Domain_Model.png' | relative_url }}" alt="Domain Model for SSC and SSC Metadata Concepts">
      <figcaption>
        Domain model for SSC and SSC metadata concepts, organised into four clusters: activities, artefacts, actors, and metadata types.
      </figcaption>
    </figure>
  </div>
</section>

<section class="section section--alt">
  <div class="container">
    <h2>The SSC metadata life cycle</h2>
    <p>
      The dynamic half of the domain model is the <strong>ten-activity life cycle</strong> that organises
      everything an SCM2 system must support. We split it into three phases:
    </p>
    <ul class="framework-list">
      <li><strong>Generation</strong>: metadata creation (pre-build, build-time, post-build), signing, and verify-and-update.</li>
      <li><strong>Sharing</strong>: advertisement, access (policy-based authorisation), and transport from producers and providers to consumers.</li>
      <li><strong>Consumption</strong>: acquisition, resolution (linking subjects to artefacts and transitive dependencies), content management, and utilisation (vulnerability monitoring, verification, enrichment).</li>
    </ul>
    <p>
      Where the frameworks we analysed diverge (for example, whether signing is mandatory, or whether a
      third-party provider handles advertisement), the RA captures both as <em>variants</em> tied to
      explicit variation points.
    </p>
    <figure class="figure">
      <img src="{{ '/assets/figures/SSC_metadata_life_cycle.png' | relative_url }}" alt="Life cycle of SSC Metadata">
      <figcaption>
        Life cycle of SSC metadata, showing the ten activities across generation, sharing, and consumption phases, with the actors that perform them.
      </figcaption>
    </figure>
  </div>
</section>

<section class="section">
  <div class="container">
    <h2>The SCM2 architectural blueprint</h2>
    <p>
      The second half of the RA is an architectural blueprint expressed with the C4 model: a
      <strong>context diagram</strong> situating SCM2 within the broader IT environment, and a
      <strong>container diagram</strong> decomposing an SCM2 instance into 13 functional containers.
      We organise these into five groups mirroring the life cycle phases.
    </p>

    <figure class="figure">
      <img src="{{ '/assets/figures/SCM2_Context.png' | relative_url }}" alt="Context model of SCM2">
      <figcaption>
        Context model: SCM2 positioned among producer-side actors (metadata producers, source repos, build systems, SCA, binary analysis) and consumer-side actors (auditors, asset management, security posture, distribution channels).
      </figcaption>
    </figure>

    <figure class="figure">
      <img src="{{ '/assets/figures/SCM2_Container.png' | relative_url }}" alt="Container model of SCM2">
      <figcaption>
        Container model: 13 SCM2 containers distributed across generation, signing, publishing, sharing, and consumption groups.
      </figcaption>
    </figure>

    <div class="containers-grid">
      <div class="container-card">
        <span class="group-label">Generation</span>
        <h3>SSC Metadata Editor</h3>
        <p>GUI for reviewing and editing SSC metadata documents (NTIA "Edit" tool type).</p>
      </div>
      <div class="container-card">
        <span class="group-label">Generation</span>
        <h3>Pipeline Observer</h3>
        <p>Captures evidence about tasks in the build pipeline (from Secure Software Factory).</p>
      </div>
      <div class="container-card">
        <span class="group-label">Generation</span>
        <h3>SSC Metadata Generator</h3>
        <p>Creates SSC metadata documents in a prescribed standard (SPDX, CycloneDX, in-toto).</p>
      </div>
      <div class="container-card">
        <span class="group-label">Signing</span>
        <h3>SSC Metadata Signer</h3>
        <p>Turns generated metadata into authenticated software attestations (e.g. cosign + in-toto).</p>
      </div>
      <div class="container-card">
        <span class="group-label">Publishing</span>
        <h3>SSC Metadata Publisher</h3>
        <p>Implements advertisement and optional notarisation (e.g. sigstore rekor client).</p>
      </div>
      <div class="container-card">
        <span class="group-label">Publishing</span>
        <h3>Access Control</h3>
        <p>Specifies and enforces fine-grained access policies on published metadata.</p>
      </div>
      <div class="container-card">
        <span class="group-label">Sharing</span>
        <h3>Metadata Repository</h3>
        <p>Stores generated SSC metadata documents (cloud storage, OCI registry, PostgreSQL).</p>
      </div>
      <div class="container-card">
        <span class="group-label">Sharing</span>
        <h3>Access Service</h3>
        <p>Wraps the repository and serves authorised query/retrieve requests from consumers.</p>
      </div>
      <div class="container-card">
        <span class="group-label">Sharing</span>
        <h3>Registry</h3>
        <p>Verifiable, append-only log of notarisation records (e.g. Rekor transparency log).</p>
      </div>
      <div class="container-card">
        <span class="group-label">Sharing</span>
        <h3>Transparency Service</h3>
        <p>Validates and notarises submitted metadata, recording the process in the registry.</p>
      </div>
      <div class="container-card">
        <span class="group-label">Consumption</span>
        <h3>Metadata Validator</h3>
        <p>Validates the syntax of an SSC metadata document against a given standard.</p>
      </div>
      <div class="container-card">
        <span class="group-label">Consumption</span>
        <h3>Metadata Verifier</h3>
        <p>Verifies the contents of a metadata document (signatures, claims, attestations).</p>
      </div>
      <div class="container-card">
        <span class="group-label">Consumption</span>
        <h3>Metadata Resolver</h3>
        <p>Maps subjects to artefacts and resolves transitive dependencies.</p>
      </div>
    </div>
  </div>
</section>

<section class="section section--alt">
  <div class="container">
    <h2>What the evaluation revealed</h2>
    <p>
      We mapped five prominent SSC security solutions (Scribe, Chainguard Enforce, Anchore, Snyk, and
      FOSSA) onto the proposed RA. The mapping confirmed the RA's descriptive power (RQ1) and surfaced
      four insights about the state of practice (RQ2):
    </p>

    <div class="finding">
      <h3>Containers rather than packages</h3>
      <div class="finding-grid">
        <div class="finding-item"><span class="num">3 / 5</span><span class="lbl">tools focus on <strong>container images</strong> rather than packages</span></div>
        <div class="finding-item"><span class="num">2</span><span class="lbl">SBOM standards widely supported: <strong>SPDX &amp; CycloneDX</strong></span></div>
        <div class="finding-item"><span class="num">4 / 5</span><span class="lbl">do <strong>not</strong> implement a pipeline observer</span></div>
      </div>
    </div>

    <div class="finding">
      <h3>Consumers are also producers</h3>
      <p>
        Most of the SCM2 implementations we looked at are <em>single-user</em>: an organisation generates SBOMs
        from artefacts it already consumes. The <em>multi-user</em> ecosystem envisioned by SCITT and the SBOM
        network concept, where producers, providers, and consumers are distinct entities, remains rare.
      </p>
    </div>

    <div class="finding">
      <h3>SBOM dominates, provenance lags</h3>
      <p>
        Every tool we mapped focuses on SBOM. Software provenance in SLSA or in-toto form, and attestations
        that go beyond wrapping SBOM content, are largely absent. Where attestation and notarisation do appear,
        the implementation is the <strong>sigstore</strong> suite.
      </p>
    </div>

    <div class="finding">
      <h3>Centralised, single-user, mostly distributed</h3>
      <p>
        Four out of five tools deploy as centralised services, two as distributed systems. None operates as a
        decentralised multi-user ecosystem. This points to a clear future-work direction for SCM2: a decentralised
        federation of transparency services where metadata is generated at the point of origin and consumed via
        secure channels.
      </p>
    </div>
  </div>
</section>

<section class="section">
  <div class="container">
    <h2>Abstract</h2>
    <p>
      With the rapid rise in Software Supply Chain (SSC) attacks, organisations need thorough and trustworthy
      visibility over the entire SSC of their software inventory to detect risks early and identify compromised
      assets rapidly in the event of an SSC attack. One way to achieve such visibility is through SSC metadata,
      the machine-readable and authenticated documents describing an artefact's lifecycle. Adopting SSC metadata
      requires organisations to procure or develop a Software Supply Chain Metadata Management system (SCM2),
      a suite of software tools for performing lifecycle activities of SSC metadata documents such as creation,
      signing, distribution, and consumption. Selecting or developing an SCM2 is challenging because
      practitioners lack a comprehensive domain model and architectural blueprint to navigate the vast design
      space of SSC metadata terminologies, frameworks, and solutions.
    </p>
    <p>
      In this paper we address that challenge by presenting an empirically grounded Reference Architecture (RA)
      comprising a domain model and an architectural blueprint for SCM2 systems. We constructed our RA
      systematically on an empirical foundation built with industry-driven and peer-reviewed SSC security
      frameworks. We then did a theoretical evaluation that mapped five prominent SSC security tools onto the RA
      to confirm its validity and applicability, affirming it as an effective framework for analysing existing
      SCM2 solutions and guiding the engineering of new SCM2 systems.
    </p>
  </div>
</section>

<section class="section section--alt">
  <div class="container">
    <h2>BibTeX</h2>
    <pre class="bibtex"><code>@inproceedings{tran2024empirically,
  title     = {An Empirically Grounded Reference Architecture for Software Supply Chain Metadata Management},
  author    = {Tran, Nguyen Khoi and Pallewatta, Samodha and Babar, Muhammad Ali},
  booktitle = {Proceedings of the 28th International Conference on Evaluation and Assessment in Software Engineering},
  pages     = {38--47},
  year      = {2024},
  doi       = {10.1145/3661167.3661212}
}</code></pre>
    <p class="doi-line">
      DOI: <a href="https://doi.org/10.1145/3661167.3661212" rel="noopener">10.1145/3661167.3661212</a>
    </p>
  </div>
</section>