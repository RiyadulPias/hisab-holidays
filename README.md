# hisab-holidays

Bangladesh government holiday data for the "Riyadul's Agent" Android app.
The app reads `holidays.json` from this repo (raw URL) and refreshes it automatically.

- `holidays.json` — verified holiday list; `updated` is the last revision date.
- Updated when the government gazette or moon-sighting dates change.

## ramadan.json (published when Islamic Foundation releases the Ramadan timetable)

```json
{
  "hijriYear": 1448,
  "updated": "2027-01-20",
  "source": "Islamic Foundation Bangladesh",
  "dhaka": [ {"date": "2027-02-09", "sehri": "05:13", "iftar": "17:46"}, "... 29-30 days ..." ],
  "districts": {
    "সিলেট": { "days": [ {"date": "2027-02-09", "sehri": "05:08", "iftar": "17:41"}, "..." ] },
    "চট্টগ্রাম": { "sehri": -4, "iftar": -5 }
  }
}
```
- Times are 24-hour `HH:MM`. `sehri` = Fajr start (end of sehri), as the Foundation defines it.
- A district may have full `days` (preferred, the Foundation publishes 64 district tables) or minute offsets relative to Dhaka.
- District names must match the app's list (Bangla names). Missing districts fall back to Dhaka + calculated difference and are labelled in the app.
