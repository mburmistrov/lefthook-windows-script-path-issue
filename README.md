# Lefthook Windows script path issue demo
This repository is a demo for an issue with https://github.com/evilmartians/lefthook on Windows starting v1.7.16/v1.8.0.

## Reproduction steps
**Step 0:** Use Windows. 

**Step 1:** Clone the repository. 

**Step 2:** Run `npm install`. 

**Step 3:** Try to commit a change, e.g.  
```bash
echo hi >> example
git add example
git commit -m 'Test commit'
``` 

**Step 4:** Instead of a successful commit, see an error like below
```
Error: Cannot find module 'C:\Users\mmb\lefthook-windows-script-path-issue\'C:\Users\mmb\lefthook-windows-script-path-issue\.lefthook\commit-msg\hello-world.js''
at Module._resolveFilename (node:internal/modules/cjs/loader:1212:15)
at Module._load (node:internal/modules/cjs/loader:1043:27)
at Function.executeUserEntryPoint [as runMain] (node:internal/modules/run_main:164:12)
at node:internal/main/run_main_module:28:49 {
code: 'MODULE_NOT_FOUND',
requireStack: []
}

Node.js v20.19.0
┃  hello-world.js ❯


exit status 1
────────────────────────────────────
summary: (done in 0.10 seconds)
```

## Notes
- Log of a failed command is in `verbose-log.txt` file.
- Tested on Lefthook v1.11.3 and Windows 10 x64.
- The issue reproduces on different PCs.
- The issue reproduces both in PowerShell and Git Bash.
- On macOS everything is okay.
- On Lefthook v1.7.15 everything is okay.
