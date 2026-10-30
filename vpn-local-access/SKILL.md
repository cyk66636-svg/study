---
name: vpn-local-access
description: Diagnose and fix local, intranet, or Chinese websites and desktop apps losing connectivity when a VPN or proxy client starts, especially Clash Verge Rev/Mihomo on Windows. Use for requests to keep local access working alongside a proxy.
---

# VPN Local Access

Restore access to the user's named sites or apps while the proxy client remains usable. Installation of this skill changes no network settings; apply it when the user asks for diagnosis or repair. A universal guarantee is impossible across VPN clients, networks, DNS policies, and site changes. Verify the requested targets on the actual computer.

## Diagnose

1. Identify the VPN/proxy client, version, active profile, routing mode, system proxy, TUN, DNS mode, and the exact failing site or app. Treat `localhost`, a private IP, an intranet hostname, and a public Chinese website as different cases. Preserve the user's chosen client and subscription.
2. Compare the target with the client off and on. Record DNS answer, destination IP, route, browser or app error, and proxy connection decision where available. Check whether failure is DNS resolution, an unreachable route, wrong proxy choice, TLS failure, or application-specific proxy behavior. Do not infer success from the proxy configuration alone.
3. On Windows, inspect applicable system proxy/PAC bypass, WinHTTP proxy, browser proxy extensions, and `HTTP_PROXY`/`HTTPS_PROXY`/`NO_PROXY` for the affected app. A system-proxy bypass does not necessarily bypass TUN. Conversely, a TUN `DIRECT` rule does not prevent an app from explicitly using the system proxy; inspect both when both are enabled.
4. For Clash Verge Rev/Mihomo, check the active profile's rule enhancement and merge selection in `profiles.yaml`, persisted mode in `config.yaml`, and the generated core configuration. Avoid printing subscription URLs, tokens, node credentials, or full configuration files in logs or replies.

## Repair

- Prefer the smallest rule matching the failing hostname or app. Use `DIRECT` for a locally reachable target; place specific direct rules before broader proxy or reject rules. For a private-IP target, verify the route and DNS result too. If a site is reachable only through a corporate VPN, preserve that route instead of forcing `DIRECT` through the wrong interface.
- In Clash Verge Rev, use the active profile's rules enhancement (`prepend`) for persistent rules. The generated `clash-verge.yaml` is output, not the durable source. The saved outbound mode can override a subscription's `mode`; set it to `rule` through the app when possible, or carefully update its persisted config while the app is closed. In `global` mode, ordinary `DIRECT` rules do not decide traffic.
- Example for a confirmed target: `DOMAIN,portal.example.internal,DIRECT` or `PROCESS-NAME,Weixin.exe,DIRECT`. Add the actual target's domain or executable only after identifying it. Do not copy a broad Tencent or private-network allowlist onto every computer.
- If a browser uses a system proxy for the local target, add its precise hostname to that proxy's bypass configuration or PAC policy. For `localhost` and loopback, confirm bypass behavior directly. If TUN intercepts traffic, inspect the client's route exclusions and rules independently.
- If DNS gives a fake IP or public answer for an intranet name, configure the client's DNS policy or fake-IP filter for that exact domain and use the appropriate local DNS server. Do not replace the system DNS blindly or disable TUN merely to make one site work.
- Before editing, make timestamped backups of every file to be changed. Preserve subscription and user changes. Validate YAML with the installed core if possible, reload or restart the client, and check that the generated config retained the intended mode and rule order. Avoid unnecessary process termination.

## Verify and report

Test the named target with the proxy running, plus one site that should still use the proxy. For a desktop app, re-establish its connection if needed. Confirm the observed route or rule decision, not just that the UI says `rule`. If the failure remains, report the failing layer and the evidence; do not claim it is fixed. Summarize the files or settings changed, backup locations, test results, and any unverified cases.
