# Japan Overseas Dependents Check

Free checker for Japan's income-tax deductions for relatives living outside Japan (国外居住親族の扶養控除等): who qualifies by age, the ¥380,000 remittance rule for ages 30-69, 2026 amounts under the new ¥620,000 income limit, spouse and specified-relative tables, and the documents your employer needs at the year-end adjustment.

- Full app and API (Vercel): https://japan-overseas-dependents.vercel.app
- Checker (GitHub Pages): https://akiba-labs.github.io/japan-overseas-dependents/
- Keyless JSON API: `GET /api/check?relationship=parent&age=62&remittanceTotal=450000`
- Rules: `/api/rules` · OpenAPI: `/openapi.json` · `/llms.txt` · `/.well-known/ai-plugin.json`
- MCP: `japan_overseas_dependents_check` on https://free-agent-tools.vercel.app/mcp

Sources: National Tax Agency Q&A on relatives living abroad (revised Aug 2026), Tax Answers 1180/1177, 2026 year-end adjustment guide. Rules as of 2026-10-25.

**Disclaimer:** educational, not tax advice, not affiliated with the National Tax Agency. Income tax only. Your employer or tax office decides.

```
npm ci
npm test
npm run build
npm run build:pages
```

`npm run build` is the Vercel app (checker, JSON API, share pages). `npm run build:pages` writes a static `out/` for GitHub Pages and checks that internal links and assets resolve under `/japan-overseas-dependents`. Server routes stay in the repo; the Pages script only moves them aside for that build.

GitHub settings: **Settings → Pages → Build and deployment → Source: GitHub Actions**. Pushes to `main` deploy with `.github/workflows/pages.yml`. The copy-paste steps for the other tool repos are at the top of `scripts/build-pages.mjs`.
