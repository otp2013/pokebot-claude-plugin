---
name: career-plan
description: Plan a career move with PokeBot, giving career goals with timelines, a skill-gap analysis with a readiness score, or a week-by-week growth plan of 1, 3, 6 or 12 months. Use when the user asks for career goals, which skills they need for a target role, how ready they are for it, or a learning or growth plan to reach it.
---

# Career plan with PokeBot

Pick the PokeBot tool by what the user asked for:

| The user asks for | Tool | Required inputs |
| --- | --- | --- |
| Career goals, such as goals for a move to a new role | `analyze-career-goals` | current_role, target_role |
| Skill gaps, or how ready they are for a target role | `analyze-skill-gap` | current_role, target_role, target_level (entry, mid, senior or lead) |
| A growth, learning or development plan | `generate-growth-plan` | main_goal, target_role |

If the user asks for more than one, run each. If it isn't clear which one they want, ask.

## Steps

1. Ask for any required input the user hasn't given, all in one short message. Never invent roles, goals or details.
2. Pass optional details the user mentions:
   - career goals: goal_type (short-term, mid-term, long-term or all), industry, priorities;
   - skill gaps: industry, focus_areas (technical, soft, leadership or domain);
   - growth plan: timeline, intensity (light, moderate or intensive), target_skills, learning_style, preferred_formats, focus_areas.
3. Growth plans come in four lengths: 1-month, 3-months (the default), 6-months and 1-year. For any other length, use the closest one and tell the user it was rounded.
4. If the user shared their resume in this chat for this request, you can pass it as resume_text to `analyze-career-goals` or `analyze-skill-gap`.
5. Show the result as PokeBot returned it. Don't change its scores, timelines or plan, or add your own.
6. If the result has a link to the saved copy, share it.

## Saving

Results are saved to the user's PokeBot account by default. If the user asks not to save one, set save_to_account to false.

## Limits and errors

If PokeBot returns a usage-limit message, show it to the user as it is, including its link, and don't retry.

## If PokeBot isn't connected

If PokeBot's tools aren't available in this chat, tell the user how to turn them on:

1. Connect PokeBot from this plugin's **Connectors** tab, or from **Customize > Connectors**, and sign in with a PokeBot account. A free account works.
2. Turn PokeBot on for this chat with **+ > Connectors**.

If the user would rather not use PokeBot, help them without it, and don't present your own plan as PokeBot's.
