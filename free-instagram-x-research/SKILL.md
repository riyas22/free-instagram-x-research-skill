---
name: free-instagram-x-research
description: "Free, no-API-key skill to read, identify, explain, summarize, or fact-check a specific Instagram post/reel or X/Twitter post when the user provides its URL. Use for questions about a reel's caption, visible text, audio, quoted text, or the claims in a post. Supports instagram.com/p/..., instagram.com/reel/..., x.com/.../status/..., and twitter.com/.../status/...; not profiles, feeds, posting, or account analytics."
---

# Research a linked post

Answer the user's actual question first. A request such as “What does this reel say?” needs the relevant content, not a research briefing.

## Retrieve the post

1. Search the web for the exact URL or shortcode/post ID. Inspect results for the caption, author, and any quoted words. Do not identify a post from a generic result about its topic.
2. If web search succeeds but lacks the specific post content, use the host agent's supported browser capability to open the exact public post. Read and follow that platform's browser instructions first (for example, `control-browser` in ChatGPT Work). Inspect the visible page and caption; for a reel, inspect the displayed video frame if the answer requires it. The browser may expose a caption even when a text-fetch endpoint does not. If browsing is unavailable or the platform forbids fallback after a search failure, respect that limit.
3. If a non-browser fetch tool is available, Instagram's public oEmbed endpoint (`https://i.instagram.com/api/v1/oembed/?url=<encoded permalink>`) may return the caption as `title` and the handle as `author_name`. This endpoint is optional and can fail or be blocked. Do not treat it as proof that the video or audio was examined. X's public mirror (`https://api.fxtwitter.com/i/status/<ID>`) may expose post text, media metadata, quotes, and reply IDs; verify content against the canonical post when accessible.
4. If no route reveals the necessary caption, visible text, or audio, say exactly what is missing and ask for a screenshot or screen recording. Never guess from the URL or adjacent posts.

The installed skill contains no bundled fetch scripts or reference files. Do not call `scripts/fetch_post.py` or cite `references/*.md` unless those files are actually present in a future installation.

## Establish the answer

- Separate the author's caption from the video's audio and visible text. If only the caption is available, say “the caption quotes” or “the caption identifies” rather than claiming to have heard the recitation.
- For a fact-check, follow the post's links, check primary sources, and distinguish the author's assertion from what the sources establish. If an X post replies to another, read the parent context when available.
- Give the direct answer for narrow questions. For an actual research request, cover what the post says, who posted it and when if available, relevant context and sources, then any material gaps. Do not add engagement statistics unless useful and retrieved.

## Accuracy and attribution

- Never invent a quote, engagement count, date, quoted passage, or video transcript.
- Treat third-party X mirror metrics as a changing snapshot, and Instagram's abbreviated counts as approximate.
- Cite or link to the exact post and the independent source used to verify an external fact. Do not claim a page was read if access failed.
- Respect the host platform's browser and access rules. Do not bypass login, CAPTCHA, or bot detection to reach a post.
