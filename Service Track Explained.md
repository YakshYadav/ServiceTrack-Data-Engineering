# ServiceTrack — Explained Simply

## What problem does this solve?

Imagine a mobile repair shop. Every time a customer walks in with a broken phone, laptop, or AC, the shop writes down: who the customer is, what device it is, what's wrong with it, which technician is fixing it, and when it's supposed to be ready.

This information gets written down every single day — but once the device is fixed and handed back, that job card just gets filed away and forgotten. Nobody ever looks back at hundreds of these cards to ask questions like:

- Which technician finishes jobs fastest, and who's often late?
- Which customers keep coming back with the same broken device?
- What percentage of repairs actually get delivered on time?
- Which phone or laptop brand breaks down the most?

The answers are all sitting there in the paperwork — there's just no system that reads through it and turns it into something useful.

**This project is that system.**

## What does it actually do?

It's a pipeline — a series of automated steps — that:

1. **Reads in the raw data.** Three files: a list of customers, a list of devices, and a list of every repair job (1,510 of them, covering 90 days).
2. **Cleans it up.** Real data is messy. Some job records are duplicated by mistake. Some are missing the technician's name. This step fixes those problems automatically instead of a person doing it by hand.
3. **Connects the dots.** It links each job to the right customer and the right device, and works out how many days each repair actually took.
4. **Builds the final answer sheets.** Three summary tables come out the other end:
   - One showing how well each device brand is meeting the 5-day repair promise.
   - One ranking technicians by speed, workload, and money earned.
   - One showing which devices and models break down the most.

## Why is it built this way?

This is modeled after how real companies (Microsoft, Databricks-style teams) build this kind of system, using a pattern called **Bronze → Silver → Gold**:

- **Bronze** = the data exactly as it came in, untouched — a safety copy.
- **Silver** = the cleaned-up, joined-together version.
- **Gold** = the final, ready-to-read summary tables that a manager could open and understand in seconds.

Think of it like cooking: Bronze is the raw groceries, Silver is the prepped and chopped ingredients, Gold is the finished dish on the plate.

## What would a shop manager actually get out of this?

- A clear view of which technicians need support or training.
- A way to catch repeat customers early — if someone keeps coming back with the same issue, that's usually a sign of a bad repair or a bad device, and it's worth fixing before it damages the shop's reputation.
- Real numbers on how many repairs are late, instead of a guess.
- Data to help decide which spare parts to stock up on.

## The technical side, in one sentence

It's built entirely on **Databricks** using **PySpark** (a tool for processing large amounts of data fast), **Delta Lake** (a reliable way to store data so nothing gets corrupted or lost), and **Auto Loader** (which automatically picks up new files as they arrive, instead of someone manually re-running things every day).

---


