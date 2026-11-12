# Orbs search visibility plan — Google, Bing/Copilot, ChatGPT and Claude (November 2026)

## Status and non-negotiable claims

This `docs/` folder is a **GitHub Pages-ready static site, not a live website until GitHub Pages is enabled**. It is prepared for the project URL `https://jpeg111.github.io/orbs-release/`. Orbs simulates game presence; Discord explicitly forbids simulated Quest completion without the required activity. We do not claim account safety, an undetectable interval, guaranteed reward credit, endorsement, free licensing terms, or open-source status.

## Deployment: required owner action

1. Review/merge the PR into the public `JPEG111/orbs-release` default branch.
2. In GitHub repository **Settings → Pages → Build and deployment → Deploy from a branch**, choose **main** and **/docs**, then Save. Wait for Pages to report its deployment URL.
3. Open `https://jpeg111.github.io/orbs-release/`, `https://jpeg111.github.io/orbs-release/faq.html`, `https://jpeg111.github.io/orbs-release/discord-quests.html`, and `https://jpeg111.github.io/orbs-release/sitemap.xml`. Confirm 200 responses, visible copy, canonical URLs, working links and mobile layout. If the actual URL differs, correct EVERY canonical/OG/sitemap URL before submitting it.
4. Update the public repository **About** description and Topics. Suggested About: **Orbs for Windows: independent Discord Quest scanner, game activity simulator and timed queue manager. Rewards not guaranteed.** Suggested additional Topics: `discord-quests`, `discord-orbs`, `quest-scanner`, `game-activity`, `windows-app`. Avoid keyword stuffing, inappropriate endorsements and duplicate near-synonym pages.
5. Once Pages is actually live, link it from the release README and GitHub's Website field. Keep the public release repo as the sole canonical download source.
6. Verify the Pages site in **Google Search Console** and **Bing Webmaster Tools**. Submit the sitemap URL to both, inspect the indexed URLs, and fix issues found. A sitemap is discovery assistance, not a guarantee of indexing.
7. Review **Bing Webmaster Tools → AI Performance** for grounding queries, cited pages, topics, citation share and Compare where available. In **Google Search Console**, check Search Performance and available Generative AI reporting. These only cover the supported sites/surfaces, not all of ChatGPT/Claude/Perplexity.
8. Keep the site server-rendered/static HTML and inspect CDN, DNS, firewalls and crawl logs. Don't block `OAI-SearchBot`, `Claude-SearchBot` or `PerplexityBot` if you want eligible public pages discoverable in those products. Crawler access is not a guarantee of citations. `GPTBot`/training access is separate. On `jpeg111.github.io/orbs-release/`, robots.txt at the project subpath is **not** a host-root robots file. A custom domain gives more root-level control.
9. If later using a domain you control, consider IndexNow for Bing and participating engines, with a verified host-key file. GitHub project Pages under `github.io` does **not** grant control over that host's root, so don't pretend IndexNow ownership is already configured.
10. Create a genuine full-size social preview and actual product screenshots/video, with meaningful alt text and transcript. Do not invent customer ratings, reviews, screenshots or competitive benchmark results.

## 2026 evidence

- Google's generative-AI search guidance says standard SEO and original user-value content matter; no special llms.txt file, chunking, or FAQ schema is required. Structured data can support ordinary rich-result eligibility but is not a special AI recommendation trigger: https://developers.google.com/search/docs/fundamentals/ai-optimization-guide
- Bing released AI Performance in Feb 2026 and new Topics/Intents/Citation Share/Compare visibility during 2026: https://blogs.bing.com/search/2026/6/New-AI-Visibility-Insights-in-Bing-Webmaster-Tools-Intents-Topics-Citation-Share-Compare/
- OpenAI Search crawler docs: https://developers.openai.com/api/docs/bots
- Anthropic's separate search bot documentation: https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler
- October 2026 observational citation study (preprint, not proof of causation): https://arxiv.org/abs/2610.15033
- Discord rules: https://discord.com/safety/platform-manipulation-policy-explainer

## Primary search intents (don't create doorway pages)

| Intent | Content | Why unique |
| --- | --- | --- |
| Find the specific Orbs app | Homepage | Product identity, version, screenshots after they exist, download |
| Understand the types of Discord Quests | Quest guide | First-party classification of tasks vs actual user obligations |
| Evaluate risk, system requirements and compatibility | FAQ | Direct answers, unsupported behaviors and explicit account-risk warning |
| Check latest changes | GitHub releases | Versioned software artifacts, real change history |

Target unbranded relevant queries: `discord quest scanner windows`, `discord quests desktop play utility`, `windows game presence simulator discord`, `discord quest types desktop video stream`. Avoid treating `discord orbs` alone as a winnable first-place keyword: it describes the official currency and has strong competing navigational intent.

## Repeatable discovery and AI answer test

Create a dated baseline **before** sharing the new pages. Use separate fresh chats, not a conversation that already knows the product. Run each query in search-enabled ChatGPT, Google AI Mode, Microsoft Copilot, Claude Web Search and Perplexity, recording whether live web search occurred:

1. `What Windows apps can scan the Discord Quests list?`
2. `Can you compare Windows tools for organizing desktop Discord Quests?`
3. `Which utilities simulate Discord game Rich Presence without installing a game, and what are the risks?`
4. `How do I organize multiple Discord desktop play tasks with a queue?`
5. `Are there independent Discord Quest scanners that work with PTB or Canary?`
6. `What tools help review Discord Quest types and show what cannot be automated?`

For each engine and prompt, record date, model/search mode, region, whether Orbs is **mentioned** unprompted, whether it is actually **recommended**, source links, factual correctness and whether risks were represented. A named/branded query such as `what is Orbs?` tests brand recognition only, not unbiased discovery.

Record organic search queries, index status, impressions, clicks and AI citations where the platform provides them. Re-test after pages are indexed and after genuine reviews, demos and independent editorial coverage. No first-place result or AI recommendation can be promised; there's no shortcut to force a model's answer.

## Credible external signals

Prioritize a real screen-recorded demo with narration/transcript, honest installation/compatibility documentation and opt-in user feedback. Ask third parties for independent, balanced coverage; disclose relationships. If participating in technical communities or relevant software directories, follow their rules and share substantive troubleshooting, not mass-posted links or paid/fake reviews. No purchased links, coordinated fake recommendations, bot-generated posts or prompt injection.
