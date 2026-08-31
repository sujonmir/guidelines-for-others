<!doctype html>
<html lang="en"><head><meta charset="utf-8"><meta name="viewport" content="width=device-width,initial-scale=1">
<title>Retainful — Go-Live Steps</title>
<style>
:root{--b:#1a7f5a;--ink:#1c2530;--mut:#5b6672;--line:#e3e8ee;--warn:#8a5a00;--warnbg:#fff6e5}
*{box-sizing:border-box}
body{margin:0;background:#f5f7fa;color:var(--ink);font:15px/1.6 -apple-system,Segoe UI,Roboto,Arial,sans-serif}
.wrap{max-width:640px;margin:0 auto;padding:22px 18px 40px}
h1{font-size:20px;margin:0 0 4px}
.sub{color:var(--mut);margin:0 0 18px;font-size:13.5px}
.note{background:var(--warnbg);border:1px solid #f0dca8;color:var(--warn);border-radius:10px;padding:10px 12px;font-size:13.5px;margin:0 0 18px}
.card{background:#fff;border:1px solid var(--line);border-radius:12px;padding:16px 18px;margin:0 0 14px}
.tag{display:inline-block;background:var(--b);color:#fff;font-size:12px;font-weight:700;border-radius:6px;padding:2px 8px;margin-right:8px}
h2{font-size:16px;margin:2px 0 10px;display:flex;align-items:center}
ol{margin:0;padding-left:20px}li{margin:6px 0}
kbd{background:#eef1f5;border:1px solid var(--line);border-radius:5px;padding:1px 6px;font:600 13px ui-monospace,Menlo,monospace}
.ok{color:var(--b);font-weight:600}
.copy{background:#f7f9fb;border:1px solid var(--line);border-radius:8px;padding:10px 12px;margin-top:8px;font-size:13.5px}
.copy b{display:block;margin-bottom:2px}
.done{background:#eaf7f0;border:1px solid #bfe6d2;border-radius:10px;padding:10px 12px;font-size:13.5px;margin-top:16px}
small{color:var(--mut)}
</style></head>
<body><div class="wrap">
<h1>Retainful — 2 steps to go live</h1>
<p class="sub">Tracking is already live &amp; tested. Only these two dashboard clicks remain — do them from an account with <b>Edit &amp; Publish Content</b> permission (the test login can't publish).</p>

<div class="note">⚠️ Log in with the <b>owner / full-access</b> Retainful account first — otherwise the <b>Publish</b> button is blocked.</div>

<div class="card">
<h2><span class="tag">1</span> Turn on the Cart-abandoned emails</h2>
<ol>
<li>Automations → open <b>REST - Cart abandoned</b>.</li>
<li>Click the <b>Abandoned Cart</b> trigger → check <b>Customer filters</b>.</li>
<li>It should read <span class="ok">"No customer filters applied"</span> (I already removed the <kbd>Email contains retainful</kbd> test-gate). If the gate is still there → <b>Edit</b> → delete it → <b>Save</b>.</li>
<li>Top-right → <b>Publish Changes</b>. ✅</li>
</ol>
<small>Now real subscribers get the recovery email 30 min after add-to-cart (auto-stops if they check out or buy).</small>
</div>

<div class="card">
<h2><span class="tag">2</span> Finish the Checkout-abandoned flow</h2>
<ol>
<li>Open <b>REST - Cart abandoned</b> → open <b>Email 1</b> → <b>Duplicate</b> it (keeps brand + recovery link).</li>
<li>Open <b>REST - Checkout abandoned</b> → after the <kbd>Wait 1 hour</kbd> step, add a <b>Send Email</b> node → paste the duplicated email.</li>
<li>Tweak the wording to a "you were one step away at checkout" tone (copy below).</li>
<li>Top-right → <b>Publish Workflow</b>. ✅</li>
</ol>
<div class="copy">
<b>Subject:</b> You're one step away 👀
<b>Body:</b> Hi {{first_name|there}}, you made it all the way to checkout — your items are still saved. Pick up right where you left off. [ Complete my order → ] &nbsp;— Swiss Tides
</div>
</div>

<div class="done">✅ After both publish: tell Retainful support it's fixed so they can run their final test.</div>
</div></body></html>
