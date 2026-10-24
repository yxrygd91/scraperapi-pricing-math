# web scraping tool online: how the credit math really works, which plan fits your project, and where ScraperAPI beats (or loses to) the alternatives

Most people searching for a web scraping tool online want the same three things answered: will it get through anti-bot walls, what does it actually cost at scale, and can I try it without a credit card. The short version: browser extensions and no-code scrapers handle small one-off jobs, but for anything you run repeatedly against protected sites — Amazon, Google, LinkedIn — an API service that rotates proxies and handles CAPTCHAs server-side is the realistic option. One of the most established in that category is **ScraperAPI**: 7-day trial with 5,000 credits and no card required, paid plans from $49/month, and a credit system whose fine print matters more than the headline price.

> **Quick pick:** If you're a developer or run scheduled scrapes against sites with bot protection, the **Business plan at $299/month** (3,000,000 credits, 100 concurrent threads, country-level geotargeting) is where most production workloads land. Lighter testing fits the free plan or 7-day trial first — every paid plan includes JS rendering, premium proxies, and CAPTCHA handling. 👉 [Start the 7-day free trial — 5,000 credits, no credit card](https://www.scraperapi.com/signup?fp_ref=coupons)

## What "online" actually means: three kinds of tools, three different jobs

A web scraping tool online generally falls into one of three camps, and picking the wrong category wastes more money than picking the wrong brand.

**API services** (ScraperAPI, ScrapingBee, Infatica) take a URL and an API key, and return clean HTML or structured data. The provider runs the proxy pools, headless browsers, and CAPTCHA solving on their infrastructure. You write a few lines of code and never think about IP rotation.

**No-code apps and cloud platforms** (Octoparse, ParseHub, Apify) give you a visual interface or a marketplace of pre-built scrapers. Good for analysts who don't write code. Octoparse's free plan, for example, is a genuine no-expiration free tier: 10 crawler slots, 2 concurrent local runs, up to 10,000 records per export, capped at 50,000 records per month.

**Browser extensions** (webscraper.io) run locally in your browser and are free with no page cap — but they only work while your browser is open and your own IP is doing the requesting. Fine for a 200-row table you need once. Not fine for monitoring 10,000 product pages daily.

One recent analysis of AI-era scraping tools put the cost problem bluntly, and it applies across categories: cost blows up through multipliers, not the headline price. Whole-site crawls, structured output, and daily re-runs stack into hundreds of thousands of credits. That's why the credit system below deserves more attention than the monthly fee.

## ScraperAPI plans and pricing: the full current lineup

ScraperAPI publishes seven tiers. Annual billing takes 10% off every plan automatically. All plans include JS rendering, premium proxies, JSON auto parsing, rotating proxy pools, custom headers, CAPTCHA and anti-bot detection, session support, automatic retries, unlimited bandwidth, and a 99.9% uptime guarantee.

| Plan | API credits | Concurrent threads | Monthly | Annual (per month) | Link |
| --- | --- | --- | --- | --- | --- |
| Hobby | 100,000 | 20 | $49 | $44.10 | [ Get Hobby](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Startup | 1,000,000 | 50 | $149 | $134.10 | [ Get Startup](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Business | 3,000,000 | 100 | $299 | $269.10 | [ Get Business](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Scaling | 5,000,000 | 200 | $475 | $427.50 | [ Get Scaling](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Professional | 10,500,000 | 300 | $975 | $877.50 | [ Get Professional](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Advanced | 21,500,000 | 500 | $1,975 | $1,777.50 | [ Get Advanced](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Enterprise | 22,000,000+ | 500+ | Custom | Custom | [ Contact Sales](https://www.scraperapi.com/pricing/?fp_ref=coupons) |

The free plan sits outside this table: 1,000 credits per month with a maximum of 5 concurrent connections, no credit card. If you need extra credits just for testing, support can grant them on request.

Under the hood, the proxy pool exceeds 150 million IPs across datacenter, residential, and mobile types, covering 150 countries, with ML-driven proxy selection handling the rotation so your code doesn't have to.

## The credit math most reviews skip

This is where ScraperAPI's real pricing lives, and it's the part almost no comparison table shows you.

A standard page costs 1 credit. But harder targets have custom pricing:

- **Amazon: 5 credits per request**
- **Google and Bing (including subdomains): 25 credits**
- **LinkedIn: 30 credits**
- **Sites behind Cloudflare, Datadome, or PerimeterX: +10 credits per request** when the protection is bypassed

Run those numbers against the Hobby plan and the picture changes fast. 100,000 credits is 100,000 standard pages — or 20,000 Amazon pages, or only 4,000 Google searches, or roughly 3,300 LinkedIn pages. If most of your target URLs sit behind Datadome, each request burns 11 credits instead of 1, and your plan shrinks by about 90% without any warning on the checkout page.

Two tools keep this under control. The Domain Cost Estimator in the dashboard shows the exact cost of any URL before you run it. The `max_cost` parameter caps what any single request can spend. Set both before your first big batch — it's the difference between a predictable bill and a surprise upgrade.

Three escape valves exist when credits run out:

1. **Default behavior:** scraping pauses until credits renew.
2. **Auto-upgrade** (Hobby through Professional, opt-in): your account automatically moves to the next plan.
3. **Pay-as-you-go** (Scaling through Enterprise): keep scraping at a fixed per-credit rate up to a monthly spending cap you set.

One more thing worth knowing before you commit: exceeding concurrent threads returns a 429 and the request is rejected rather than queued — you retry it yourself at no charge. 👉 [Check the current plan prices and annual discounts](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## Real total cost: what year one and year two actually look like

The 10% annual discount is applied at checkout with no code. Here's what the two most common plans cost over time:

- **Hobby:** monthly billing costs $588 over a year; annual billing costs $529.20 — saving $58.80. Year two is the same $529.20 (no renewal price hike is published).
- **Business:** monthly billing costs $3,588 over a year; annual billing costs $3,229.20 — saving $358.80. On a spend this size, that difference funds hundreds of thousands of additional standard-page requests at Business-tier rates.
- **Professional:** $11,700 monthly vs. $10,530 annual — a $1,170 gap.

The decision rule follows from the trial: run real requests against your actual targets during the 7 days, watch the credit burn in the dashboard, then pick the tier your burn rate implies — not the tier your URL count implies. URL count and credit count diverge badly on Google, Amazon, and protected sites.

## Running it on a schedule: DataPipeline

Unattended production scraping is where the API alone stops being enough, and it's rarely mentioned in comparison articles. ScraperAPI's DataPipeline is a cloud-hosted scheduler: each project can run up to 10,000 URLs concurrently, and you can build looped jobs from keywords, Amazon ASINs, or Walmart IDs. Results come back as JSON or CSV, or get pushed to a webhook. A visual interface plus dedicated scheduling endpoints handle precise timing, and the dashboard lets you monitor progress, cancel tasks, review configurations, and download data without any third-party tooling.

For anyone choosing between "I'll cron-job it myself" and a managed pipeline, the distinction matters: DataPipeline runs on ScraperAPI's infrastructure, so scheduled jobs don't compete with your own servers or local machine. There's also a Render Instruction Set — a JSON object sent in the request header that tells the controlled headless browser how to interact with the page before it returns.

## How ScraperAPI compares with the alternatives

Pricing below was verified in recent third-party comparisons (mid-to-late 2026); confirm current rates before deciding, since providers adjust frequently.

| Tool | Type | Starting price | Free tier | Code required |
| --- | --- | --- | --- | --- |
| ScraperAPI | API | $49/month | 1,000 credits/mo + 5,000-credit trial | Yes |
| Apify | Platform | $29/month | $5 in monthly usage | Optional |
| Oxylabs | Platform | $49/month | Trial with up to 2,000 results | Yes |
| ScrapingBee | API | $49/month (150k credits) | 1,000 credits | Yes |
| Infatica | API | From $18/month | 7-day trial, 5,000 successful requests | Yes |
| Bright Data | Platform | $1.50/1k records (PAYG) or $499/mo | 5,000 shared monthly credits | Yes/No |
| Firecrawl | LLM-native API | $16/month billed annually | 1,000 credits/mo | Yes |
| Octoparse | No-code app | $83/month ($69 annual) | Free plan, no expiration | No |
| ParseHub | No-code app | $189/month | Free, 5 projects | No |

Where each one makes more sense than ScraperAPI: Apify at $29/month is cheaper if you mainly want pre-built scrapers someone else maintains. Bright Data's Web Scraper API at $499/month includes maintained scrapers for 1,000+ sites and unlimited concurrency — an enterprise-scale play with a steeper learning curve and less uniform billing units. Octoparse or ParseHub fit non-coders who'd never touch an API. Firecrawl targets RAG and LLM pipelines specifically, where Markdown output matters more than anti-bot muscle.

Where ScraperAPI holds its ground: at $299/month, the Business plan's 3,000,000 credits translate to 600,000 e-commerce requests or 120,000 SERP requests by the company's own math — and per that same company comparison, Oxylabs' comparable Advanced tier costs $249/month with a smaller effective request allowance. Take that last part as vendor framing; the $249 price point itself is the checkable fact. Infatica's entry plan starts at $18/month, $31 less than Hobby, but its only free tier is the trial; ScraperAPI's permanent 1,000 credits/month is unusual among API competitors, most of which gate everything behind paid plans after the trial.

## Trial, discounts, and where coupon-site claims fall apart

ScraperAPI's own checkout offers two savings: the 7-day free trial (5,000 credits, no card) and the automatic 10% annual discount. There is no rotating public coupon program.

The codes floating around aggregator sites mostly come from three places: affiliate-negotiated codes, coupon sites republishing each other, and forum posts with no proof of validity. Most of the dramatic claims don't survive checking. The one code repeatedly verified across multiple sources through 2026 is **START10** — 10% off your first month for new users on any paid plan. Codes like it are reserved for new accounts, so they generally won't apply to an upgrade on an existing subscription.

The practical order of operations:

1. Sign up and start the trial — 5,000 credits, no card required.
2. Run real requests against your actual targets and watch the burn rate.
3. Subscribe on annual billing for the automatic 10%.
4. If a first-month code is available and stackable, apply it at checkout; if it doesn't stack, you still keep the annual discount. 👉 [Activate the free trial and see current discounts](https://www.scraperapi.com/signup?fp_ref=coupons)

## The fine-print limits (and who shouldn't buy this at all)

Three restrictions live below the main pricing table and affect real decisions:

- **Geotargeting:** Hobby and Startup are limited to US & EU locations only. Country-level geotargeting anywhere in the world starts at Business ($299/month).
- **Analytics retention:** lower tiers only keep 30 days of analytics history; Business and up get unlimited.
- **Concurrency is hard:** hitting the thread cap means rejected requests, not queuing. Long-running parallel jobs need to budget thread count explicitly.

Honest "not for you" cases: if your targets are static, unprotected pages and you scrape once a week, a free browser extension or a Python script with BeautifulSoup costs nothing and works fine. If you can't write any code and need recurring scheduled extraction, a no-code tool with a genuine free plan fits better. And if you're feeding an LLM agent with page text rather than fighting bot walls, lighter tools built for that purpose start around $16/month. API services charge for anti-bot infrastructure you may not need.

A more neutral risk to keep in mind: anti-bot bypass is getting more contested. Cloudflare, which says it handles traffic for roughly 20% of the web, now asks every new site whether AI crawlers may read it. Whatever tool you pick, keep scraping within the legal and terms-of-service boundaries of your targets.

## FAQ

**Is the free plan really free forever?** Yes — 1,000 API credits per month with up to 5 concurrent connections, no card. During the 7-day trial your balance is 5,000 credits; afterward the free plan reverts to 1,000 per month.

**What happens when my credits run out mid-month?** Scraping pauses by default until renewal. Hobby through Professional can opt into auto-upgrade; Scaling and above can enable pay-as-you-go up to a self-set monthly cap.

**How many requests do I actually get?** It depends entirely on target mix. Standard pages cost 1 credit; Amazon 5; Google and Bing 25; LinkedIn 30; bypassing Cloudflare, Datadome, or PerimeterX adds 10 per request. The dashboard's Domain Cost Estimator gives exact numbers per URL.

**Does annual billing change the credit allowance?** No — same credits and threads, just 10% off the price.

**Can I scrape Google search results?** Yes, but at 25 credits per request. On the Startup plan's 1,000,000 credits, that's about 40,000 Google searches per month.

## Final picks before you commit

- **Just getting started or scraping simple sites:** stay on the free plan and the 7-day trial — the trial's 5,000 credits cost you nothing and no card is involved.
- **Production scraping of Amazon/e-commerce targets:** Hobby ($49) or Startup ($149) cover 20,000–200,000 Amazon pages per month; annual billing trims 10%.
- **SERP tracking or mixed targets with bot protection:** Business at $299/month is the first tier with country-level geotargeting and unlimited analytics, and its 3M credits absorb the 25–30x cost of Google and LinkedIn requests.
- **10M+ credits, hundreds of concurrent threads, or unpredictable spikes:** Scaling ($475) through Advanced ($1,975) add pay-as-you-go; Professional ($975) sits in the middle with both high volume and the auto-upgrade safety net.

Before paying, do one last check with the Domain Cost Estimator on your top five URLs — if they're mostly Google or protected sites, size the plan on credits-per-request, not raw page counts. When the numbers check out, 👉 [pick your plan and start with the 5,000-credit free trial](https://www.scraperapi.com/signup?fp_ref=coupons)
