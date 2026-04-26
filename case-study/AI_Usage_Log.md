# AI Tool Usage Log

## NYPD Domain Awareness System Case Study

This document records how AI tools were used during the development of this case study package. It includes the specific prompts submitted to each tool, a candid assessment of the outputs, what required verification or correction, and what I would do differently.

---

## Tool 1: Claude (Anthropic)

### What I Used It For

Claude was the primary drafting tool for the case study. I used it to synthesize research into narrative prose, develop the protagonist-centered structure, draft the governance tension sections, write the teaching note, and generate the discussion questions. Claude was also used to maintain document consistency across the four case study files and to draft sections of the source bibliography.

### Example Prompts

1. *"Write a draft of an HBR-style case study about the NYPD Domain Awareness System. Cover the technology capabilities, the partnership with Microsoft, the rollout timeline, and the civil liberties concerns."*

2. *"Rewrite this as a story, not a report. I need to feel the tension between Kelly's operational instincts and the civil liberties criticism. Start with a specific moment — put the reader in a room with him."*

3. *"The section on the 2021 governance policy feels too neutral. Help me show why the ACLU's response — 'Who watches the watchers?' — matters strategically, not just politically. I want students to argue about it."*

### What the Output Was

The first prompt produced a technically accurate but narratively flat document — organized by topic (cameras, then license plates, then sensors, then policy), written in declarative summary prose, with no protagonist and no scene-setting. It read like a government report, not a classroom case study. The civil liberties section was present but felt appended rather than integrated into the central tension.

After the second and third prompts, the output shifted substantially. Claude produced the opening scene with Kelly in the Real Time Crime Center, introduced the recurring framing of the three governance paths, and rewrote the policy section to show the ACLU's critique as a structural argument rather than a political objection. The final narrative structure — opening vignette, operational success, public confrontation, policy response, open decision — came from this iterative refinement.

### What I Verified or Corrected

- Cross-checked all dates against primary sources: DAS public launch confirmed as 2012, the Impact and Use Policy confirmed as April 9, 2021.
- Verified the camera count (~9,000), license plate reader count (~500), and the federal grant figures against the NYPD Technology page and the INFORMS Edelman case.
- Confirmed that the case's description of Patternizr was consistent with the 2019 INFORMS peer-reviewed paper, not just Claude's general knowledge.
- Removed a claim that Kelly personally attended the 2013 Times Square protest monitoring — that was inferred by Claude and not documented in any confirmed source.
- Corrected Claude's initial framing of Patternizr as a "facial recognition" tool; it is a crime-series linking algorithm, not facial recognition.

### What I Would Do Differently

Start with the governance tension prompt, not the technology overview prompt. The first response required substantial rewriting because I did not signal upfront that the case needed to feel like a story with a moral dilemma, not a technical briefing. Providing Claude with the HBR case study format — protagonist, decision point, tradeoffs, no resolution — at the beginning of the session would have reduced revision cycles. I also would have specified earlier that all factual claims needed to be flagged when they came from Claude's general knowledge rather than a named source.

---

## Tool 2: Perplexity

### What I Used It For

Perplexity was used during the research phase for source discovery, URL verification, and quick fact-checking of specific claims. It was especially useful for finding civil liberties organization reports, confirming that the INFORMS Patternizr paper existed and locating its DOI, and identifying the Brennan Center's surveillance technology report. I used Perplexity until my student account credits ran out, at which point I transitioned entirely to Claude and direct web searches.

### Example Prompts

1. *"What peer-reviewed papers exist on the NYPD's Patternizr algorithm? Give me the full citations including journal name, year, and DOI if available."*

2. *"What are the main civil liberties criticisms of the NYPD Domain Awareness System? I'm looking for reports from ACLU, NYCLU, and the Brennan Center specifically."*

3. *"Find the official NYPD policy document on DAS governance from 2021. I need the exact title and URL."*

### What the Output Was

For the Patternizr query, Perplexity correctly identified the 2019 INFORMS Journal on Applied Analytics paper and provided the DOI. For the civil liberties query, it surfaced the ACLU license plate reader report, the NYCLU automatic plate reader report, and the Brennan Center surveillance technology report — all of which became Tier 2 sources in the registry. For the 2021 policy document, it provided the correct title and a functional URL to the NYPD's public PDF.

One suggested source — a claimed 2019 ProPublica investigation specifically focused on DAS algorithms — could not be verified through independent search. That source was not included in the registry.

### What I Verified or Corrected

- Manually confirmed each URL by attempting to load the page and checking that the content matched the description Perplexity provided.
- Checked the INFORMS DOI by accessing the abstract page and confirming the authors (Brantingham et al.) and publication year.
- Discarded the unconfirmed ProPublica reference after two independent search attempts failed to locate it.
- Noted that Perplexity's summary of the Fordham Urban Law Journal article was accurate in substance but misdated the article by one year — the correct publication date was confirmed via the law journal's online archive.

### What I Would Do Differently

Use Perplexity credits more strategically. I spent early credits on broad queries ("tell me about DAS") that produced general summaries I could have obtained from any search engine. The high-value use case was targeted source verification — asking for a specific citation or a specific URL — which I only shifted toward after credits were nearly depleted. I would also create a structured list of the ten most critical sources I needed to find before opening Perplexity, rather than searching reactively as gaps appeared during writing.

---

## Tool 3: GitHub Copilot

### What I Used It For

GitHub Copilot (in VS Code Agent Mode) was used for three purposes: drafting and completing the `.claude/skills/` markdown files, autocompleting repetitive table formatting in `sources/Source_Registry.md`, and generating the GitHub Actions workflow configurations in `.github/workflows/`. I also used it to draft the initial version of the `.github/copilot-instructions.md` file, which mirrors the behavioral guidance in CLAUDE.md for Copilot users.

### Example Prompts

1. *"Write a skill file for a slash command called `/add-sources` that adds a source to Source_Registry.md and prompts for tier, date accessed, URL, and a one-sentence description. Follow the format of the existing skill files in .claude/skills/."*

2. *"Complete this markdown table with consistent formatting. I need rows for entries 4 through 9 with columns: number, source name, tier, date, publisher, local file, and key content. Use the same style as the existing rows."*

3. *"Help me write a GitHub Actions workflow that runs on pull requests and validates that all markdown links in the case-study/ folder are reachable. Use the markdown-link-check action."*

### What the Output Was

For the skill file prompt, Copilot produced a well-structured markdown template with the correct frontmatter format and a logical conversational flow — but it populated the example source entries with generic placeholder text ("Source Name Here", "https://example.com") rather than project-specific content. The structure was correct; the content required replacement.

For the table completion prompt, Copilot accurately replicated the column formatting and populated most rows correctly. It generated plausible-sounding "Key Content" descriptions for entries it had not seen, which required line-by-line review and correction against the actual sources.

For the GitHub Actions workflow, Copilot generated a functional `.yml` file using the `markdown-link-check` action that matched the existing workflow structure in the repository. This required minimal editing — primarily adjusting the file path filter to match the project's directory structure.

### What I Verified or Corrected

- Reviewed each Copilot-generated skill file against the behavioral specifications in CLAUDE.md. Several files used generic phrases like "ask the user for more details" without specifying which details — these were revised to include project-specific field names.
- Checked every table row Copilot completed against the actual sources. Three "Key Content" cells contained inaccurate characterizations and were rewritten.
- Tested the GitHub Actions workflow against a local branch before committing. The initial version incorrectly set the working directory; corrected by adjusting the `paths` filter in the workflow trigger.
- Confirmed that the `.github/copilot-instructions.md` file generated by Copilot accurately reflected the slash command equivalents documented in CLAUDE.md, since Copilot was completing that file without access to CLAUDE.md in its context window.

### What I Would Do Differently

Provide more context at the start of the Copilot Agent Mode session. Because Copilot did not have CLAUDE.md loaded in its context when I began, the first several skill files it drafted used generic assistant language instead of the project's specific conventions. Loading CLAUDE.md as a reference file at the start of the session — using Agent Mode's "add to context" feature — would have reduced the number of corrections required. I would also separate the table-completion task from the skill-drafting task in separate sessions, since the two types of outputs require different verification approaches and mixing them slowed the review process.

---

## Summary Reflection

Each tool served a different function in the workflow and performed best when used for a narrow, well-defined task. Claude was strongest for narrative synthesis and iterative refinement of tone — but required explicit framing from the beginning to produce case study prose rather than technical summaries. Perplexity was most efficient for targeted source discovery, though its credits limited sustained use. GitHub Copilot was useful for repetitive structural tasks and file scaffolding, but its outputs required careful fact-checking wherever it was generating content rather than completing a pattern.

The most significant lesson across all three tools is that prompt precision matters more than prompt length. Vague initial prompts — asking for a "case study about DAS" or "a skill file for adding sources" — produced outputs that required substantial rework. Prompts that specified the audience, the format, the constraint (e.g., "every claim must be flagged if it comes from general knowledge"), and the tone produced outputs that were closer to usable on the first pass.
