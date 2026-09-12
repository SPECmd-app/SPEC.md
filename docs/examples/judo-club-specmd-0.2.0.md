---
specmd: "0.2.0"
spec_version: "0.1.1"
status: draft
name: "Judo Club Website"
last_updated: "2026-09-11"
---

# Judo Club Website Specification

## Specification Contract

This document defines the required behavior of the Judo Club Website.

A conforming implementation MAY use a different programming language, framework, hosting platform, content structure, build system, or visual design unless this specification explicitly constrains it.

Normative terms used in this document follow **BCP 14 (RFC 2119 and RFC 8174)** when written in uppercase:

- **MUST / MUST NOT** — mandatory for conformance.
- **SHOULD / SHOULD NOT** — recommendations for which deviation requires a valid reason.
- **MAY** — optional.

Requirements and explicitly normative statements define conformance.

Examples, rationale, notes, and implementation guidance are informative unless explicitly marked normative.

If source code, DESIGN.md, or other implementation documentation conflicts with this specification, this specification is authoritative for required system behavior.

If two normative statements conflict and the conflict cannot be resolved from this document, the implementer MUST surface the conflict rather than silently choose an interpretation.

If this specification leaves an implementation detail unspecified and the choice does not alter required behavior, the implementer MAY choose an appropriate solution.

If an omission could materially change externally observable behavior, data semantics, security, privacy, accessibility, or conformance, the implementer MUST treat it as an ambiguity and surface it rather than silently inventing a product rule.

### Implementation Freedom

Unless explicitly constrained, an implementation MAY change:

- programming language;
- framework and libraries;
- static or dynamic rendering approach;
- hosting provider;
- source-code organization;
- internal component structure;
- CSS methodology;
- build tooling;
- visual styling.

A conforming implementation MUST preserve:

- required pages and content categories;
- English and Japanese language behavior;
- required navigation behavior;
- required user interactions;
- accessibility requirements;
- stated constraints and non-goals;
- verification and acceptance behavior.

### Specification Version and Change Discipline

This specification is version **0.1.1** and is currently a **draft**.

It conforms to **SPEC.md Standard 0.2.0**. The SPEC.md standard version and this Judo Club specification version are intentionally independent.

Specification versions use `MAJOR.MINOR.PATCH`:

- **MAJOR** — required behavior changes in a way that may make a previously conforming implementation non-conforming.
- **MINOR** — additive changes that preserve previous conformance.
- **PATCH** — editorial clarification with no required behavioral difference.

While this document remains an unpublished draft, edits may be incorporated into the same draft version. Once a version is baselined or published, later normative changes SHOULD follow the versioning rules above.

Requirement identifiers such as `FUN-007` and `LANG-003` are stable identities. Moving a requirement to another section MUST NOT change its identifier. Retired identifiers SHOULD NOT be reused.

### Specification Set

This example is intentionally a **single-file specification**.

There are no normative specification modules or normative companion documents required for conformance.

A larger system could decompose its specification into directly referenced modules, but doing so would add unnecessary complexity to this teaching example.

---

## System at a Glance

**Purpose:** Provide clear information about a local judo club and allow prospective members to contact the club.

**Supported languages:**
- English
- Japanese

**Primary users:**
- prospective members;
- current members;
- parents or guardians;
- general visitors.

**Primary site areas:**
- Home
- About
- Classes and Schedule
- Gallery
- FAQ
- Contact
- Privacy

**Primary interactions:**
- navigate between pages;
- switch language;
- review class information;
- browse gallery images;
- open an enlarged gallery image;
- submit contact information through a direct communication handoff.

---

## Critical Invariants

The following properties MUST remain true in every conforming implementation:

- English and Japanese content MUST both be fully usable.
- Language switching between English and Japanese MUST preserve the visitor's current logical page for every required page.
- A visitor MUST NOT be required to create an account.
- The site MUST NOT store contact-form submissions in its own application database.
- Gallery images MUST remain usable with keyboard interaction where a keyboard is available.
- Core informational content MUST remain available even if optional client-side enhancements fail.

---

# 1. Overview and Scope

## 1.1 Purpose

The Judo Club Website provides public information about a local judo club.

The site exists to help visitors:

- understand what the club offers;
- learn about the coach or coaching team;
- view available classes and schedules;
- understand basic participation information;
- view club photographs;
- read frequently asked questions;
- contact the club.

## 1.2 Goals

The system MUST provide the same core site capabilities in English and Japanese.

The site SHOULD make the most common visitor tasks easy to complete:

1. understand what the club is;
2. find an appropriate class;
3. check when classes take place;
4. learn what is needed to participate;
5. contact the club.

## 1.3 System Boundary

The system includes:

- public website pages;
- English and Japanese content;
- navigation;
- language switching;
- gallery browsing;
- FAQ presentation;
- contact-form interaction;
- privacy information.

The system does not include:

- user accounts;
- member login;
- payment processing;
- online class booking;
- attendance management;
- competition registration;
- a content-management system;
- e-commerce.

## 1.4 Actors

### Visitor

A person browsing the public website.

A Visitor MAY browse any public page, switch language, view gallery images, and use the contact flow.

### Club Contact

The person or communication channel that receives a visitor's contact message.

The website does not require the Club Contact to use the website itself.

## 1.5 Supported Languages

The site supports:

- English (`en`);
- Japanese (`ja`).

Each supported language MUST provide the same logical page set unless a page is explicitly marked language-specific.

English and Japanese pages MAY use different wording where necessary for natural language, but MUST preserve the same factual meaning.

---

# 2. Context and Definitions

## 2.1 Terminology

**Club**  
The judo organization represented by the website.

**Class**  
A scheduled judo training session or recurring training group.

**Schedule Entry**  
A recurring day/time combination associated with a Class.

**Gallery Image**  
A photograph published on the Gallery page.

**Language Equivalent**  
The corresponding page representing the same logical content in another supported language.

**Contact Handoff**  
The transition from the website's contact form to an external communication mechanism without the website storing the submitted message.

## 2.2 Assumptions

The specification assumes:

- the club has one public identity;
- class schedules are maintained manually by the site maintainer;
- visitors do not need personalized accounts;
- the site has low-complexity public content;
- the club monitors at least one direct communication channel suitable for receiving enquiries.

These assumptions do not require a particular hosting or implementation technology.

## 2.3 Open Issues

There are no unresolved product requirements in this example.

If an unresolved matter is introduced later, it SHOULD be listed here using an explicit marker such as `TBD`, `Open Issue`, or `Unverified`.

An unresolved item MUST NOT be silently treated as a normative requirement.

## 2.4 Representation Conventions

Unless explicitly stated otherwise:

- dates use ISO 8601 `YYYY-MM-DD`;
- times use 24-hour notation `HH:MM`;
- language identifiers use BCP 47 language tags;
- structured booleans use `true` and `false`;
- text encoding is UTF-8.

User-facing date/time presentation MAY be localized.

`null`, absent, empty string, empty collection, zero, and `false` are distinct values unless explicitly stated otherwise.

---

# 3. System Model

## 3.1 Conceptual Model

The website contains the following primary concepts:

- Site
- Language
- Page
- Club
- Coach
- Class
- Schedule Entry
- FAQ Entry
- Gallery Image
- Contact Enquiry

## 3.2 Logical Entities

### Club

Represents the judo club.

Behaviorally significant information includes:

- club name;
- short description;
- location;
- contact information.

### Coach

Represents a coach or instructor presented by the site.

A Coach MAY contain:

- name;
- role;
- credentials;
- biography;
- photograph.

The site MUST support at least one Coach.

### Class

Represents a recurring training group or class.

A Class MUST have:

- name;
- description;
- at least one Schedule Entry.

A Class MAY additionally include:

- intended skill level;
- recommended age range;
- equipment guidance;
- additional participation notes.

### Schedule Entry

Represents one recurring day/time for a Class.

A Schedule Entry MUST identify:

- day of week;
- start time;
- end time.

### FAQ Entry

Represents one question and answer.

Each FAQ Entry MUST provide:

- an English question and answer;
- a Japanese question and answer.

### Gallery Image

Represents one image available through the Gallery.

Each Gallery Image MUST provide:

- an image asset;
- English alternative text;
- Japanese alternative text.

A Gallery Image MAY provide a visible caption in one or both languages.

### Contact Enquiry

Represents the visitor-entered information used to compose a contact message.

The website MUST NOT persist a Contact Enquiry in its own application database.

## 3.3 Relationships

```text
Club 1 ---- 1..* Coach
Club 1 ---- 1..* Class
Class 1 ---- 1..* Schedule Entry
Site 1 ---- 0..* FAQ Entry
Site 1 ---- 0..* Gallery Image
```

The diagram above is informative. The prose definitions are authoritative.

## 3.4 Page Model

The logical page set is:

- Home
- About
- Classes and Schedule
- Gallery
- FAQ
- Contact
- Privacy

Each logical page MUST have an English representation and a Japanese representation.

The exact URL structure is an implementation choice unless constrained by another requirement.

## 3.5 Primary Behavioral Flows

### FLW-001 — Language Switch

```text
Visitor
  ↓
Current Page
  ↓
Select another language
  ↓
Equivalent page in selected language
```

The language switch MUST navigate to the language equivalent of the current logical page when one exists.

### FLW-002 — Contact Handoff

```text
Visitor
  ↓
Contact Form
  ↓
Validate required fields
  ↓
Compose message in current page language
  ↓
Open external communication channel
```

The website MUST NOT persist the enquiry as part of this flow.

### FLW-003 — Gallery Image View

```text
Visitor
  ↓
Gallery
  ↓
Select image
  ↓
Open enlarged view
  ↓
Close enlarged view
  ↓
Return to gallery context
```

The visitor MUST be able to dismiss the enlarged view without navigating away from the Gallery page.

---

# 4. Requirements

## 4.1 Functional Requirements

### FUN-001 — Required Pages

The site MUST provide the following logical pages:

- Home;
- About;
- Classes and Schedule;
- Gallery;
- FAQ;
- Contact;
- Privacy.

### FUN-002 — Navigation

Every primary page MUST provide navigation to the other primary site areas.

Navigation MAY differ visually between desktop and mobile layouts.

### FUN-003 — Home Page

The Home page MUST provide:

- the club identity;
- a concise description of the club;
- a clear path to Classes and Schedule;
- a clear path to Contact.

### FUN-004 — About Page

The About page MUST provide:

- a description of the club;
- information about at least one Coach;
- a description of the club's training approach.

### FUN-005 — Classes and Schedule

The Classes and Schedule page MUST list every currently offered Class.

For each Class, the page MUST show:

- class name;
- class description;
- recurring training day(s);
- start and end time(s).

### FUN-006 — FAQ

The FAQ page MUST present the current FAQ Entries.

Each visible question MUST be paired with its corresponding answer.

### FUN-007 — Contact Form

The Contact page MUST provide a form that collects:

- name;
- contact detail;
- optional class preference;
- optional message.

When a visitor chooses a class preference, the selectable class values MUST be derived from the Classes currently offered by the site.

The class-preference control MAY additionally offer a language-appropriate value meaning "No preference" or "Not sure."

The exact input used for contact detail MAY be phone, email, or another clearly defined direct-contact identifier.

### FUN-008 — Contact Handoff

Submitting a valid Contact form MUST initiate a Contact Handoff to the configured external communication mechanism.

The site MUST NOT require its own backend database to store the enquiry.

### FUN-009 — Privacy Page

The Privacy page MUST explain the contact-flow behavior in terms understandable to a visitor.

It MUST state whether the website stores contact-form submissions.

## 4.2 Language Requirements

### LANG-001 — Complete Language Coverage

Every required logical page MUST be available in English and Japanese.

### LANG-002 — Language Switch

Every required page MUST provide a visible mechanism to switch between English and Japanese.

### LANG-003 — Equivalent Destination

For every required logical page, switching language MUST navigate to the same logical page in the selected language.

Example — informative:

- English Gallery → Japanese Gallery
- Japanese FAQ → English FAQ

This requirement applies to the required page set defined by this specification. Future optional content that exists in only one language would require its own explicitly defined fallback behavior.

### LANG-004 — Language-Specific UI

Navigation labels, form labels, buttons, validation messages, gallery controls, and other visitor-facing interface text MUST use the current page language.

### LANG-005 — Contact Message Language

A Contact Handoff MUST compose its default message using the language of the Contact page currently being used.

### LANG-006 — Japanese Text Support

The implementation MUST support Japanese characters throughout visitor-facing content and contact-message composition.

## 4.3 User Experience and Interaction Requirements

### UX-001 — Primary Tasks

A visitor SHOULD be able to reach:

- class schedule information;
- FAQ information;
- contact functionality;

directly from primary navigation or a prominent equivalent path.

### UX-002 — Mobile Navigation

The site MUST remain navigable on a narrow/mobile viewport.

A mobile-specific navigation pattern MAY differ from the desktop pattern.

### UX-003 — Gallery Browsing

The Gallery MUST present Gallery Images in a browseable visual collection.

Selecting an image MUST open an enlarged view.

### UX-004 — Gallery Close Behavior

The enlarged Gallery view MUST provide an explicit close control.

On environments supporting keyboard input, pressing `Escape` SHOULD close the enlarged Gallery view.

### UX-005 — Gallery Context

Closing an enlarged Gallery image MUST return the visitor to the Gallery without losing the logical page context.

### UX-006 — User Feedback

A user-triggered action that fails MUST provide visible feedback when the failure is detectable by the website.

The interface SHOULD NOT fail silently.

### UX-007 — Contact Validation

The Contact form MUST identify missing required information before initiating the Contact Handoff.

Validation messages MUST use the current page language.

## 4.4 Accessibility Requirements

### ACC-001 — Meaningful Images

Every meaningful Gallery Image MUST have language-appropriate alternative text.

### ACC-002 — Decorative Images

Purely decorative images SHOULD use an empty text alternative or an equivalent mechanism that prevents redundant screen-reader output.

### ACC-003 — Keyboard Access

On user agents and devices that provide keyboard input, all interactive controls MUST be operable using a keyboard.

### ACC-004 — Heading Structure

Page headings MUST follow a logical document hierarchy and MUST NOT rely on visual styling alone to communicate heading structure.

### ACC-005 — Form Labels

Every user-input field MUST have an accessible label.

### ACC-006 — Language Declaration

Each page MUST identify its current human language through the implementation mechanism appropriate to the delivery format.

## 4.5 Reliability and Graceful Degradation

### REL-001 — Core Content Availability

Core informational content MUST remain readable if optional client-side enhancements fail.

### REL-002 — Gallery Failure

Failure of the enlarged Gallery interaction MUST NOT make the underlying Gallery images unavailable.

### REL-003 — Contact Failure

If the external Contact Handoff cannot be initiated, the visitor MUST receive visible feedback rather than an apparently successful submission.

## 4.6 Privacy Requirements

### PRIV-001 — Contact Data Persistence

The website MUST NOT persist Contact Enquiry contents in its own application database.

### PRIV-002 — Unnecessary Collection

The Contact form SHOULD collect only information reasonably necessary to respond to the enquiry.

## 4.7 Security Requirements

### SEC-001 — Secrets

Secrets, private credentials, or API keys MUST NOT be embedded in visitor-delivered source code.

### SEC-002 — User Content

Visitor-provided Contact Enquiry values MUST NOT be interpreted as executable markup or code.

## 4.8 Performance Requirements

### PERF-001 — Page Usability

The site SHOULD remain usable while large media assets are loading.

### PERF-002 — Gallery Loading

The implementation SHOULD avoid requiring all full-resolution Gallery images to be downloaded before the Gallery becomes usable.

---

# 5. Interfaces and External Contracts

## 5.1 Contact Communication Interface

The site interacts with one external communication mechanism for Contact Handoff.

The mechanism MAY be:

- email-client handoff;
- messaging application deep link;
- another direct communication mechanism.

The specific provider is an implementation/configuration choice unless a project adopting this specification explicitly constrains it.

### Purpose

The interface exists only to transfer a visitor's contact message to a channel monitored by the club.

### Data Authority

The website is authoritative only for the message being composed during the current browser interaction.

After handoff, the external communication mechanism is responsible for actual message transmission and delivery.

### Supported Operation

The integration MAY initiate a message composition/handoff.

### Prohibited Operations

The website MUST NOT:

- silently subscribe the visitor to marketing communication;
- store the Contact Enquiry in an application database;
- claim that the message was delivered when only the handoff was initiated.

### Failure Behavior

If the handoff cannot be initiated, the website MUST provide visible failure feedback.

---

# 6. Constraints and Non-Goals

## 6.1 Implementation Constraints

The implementation MUST support English and Japanese text.

The implementation MUST provide the required public pages and interactions.

No specific framework, build system, database, or hosting provider is required.

## 6.2 Non-Goals

The following are explicitly outside the scope of this specification:

- user registration;
- member login;
- membership payments;
- online class reservation;
- attendance tracking;
- belt or grading administration;
- tournament registration;
- live chat;
- e-commerce;
- a general-purpose CMS;
- automated spam, abuse, or rate-limiting controls for the contact handoff;
- SEO/GEO-specific behavior;
- search-engine optimization requirements;
- AI-crawler optimization requirements.

A conforming implementation MAY add unrelated capabilities only if they do not conflict with this specification, but such capabilities are not required for conformance.

---

# 7. Verification and Acceptance

The verification examples below define expected conformance evidence.

Where `Given / When / Then` wording is used, it is a BDD/Gherkin-inspired readable acceptance format. It is not required to be executable Gherkin.

## 7.1 Required Page Verification

**Method:** Inspection + Demonstration

Verify that all required logical pages exist in both English and Japanese.

Expected:

- Home — English and Japanese
- About — English and Japanese
- Classes and Schedule — English and Japanese
- Gallery — English and Japanese
- FAQ — English and Japanese
- Contact — English and Japanese
- Privacy — English and Japanese

## 7.2 Language Switch Acceptance

**Method:** Test

Given:
- the visitor is on any required English page;

When:
- the visitor selects Japanese;

Then:
- the corresponding Japanese logical page is opened.

And the inverse MUST work from Japanese to English.

## 7.3 Schedule Acceptance

**Method:** Inspection

For each Class:

- at least one Schedule Entry is visible;
- every Schedule Entry shows day of week;
- every Schedule Entry shows start time;
- every Schedule Entry shows end time.

## 7.4 Gallery Acceptance

**Method:** Demonstration + Test

Given:
- the visitor is viewing the Gallery;

When:
- the visitor selects a Gallery Image;

Then:
- an enlarged representation is shown.

When:
- the visitor activates the close control;

Then:
- the enlarged view closes;
- the Gallery remains the active logical page.

## 7.5 Contact Handoff Acceptance

**Method:** Test

Given:
- the visitor is on the English Contact page;
- all required Contact fields are valid;

When:
- the visitor submits the form;

Then:
- the external Contact Handoff is initiated;
- the composed default message is in English;
- the website does not persist the Contact Enquiry in its own application database.

Repeat in Japanese.

The composed default message MUST be in Japanese.

## 7.6 Class Preference Acceptance

**Method:** Inspection + Test

Given:
- one or more Classes are currently offered by the site;

When:
- the visitor opens the class-preference control on the Contact page;

Then:
- each selectable class corresponds to a currently offered Class;
- the control MAY also contain a language-appropriate "No preference" or "Not sure" choice.

## 7.7 Validation Acceptance

**Method:** Test

Given:
- a required Contact field is empty;

When:
- the visitor attempts to submit;

Then:
- the Contact Handoff MUST NOT begin;
- the missing information MUST be identified;
- the validation message MUST use the current page language.

## 7.8 Accessibility Verification

**Method:** Inspection + Demonstration

Verify:

- meaningful Gallery images have English alt text on English pages;
- meaningful Gallery images have Japanese alt text on Japanese pages;
- Contact inputs have accessible labels;
- primary interactive controls are keyboard operable on keyboard-capable user agents;
- page headings follow a logical document hierarchy;
- the current page language is declared.

---

# 8. Notes and Rationale

This chapter is informative and does not define requirements.

## 8.1 Why English and Japanese Are Separate Content Experiences

The example uses English and Japanese to demonstrate that multilingual behavior is part of the product contract rather than merely a visual text substitution.

An implementation is free to organize the content differently internally as long as both language experiences remain complete and equivalent in meaning.

## 8.2 Design Portability

This example demonstrates the SPEC.md principle:

> Source code is one implementation of an idea.  
> SPEC.md is the transferable expression of the idea itself.

The club website could be recreated with different frameworks, languages, hosting providers, component architectures, or build systems while still conforming to the same specification.

## 8.3 Why the Exact Technology Is Not Specified

This specification is intended to support clean-room reimplementation.

One implementation might use:

- a static-site generator;
- a server-rendered framework;
- plain HTML;
- a JavaScript framework.

Those choices do not define the product.

## 8.4 Why Contact Data Is Not Stored

The Contact flow demonstrates a behavioral requirement without dictating an implementation stack.

Avoiding application-side persistence keeps the example small while still demonstrating:

- validation;
- an external interface;
- failure handling;
- privacy constraints;
- language-specific behavior.

## 8.5 Why SEO/GEO Is Not Included

SEO, GEO, structured-data, crawler, sitemap, and machine-discoverability requirements are intentionally omitted from this introductory example.

They may be demonstrated later through optional SPEC.md extensions.

## 8.6 Why Spam and Rate Limiting Are Not Required

This introductory example uses a client-side Contact Handoff rather than a contact-submission backend.

Server-side rate limiting, CAPTCHA, abuse detection, and similar controls are therefore intentionally outside the teaching scope of this example. A production specification that introduces a server-side contact endpoint should reconsider those controls as explicit security, reliability, or operational requirements.

## 8.7 Why the Gallery Is Included

The Gallery demonstrates that SPEC.md may specify behaviorally significant UI/UX without prescribing the visual design.

The specification requires:

- browseable images;
- enlarged view;
- close behavior;
- accessibility behavior.

It does not require:

- a specific CSS framework;
- a particular animation;
- a specific layout;
- a fixed breakpoint.

---

# Informative Implementation Guidance

This section is informative.

A possible implementation sequence is:

1. Create the required English and Japanese page structure.
2. Implement common navigation and language switching.
3. Add club, coach, class, and schedule content.
4. Implement Gallery browsing and enlarged-image interaction.
5. Implement FAQ and Privacy pages.
6. Implement Contact form validation, class-preference binding, and external handoff.
7. Complete accessibility checks.
8. Run the acceptance tests in both languages.

A conforming implementation MAY use a different implementation order.

This introductory example intentionally does not require `DESIGN.md`, `TASKS.md`, or `TRACE.md`. Those are optional implementation/workflow artifacts and are unnecessary to understand or implement this small design.
