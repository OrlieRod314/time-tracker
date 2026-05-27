# time-tracker

A terminal UI for logging time against charge codes, one CSV log per day.

## Requirements

`whiptail` (pre-installed on most Debian/Ubuntu systems) or `dialog`:

```
sudo apt install whiptail
```

## Usage

```
./timetrack
```

Or put it on your PATH:

```
sudo ln -s "$(pwd)/timetrack" /usr/local/bin/timetrack
```

## Data

| Path | Contents |
|------|----------|
| `~/.config/time-tracker/codes` | Charge codes (`CODE:Description`, one per line) |
| `~/.local/share/time-tracker/YYYY-MM-DD.csv` | Daily log, one session per row |

Log format: `timestamp,code,description,seconds`

Respects `$XDG_CONFIG_HOME` and `$XDG_DATA_HOME` if set.

## Flow

1. **Manage Codes** — add/remove charge codes before first use
2. **Start Tracking** — pick a code; a live timer runs until you press Enter or q
3. **Today's Summary** — time per code for today
4. **Browse Logs** — pick any past date to see its summary
