[00:00] Now that we've proven our site is vulnerable to XSS and that we could use that XSS to steal a document and cookie, let's fix that problem. In later lesson, I'll show you how to fix XSS in general. First, let's focus on simply protecting document.cookie.

[00:15] By default, when a browser sets a cookie, it's accessed both via either document.cookie or is sent in every request to the target domain. We can inspect the response from our server and see that when it sets cookie, it doesn't set the HTTP only flag. Let's fix that.

[00:32] We'll go over to our `index.jf` file and we'll see where the session cookie settings are saved. We'll notice that we've had `httpOnly` set to `false`. 

### index.js
```js
app.use(
  session({
    secret: "key",
    resave: false,
    saveUninitialized: true,
    cookie: {
      sameSite: "lax",
      secure: true
    }
  })
)
```

If we remove this property from our cookie configuration and hit save, clear our cookies and reload, we'll see that now the setcookie call sets the httpOnly flag.

[00:57] If we log back in and attempt to post our malicious payload again, we can see if that the XSS still succeeds, but the payload it sends does not contain the actual cookie value. Indeed, the server's unable to log anything.

[01:18] What this means is that if you don't need to access programmatically to document.cookie in your application, set the httpOnly flag when sending cookies.