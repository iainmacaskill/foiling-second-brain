---
title: The Generic Foiling Podcast — a second brain
description: An AI-maintained knowledge base built from 147 episodes of a foiling podcast — a working demo of the "second brain" pattern.
---

## Where to start

- **[[Entities/The Generic Foiling Podcast|The show itself]]** — format, hosts, span.
- A handful of episodes are fully transcript-deep (not just summarised from a blurb) — start with **[[Summaries/S - Ep 001 An Introduction|the very first episode]]**.

<button id="open-graph-btn" class="open-graph-button" aria-label="Open the graph" type="button" onclick="document.querySelector('.global-graph-icon')?.click()">
  <svg class="open-graph-button-icon" aria-hidden="true" version="1.1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 55 55" fill="currentColor">
    <path d="M49,0c-3.309,0-6,2.691-6,6c0,1.035,0.263,2.009,0.726,2.86l-9.829,9.829C32.542,17.634,30.846,17,29,17
    s-3.542,0.634-4.898,1.688l-7.669-7.669C16.785,10.424,17,9.74,17,9c0-2.206-1.794-4-4-4S9,6.794,9,9s1.794,4,4,4
    c0.74,0,1.424-0.215,2.019-0.567l7.669,7.669C21.634,21.458,21,23.154,21,25s0.634,3.542,1.688,4.897L10.024,42.562
    C8.958,41.595,7.549,41,6,41c-3.309,0-6,2.691-6,6s2.691,6,6,6s6-2.691,6-6c0-1.035-0.263-2.009-0.726-2.86l12.829-12.829
    c1.106,0.86,2.44,1.436,3.898,1.619v10.16c-2.833,0.478-5,2.942-5,5.91c0,3.309,2.691,6,6,6s6-2.691,6-6c0-2.967-2.167-5.431-5-5.91
    v-10.16c1.458-0.183,2.792-0.759,3.898-1.619l7.669,7.669C41.215,39.576,41,40.26,41,41c0,2.206,1.794,4,4,4s4-1.794,4-4
    s-1.794-4-4-4c-0.74,0-1.424,0.215-2.019,0.567l-7.669-7.669C36.366,28.542,37,26.846,37,25s-0.634-3.542-1.688-4.897l9.665-9.665
    C46.042,11.405,47.451,12,49,12c3.309,0,6-2.691,6-6S52.309,0,49,0z M11,9c0-1.103,0.897-2,2-2s2,0.897,2,2s-0.897,2-2,2
    S11,10.103,11,9z M6,51c-2.206,0-4-1.794-4-4s1.794-4,4-4s4,1.794,4,4S8.206,51,6,51z M33,49c0,2.206-1.794,4-4,4s-4-1.794-4-4
    s1.794-4,4-4S33,46.794,33,49z M29,31c-3.309,0-6-2.691-6-6s2.691-6,6-6s6,2.691,6,6S32.309,31,29,31z M47,41c0,1.103-0.897,2-2,2
    s-2-0.897-2-2s0.897-2,2-2S47,39.897,47,41z M49,10c-2.206,0-4-1.794-4-4s1.794-4,4-4s4,1.794,4,4S51.206,10,49,10z"/>
  </svg>
  <span>Open the Graph</span>
</button>
<p class="open-graph-hint">Opens the full graph — zoom in (scroll/pinch) once it loads, it starts zoomed out.</p>

<style>
.open-graph-button {
  position: relative;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  margin-top: 0.5rem;
  padding: 0.9rem 1.8rem;
  border: 1px solid var(--lightgray);
  border-radius: 8px;
  background: var(--light);
  color: var(--dark);
  font-family: var(--headerFont);
  font-size: 1rem;
  cursor: pointer;
}
.open-graph-button:hover { border-color: var(--gray); }
.open-graph-button-icon {
  position: absolute;
  inset: 0;
  margin: auto;
  width: 65%;
  height: 65%;
  opacity: 0.13;
  color: var(--secondary);
  pointer-events: none;
}
.open-graph-button span { position: relative; z-index: 1; font-weight: 600; }
.open-graph-hint { margin-top: -0.5rem; font-size: 0.85rem; color: var(--gray); }
</style>

## What this is

This site is a knowledge base built entirely by AI from **[The Generic Foiling Podcast](https://open.spotify.com/show/7wBQo7HwIbwXE8NncFk25z)** — 147 episodes (2022–2026) hosted by Liam and Freddie, covering wing foiling, downwind, prone and kite foiling.

It's a demonstration of the **"second brain" pattern**: an AI librarian that reads raw source material, files it, cross-links it, and keeps it organised — following the approach popularised by Andrej Karpathy (Obsidian as the interface, an LLM as the librarian, a markdown wiki as the growing knowledge base).

I built it as a portfolio piece, applied to public podcast content rather than private notes, so I can show the method openly.

## How it was built

1. **Catalogue** — pulled all 147 episodes from the podcast's RSS feed (title, date, duration, description).
2. **Graph from metadata** — an AI agent read every title and description and built a cross-linked knowledge graph: every guest, brand, gear-maker and location became a page, and every discipline and technique (wing foiling, downwind, pumping, parawing…) became a concept page linking back to the episodes that discuss it.
3. **Transcribe** — episode audio, downloaded from the RSS feed, transcribed locally with [faster-whisper](https://github.com/SYSTRAN/faster-whisper) at roughly 10× real-time.
4. **Deep ingest** — for transcribed episodes, an AI agent reads the full conversation and writes a proper summary — what was actually said, by whom, with the gear and opinions attributed — then updates every person/brand/concept page the episode touches.
5. **Publish** — the resulting wiki, rendered as this site with [Quartz](https://quartz.jzhao.xyz/).

Nothing here was written by a human. The judgement of *what's worth keeping* is mine; the filing, linking and writing is the AI's.

## A note on accuracy

Episode transcripts are auto-generated and unreviewed. Where the audio was garbled, the summary pages say so rather than guessing. This is a knowledge base, not a verbatim transcript archive — content is summarised and attributed, with credit to [The Generic Foiling Podcast](https://open.spotify.com/show/7wBQo7HwIbwXE8NncFk25z) throughout.

*— [Iain Macaskill](https://www.linkedin.com/in/iainmacaskill/)*
