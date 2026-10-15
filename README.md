# PokeBot.ai Career Coach

PokeBot.ai Career Coach brings PokeBot's job-search tools into Claude: text mock interviews, resume scores, resume-to-job matches, cover letters and career plans. The plugin pairs PokeBot's connector with five skills. The skills tell Claude when to use each PokeBot tool and how to run it, for example asking one interview question at a time and sending only the answers you write.

## What you can do

| Skill | What it does | PokeBot tools it uses |
| --- | --- | --- |
| mock-interview | A text mock interview for a role you choose. Each answer gets a score, feedback and a suggested answer, and you get a performance summary at the end. | start-interview, submit-answer, end-interview |
| resume-score | Scores your resume out of 100, with strengths, weaknesses and recommendations. | analyze-resume |
| job-match | Checks how well your resume matches a job description: a match score, covered and missing keywords, and tailoring advice. | match-resume-to-job |
| cover-letter | Writes a cover letter from your resume and a job description. | generate-cover-letter |
| career-plan | Career goals with timelines, a skill-gap analysis with a readiness score, or a week-by-week growth plan. | analyze-career-goals, analyze-skill-gap, generate-growth-plan |

## Before you start

- **A PokeBot account.** A free account works. Free accounts include 20 runs a month in Claude, shared across all tools and reset on the 1st of each month (UTC). Starting an interview counts as one run; answering its questions and finishing it don't. Paid PokeBot plans use their own plan limits. You can create an account at https://app.pokebot.ai or from the sign-in page Claude opens.
- **Code execution and file creation turned on** in Claude, under Settings > Capabilities. Claude needs it to use skills. Without it, you can still use PokeBot through its connector.
- **A Claude plan that shows directory plugins:** Pro, Max, Team or Enterprise.

## Set up

1. Add the plugin in Claude from **Customize > Plugins**.
2. Open the plugin's **Connectors** tab and connect PokeBot. Sign in to PokeBot, then select **Approve**. This is the same PokeBot server as the PokeBot.ai Career Coach connector in Claude's directory.
3. In a chat, check that PokeBot is turned on under **+ > Connectors**.

The full setup guide is at https://pokebot.ai/claude.

## Use it

Ask in your own words, for example:

- "Give me a 3-question behavioral mock interview for a Data Scientist role."
- "Score my resume." Paste or attach your resume.
- "How well does my resume match this job?" Add the job description.
- "Write a cover letter for this job from my resume."
- "Make me a 3-month growth plan to become a data scientist."

You can also type / in the message box and pick a PokeBot skill. In Claude Code, the skills are /pokebot:mock-interview, /pokebot:resume-score, /pokebot:job-match, /pokebot:cover-letter and /pokebot:career-plan.

## What PokeBot receives and keeps

- The plugin connects Claude to PokeBot's MCP server at https://connect.pokebot.ai/mcp. You sign in through OAuth, and the plugin holds no keys or passwords.
- When Claude runs a PokeBot tool, it sends PokeBot that tool's inputs only: for example your resume text, a job description, your current and target roles and career goals, and your interview answers. PokeBot doesn't receive the rest of your conversation.
- Results are saved to your PokeBot account, so you can open them later in the PokeBot app. To skip saving a resume score, job match, cover letter or career plan, ask Claude not to save it. The full resume text isn't saved with resume scores and job matches, though a result can quote parts of it. Mock interviews are always kept in your PokeBot interview history, including the details you start them with (such as resume text and a job description) and your answers.
- The plugin contains only instructions for Claude and the server address above. It runs no code on your computer and sends data nowhere else.
- Your prompts and PokeBot's results are also processed by Anthropic as part of Claude, under Anthropic's own privacy policy.
- You can end Claude's access at any time in PokeBot under Settings > Integrations > Connected apps.

Privacy policy: https://pokebot.ai/privacy#claude

## Support

Email support@pokebot.ai. Setup guide: https://pokebot.ai/claude

## License

The plugin's files are released under the MIT license; see LICENSE. The PokeBot name and the Pokie mascot icon are PokeBot's brand assets and are not covered by that license.
