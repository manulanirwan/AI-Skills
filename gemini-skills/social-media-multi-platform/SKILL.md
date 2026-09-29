---
name: social-media-multi-platform
description: "Generate platform-specific social media captions (Reddit, Facebook, LinkedIn, YouTube, X, Threads, Instagram, TikTok) from raw post details, notes, or draft content. Defaults to all eight platforms when none is named. Use whenever the user gives post, video, project, product, or announcement details and wants captions. If the user names specific platforms, generate only those. Preserves every user-supplied fact, enforces exact character limits by running a length check, applies fixed hashtag ranges per platform, and judges whether content suits Reddit before forcing a Reddit post."
---
# Social Media Multi-Platform Caption Generator

Turns raw post details into separate, platform-adapted captions. The user's input is the single source of truth. Nothing is invented. Nothing important is dropped without the Read More Details fallback.

## Step 0: Extract source facts

Before writing anything, list every piece of information in the user's input: main topic, names, people, companies, products, tools, technologies, features, technical details, numbers, statistics, dates, prices, versions, results, benefits, problems, solutions, instructions, links, CTAs, warnings, comparisons, and any claims the user made.

Check every caption against this list in Step 5. If a detail is unclear, leave it out. Do not guess.

## Step 1: Determine which platforms to generate

**Default: generate all eight platforms.** "Create all" is the default, not a phrase the user has to type.

- No platform named: generate all eight (Reddit, Facebook, LinkedIn, YouTube, X, Threads, Instagram, TikTok). This applies to requests like "generate captions" or "make posts for this".
- One or more platforms named (for example "only LinkedIn and X", "give me an Instagram caption", "just TikTok and Threads"): generate only those. Do not add others.
- "X Premium" modifies the X platform. If the user says only "X Premium" with no other platform, generate all eight and use the 25,000-character limit for X, unless context shows they want X alone.

## Step 2: Reddit suitability check (run before drafting Reddit)

**Suitable:** technology, cybersecurity, programming, AI, software, tutorials, technical projects, questions, discussions, useful discoveries, educational content, relevant personal or project experience.

**Not suitable:** pure promotional or ad content, generic lifestyle posts, Instagram-style captions with no discussion value, content clearly meant for one platform only.

- Suitable: draft it normally.
- Not suitable: output this block and do not force a low-quality post.
  ```
  Reddit

  Not recommended for this content.
  Reason: [short factual reason]
  ```
- If the user explicitly asks for Reddit despite unsuitability, write the best possible version without inventing content to make it fit.

## Step 3: Draft each platform in its own style

Facts stay identical across platforms. Only presentation changes. Do not copy one caption into every platform.

### Platform style guide

**Reddit (limit 40,000)**
- Clear title when appropriate, strong opening, natural paragraphs.
- Technical detail is welcome. Informative, human tone.
- No marketing language, no excessive emojis, no hashtag spam.
- Reads like a real post from a Reddit user, not an ad.

**Facebook (limit 63,206)**
- Strong opening line, short paragraphs, natural spacing.
- Emojis only when they add clarity.
- Practical language, clear CTA when needed.
- Mobile-readable. Avoid dense unbroken blocks of text.

**LinkedIn (limit 3,000)**
- Strong first line, short paragraphs, professional tone.
- Technical or business context drawn only from supplied information.
- No exaggerated corporate language. No invented achievements or experience.

**YouTube**
- Title (limit 100): states the topic accurately. No clickbait claims unsupported by the source.
- Description (limit 5,000): keeps the important source information in full where it fits. Use the CTA if it does not fit.

**X (standard limit 280, Premium limit 25,000)**
- Standard: strongest hook first, extremely concise, highest-value facts only.
- Premium (only if the user says so): more room for detail.
- Count the CTA and URL in the total. On standard X this usually means either the CTA or the full message, rarely both plus extensive detail.

**Threads (limit 500)**
- Strong, conversational opening. Natural formatting, not a press release.
- Do not overstuff 500 characters.

**Instagram (limit 2,200)**
- Strong opening line, short paragraphs, useful line spacing.
- Emojis where they aid readability, not as filler.
- Clear CTA. Hashtags tied directly to the actual topic.

**TikTok (limit: configured value, see TikTok limit note in Step 4)**
- Strong hook, short readable structure, relevant CTA.
- Never claim "viral", "trending", or "everyone is using this" unless the user supplied that claim.

**Universal rules**
- No fake stats, testimonials, results, quotes, or unsupported claims.
- Do not change the factual meaning of anything the user supplied.
- No machine-sounding phrasing or generic AI-style intros.
- Do not repeat the same sentence reworded to pad length.

### Hashtag ranges (ceilings, not targets)

| Platform | Range |
|---|---|
| Reddit | 0 (only if the user explicitly requests) |
| Facebook | 2-5 |
| LinkedIn | 3-5 |
| YouTube | 3-5 |
| X standard | 0-2 (only if they fit naturally) |
| X Premium | 0-5 |
| Threads | 2-3 |
| Instagram | 5-8 |
| TikTok | 4-6 |

Use fewer if fewer relevant hashtags exist. Never invent a hashtag that implies a fact the user did not give. If hashtags would push important content past the limit, cut hashtags before content.

### Read More Details CTA: decision process

Use exactly: `Read More Details: https://www.facebook.com/ManulaNirwanOfficial`
Never alter, shorten, or replace this URL.

1. Try to fit all important information first.
2. If the complete version fits the platform limit, publish it. Do not add the CTA for decoration.
3. If it does not fit, apply this priority order, trim from the bottom up, and add the CTA near the end:
   1. Main topic
   2. Critical facts
   3. Names and entities
   4. Important numbers and dates
   5. Main result or benefit
   6. Important technical details
   7. Supporting details
   8. CTA
   9. Hashtags
4. If adding the CTA pushes the post over the limit, cut lower-priority supporting details and hashtags first. Never cut the CTA. Never leave a half-finished sentence.
5. On very short platforms (X standard, Threads), if the CTA still cannot fit after trimming everything else, drop the CTA and keep the strongest core message instead of publishing a broken post.

The CTA is a fallback for content that does not fit. It is not a default addition.

## Step 4: Validate character counts by running code

Do not estimate counts by eye. For each caption:

1. Write the exact final text (hashtags, CTA, URLs, emojis included) to a file, for example `draft.txt`.
2. Run this command, replacing `PLATFORM_KEY` and `draft.txt`:

```bash
python3 - PLATFORM_KEY draft.txt <<'PY'
import sys
TIKTOK_CAPTION_LIMIT = 2200  # configured placeholder, not verified
LIMITS = {
    "reddit": 40000, "facebook": 63206, "linkedin": 3000,
    "youtube_title": 100, "youtube_description": 5000,
    "x_standard": 280, "x_premium": 25000, "threads": 500,
    "instagram": 2200, "tiktok": TIKTOK_CAPTION_LIMIT,
}
key, path = sys.argv[1].lower(), sys.argv[2]
if key not in LIMITS:
    sys.exit("Unknown key. Valid: " + ", ".join(LIMITS))
text = open(path, encoding="utf-8").read()
if text.endswith("\n"):
    text = text[:-1]
n, limit = len(text), LIMITS[key]
print(f"Platform: {key}\nLimit: {limit}\nCharacter count: {n}\nRemaining: {limit - n}")
if n > limit:
    print(f"RESULT: OVER by {n - limit}. Shorten and re-check.")
    sys.exit(1)
print("RESULT: OK")
PY
```

Platform keys: `reddit`, `facebook`, `linkedin`, `youtube_title`, `youtube_description`, `x_standard`, `x_premium`, `threads`, `instagram`, `tiktok`.

3. If the result is `OVER`, trim using the Step 3 priority order, rewrite, and run again. Repeat until `OK`.
4. Include the caption in the final output only with the exact count the command printed.

If you cannot run code in the current environment, do not report a count as exact. State: "Character count could not be programmatically verified." Keep the draft near 90% of the limit as a safety margin.

### TikTok limit note

TikTok's caption limit has changed several times (300, then 2,200, then reportedly 4,000 in some sources). Different TikTok surfaces may enforce different limits, and sources disagree. The value `TIKTOK_CAPTION_LIMIT = 2200` is a conservative placeholder, not a verified maximum.

- Never call it "the current verified TikTok limit".
- When reporting the TikTok count, state that the limit is a configured value and that the user should confirm the current limit in TikTok's own documentation if precision matters.
- If the user gives a confirmed limit, use their number in place of 2200 in the command and in the output line.

## Step 5: Final validation pass

Before returning output, check every caption against the Step 0 fact list:

- No important fact is omitted (unless intentionally deferred behind the CTA).
- Names, numbers, dates, and product or technology names are correct and unchanged.
- No invented facts, statistics, features, quotes, results, or claims.
- URLs are exactly as supplied.
- Each caption reads as written for its platform, not copied.
- No unnecessary CTA.
- No hashtag stuffing beyond the ranges above.
- Character count confirmed by running code, or flagged as unverified.

## Output format

```
Reddit

[post, or "Not recommended" block]

Character count: X / 40,000

---

Facebook

[post]

Character count: X / 63,206

---

LinkedIn

[post]

Character count: X / 3,000

---

YouTube

Title:
[title]
Title character count: X / 100

Description:
[description]
Description character count: X / 5,000

Hashtags:
[hashtags]

---

X

[post]

Character count: X / 280 (or / 25,000 if Premium)

---

Threads

[post]

Character count: X / 500

---

Instagram

[caption]

Character count: X / 2,200

---

TikTok

[caption]

Character count: X / [configured TikTok limit] (configured value, not independently verified as TikTok's current limit)
```

## Special commands

- **"Create all"**: confirms the default. All 8 platforms.
- **"Only [platform]"** or naming specific platforms: those platforms only.
- **"Make X shorter"**: rewrite only X, then re-run the length check.
- **"Make it more professional"**: adjust tone for the named platform, facts unchanged.
- **"Keep every detail"**: apply priority-order trimming as far as possible before touching content. Use the CTA more readily.
- **"X Premium"**: use the 25,000-character limit and the 0-5 hashtag range.
- **"Short version" / "Long version"**: adjust target length within the platform's real limit. Still validate by running the check.
