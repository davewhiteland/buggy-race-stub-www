# buggy-race-stub-www

This is a static GitHub Pages Jekyll site ([how/what?](https://docs.github.com/en/pages))
that can be deployed as a stub when the buggy race server is not running. This
is useful at RHUL because we don't need to run the server in terms 1 and 2.

* [Buggy Racing documentation for this repo](https://www.buggyrace.net/docs/shutdown/placeholder)

At such times, we change the DNS CNAME record for `<subdomain>.buggyrace.net`
to point at the GitHub pages domain (`<username>.github.io`), give it enough
hours to propogate through the internets, and then teardown the Heroku site
(in Heroku parlance: _delete the app_). (That also means we stop paying for
the it, you see).

This static site is just an index page (with a similarly-styled 404 page
to capture any requests coming from URLs that were (rightly) linking to
race server while it was running).

When it's time to run the race server again, we'll fire it up (probably
but not necessarily on Heroku) and change the DNS record to point at the
active server again.

---

[Instructions managing a custom domain on GitHub Pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)
(TLDR: go to _Settings_ and switch _Pages_ on after telling it the (subdomain)
URL it's running on. You'll need to do some verification that you have access
to both the DNS record and the GitHub repo of course (if you haven't already).

