# Security Policy

## Reporting a Vulnerability

This project is a client-side, static web app — it doesn't run a server or
store user data, so the main risks would come from third-party dependencies
(MediaPipe, Three.js, the CDNs they're loaded from) or from the app itself
mishandling camera data in a way that leaks it somewhere it shouldn't.

If you find a security issue:

1. **Do not open a public issue.**
2. Use GitHub's **[Private vulnerability reporting](../../security/advisories/new)**
   feature (Security tab → "Report a vulnerability") so it can be triaged
   before details are public.
3. Include as much detail as you can: steps to reproduce, affected browser/OS,
   and potential impact.

We'll do our best to respond within a few days and to credit you in the fix
unless you'd prefer to stay anonymous.

## Supported Versions

This project doesn't currently maintain multiple release branches — only the
latest version on `main` receives fixes.
