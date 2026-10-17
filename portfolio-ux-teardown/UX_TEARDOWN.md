# UX Teardown — Capitec Bank App
*A usability case study applying conceptual models, affordance theory, and cognitive load principles to a production fintech product.*

## Why I Picked This App
I use Capitec daily for transfers, bill payments, and savings goals, so I have real friction points to draw on rather than guessing. Banking apps are also a strong test case for usability: the stakes of a mistake are financial, the user base spans every age and literacy level, and the interface has to compress a genuinely complex domain (accounts, credit, payments, disputes) into something a first-time user can operate without training. That combination makes it a good target for a teardown — the design decisions here aren't cosmetic, they carry real consequences.

## (a) Conceptual Model

Capitec's app is built around the **"wallet with compartments"** conceptual model rather than a single undifferentiated balance. The home screen presents your money as distinct pockets — Transact Account, Credit, Savings Plans, Fixed-Term Savings — each with its own visible balance and its own color-coded card. This borrows a mental model users already have from physical cash: separating money by purpose (rent money in one envelope, spending money in another) so you don't accidentally spend what's earmarked.

This model succeeds for three reasons:
1. **It reduces the user's need to do mental accounting.** The app does the separating for you instead of asking you to remember "R2,000 of this R5,000 is actually for rent."
2. **It matches an existing cultural practice.** Stokvels, envelope budgeting, and informal savings pockets are common financial behaviors in South Africa, so the metaphor isn't foreign — it's digitizing something users already do.
3. **It scales gracefully.** Adding a new savings goal doesn't restructure the interface; it just adds another compartment, consistent with how adding a new jam jar of coins doesn't change how the existing jars work.

**Where the model breaks down:** moving money *between your own pockets* uses the identical "Pay" flow as sending money to another person — same form, same "recipient" terminology, same confirmation screen warning you the transaction can't be reversed. For a few seconds, the interface asks you to think of your own Savings Pocket as an external party you're "paying," which momentarily contradicts the "it's all still my money, just organized" promise the wallet metaphor made on the home screen. A user transferring R500 from Transact to Savings has a brief moment of "wait, am I sending this to someone else?" before the pocket icon on the confirmation screen resolves the confusion. This is a conceptual model seam — the kind of inconsistency that doesn't break the app, but very slightly taxes trust at exactly the moment the user should feel safest.

## (b) Three Affordances

| # | Element | Signal | Verdict |
|---|---------|--------|---------|
| 1 | Orange "Pay" button, home screen | Bold color, central placement, single imperative verb | **Accurate** — does exactly what it visually promises |
| 2 | Circular profile icon, top-right corner | Relies entirely on platform convention (every app uses this spot) | **Under-communicates** — no badge or visual cue hints that notifications and security settings live there too |
| 3 | Swipe-left on a statement row | Visually identical to a static list item at rest | **Hidden** — the gesture exists but the interface gives zero indication it's interactive |

**1. The "Pay" button** is the strongest affordance in the app. Its color breaks from the otherwise muted palette, it sits in the thumb-reachable zone on mobile, and the label is a verb, not a noun — "Pay" tells you what will happen, not just what the button is. This follows the principle that the best affordances state the action, not the object.

**2. The profile icon** is a classic case of an affordance that works only because of learned convention, not because the interface itself teaches it. A first-time banking app user — someone for whom Capitec is deliberately designed, given its focus on accessibility and financial inclusion — has no guarantee they've internalized "circle in the corner = settings" from other apps. There's no label, no subtle animation on first login, nothing that converts platform convention into an explicit signal.

**3. Swipe-to-dispute** is the clearest affordance failure. A static list row, by every visual cue, says "this is just text for me to read." Nothing — no edge shadow, no partial reveal, no onboarding tooltip — tells the user that dragging it exposes a dispute action. I only discovered this by accident after three months of regular use, which is itself evidence the signal is too weak to count as a real affordance; it's a hidden feature wearing the costume of a passive display element.

## (c) Cognitive Load

**Reduces load well — Recent payees as tappable avatars.**
Before you type anything into the Pay flow, the app surfaces your five most recent recipients as faces/initials you can tap directly. This exploits **recognition over recall**, one of the most reliable levers in interaction design: recognizing a familiar face is near-instant and low-effort, while recalling and typing a full name or account number requires active memory retrieval and is far more error-prone, especially under time pressure (e.g., paying a vendor while they wait).

**Reduces load well — Inline balance display at the point of decision.**
Your current balance appears directly on the payment confirmation screen, next to the amount you're about to send. Without this, the user would need to hold their balance in working memory from an earlier screen or switch away to check it — both of which introduce the risk of acting on stale information. Surfacing the number exactly where the decision is made (pay / don't pay) removes a memory burden at the single point where an error would be costly.

**Risks a slip-type error — Pay and Request buttons share near-identical styling.**
The quick-actions row places "Pay" and "Request Money" side by side, using the same orange hue and comparable icon weight, differentiated only by a small icon and a text label that most users stop consciously reading after the first few uses (interfaces used daily shift from deliberate reading to pattern-matching by position and color). This is a **slip**, not a **mistake** — the user's intention is correct (they know exactly who they want to pay and why), but the execution goes wrong because the interface fails to visually encode the difference between two actions with opposite financial direction. Slips are typically harder to prevent through instruction (the user already "knows better") and are instead fixed by changing the interface itself, which is the basis for my redesign recommendation below.

## (d) Redesign Recommendation

**Change:** Differentiate the Pay and Request buttons by **hue**, not just icon or label — for example, keep Pay in Capitec's signature orange (consistent with its brand identity and the rest of the app), and shift Request to a cool, visually opposite color such as blue or teal.

**Why this specific fix addresses the specific problem:** The error identified in (c) is a slip rooted in low-effort pattern matching, which research on visual search consistently shows is resolved far more reliably by *pre-attentive* cues — color, in particular — than by cues requiring active reading, such as text labels or small icon differences. Color differences are detected in parallel, almost instantly, before a user consciously processes the icon or re-reads the label; shape and text differences require focused, sequential attention that a user in "autopilot" mode on a familiar app is precisely the person *not* doing. Because the underlying cause is a visual-search failure rather than a comprehension failure, the fix has to live at the visual-search level too — recoloring the buttons closes the gap between what the user intends and what the interface makes easy to do by accident, without adding a single extra step, confirmation screen, or friction point to the existing flow. This is also the kind of fix that costs the product team almost nothing to ship (a styling change, not a flow redesign) while directly addressing a financial-risk error, which is exactly the kind of cost-to-impact ratio that makes a redesign recommendation credible rather than aspirational.

## Reflection
This teardown applies three separate lenses — conceptual models, affordance theory, and cognitive load — to the same product, which is deliberate: real usability problems rarely show up under just one lens. The Pay/Request slip, for instance, would look like a minor styling nitpick in isolation, but framed through cognitive load theory (recognition vs. recall, pre-attentive processing) it becomes a specific, defensible, low-cost fix with a clear mechanism for why it works. That's the standard I tried to hold this analysis to throughout: not "this feels off," but "here is the mechanism, and here is the fix that addresses that exact mechanism."