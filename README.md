# git abia

Austin is awesome. ABIA (Austin-Bergstrom International Airport), not so much.

One thing that sucks about ABIA is that the wireless there blocks the ports
used by ssh and git protocols, meaning that if your git remotes are set to one
of those, you are screwed. The solution is to use https, but there are good
reasons to not want to use that always (e.g., the other two do not require a
password), and regardless, it's a pain to switch your remotes when all you
want to do is get some work done while you're waiting for you plane.

git abia solves this by automatically switching your remotes to use https. To
use, just replace a command like

```bash
$ git fetch remotename
```

with

```bash
$ git abia fetch remotename
```

## Installation

Just put git abia somewhere on your `PATH`. git will automatically pick it up.

## Notes

This works with GitHub urls. It will work with other services if they use the
same url format.

It works by using `git remote set-url` to temporarily change `git@` and
`git://` urls to `https://`, and then setting them back.  Note that you may
have to enter your GitHub username and password, especially if you are
pushing.

I suck at bash. I just wrote this up on a plane one day after sitting in
ABIA. If you know how to do this better, pull requests are welcome.

## License

MIT license. See the LICENSE file.
