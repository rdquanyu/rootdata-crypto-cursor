# RootData Crypto for Cursor

A Cursor skill for factual Web3 research using RootData's dedicated Skill API.
It queries projects, investors, public professional profiles, recent funding,
upcoming crypto events, RD and X rankings, stock contract exchange rankings,
and personnel changes. It provides research data, not trade execution.

## Installation and use

Import this public GitHub repository using Cursor's plugin marketplace import
flow (Customize → From GitHub Repository), then install `rootdata-crypto`.
This repository includes a Cursor plugin manifest and a marketplace manifest.
It can also be submitted for review at https://cursor.com/marketplace/publish.
Marketplace availability depends on Cursor's review; this repository alone
does not mean the plugin is approved or listed.

Example requests:

- Find Ethereum's project details, team and investors.
- 查询最近一个月的加密项目融资记录，并注明来源。
- List crypto events for the next five days.
- Compare the RD Hot Index and RD Growth Index rankings.

## Access and configuration

The skill uses HTTPS POST requests to `https://api.rootdata.com/open/skill`.
No MCP installation or paid OpenAPI subscription is needed. The runtime needs
network access and an HTTP or shell tool. Reuse `ROOTDATA_SKILL_KEY` from the
environment or local secret storage. If absent, the skill describes how to
request a key via `/init` and store it locally. Do not commit or share keys.
Initialization is limited to three keys per IP per 24 hours. Data calls are
limited to 200 requests per key per minute. Respect throttling responses.
The service receives the query arguments needed to return the requested data.

## Coverage and limits

The twelve endpoints are documented in `skills/rootdata-crypto/references/`.
Calendar queries cover today plus four days in Asia/Shanghai and exclude
macroeconomic events. Funding queries cover the latest six calendar months,
with up to five investors per round. Missing data should not be treated as
zero. RD heat is an index, not a count of searches. Cite returned source URLs.

## Support and service policies

- Website: https://www.rootdata.com
- Support: contact@rootdata.com
- Privacy: https://www.rootdata.com/pa
- Terms: https://www.rootdata.com/ua

This repository contains only the plugin instructions, endpoint references and
brand asset. It contains no RootData backend code, account credentials or API keys.
