---
name: nyaya-reasoning
description: Structured argument-building and argument-checking based on the Nyāya school of Indian logic (the five-member syllogism, pervasion checks, hidden-condition checks, and the five fallacious-reason types), extended with modern practices such as calibrated confidence, base rates, rival explanations, and falsifiability. Use this skill whenever the user asks Claude to justify a conclusion rigorously, diagnose a root cause, evaluate or critique an argument, check a claim for hidden assumptions or confounders, interpret data, or make a high-stakes judgment (debugging, code or design review, decisions with trade-offs, medical or legal-style questions, research claims). Also use it when the user mentions Nyāya, Tarkasaṅgraha, syllogism, fallacies, "check my reasoning", "play devil's advocate", or "what could be wrong with this conclusion", even if they don't name the method. Skip it for simple lookups, casual chat, creative writing, matters of taste, or low-stakes quick decisions.
---

# Nyāya Reasoning

A method for making reasoning visible and testable. It comes from the *Tarkasaṅgraha* of Annaṃbhaṭṭa, a Nyāya primer, and is extended here with modern practice. Its main value is catching errors before anyone acts on a conclusion. Most reasoning failures sit in an unstated rule or an unchecked premise, so the method forces both into the open.

It will not make a conclusion true. It shows where to look, and it often reveals that a conclusion is weaker than it first seemed. That is the point.

## When to use it, and how much

Match effort to stakes.

**Good fit:** root-cause debugging; reviewing arguments, proposals, and reports; interpreting data; decisions with trade-offs; medical, legal, or research-style questions (as a way to organise questions, not to replace experts); grading or prompting AI reasoning; teaching critical thinking.

**Poor fit:** simple factual questions, creative work, casual conversation, taste or pure opinion, fast low-stakes decisions. For problems that need real probabilities or statistics, use this alongside those methods, not instead of them.

**Three levels:**

- **Light (most cases):** Do the work internally. In the answer, give the conclusion, the key evidence, the rule connecting them, and one honest, specific caveat.
- **Full (high-stakes, ambiguous, or requested):** Lead with the conclusion and confidence in one or two sentences. Then show only the parts that changed the answer: the rule, the checks that found something, the competing explanations, and the test that would settle it. Aim for under about 200 words unless the user asks for more depth or the problem genuinely needs it. The template below is a menu, not a form to fill in. Drop any line where the check found nothing worth reporting, except to say briefly what you tried when the user would otherwise assume you didn't look.
- **Critique mode:** When the user supplies an argument, run the checks against it and report findings.

Do not turn every answer into a ritual.

## Core principles of strong reasoning

1. **State the hidden rule.** Every conclusion rests on a general rule ("wherever X, there Y"). Write it out in full and ask whether it is actually true. Many bad conclusions come from a rule that sounds right but fails in some cases.
2. **Test the rule on both sides.** Where the evidence appears, does the conclusion hold? Where the conclusion is false, is the evidence absent? Look for any case where the evidence is present and the conclusion is false. A rule checked only on confirming cases is weak.
3. **Look for other explanations.** Ask what else accompanies the conclusion and might be the real cause (a hidden condition, confounder, or defeater), and name at least one rival explanation. Smoke does not mean fire everywhere; it means fire where there is also wet fuel (a red-hot iron ball has fire without smoke). Say what evidence would separate the explanations.
4. **Run the fallacy checklist** (below) against the argument.
5. **Check the source.** Ask who said it, whether they would know, and whether the claim hangs together. A strong argument built on a weak source is still weak.
6. **State degrees of confidence.** Nyāya treats conclusions as established or not. Real evidence comes in degrees, so say how likely the conclusion is and why.
7. **Use base rates.** Ask how common the conclusion is before weighing the specific evidence.
8. **Name what would change your mind.** If no observation could prove the claim wrong, the claim is weak.
9. **Update.** When new evidence arrives, revise the conclusion instead of defending it.

## The five-member argument

Write non-trivial conclusions in this order:

1. **Claim (pratijñā):** the conclusion, stated plainly.
2. **Reason (hetu):** the observed evidence the claim rests on.
3. **Rule with example (udāharaṇa):** the general rule linking evidence to claim, plus a real case where it held.
4. **Application (upanaya):** confirmation that the evidence is actually present in this case.
5. **Conclusion (nigamana):** the claim restated as following from steps 2–4.

Step 3 matters most. If you cannot state a real rule or a real example, the argument is weaker than it looks, so say so.

## The two counterexample checks

Run both before concluding.

- **Negative-case check (vipakṣa):** Find a case where the reason is present but the claim is false, and a case where the claim is true but the reason is absent.
- **Other-explanations check (upādhi and rivals):** Find a factor that accompanies the claim but is not the real cause, and any rival explanation that fits the same evidence. A true hidden condition pervades the claim (wherever the claim holds, it holds) but does not pervade the reason (the reason can occur without it). Treat the two together: a hidden condition is usually the seed of a rival explanation.

If either check finds a problem, weaken the conclusion ("likely X, unless Y") instead of stating it flatly. The check must be specific to the case at hand. "Something could go wrong" is not a check. If a check finds nothing, say what you actually tried.

## Fallacy checklist (the five hetvābhāsa)

| Type | Meaning | Quick test |
|---|---|---|
| **Erratic (savyabhicāra)** | The reason is not reliably tied to the claim. Variants: *common* (it also appears where the claim is false), *uncommon* (it appears only in the subject, so nothing can be compared), *non-conclusive* (the claim covers everything, so no example exists). | Does the reason also show up where the claim is false? |
| **Contradictory (viruddha)** | The reason actually proves the opposite. | Does the evidence entail the negation of the claim? |
| **Counterbalanced (satpratipakṣa)** | An equally strong reason proves the opposite. | Is there a rival argument of equal weight? If so, call the matter undecided. |
| **Unestablished (asiddha)** | A premise fails. Variants: the subject does not exist (*āśrayāsiddha*), the reason is not present in the subject (*svarūpāsiddha*), or the rule has a hidden condition (*vyāpyatvāsiddha*). | Is each premise actually true of this case? |
| **Sublated (bādhita)** | Direct evidence contradicts the claim. | Does observation or another reliable source already refute it? |

## Source reliability

When an argument rests mainly on what someone said or reported, read `references/source-reliability.md` before judging how much weight it deserves. For most tasks the one-line version is enough: ask who said it, whether they would know, and whether the claim hangs together.

## Guarding against self-deception

- Look for counterexamples before looking for support, because people find what they expect.
- Where possible, make a separate pass (or use a second reviewer) to attack the argument instead of reviewing your own work.
- Distrust a conclusion the user, or you, wanted to reach.

## Facts first

For claims about current facts (a ranking, a policy, a recent event), gather evidence before building the argument whenever you can search or read sources. Say which facts you verified and which you assumed. Reasoning over weak facts is still weak.

## Be fair to the user's idea

A method built around counterexamples can lean toward doubt. Also state the strongest case for the user's view, and say plainly when the evidence supports it. Do not end up more pessimistic than the evidence warrants.

## Forecasts

For predictions, use a reference class (how often does this kind of case turn out this way?), name the key uncertainties, and say which upcoming event or data would change the estimate. Give a confidence level, not a flat yes or no.

## Tone and wording

- Use plain words in answers. The Sanskrit terms in this file are labels for Claude's own use, so do not put them in the answer unless the user has used them or asked about Nyāya. Say "hidden condition," "rival explanation," or "the rule your argument relies on" in place of *upādhi*, *vipakṣa*, or *vyāpti*.
- Do not say "Nyāya" or "the five-member form" unprompted. Show the reasoning, not the method's name.
- Keep the structure light. Short labelled lines are fine; long headed sections are not.
- Check the length before sending. If a full-mode answer runs well past the target, cut the checks that found nothing and any point the user could not act on.

## When to ask a clarifying question

Answer first when you can. Ask only when a missing fact would change the conclusion, not just polish it.

- **Ask** when the answer depends on a fact the user has and you don't (their goal, constraints, the data behind a claim, what they already tried), and different answers to that question would lead to different conclusions.
- **Don't ask** when you can give a useful conditional answer ("if your goal is X, then ...; if Y, then ..."), when the question is minor, or when the user has already shown impatience with questions.
- Ask one question, the one whose answer would most change the conclusion. Give your best provisional answer alongside it, so the user is not left waiting.
- In critique mode, if the argument depends on an unstated number or source, name what is missing and say how the verdict would change.

## Output template (full mode)

Use only the lines that matter, and lead with the conclusion.

```
Conclusion: ... (confidence: high / moderate / low, because ...)
Rule (with a past example): ...
Counterexample check: a case where the rule might fail is ... (what I tried: ...)
Other explanations: hidden conditions and rivals ... ; what would separate them: ...
What would settle it: ... / What would change my mind: ...
```

Add the claim, evidence, and application lines (the full five members) only when the user asks for the formal structure or is reviewing an argument.

## Critique mode

When reviewing someone else's argument:

1. Restate it in the five-member form, filling in any missing rule.
2. Run the two checks and the fallacy table.
3. Report the most serious problem first, naming the fallacy type and showing the failing case.
4. Say what additional evidence would fix it.

## Quick test for any conclusion

If these cannot all be answered clearly, that is where to look next.

1. What is the rule?
2. Where could the rule fail?
3. What else could explain the evidence?
4. Who says so, and why trust them?
5. What would change my mind?
6. How confident am I, and why?

## Cautions

- A tidy five-step argument can still be wrong. The checks must be genuine, not a closing line added for show.
- The stated rule may be invented or overconfident. Ground it in data, a cited source, or an explicit "this is an assumption."
- The method does not solve how finite observations justify universal rules. Be honest when a rule rests on only a few cases.
- Structure shows where to look, not whether the conclusion is right.
- Do not claim this outperforms other reasoning methods unless the user has tested it.
