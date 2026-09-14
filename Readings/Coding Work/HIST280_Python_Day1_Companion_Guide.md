# HIST 280 — Python Day 1 Companion Guide
### Reinforcing "Anatomy of a Python Script" + "Variables" (Melanie Walsh, *Intro to Cultural Analytics & Python*)

---

## 1. Anchor Analogy: The Script as a Recipe

Before touching code, frame the whole lesson with one metaphor and return to it throughout:

> **A Python script is like a recipe.**
> - **Imports** = gathering special tools/gadgets you didn't make yourself (a food processor someone else invented)
> - **Functions** = a sub-recipe you can reuse ("make the sauce" — you define it once, use it whenever)
> - **Variables** = the ingredients list (flour, sugar, oven temp) — set once, used throughout
> - **Read in file** = pulling the raw ingredients out of the fridge
> - **Manipulate/analyze** = the actual cooking steps
> - **Output** = plating the dish
> - **Comments** = handwritten notes in the margins of a cookbook

**Activity:** Ask students to redraw this analogy for a *non-cooking* process of their choice (getting ready in the morning, doing laundry, planning a research trip). This forces them to abstract the six-step structure away from the specific example and shows they understand the *shape*, not just Walsh's example.

---

## 2. "Spot the Chunk" Warm-Up

Project Walsh's full "Yellow Wallpaper" word-frequency script (the commented version) and have students — individually or in pairs — label each line with which of the six anatomy stages it belongs to, *before* you reveal her section headers. This is low-stakes pattern recognition and surfaces confusion early (many will misplace "define variables" vs. "manipulate data").

Follow with a **fill-in-the-blank version**: give them the script with the six section-comment headers removed, and ask them to write the comments back in.

---

## 3. Variable-Naming Card Sort

Print or project a mixed list of names — some good, some bad — pulled from real code:
`f`, `filepath_of_text`, `x`, `stopwords`, `data1`, `number_of_desired_words`, `temp`, `meaningful_words`, `thing`, `full_text`

Have students sort into two piles ("Would help me" / "Would confuse future-me") and justify a few choices out loud. This turns the "good names vs. bad names" section of the reading into something tactile rather than something they just nodded along to.

---

## 4. The "Six-Month-Later Test"

Give students this one memorable heuristic and have them apply it to their own variable names for the rest of the semester:

> **"If I opened this script cold in six months, would this name tell me what's inside?"**

Ask a few students to test it live on names like `f` vs. `filepath_of_text`.

---

## 5. Assignment vs. Equality — Physical Demonstration

The `=` vs `==` distinction trips up nearly everyone early on. A quick embodied version:

- Hold up an empty box (or draw one) labeled `x`. Say "`x = 5`" while physically placing a card with "5" into the box. **This is an action** — something is happening.
- Then ask: "Is `2 * 2 == 4` true?" — no box, no action, just a yes/no question being asked. **This is a question**, not an action.

Reinforce verbally: *single equals **does** something; double equals **asks** something.*

---

## 6. Predict-Then-Run

For each code snippet in the tutorial (assigning `new_variable = 100`, reassigning `filepath_of_text` to the Beyoncé lyrics file, etc.), have students **predict the output on paper before running it**. This catches the common misconception that variables are "permanent" once set, and sets up the reassignment section naturally — when the Yellow Wallpaper filepath gets swapped for Lemonade, ask "why did the *whole* output change from one line?"

---

## 7. "Find the Off-Limits Name" Debugging Challenge

Give students a script with one deliberately broken variable name (`True = "some_file.txt"`, or a name with a space or hyphen in it). Have them find and fix the error *before* running it, then run it to confirm. This builds the muscle of reading error messages (`SyntaxError: can't assign to keyword`) without panic.

---

## 8. Exit Ticket (2 minutes, end of class)

One index card, two questions:
1. **Name the six parts of a Python script, in order** (recipe metaphor allowed as a memory aid).
2. **Write one variable assignment of your own**, using a name that would pass the "six-month-later test."

This gives you an immediate read on who's solid and who needs a follow-up before the next class (likely Data Types).

---

## Optional Stretch: Connect to the Humanities Framing

Walsh explicitly says the goal isn't to become "the most efficient software developers" but to study and argue about culture. Consider closing with a discussion prompt tying this back to the course's actual content:

> *"If you swapped in a variable for a text you're studying for this course — a speech, a diary, a newspaper archive — what would `filepath_of_text` point to? What would `stopwords` need to look like differently for a 19th-century historical document versus modern song lyrics?"*

This keeps the technical lesson anchored to *why* they're learning Python in a history class at all, and previews issues (spelling variants, OCR errors, archaic language) they'll hit later in the course.
