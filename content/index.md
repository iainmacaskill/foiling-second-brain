---
title: The Generic Foiling Podcast — a second brain
description: An AI-maintained knowledge base built from 147 episodes of a foiling podcast — a working demo of the "second brain" pattern.
---

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

## Where to start

- **[[Entities/The Generic Foiling Podcast|The show itself]]** — format, hosts, span.
- Browse the **graph** (top right) to see the shape of four years of foiling conversation — the guests, brands and disciplines, and how they connect.
- A handful of episodes are fully transcript-deep (not just summarised from a blurb) — start with **[[Summaries/S - Ep 001 An Introduction|the very first episode]]**.

## A note on accuracy

Episode transcripts are auto-generated and unreviewed. Where the audio was garbled, the summary pages say so rather than guessing. This is a knowledge base, not a verbatim transcript archive — content is summarised and attributed, with credit to [The Generic Foiling Podcast](https://open.spotify.com/show/7wBQo7HwIbwXE8NncFk25z) throughout.

*— [Iain Macaskill](https://www.linkedin.com/in/iainmacaskill/)*
