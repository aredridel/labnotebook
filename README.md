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
