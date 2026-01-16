# tiktokbotdetector
tiktok bot detector - account cleanup
------------------------------------------

If you can access TikTok data (via what TikTok exposes + what you can observe), you can detect bot-like behavior pretty well:

Account-level signals

Brand new account + tons of activity immediately

No profile pic / weird username patterns / random digits

Following 5,000 accounts, followers = 3

Very low content history, or repost-only patterns

Bio/links look templated across many accounts

Behavior signals

Likes/comments arrive in tight bursts (e.g., 50 likes in 20 seconds)

Comment text repeats across different videos (“🔥🔥🔥”, “nice”, copy/paste spam)

Same accounts appear on many of your posts within seconds of posting

Engagement comes heavily from regions/languages that don’t match your audience (not proof, but a flag)

Network signals

Clusters of accounts that always show up together

Many accounts created around same dates, behaving similarly

Comment/like timing that’s too “machine perfect”

The big constraint: TikTok access

Your “how” depends on what data you can legally and practically pull:

If you rely only on what TikTok shows publicly

You can score accounts that comment/follow you.

You won’t get a full list of everyone who liked/watched (TikTok doesn’t expose that cleanly).

It’ll be “best effort” and still useful.

If you use TikTok’s official APIs

Much safer/legit, but often limited for creator analytics and especially for enumerating engagers.

Still can work, but you build within their rules.

If you try to scrape or automate

You’ll get more data short-term, but it’s fragile and can get accounts/app blocked.

Also a compliance/legal headache.

What the app could look like (practical product)

You log in (or you paste your @handle)

The system watches new comments/follows (and optionally viewers if accessible)

It assigns a risk score and reasons:

“New account, no posts, burst-like behavior”

“Comment matches known spam template”

“Part of a cluster that hits posts within 30 seconds”

You get dashboards:

“Suspicious engagement % per post”

“Top suspicious commenters”

“Clusters detected”

Optional: export a block list / report list (manual action by you)

How accurate can it be?

Pretty good at obvious bot waves

Middling on “fake but careful” accounts

Will always have false positives (e.g., a shy real person with no posts can look fake)

If you want to build this, here’s the key question

Do you want it to work from:

your own TikTok data as a creator (if you can export / access analytics), or

publicly visible stuff only (comments/followers), or

a browser extension that runs while you’re logged in (often the most practical without breaking rules)?

If you tell me which direction you want, I’ll map out a clean architecture + the specific signals/scoring model you’d start with.
