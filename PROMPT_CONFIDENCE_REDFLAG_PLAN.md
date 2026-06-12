# Prompt Confidence Red/Yellow Flag Plan

## Goal
Reduce AI-sounding language in prompts so outputs read like natural human texting and avoid common "this feels AI" reactions.

## Scope
- App: `rizzchatai`
- File: `prompts/rizzchatai.json`
- Prompt keys:
  - `openerSystem`
  - `appChatSystem`
  - `regChatSystem`
  - review user templates for terse/instructional wording

## Red Flag Categories (Must Fix)
1. Canned phrase traps
   - Examples: "go-to", "found your person yet", "green flag/red flag" in early openers.
2. Scripted conversion language
   - Examples: lines that read like sales funnels rather than normal texting.
3. Motivational-coach or customer-support voice
   - Examples: upbeat generic empathy, polished recap framing.
4. Overly performative confidence
   - Examples: pushy or pre-scripted closes that ignore chat context.

## Yellow Flag Categories (Should Reduce)
1. Prompt-manual wording
   - Heavy "Goal/Tone/Steps/Output Format" structure that leaks into outputs.
2. Corporate/process language
   - Examples: analyze, determine, maintain flow, relationship dynamic.
3. Over-constraint duplication
   - Repeated "no meta", "never reference AI", "output only" directives.
4. Formulaic rhythm
   - Repeated sentence skeletons and highly symmetric message cadence.

## Rubric For Evaluation
Score each generated message per fixture on:
- Authenticity (0-2): sounds like a real person vs template.
- Specificity (0-2): tied to concrete chat/profile details.
- Timing fit (0-2): escalation pace matches conversation stage.
- Social calibration (0-2): confident but not pushy/performative.
- AI fingerprint risk (0-2): canned/robotic markers present.

Pass criteria:
- No red flags in outputs.
- Average >= 8/10 across fixtures for each mode.

## Execution Plan
1. Baseline audit
   - Run current fixtures for `opener`, `app_chat`, `reg_chat`.
   - Tag red/yellow markers in outputs.
2. Prompt text triage (no behavior changes yet)
   - Mark each line Keep/Rewrite/Delete in system prompts.
   - Preserve boundary and safety constraints.
3. Rewrite pass (minimal high-impact)
   - Replace abstract/process wording with concrete, natural texting guidance.
   - Collapse duplicate directives into one concise section per prompt.
4. Example refresh
   - Replace stale/canned examples with natural, context-anchored lines.
   - Ensure variety in cadence, not one repeated skeleton.
5. Validation round 1
   - Re-run fixtures and score with rubric.
   - Fix any remaining red markers.
6. Validation round 2
   - Reduce yellow markers while protecting constraints.
7. Final gate
   - Confirm no regression on boundary behavior and conversation goals.

## Immediate Phrase Watchlist
- go-to
- found your person yet
- found Mr Right yet
- green flag / red flag (in cold openers)
- Let’s keep this going in person (when used as a stock transition)
- polished recap language ("I appreciate you sharing that" style)

## Deliverables
1. Keep/Rewrite/Delete table for each system prompt section.
2. Updated prompt text draft (local, not yet promoted).
3. Fixture scorecard before/after with red/yellow counts.
4. Final recommendation for promotion readiness.
