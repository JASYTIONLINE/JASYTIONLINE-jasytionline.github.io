---
title: CMPA 3301 – Module 4 Reading Notes & Support Docs
description: Consolidated Cliff Notes, SLOs, and supporting concepts for Module 4 (CSS focus, HTML as review)
date: 2025-09-05
tags:
  - cmpa3301
  - module4
  - readings
  - cliff-notes
  - support
classification: private
retention: permanent
integrityCheck: true
role: support-doc
function: d3-Execution
id: reading-notes-support-m4-cmpa-3301
shortcode: rn-master
aliases:
  - cliff-notes-support-m4
  - reading-summary-support-m4
---

# CMPA 3301 – Module 4 Reading Notes & Support Docs

## Student Learning Outcomes (SLOs)

After completing Module 4 readings, students will be able to:  
- <a id="SLO1"></a>**SLO1:** Differentiate between **structure (HTML)** and **presentation (CSS)**.  
- <a id="SLO2"></a>**SLO2:** Apply the **separation of concerns (SoC)** principle when designing web pages.  
- <a id="SLO3"></a>**SLO3:** Identify and use **fundamental CSS properties** (`color`, `background-color`, `font-family`, `font-size`, `margin`, `padding`).  
- <a id="SLO4"></a>**SLO4:** Demonstrate how a **stylesheet functions as a project plan** for website presentation.  
- <a id="SLO5"></a>**SLO5:** Relate **HTML scope (structure)** and **CSS planning (presentation)** when building simple projects.  

---

### SLO Summary in Plain Language

- **SLO1:** The difference between HTML and CSS is that **HTML is the skeleton** — it defines the content and structure of the page — while **CSS is the wardrobe** — it controls how that content looks (colors, fonts, spacing, layout).  
- **SLO2:** Separation of Concerns (SoC) means **keeping HTML and CSS in their own lanes**: HTML handles structure, CSS handles presentation. Mixing them makes projects messy; separating them makes code clean and scalable.  
- **SLO3:** CSS has **core properties** you must know: color and background-color for visuals, font-family and font-size for text style, and margin/padding for spacing. These six properties form the foundation of all styling.  
- **SLO4:** A stylesheet acts like a **project plan for design** — it’s a single source of truth that browsers follow to keep pages consistent. Update the stylesheet, and the whole website updates.  
- **SLO5:** HTML and CSS together form a **framework**: HTML provides the scope and content, CSS provides the plan and style. Keeping both in sync ensures pages are clear, usable, and adaptable.  

---

## Jump Links
- [CSS is the Wardrobe of the Web](#css-is-the-wardrobe-of-the-web-week-04-reading)  
- [Stylesheet as a Project Plan](#stylesheet-as-a-project-plan)  
- [Separation of Concerns (SoC)](#separation-of-concerns-soc)  
- [HTML & CSS as Framework](#html--css-as-framework)  
- [Personal Notes](#personal-notes)  
- [Footnote: HTML Skeleton Review](#footnote-html-skeleton-review)  

---

## CSS is the Wardrobe of the Web (Week 04 Reading)

**Core Idea ([SLO1](#SLO1), [SLO3](#SLO3), [SLO4](#SLO4)):**  
CSS provides the styling and presentation — the “clothing” that makes the skeleton (HTML) readable and attractive.  

**Anatomy of a CSS Rule ([SLO3](#SLO3)):**  
- `color` = text color.  
- `background-color` = background fill.  
- `font-family` = typeface.  
- `font-size` = text size.  
- `margin` = space outside an element’s border.  
- `padding` = space inside an element’s border.  

**Impact ([SLO4](#SLO4)):**  
- CSS turns plain HTML into a styled, organized, usable site.  
- By editing one stylesheet, you can change the look of an entire website instantly.  

[🔝 Back to Jump Links](#jump-links)

---

## Stylesheet as a Project Plan

**Concept ([SLO4](#SLO4))**  
A **stylesheet** is like a set of instructions for how a webpage should look.  
It’s a “map” that browsers follow to ensure consistency across content.  

**Application ([SLO4](#SLO4))**  
- One external CSS file can control hundreds of pages.  
- Updating the stylesheet = updating the “plan” for presentation without changing the HTML structure.  
- This mirrors the course analogy: **Project Plan = “clear map for smart decision-making.”** (Kogon & Blakemore, 2024, Ch. 4)  

[🔝 Back to Jump Links](#jump-links)

---

## Separation of Concerns (SoC)

**Concept ([SLO2](#SLO2))**  
The principle of **SoC**:  
- **HTML** defines content and structure.  
- **CSS** defines presentation and style.  
- Keeping them separate makes code cleaner, easier to maintain, and less error-prone.  

**Stylesheet Placement and SoC Alignment ([SLO2](#SLO2)):**  

1. **Inline styles (🚫 worst):**  
   ```html
   <p style="color: red;">Hello</p>
   ```  
   - HTML and CSS completely mixed.  
   - Not reusable; violates SoC.  

2. **Internal stylesheets (⚠️ partial SoC):**  
   ```html
   <style>
     p { color: red; }
   </style>
   ```  
   - CSS lives inside the HTML file.  
   - Better than inline, but not scalable for large projects.  

3. **External stylesheets (✅ best practice, full SoC):**  
   ```html
   <link rel="stylesheet" href="styles.css">
   ```  
   - CSS in its own `.css` file.  
   - HTML remains pure content; CSS remains pure style.  
   - Supports consistency, scalability, and professional maintainability.  

**Summary:**  
- Inline → 🚫 violates SoC.  
- Internal → ⚠️ partial SoC (okay for small tests).  
- External → ✅ full SoC, industry standard.  

[🔝 Back to Jump Links](#jump-links)

---

## HTML & CSS as Framework

**Concept ([SLO1](#SLO1), [SLO4](#SLO4), [SLO5](#SLO5))**  
- **HTML** = the skeleton → defines structure and meaning.  
- **CSS** = the wardrobe → defines presentation and identity.  
- Together they form a complete framework for web development.  

**Application ([SLO1](#SLO1), [SLO5](#SLO5)):**  
- HTML gives the page content, headings, and organization.  
- CSS layers style and presentation on top.  
- The two combined = a complete webpage that is structured and styled.  

[🔝 Back to Jump Links](#jump-links)

---

## Personal Notes

- For **Discussion 04**, cite these key quotes:  
  - *“Just as a project plan is a ‘clear map for smart decision-making,’ a stylesheet provides a clear map for the browser.”* (Ch. 4)  
  - *“It’s much better to plan for the ‘what-ifs’ than to deal with the pain of ‘if only.’”* (Ch. 4)  

- For **Exercises**:  
  - **Find Your Palette** → use `color` and `background-color` to show usability.  
  - **Box Model** → practice with `margin` and `padding`.  

[🔝 Back to Jump Links](#jump-links)

---

## Footnote: HTML Skeleton Review

**Note ([SLO1](#SLO1), [SLO5](#SLO5)):**  
This week’s focus is **CSS (Wardrobe)**.  
**HTML (Skeleton)** is included only as review from Week 03.  

**Summary ([SLO1](#SLO1)):**  
- HTML defines structure/meaning.  
- Quote: *“The goal of scoping is to ‘Clarify a shared and measurable set of expectations.’”* (Ch. 3).  
- Essential tags: `<html>`, `<head>`, `<title>`, `<body>`, headings, lists, `<p>`, `<a>`.  

**Role ([SLO1](#SLO1), [SLO5](#SLO5)):**  
- Reminder of scope definition before styling is applied.  
- Balanced by CSS (Wardrobe) as the **Project Plan**, described as a *“clear map for smart decision-making.”* (Ch. 4)  

[🔝 Back to Jump Links](#jump-links)
