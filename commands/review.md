# /review — Automated Code Review

Run the following steps in order.

1. Run `git diff main` to check what has changed
2. Summarize each changed file in one line
3. Check for bugs or security issues — if none, say "None found"
4. End with one of the following verdicts:

✅ MERGE OK — Safe to merge as-is  
⚠️ CHANGES SUGGESTED — Minor issues, list them  
❌ CHANGES REQUIRED — Must fix before merging, explain why