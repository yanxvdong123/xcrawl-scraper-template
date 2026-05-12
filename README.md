# XCrawl Open Source Scraper Templates

Ready-to-use scraping templates for developers.

## Templates

| Name | Language | Description |
|------|----------|-------------|
| `node-basic` | Node.js | Minimal scraper — 1 file, 30 lines |
| `python-basic` | Python | Same in Python |
| `typescript-sdk` | TypeScript | Full SDK usage example |
| `react-app` | JS (frontend) | Scraper UI for demo purposes |
| `express-api` | Node.js | Self-hosted API wrapper around XCrawl |
| `fastapi-wrapper` | Python | Same in Python (FastAPI) |
| `nextjs-demo` | TypeScript | Next.js app showing scraping results |
| `scheduled-worker` | JS | Cron-job based scraper |
| `danfojs-analysis` | JS | Scrape → analyze in browser |

## Quick Start: Node Basic

```javascript
// node-basic/scrape.js
const axios = require('axios');

const API_KEY = process.env.XCRAWL_API_KEY || 'your-key';
const URL = process.argv[2] || 'https://example.com';

axios.post('https://api.xcrawl.com/v1/scrape', {
  url: URL,
  format: 'markdown',
}, {
  headers: { 'X-API-Key': API_KEY },
}).then(res => console.log(res.data.content))
  .catch(err => console.error(err.message));
```

## Quick Start: Python Basic

```python
# python-basic/scrape.py
import os
import sys
import requests

api_key = os.environ.get("XCRAWL_API_KEY", "your-key")
url = sys.argv[1] if len(sys.argv) > 1 else "https://example.com"

resp = requests.post(
    "https://api.xcrawl.com/v1/scrape",
    json={"url": url, "format": "markdown"},
    headers={"X-API-Key": api_key},
)
print(resp.json().get("content", resp.text))
```

## GitHub Repository

All templates published at: https://github.com/yourusername/xcrawl-scraper-templates

## License

MIT — free to use, modify, and share.
