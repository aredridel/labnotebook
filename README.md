# Sun Oct 26 18:13:36 EDT 2014

My god, the `express-session` store interface is terrible.

# Mon Oct 27 21:47:38 EDT 2014

I keep making the same higher order function over and over.

```
function errTo(errcb, resultcb) {
    return function (err, result) {
        if (err) {
            errcb(err);
        } else {
            resultcb(result);
        }
    };
}
```

Guess I'll make a module now.

Oh, hey, [iferr](https://github.com/shesek/iferr).

# Tue Oct 28 23:02:04 EDT 2014

I've a controller `next.js` that just has a `router.get('/*'` in it. If I pass the URL `/next/http://foo.bar` to it, `req.params[0]` is `http://foo.bar`.  If I pass `/next/http://foo.bar/`, `req.params[0]` is `/next/http://foo.bar`.

Very weird.

# Wed Oct 29 01:03:31 EDT 2014

Turns out to be a broken check for `://` in URLs; ultimately decided to just
skip checking if the URL starts with `/`. URL parsing in Express is magical,
but it's mostly usable magic. PR made.

