# Autónomo al día

**Real-time taxes for Spain's self-employed.** Upload your invoices and the app reads them, applies Spanish tax law and keeps your quarterly returns ready to file. Every day you know how much of your money is yours and how much belongs to the tax office.

> This repository is a public overview. The source code is private.

**Status:** in active development. Version 1 (tax year 2025) works end to end; next come the 2026 tax year and the annual returns.

## What it does

- **Reads every tax document:** invoices received and issued, receipts, e-invoices, scans and phone photos.
- **Assesses each one:** what is deductible for VAT and income tax, in which quarter, and why, in plain Spanish.
- **Keeps the books:** the legally required VAT and income-tax registers, in the tax office's official format.
- **Prepares the quarterly returns:** modelos 303, 130, 111, 115 and 349, as official files ready to file.
- **Shows a live dashboard:** income, expenses, taxes so far and how much to set aside.
- **Asks only what it can't know:** short, plain questions, never accounting jargon.

## How it works

1. **Reads:** AI extracts the data from any format; e-invoices are read directly.
2. **Checks:** totals, tax IDs, VAT rates and EU VAT numbers are validated.
3. **Assesses:** an innovative AI model setup and a tax engine work out each document's treatment, books and returns.

## AI expertise behind it

- **Multimodal extraction with structured outputs:** PDFs, scans and photos read into a strict JSON schema, with large schemas split into parallel calls.
- **Provider-agnostic model layer:** AI providers and models switched in configuration, with no rebuild or restart.
- **Novel assessment architecture:** an original arrangement of AI models that judges each document's tax meaning. Design kept private.
- **Hybrid AI and deterministic design:** AI only where a real semantic judgment is needed; OCR, PDF text and XML parsing do the rest, and the law runs in code, never in a model.
- **Cost engineering:** prompt caching, AI results cached by their inputs so an edit never repeats a call, per-user usage caps and rate limits.
- **Evaluation:** labelled datasets measure AI accuracy, and a regression corpus pins every tax figure so any change that moves one is caught.
- **Corrections with an audit trail:** every fact records its source; users can correct any value, and each correction is audited and recalculated at once.
- **Explainability and provenance:** every result carries the rules version and inputs behind it, plus a plain-language reason.
- **Reliable AI pipelines:** background jobs with retries and progress, replayable stages with the same result every time.
- **Responsible AI and privacy:** EU data hosting, minimum data sent to AI providers, no training on customer documents.
- **AI-native engineering:** built with AI coding agents run as a coordinated team (parallel sessions, sub-agents, isolated worktrees) under a written operating manual and automated checks.
- **AI-assisted legal research:** agents research Spanish tax law against a strict hierarchy of official sources, and tests check that the code matches the research.

## A tax engine built like a tax adviser

- Every rule traces to an official source for its tax year.
- Rules are versioned by tax year, so any past year can be recalculated.
- Where the law offers a choice, the app takes the one best for the user; where it is silent, the safe treatment that survives an inspection.
- Filed quarters are locked; changes go through a correction flow.

## By the numbers

| 700+ commits | 2,200+ automated tests | 400+ legal research findings | 1,000+ official sources |
|:---:|:---:|:---:|:---:|
| since October 2026 | rules, pipeline and API | each with its official sources | laws, rulings and forms |

## Stack

Next.js (TypeScript, Tailwind, shadcn/ui) · ASP.NET Core (C#, .NET 10) · EF Core · PostgreSQL on Supabase (EU) · LLM APIs · Tesseract OCR · versioned OpenAPI contract, ready for mobile apps
