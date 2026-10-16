---
name: mock-interview
description: Run a mock interview with PokeBot, one question at a time, with a score, feedback and a suggested answer after each answer and a performance summary at the end. Use when the user asks for a mock interview, interview practice, or to practice answering interview questions for a role.
---

# Mock interview with PokeBot

Use PokeBot's tools `start-interview`, `submit-answer` and `end-interview`.

## Before you start

1. You need three things: the role (position), the seniority (entry, mid, senior, lead or executive) and the interview type (technical, behavioral, resume, job_fit or other). Ask for any the user hasn't given, all in one short message.
2. Pass optional details the user mentions, such as the company, industry, difficulty (easy, medium or hard) or feedback style (encouraging, normal or constructive). Otherwise leave the defaults.
3. An interview has 3 to 8 main questions (5 by default). If the user asks for fewer or more, use the nearest allowed number and tell them.
4. Some interview types need text from the user:
   - resume: their resume text, in resume_content;
   - job_fit: their resume text and the job description;
   - other: the scenario to practice, such as a salary negotiation, in scenario_description.

   Use only text the user pasted or attached in this chat. Never write a resume, job description or scenario for them.

## Run the interview

1. Call `start-interview`. Show the first question as PokeBot wrote it, with its number (for example "Question 1 of 5"). Then stop and wait for the user's answer.
2. When the user answers, call `submit-answer` with the session_id from `start-interview` and the user's answer exactly as they wrote it. Don't correct, shorten, expand or polish it.
3. Show PokeBot's score, feedback and suggested answer, then the follow-up or next question. Stop and wait again. PokeBot asks at most one follow-up per main question.
4. When PokeBot says that was the last question, or the user asks to stop, call `end-interview` with the same session_id. Show the summary: the overall score, strengths, areas to improve and the recommendation.

## Rules

- One question at a time. Never answer a question for the user, and never submit anything they didn't write as their answer. If they ask something else, such as to repeat the question, reply without calling `submit-answer`.
- Show only the scores and feedback PokeBot returned. Don't add scores of your own.
- Interviews are always saved to the user's PokeBot interview history, including the details used to start them (such as resume text) and the user's answers. If the user asks not to save one, tell them this before you start.
- If PokeBot returns a usage-limit message, show it to the user as it is, including its link, and don't retry.
- If PokeBot says the session isn't taking answers, offer the summary with `end-interview` (same session_id) or a new interview. If it says the session wasn't found, tell the user and offer to start a new interview.

## If PokeBot isn't connected

If PokeBot's tools aren't available in this chat, tell the user how to turn them on, and in the same message offer to help without PokeBot instead:

1. Connect PokeBot from this plugin's **Connectors** tab, or from **Customize > Connectors**, and sign in with a PokeBot account. A free account works. On a Team or Enterprise plan, an Owner may need to add PokeBot first.
2. Turn PokeBot on for this chat with **+ > Connectors**. In Claude Code, run `/mcp` and sign in to pokebot instead.

If you help without PokeBot, don't present your own questions, scores or feedback as PokeBot's.
