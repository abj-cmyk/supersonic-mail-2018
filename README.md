# Supersonic

Email, with a little more breathing room.

An independent, MIT-licensed recreation of the focused, keyboard-first spirit of 2018 Superhuman. A working frontend demo built with plain HTML, CSS, and JavaScript. No dependencies, build step, account, API key, or subscription.

**This is a browser-local demo, not a connected email client.** The inbox is sample data. Sending saves a message to the local Sent folder; it never sends email. The calendar is illustrative, and attachment previews are placeholders. It is independently implemented and is not affiliated with Superhuman.

[Source code](https://github.com/abj-cmyk/supersonic-mail-2018)

## Run it

```sh
npm start
```

Open http://127.0.0.1:3000. Requires Node.js 18 or newer. Alternatively, serve `dist/` with any static server:

```sh
python3 -m http.server 3000 --directory dist
```

## What works

- Important / Other split inboxes and unread filtering
- Conversation reader and replies
- Instant full-text search across all sample mail folders
- Command palette with arrow-key navigation and filtering
- Compose, auto-saving drafts, and local demo sending
- Done / archive, stars, custom labels, and undo (up to 20 actions per session)
- Snooze with presets or a chosen date; messages return while the app is open, or when reopened after the reminder time
- Inbox, Starred, Snoozed, Sent, Drafts, Done, and label views
- Focus mode, calendar navigation, daily overview, and responsive navigation
- Persistent messages, drafts, labels, and snooze times using browser localStorage

## Keyboard shortcuts

| Key | Action |
| --- | --- |
| `J` / `K`, `↓` / `↑` | Next / previous conversation |
| `Enter` | Open selected conversation |
| `Esc` | Back or close dialog |
| `C` | Compose |
| `R` | Reply |
| `E` | Mark done / return archived message to inbox |
| `S` | Star / unstar |
| `H` | Snooze |
| `Z` | Undo |
| `/` | Search all mail |
| `Cmd+K` / `Ctrl+K` | Command palette |
| `Cmd+Enter` / `Ctrl+Enter` | Save composed message to local Sent |
| `?` | Shortcut guide |

## Source layout

- `dist/index.html` — application markup and dialogs
- `dist/styles.css` — responsive design
- `dist/app.js` — sample mail, state, persistence, and all interactions
- `server.mjs` — optional dependency-free local static server

Run `npm run check` for the JavaScript syntax check. Deploy `dist/` on any static host.

## Building on this

To turn this into a real mail client, add provider authorization, a backend mail adapter, synchronization, and server-side storage. Keep credentials out of the frontend. The current data model and UI are intentionally small enough to replace without a framework migration.

Local state is stored under `supersonic-mail-v1` in your browser. It is not encrypted or synchronized to another device. To restore the sample inbox, remove that key from the browser's site storage. Do not use this demo to store sensitive email.

## License

MIT. See [LICENSE](LICENSE). The implementation, illustrations, and icons here are original; third-party names in the sample inbox belong to their respective owners.
