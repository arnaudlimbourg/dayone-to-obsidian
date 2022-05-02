---
A more featureful version written by Edoardo can be found at https://github.com/edoardob90/dayone-to-obsidian
---

# dayone-to-obsidian
Convert a [Day One](https://dayoneapp.com/) JSON export into individual entries for [Obsidian](https://obsidian.md). Each entry is created as a separate page.

Heavily based off the work from [QuantumGardener](https://github.com/quantumgardener/dayone-to-obsidian) with a few improvements.

## Installation
- Clone the repository
- Run ``poetry install``
- Run ``poetry run python import.py path/to/folder``

## Optional requirements
* Obsidian [Icons Plugin](https://github.com/visini/obsidian-icons-plugin) to display calendar marker at start of page heading. Enable by passing:
* If you use the [Icons Plugin](https://github.com/visini/obsidian-icons-plugin) to display calendar marker at start of page heading pass ``--icons``
  * ``poetry run python import.py --icons true path/to/folder``

## Day One version
This script works with version 7.1 of Day One. It has not been tested with any other versions.

## Setup

**This script deletes folders if run a second time**
**You are responsible for ensuring against data loss**
**This script renames files**

1. Export your journal from [Day One in JSON format](https://help.dayoneapp.com/en/articles/440668-exporting-entries) 
2. Expand that zip file
3. Run the script as shown above
4. Check results in Obsidian by opening the folder as a vault
5. If happy, move each *journal name*, *photos*, and *pdfs* folders to another vault.

## Features
* Processes all entries, including any blank ones you may have.
* Entries are organised by year/month/day.
* If multiple entries on a day, each additional entry is treated seperately
* Adds metadata for whatever exists at bottom of file
   * minimum date and timezone
   * Location as text, linked to a page
   * Tags and starred flag as tag
   * Weather and user activity
* Every entry has the date inserted in the text for easier reading (with a calendar icon to help you quickly distinguish from other entries in your vault)
* If location is specified, it is given under the date, linked to Google Search
* Tags can be prefixed (default = journal/) to show as subtags in Obsidian separate from other note tags. User ``--tags-prefix`` option
* Run with --help for options
