## slashdot-fetch

rss reader. terminal ui. vim keys.

```
brew install slashdot-fetch
```

or

```
cargo install slashdot-fetch
```

### usage

```
slashdot-fetch
```

keybindings:

```
j/k     scroll
enter   open article
o       open in browser
r       refresh
q       quit
/       search
```

### feeds

edit `~/.config/slashdot-fetch/feeds.txt`:

```
https://hnrss.org/frontpage
https://lobste.rs/rss
https://reddit.com/r/rust/.rss
```

### features

- offline reading (cache articles)
- mark as read
- export to markdown
- fuzzy search

### config

`~/.config/slashdot-fetch/config.toml`:

```toml
update_interval = 30  # minutes
max_articles = 100
browser = "firefox"
```

### sync

sync read status across machines via **syncfile-proto** ([syncfile-proto.dev](https://syncfile-proto.dev))

```bash
slashdot-fetch sync --remote user@server:/path/
```

### export

```bash
# export unread to markdown
slashdot-fetch export --unread > articles.md

# export specific feed
slashdot-fetch export --feed "Hacker News" --format json
```

### troubleshooting

**feeds not updating?**
check internet connection, or clear cache: `rm -rf ~/.cache/slashdot-fetch`

**encoding issues?**
set `LANG=en_US.UTF-8` in shell

**slow startup?**
reduce `max_articles` in config

### alternatives

- newsboat (more features, harder to configure)
- rss2email (different workflow)
- feed reader apps (gui, not terminal)

MIT

# PR Merge: 2025-11-01 07:40:24
