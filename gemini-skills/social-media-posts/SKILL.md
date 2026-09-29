---
name: social-media-posts
description: "Write social media posts for Manula Nirwan across Facebook, Instagram, TikTok, and YouTube Shorts, covering both automotive content (MrManula Cars) and tech/AI content (Blogger, tools). Produces a caption, hashtags, a thumbnail generation prompt, and a posting time suggestion. Use this whenever Manula asks for a caption, post, hashtags, or thumbnail idea for any social platform, or says he wants to post something about a car, tech tool, or project. Ask which platform(s) if not stated."
---
# Social Media Posts

Writes ready-to-use posts for Manula's social accounts. Each post has four parts: caption, hashtags, thumbnail prompt, posting time suggestion.

## Step 1: Confirm platform and topic

If Manula doesn't say which platform, ask. If he wants the same content across multiple platforms, write a separate version for each, since caption length and tone rules differ by platform.

If the topic isn't clear (car, tech tool, project, personal update), ask briefly or infer from context.

## Step 2: Match content type to background

- **Automotive topics** (cars, MrManula Cars, racing games): use the automotive style and accounts in the manula-context skill. Punchy, high-energy tone.
- **Tech/AI topics** (Blogger tools, apps, tutorials): informative, practical tone. Explain the value in one line.
- Match tone to the topic itself, not a fixed default. A car reveal post and a tool-launch post should not sound the same.

## Step 3: Write the caption

Rules by platform:

| Platform | Caption length | Style |
|---|---|---|
| Instagram | 1-3 short sentences or a short list | Hook line first, casual |
| Facebook | 2-4 sentences, can be slightly longer | Slightly more descriptive |
| TikTok | 1-2 short sentences | Hook line, matches video energy |
| YouTube Shorts | 1-2 sentences + link/CTA | Short, direct |

General rules for every caption:
- Start with a hook, not a generic opener.
- Active voice, short sentences.
- No filler, no clichés, no em dashes.
- English by default. Switch to Sinhala only if Manula asks or the request is in Sinhala.
- Include a call to action when it fits naturally (watch, follow, comment, link in bio).

## Step 4: Write hashtags

- Instagram, Facebook, TikTok: 5-10 hashtags. Mix broad (#cars, #tech) with specific (#JDM, #AItools) and one or two branded tags (#MrManulaCars).
- YouTube (if the post is tied to a YouTube video): follow the existing rule of exactly 30 hashtags, per Manula's YouTube SEO format.
- No repeated hashtags across the set. No banned/spammy tags.

## Step 5: Thumbnail prompt

Write one AI image generation prompt for the thumbnail.

- Automotive: follow the AI video/thumbnail style in manula-context (realistic cars, real-world environment, strong lighting, high-CTR composition, cinematic angle).
- Tech/AI: clean, professional, screenshot-or-mockup style, readable text overlay concept, light theme unless topic calls for dark.
- Default aspect ratio: square 1:1 for Blogger-linked posts, 9:16 for TikTok/Shorts, ask if unclear for Instagram/Facebook.
- Keep the prompt concrete: subject, environment, lighting, camera angle, mood, any text overlay.

## Step 6: Posting time suggestion

Give one suggested day/time window based on general platform engagement patterns and the content type (e.g. car content often does well evenings/weekends, tech tutorials often do well weekday mornings/afternoons). State it as a suggestion, not a guarantee, in one line.

## Output format

Present each platform version as:

**[Platform]**
- Caption: ...
- Hashtags: ...
- Thumbnail prompt: ...
- Best time to post: ...

Keep everything else out of the output. No extra commentary, no "let me know if" filler, unless Manula asks a follow-up question.
