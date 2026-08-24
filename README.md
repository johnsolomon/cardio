# Myotrace — Nuclear Cardiology Tool

A single-file browser tool for reading and reporting cardiac PET/CT myocardial perfusion studies:
a structured worksheet, a certified report generator, and a read-out narrative written in the order
the images are shown.

**Live:** https://johnsolomon.github.io/cardio/

## What it does

- **Worksheet** — patient, indications, stress protocol, 17-segment polar maps, gated function,
  absolute flow, coronary calcium, correlative studies.
- **Report** — generated from the worksheet by a certified generator held to 64 golden-master cases;
  every sentence is derived from an entered value.
- **Read-out narrative** — the study described the way it is presented at read-out: non-AC images
  first with stress and rest, then AC, defects called out by grade, region and the projection that
  shows them best.
- **Import (optional)** — paste an Epic note or a 4DM XML export to pre-fill the worksheet. Every
  imported value is marked and can be overwritten. Nothing has to be imported; the worksheet can be
  typed.

## Privacy

**This page is entirely self-contained and makes no network requests.** There is no server, no
analytics, and no external script, style or font — verified: zero external references, zero
`fetch`/`XMLHttpRequest` calls in the shipped file. Anything entered stays in the browser tab.

"Save" writes the current study to that browser's `localStorage` so it survives a reload. It is
readable by anyone with access to that browser profile. On a shared or public workstation, use
**Reset study** when finished, or don't use Save.

## Not a medical device

This tool assists a qualified reader in composing a report. It does not interpret images, and it
does not make or recommend a diagnosis. Every generated sentence is editable, and the reader is
responsible for the signed report.

## Running it

Download `index.html` and open it. That is the whole application — no build, no install, no network.

## Development

The source and test suite are not in this repository. The shipped file is generated from ~14 engines
by a build step, and is validated before each release by: a 64-case golden-master certification of
the report generator, ~20 unit suites, layout contracts at 9 viewports, a touch-behaviour suite, four
static and runtime audits, 250 synthetic studies, 32 clinical archetypes, and semantic, interaction
and import simulators.

Built by John Solomon, Nuclear Medicine resident.
