# Integration Map

Last updated: 2026-03-25
Source of truth: workspace `.env` key inventory (names only, values not copied here)

## Verified categories present

### Google / Composio / Productivity
- COMPOSIO_API_KEY
- COMPOSIO_PROJECT_ID
- COMPOSIO_ORG_ID
- COMPOSIO_USER_ID
- COMPOSIO_GOOGLE_CALENDAR_AUTH_CONFIG_ID
- COMPOSIO_GOOGLE_DRIVE_AUTH_CONFIG_ID
- COMPOSIO_GMAIL_AUTH_CONFIG_ID
- COMPOSIO_MCP_GMAIL_AUTH_CONFIG_ID
- GEMINI_API_KEY
- Gmail app-password entries

### Content / Social / Publishing
- COMPOSIO_MCP_LINKEDIN_AUTH_CONFIG_ID
- TWITTER_API_KEY
- HASHNODE_BLOG_API_KEY
- DEV_TO_API_KEY
- SLACK_ACCESS_TOKEN

### App / Data / Deployment
- SUPABASE_* entries
- FLY_* entries
- VERCEL_* entries
- RAILWAY_* entries
- NETLIFY_* entries
- CLOUDFLARE_* entries
- GITHUB_* and GITLAB_* entries

### Voice / Browser / Automation tooling
- ELEVENLABS_* entries
- BROWSERBASE_PROJECT_ID
- HYPERBROWSER_API_KEY
- APIFY_* entries

## Priority mapping

### Priority 1: 3-Agent Daily Loop
Most likely live access surfaces:
- Gmail / Composio
- calendar/task-related auth config IDs
- local memory + workspace persistence

### Priority 2A: QuickBooks Time
Likely requires:
- browser/session automation path
- persistent auth/session handling
- not yet verified from `.env` inventory alone

### Priority 2B: Google Drive -> Google Tasks
Most likely live access surfaces:
- COMPOSIO_API_KEY
- COMPOSIO_GOOGLE_DRIVE_AUTH_CONFIG_ID
- COMPOSIO_GOOGLE_CALENDAR_AUTH_CONFIG_ID
- COMPOSIO_GMAIL_AUTH_CONFIG_ID / MCP Gmail config
- Gemini key may support extraction/summarization steps if needed

### Priority 3: Content Engine
Most likely live access surfaces:
- LinkedIn Composio auth config
- Twitter API key
- blog/publishing keys
- deployment tokens

## Notes
- This file records categories and likely usability only.
- Secret values should remain in `.env` and not be copied into markdown.
- Every integration must still be verified before use. Configured != working.
