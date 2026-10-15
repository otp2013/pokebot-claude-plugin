---
name: cover-letter
description: Write a cover letter with PokeBot from the user's resume and a job description. Use when the user asks for a cover letter for a specific job or job posting.
---

# Cover letter with PokeBot

Use PokeBot's `generate-cover-letter` tool.

1. You need the user's resume and the job description, as text they pasted or attached in this chat. Ask for anything missing. Never write or guess either text.
2. Call `generate-cover-letter` with resume_text and job_description.
   - If the user says what the letter is for, set purpose to job-application, internal-transfer, career-change, referral or speculative.
   - If they ask for a tone, pass it as tone, for example "Professional" or "Warm".
3. Show the letter PokeBot wrote. If the result has a link to the saved copy, share it.
4. If the user then asks for changes, you can edit the letter with them in the chat. Use only facts from their resume or what they tell you; don't add experience, skills, employers or numbers they didn't give you. If a copy was saved, tell them the saved copy is PokeBot's original and doesn't include these edits.

## Saving

The letter is saved to the user's PokeBot account by default. If the user asks not to save it, set save_to_account to false.

## Limits and errors

- If PokeBot returns a usage-limit message, show it to the user as it is, including its link, and don't retry.
- If PokeBot says the resume or the job description is missing, ask the user for it.

## If PokeBot isn't connected

If PokeBot's tools aren't available in this chat, tell the user how to turn them on, and in the same message offer to help without PokeBot instead:

1. Connect PokeBot from this plugin's **Connectors** tab, or from **Customize > Connectors**, and sign in with a PokeBot account. A free account works. On a Team or Enterprise plan, an Owner may need to add PokeBot first.
2. Turn PokeBot on for this chat with **+ > Connectors**. In Claude Code, run `/mcp` and sign in to pokebot instead.

If you help without PokeBot, don't present your own letter as PokeBot's.
