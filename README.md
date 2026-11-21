# nyaya-reasoning

A structured reasoning skill for AI assistants and agents based on classical **Nyāya** logic (drawing on Annaṃbhaṭṭa's *Tarkasaṅgraha*) and modern critical thinking. It helps models surface hidden rules, test counterexamples, check for fallacies and rival explanations, and give calibrated confidence rather than jumping straight to an unexamined conclusion.

## Overview

Most reasoning failures happen when an assistant relies on an unstated rule, cherry-picks confirming evidence, or states a guess with too much certainty. `nyaya-reasoning` encourages disciplined justification—pairing a clear claim with concrete grounds, an explicit connecting rule, counterexample checks, and honesty about what would settle the question.

### What It Helps With
* **Surface implicit rules:** Make unspoken assumptions and general principles explicit before drawing conclusions.
* **Test counterexamples:** Look for cases where the rule fails or rival explanations fit the same evidence.
* **Spot weak reasoning:** Flag leaps in logic, missing evidence, and common fallacies.
* **Calibrate confidence:** State how strong the support is, note key assumptions, and identify what would change the conclusion.

## When to Use It

Match effort to the stakes of the question:

* **Good fit:** Root-cause debugging, reviewing arguments or proposals, interpreting data, trade-off decisions, structured research or policy questions, and evaluating AI reasoning.
* **Poor fit:** Simple factual lookups, casual chat, creative writing, taste or opinion, or fast low-stakes decisions.

### Depth Modes
* **Light (most cases):** Works through the checks internally and replies concisely with the conclusion, key evidence, connecting rule, and one honest caveat.
* **Full (high-stakes, ambiguous, or requested):** Leads with the conclusion and confidence, then surfaces only the checks that changed or shaped the answer—such as the rule, counterexample checks, competing explanations, and what would settle it.
* **Critique mode:** Evaluates an argument or claim by breaking down its premises and rule, checking for counterexamples, rival explanations, and fallacies, and pointing out what evidence would strengthen or test it.


## Examples

### 1. Root-Cause Debugging (Full Mode)

* **Prompt:**
* 
  > "Our API latency jumped right after a database index update. Check my reasoning that the index caused the spike—what else could explain it?"
  
* **Sample output:**
  
  > **Conclusion:** The new index is only one plausible cause (confidence: low-to-moderate, because timing alone does not establish causation).
  
  > **Rule:** Adding a heavily written index can slow down writes or cause lock contention on hot tables, though well-chosen indexes usually speed up reads.
  
  > **Counterexample check:** Indexes often improve query latency rather than hurt it; a case where the rule fails is a read-heavy endpoint whose slow query actually improved.
  
  > **Other explanations:** A concurrent traffic spike, connection pool exhaustion, or lock contention during index build; comparing latency against write volume and lock wait metrics before/after the change would separate them.
  
  > **What would settle it:** Check query plans, lock waits, and write amplification around the deploy timestamp, or test rolling back the index in staging.

### 2. Reviewing an Argument or Claim (Critique Mode)

* **Prompt:**
  
  > "Play devil's advocate on this claim: 'Our onboarding completion rose 12% this week after changing the welcome email, so the new email clearly improves activation.'"
  
* **Sample output:**
  
  > **Restated argument:** Onboarding completion rose 12% after the email change; because email updates improve activation, the new email caused the jump.
  
  > **Main weakness:** *Erratic reason / hidden condition*—a single-week lift can come from a higher-intent traffic source, a smaller cohort, or a UI tweak shipped at the same time rather than the email itself.
  
  > **What would fix it:** Compare activation across cohorts and channels over multiple weeks or run an A/B split on the welcome email.

### 3. Trade-Off Decisions (Light Mode)

* **Prompt:**
  
  > "Should we rewrite this legacy service now or wait until Q2?"
  
* **Sample output:**
  
  > Hold off on a full rewrite unless current bugs are actively blocking core releases—incremental refactoring usually beats big-bang rewrites on risk and delivery speed (moderate confidence). That assumes the service is stable enough to isolate changes; if outages are frequent or team velocity has stalled, a targeted replacement may be worth the cost.

# **How to Install Nyaya Reasoning**

1. Download or clone the repository:
   ```
   git clone https://github.com/hemant-apk/nyaya-reasoning.git
   ```
2. Open the downloaded `nyaya-reasoning` folder.
3. Copy the entire folder, including `SKILL.md` and `references/`.
4. Paste it into your AI assistant's skills directory.
5. Restart your AI assistant.
6. Start using it by asking:
   ```
   Use Nyaya Reasoning to analyze this problem.
   ```

**That's it!** Nyaya Reasoning is ready to use in a compatible AI assistant.

*Note: The skills directory depends on the AI assistant you use.*


## What's Inside?

- **`SKILL.md`** – The main instruction file that teaches the AI assistant how to apply Nyāya reasoning. It covers:
  - Five-member logical argument structure.
  - Identifying hidden assumptions.
  - Detecting logical fallacies.
  - Testing arguments with counterexamples.
  - Evaluating alternative explanations.
  - Assessing confidence and evidence.

- **`references/`** – Contains supporting documents that provide additional guidance when needed. These include:
  - `source-reliability.md` – Explains how to evaluate the credibility of sources, speakers, and statements.


## Notes & Limitations

* Structured reasoning helps locate weak spots and hidden assumptions—it does not guarantee a conclusion is true on its own.
* A rule stated from only a few cases remains provisional until tested against broader evidence or real data.
* Where quantitative probabilities or statistical tests are needed, pair this approach with proper data analysis rather than relying on reasoning structure alone.

## Contributing & License

See `CONTRIBUTING.md` for how to suggest improvements.
