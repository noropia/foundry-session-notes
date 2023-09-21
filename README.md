# foundry-session-notes
Tools for tracking session notes within Foundry.

## Features

| Description | Status | Notes |
| ----------- | ------ | ----- |
| Add session notes via Macro | Not Started | |
| Add session notes via input form | Not Started | Input fields based on current context (i.e. NPC, quest entry, time passage). |
| Find session notes by category name | Not Started | |
| Find session notes by character name | Not Started | |
| Find session notes by scene name | Not Started | |
| Find session notes by quest name | Not Started | |
| Find session notes by (game) calendar day | Not Started | |
| Find session notes by (real world) calendar day | Not Started | |
| Generate new session notes in response to a specific event | Not Started | Examples: A quest NPC died, a player gained a magic item, a player died, x time passed. |
| Support for new types of session notes | Not Started | Represented as Simple Calendar categories. |
| View session notes in a Foundry journal entry | Not Started |
| Export session notes as a [Mermaid](https://mermaid.js.org/intro/#about-mermaid) [mindmap](https://mermaid.js.org/syntax/mindmap.html#mindmap), [pie chart](https://mermaid.js.org/syntax/pie.html), [flowchart](https://mermaid.js.org/syntax/flowchart.html), [timeline](https://mermaid.js.org/syntax/timeline.html) | Not Started |
| Export session notes as a [Markdown](https://www.markdownguide.org/) document | Not Started |
| Export session notes as an HTML document | Not Started |
| Export session notes as an PDF document | Not Started |

## Examples
Content and properties of session notes are based on the type of document passed, inputs supplied from the dialog, and other contextual information.

| Document Type | Example Entry |
| ------------- | -------- |
| Item in Player Inventory | Player `player_name` gained `item_name` while exploring `scene_name`. |
| NPC | `players_in_scene` met `npc_name` at `scene_name`. |
| Quest Entry (New) | The party was tasked with performing `quest_description` for `quest_npc` while exploring `scene_name`. |
| Vehicle | The party travelled to `scene_name` using `vehicle_name`. |
| Chat Message (Combat Log for a Critical Hit) | `player_name` landed a powerful blow on a `monster_name` while exploring `scene_name`. |
| Chat Message (Combat Log for a Final Attack) | `player_name` felled a mighty `monster_name` while exploring `scene_name`. |
| Combat Encounter | `players` encountered `monsters` while exploring `scene_name`, looted `encounter_loot`, and earned `total_encounter_xp`. |
| Map Note | The party found/noticed/discovered `map_note_name` while exploring `scene_name`. |
| Chat Message | `player_name` said something memorable while exploring `scene_name`: `message_text` |
| Rollable Table Result | Some description of `roll_result`, based on the type of roll table. |
| Journal Entry | The party gained insight into the lore of `world name` while exploring `scene_name`: `journal_entry_title`. |
| Scene (On Entering Scene) | The party travelled to `scene_name`. |
| Short Rest | The party rested briefly while exploring `scene_name`. |
| Long Rest | The party camped at `scene_name`. |
| Long Rest (Random Encounter) | The party encountered `monsters` while camping at `scene_name`. |
| Calendar Time (Skipped n Weeks) | The party spent `total_weeks` in `scene_name` working on/doing/researching/building `some_specified_activity`. |
| Player List | Players `player_names` attended a session on `session_date`. |

### Macros

| Type | Name | Description | Status | Parameters |
| ---- | ---- | ----------- | ------ | ---------- |
| Macro | addSessionNote | A Foundry macro that adds a new session note to the calendar. | Not Started | |
| Macro | getCurrentSessionName | Gets the name of current session, based on date. | Not Started | |
| Macro | findSessionNote | Retrieves all session notes for the current session matching the specified category. | Not Started | |
| Macro | getSessionNoteCategory | Retrieves all session notes for the current session matching the specified category. | Not Started | |
| Macro | addEncounterNote | | Not Started | |
| Macro | addQuestNote | | Not Started | |

## Foundry Documents

| Document Type | Name | Description |
| ------------- | ---- | ----------- |
| Journal | Session Notes Journal | Journal where all session notes are stored for a campaign. |
| JournalEntry | Session Notes Page | Unique journal page where notes for the current session are stored. |

### Ideas

- **Popup Dialogue**: A simple form could be opened on clicking the button, with pre-populated fields based on the type of item. 
- Update session notes page when a new note or event is added to Simple Calendar using the built-in [hooks](https://simplecalendar.info/docs/developing-with-sc/api/namespaces/SimpleCalendar.Hooks)
- If using hooks on Simple Calendar doesn't pan out, you could instead create a macro that writes to both Simple Calendar *and* to the session notes journal at the same time.

## References
Useful documentation, example projects, and other references are listed here.

### Example Projects

- [About Time](https://gitlab.com/tposney/about-time)
- [Time's Up](https://gitlab.com/tposney/times-up)
- [Quick Notes](https://github.com/D-first/quick-notes)
- [Pin Cushion](https://github.com/p4535992/foundryvtt-pin-cushion/)
- [GM Notes](https://foundryvtt.com/packages/gm-notes)
- [Easy Notes](https://github.com/djeval/easy-notes)

### Development Articles

- [Developing With Simple Calendar](https://simplecalendar.info/docs/developing-with-sc/)
- [Simple Calendar - Hooks](https://simplecalendar.info/docs/developing-with-sc/api/namespaces/SimpleCalendar.Hooks)
- [Simple Calendar - Exporting](https://simplecalendar.info/docs/global-configuration/import-export#exporting)
- [Simple Calendar - Handlebar Helpers](https://simplecalendar.info/docs/developing-with-sc/api/enums/HandlebarHelpers) -- Likely necessary to create a "Session Notes Summary" journal page for mid-session viewing (useful even if notes are primarily exported out of Foundry)
- [Foundry Development](https://foundryvtt.com/article/intro-development/)
- [Module Making for Beginners](https://hackmd.io/@akrigline/ByHFgUZ6u/%2FF4CFuxqZSTOcqgixEf9M6A)
- [Module Development Resources](https://foundryvtt.com/article/intro-development/#resources)
- [Handlebars](https://handlebarsjs.com/guide/)

### Foundry Features

- [Foundry - Journal Entries](https://foundryvtt.com/article/journal/)
- [Foundry - Map Notes](https://foundryvtt.com/article/map-notes/)
- [Foundry - Macros](https://foundryvtt.com/article/macros/)

### Foundry API

- [Foundry API - User Interface](https://foundryvtt.com/api/index.html#user-interface)
- [Foundry API - `HandlebarsHelpers`](https://foundryvtt.com/api/classes/client.HandlebarsHelpers.html)
- [Foundry API - `ModuleClient`](https://foundryvtt.com/api/v11/modules/client.html)
- [Foundry API - `JournalEntry`](https://foundryvtt.com/api/v10/classes/client.Dialog.html)
- [Foundry API - `JournalEntry`](https://foundryvtt.com/api/v11/classes/client.JournalEntry.html)
- [Foundry API - `JournalEntry`](https://foundryvtt.com/api/v10/classes/client.JournalEntryPage.html)
- [Foundry API - `JournalEntry`](https://foundryvtt.com/api/v10/classes/client.JournalSheet.html)
- [Foundry API - `JournalEntry`](https://foundryvtt.com/api/v10/classes/client.JournalPageSheet.html)
- [Foundry API - `JournalEntry`](https://foundryvtt.com/api/v10/classes/client.Note.html)
- [Foundry API - `JournalEntry`](https://foundryvtt.com/api/v10/classes/client.NoteDocument.html)
- [Foundry API - `JournalEntry`](https://foundryvtt.com/api/v10/classes/client.Macro.html)
- [Foundry API - `JournalEntry`](https://foundryvtt.com/api/v10/classes/client.MacroFolder.html)
- [Foundry API - `JournalEntry`](https://foundryvtt.com/api/v10/classes/client.CombatTracker.html)
- [Foundry API - `JournalEntry`](https://foundryvtt.com/api/v10/classes/client.Scene.html)
- [Foundry API - `JournalEntry`](https://foundryvtt.com/api/v10/classes/client.Item.html)

#### Simple Calendar API

- [Simple Calendar API](https://simplecalendar.info/docs/developing-with-sc/api/namespaces/SimpleCalendar)
- [Simple Calendar - `addNote`](https://simplecalendar.info/docs/developing-with-sc/api/namespaces/SimpleCalendar.api#addnote)
- [Simple Calendar - `addSidebarButton`](https://simplecalendar.info/docs/developing-with-sc/api/namespaces/SimpleCalendar.api#addsidebarbutton)
- [Simple Calendar - `addNote`](https://simplecalendar.info/docs/developing-with-sc/api/namespaces/SimpleCalendar.api#addnote)
- [Simple Calendar - `advanceTimeToPreset`](https://simplecalendar.info/docs/developing-with-sc/api/namespaces/SimpleCalendar.api#advancetimetopreset)
- [Simple Calendar - `getNotes`](https://simplecalendar.info/docs/developing-with-sc/api/namespaces/SimpleCalendar.api#getnotes)
- [Simple Calendar - `getNotesForDay`](https://simplecalendar.info/docs/developing-with-sc/api/namespaces/SimpleCalendar.api#getnotesforday)
- [Simple Calendar - `removeNote`](https://simplecalendar.info/docs/developing-with-sc/api/namespaces/SimpleCalendar.api#removenote)
- [Simple Calendar - `searchNotes`](https://simplecalendar.info/docs/developing-with-sc/api/namespaces/SimpleCalendar.api#searchnotes) -- Extremely useful for assembling session notes, if categories are used to identify various types of events.
- [Simple Calendar - `isPrimaryGM`](https://simplecalendar.info/docs/developing-with-sc/api/namespaces/SimpleCalendar.api#isprimarygm)
- [Simple Calendar - `pauseClock`](https://simplecalendar.info/docs/developing-with-sc/api/namespaces/SimpleCalendar.api#pauseclock)
- [Simple Calendar - `showCalendar`](https://simplecalendar.info/docs/developing-with-sc/api/namespaces/SimpleCalendar.api#showcalendar)
- [Simple Calendar - `PresetTimeOfDay`](https://simplecalendar.info/docs/developing-with-sc/api/enums/SimpleCalendar.api.PresetTimeOfDay)
- [Simple Calendar - `NoteCategory`](https://simplecalendar.info/docs/developing-with-sc/api/interfaces/SimpleCalendar.NoteCategory)
- [Simple Calendar - `NoteData`](https://simplecalendar.info/docs/developing-with-sc/api/interfaces/SimpleCalendar.NoteData)
