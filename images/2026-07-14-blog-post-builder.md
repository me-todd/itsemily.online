---
title: "The blog post builder"
subtitle: "Solving a problem and making life easier"
date: 2026-07-14
tags: [resources]
excerpt: "A tool I vibe-coded to help me focus on writing instead of wrestling with raw HTML."
---
## What & Why

I wanted to build a tool that would make it easier for me to cut through the noise of an HTML file and focus on the writing the content.

## How I built it

It's a vibe. Yeah, I vibe-coded it. Here's what I asked Claude to help me do.

> Develop an HTML based easy to use form that identifies the inputs: Title, Subtitle, Author, Paragraph Header, paragraph text, any quotes, images, tags that will generate an HTML file that is compatible with my blog pages.

It's also important to note that I have a project set up that I've added this to and have included instructions, so that I don't have to type out 'please provide your response in plain language' each time.

When I went to look at the instructions I thought I provided, they weren't there. 🤦🏻‍♀️ This was totally a case of adding instructions to my work instance and not my personal instance. So, I added them and copied the instructions here. Because I already in the process of writing this post,

> You are a great instructor with expert level coding skills. Provide your responses in plain language so that even business people understand what happened and why it happened. The what and why should be commented in the code. Any code outputs should prioritize reusable and efficient code followed by teachability. This means that a loop should be used instead of writing out code ten times. The commented code should break the teaching aspect down further, if needed, to explain the code. Here's an example of comments in the HTML file:

```text
<script>
  // =========================================================================
  // WHAT THIS SCRIPT DOES, IN PLAIN LANGUAGE
  // -------------------------------------------------------------------------
  // This page is a form. As you fill it in, we keep everything you type in
  // one place called "state" (below). Every time something changes, we
  // rebuild two things from that state:
  //   1. The editable blocks on the left (so you can reorder/edit them)
  //   2. The live preview on the right (so you can see the finished post)
  // When you click "Download HTML", we take that same state and turn it
  // into one finished, self-contained HTML file you can upload to the blog.
  //
  // WHY it's built this way: keeping one "source of truth" (state) and
  // re-drawing the screen from it, instead of editing the page by hand in
  // a dozen different places, means the preview can never drift out of
  // sync with what you actually typed — there's only one place data lives.
  // =========================================================================

  // "state" is the single source of truth for everything the person has
  // entered: their tags, and their content blocks (paragraphs, headers,
  // quotes, code, images). Title/subtitle/author/date live directly on
  // the input fields, so we just read those when we need them.
  const state = {
    tags: [],
    blocks: [],
  };
  let blockCounter = 0; // gives every block a unique ID so we can find/move/remove the right one

  // ---------------------------------------------------------------------
  // Small reusable helpers
  // ---------------------------------------------------------------------
  // WHY: building HTML elements with document.createElement + setAttribute
  // is repetitive. These two helpers let every part of the script build
  // elements in one line instead of 4-5 lines each — one piece of code
  // reused everywhere, instead of the same setup written out over and over.

  // Builds one HTML element. Example: el('button', {class: 'tag'}, [textNode('Hi')])
  // creates a <button class="tag">Hi</button> without us writing that by hand.
```

The outcome? An easy to use blog post builder that allows me to write and then add to my file manager to post to my site.

Check out the file here: blogpostbuilder.html that you can download, modify (or have your LLM modify) for you to use if you're also learning how to build your site.

Let me know if it's helpful or if you have questions (this will be a good learning experience for me too)!
