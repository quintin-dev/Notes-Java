GitHub Copilot Context File for Dendron Note-Taking

## Overview

This file instructs GitHub Copilot Edits to convert raw sticky note captures from study sessions into well-structured, industry-relevant Dendron notes. The focus is on the following sections:

-   **Definitions**
-   **Syntax**
-   **Notes to Make (Dendron/Notion)**
-   **Key Points**

The goal is to integrate practical content directly into existing notes (using backlinks) and flag new topics for note creation when needed.

---

## General Guidelines

-   **Transform Raw Content:** Process the input sticky note and convert it into a clean, structured Markdown note.
-   **Integrate, Don’t Duplicate:** When a term, definition, or syntax example already exists in a Dendron note, insert a backlink in the format `[[Note Title]]` rather than duplicating the content.
-   **Prioritize Practicality:** Include only practical, industry-standard information. Exclude overly theoretical or non-essential content.
-   **Maintain Hierarchy:** Ensure the resulting note fits seamlessly into your Dendron hierarchy with clear sectioning and navigation.

---

## Section Instructions

### 1. Definitions

-   **Purpose:** Capture key terms and definitions.
-   **Handling:**
    -   If a definition exists in an appropriate Dendron note, insert a backlink (e.g., `[[Existing Definition Note]]`).
    -   Otherwise, include the definition inline.
-   **Note:** Do not create separate notes solely for definitions unless absolutely necessary.

### 2. Syntax

-   **Purpose:** Record code snippets or syntax examples relevant to the topic.
-   **Handling:**
    -   Format code examples using Markdown code blocks with appropriate language identifiers (e.g., `java, `js).
    -   Integrate these directly into the relevant note or include inline if no dedicated syntax note exists.

### 3. Notes to Make (Dendron/Notion)

-   **Purpose:** List topics that require further note development for later reference.
-   **Handling:**
    -   Only include items that are practical and industry-relevant.
    -   For existing topics, insert backlinks (e.g., `[[Topic Note]]`).
    -   For new topics, flag them for creation within the Dendron hierarchy.

### 4. Key Points

-   **Purpose:** Summarize critical insights and practical tips.
-   **Handling:**
    -   Format each key point as a blockquote to apply custom CSS styling.
    -   Keep statements concise and highlighted.
-   **CSS Integration:** The following CSS be pasted at the beginning all new note files created by Copilot Edits:

<!--#region styles-->
<style>
    * {
        font-size: 18px;
    }
    h1 {
        color: red;
        font-weight: bold;
        border-bottom: 2px solid red;
        font-family: 'Algerian';
        text-align: center;
        font-size: 2em;
    }
    h2 {
        color: crimson;
        font-weight: bold;
        font-family: 'Algerian';
        border-bottom: 2px solid crimson;
        font-size: 1.5em;
    }
    h3 {
        color: rgb(255, 0, 127);
        font-weight: bold;
        text-decoration: underline;
        font-size: 1.2em;
        font-size: 1.2em;
    }
    h4 {
        color: rgb(0, 255, 255);
        font-weight: bold;
        text-decoration: underline;
        font-size: 1em;
    }
    h5 {
        color: darkblue;
        font-weight: bold;
        font-style: italic;
        font-size: 0.9em;
    }
    code {
        font-family: 'Cascadia Code';
        border: 1px solid #282a36;
        border-radius: 4px;
        padding: 1px 4px;
    }
    pre {
        font-family: 'Cascadia Code';
        border: 1px solid #282a36;
        border-radius: 4px;
        padding: 1px 4px;
    }
    p {
        font-style: 'Cascadia Code';
        color: white;
    }
    li {
        margin-bottom: 10px;
        font-style: italic;
        font-weight: bold;
        color: orange;
    }
    ul {
        margin-bottom: 10px;
        font-style: italic;
        font-weight: bold;
        color: orange;
    }
    b {
        font-weight: bold;
        color: rgb(255, 0, 0);
    }
    u {
        text-decoration: underline;
        font-weight: bold;
        font-style: italic;
    }
    a {
        color: #98c379;
        text-decoration: none;
    }
    a:hover {
        text-decoration: underline;
    }
    i {
        font-style: italic;
        color: yellow;
    }
    blockquote {
        background: rgba(255, 0, 127, 0.1); /* Light pink background */
        border-left: 5px solid rgb(255, 0, 127); /* Bold pink left border */
        padding: 10px 15px;
        margin: 10px 0;
        font-style: italic;
        font-weight: bold;
        color: white;
    }
</style>
<!--#endregion-->

---

## Backlinks and New File Creation

-   **Backlinks:** For items that match existing topics, insert backlinks using `[[Note Title]]`.
-   **New Topics:** For topics not yet covered, flag these for new note creation and ensure they’re placed correctly within the Dendron hierarchy.

This file is your context reference for transforming raw sticky note inputs into structured, navigable Dendron notes. Adjust as needed to further tailor it to your workflow.
