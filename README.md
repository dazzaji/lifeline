# Life Timeline Planner - User Guide

## Quick Start

1. **Open the timeline**: Double-click `life-timeline.html` in your browser (Chrome, Safari, Firefox)
2. **Edit your events**: Open `personal-events.md` in any text editor (Sublime, VS Code, TextEdit, etc.)
3. **Refresh**: After saving changes to `personal-events.md`, refresh your browser to see updates

## What's New (Latest Fixes)

✅ **FIXED: Personal events now display correctly** - Date parsing bug resolved
✅ **Improved Week View** - One header per ISO week with clear date ranges (e.g., "W45 (Nov 3–9)")
✅ **Legend relocated** - Now bottom-right with collapse toggle, never blocks content
✅ **No emoji** - Clean CSS-based markers throughout
✅ **Shorter natural markers** - FM, NM, EQ, SOL for cleaner display
✅ **Today button** - Quick jump to current date
✅ **Better spacing** - Extra padding prevents content from hiding under legend

## Files

- `life-timeline.html` - The timeline application (all code self-contained)
- `personal-events.md` - Your personal events data (edit this file)
- `README.md` - This guide

## How to Use

### Navigation

- **Scroll**: Use mouse wheel or trackpad to scroll through time (vertical timeline)
- **Zoom In/Out**: Use the + and - buttons in the header
  - Zoom levels: All → Year → Month → Week → Day
- **Today**: Click the green "Today" button to jump to the current date
- **Filters**: Toggle checkboxes to show/hide:
  - Calendar markers (years, months, weeks)
  - Natural events (moons, solstices, equinoxes)
  - Personal events (your milestones)
- **Legend**: Click "Legend ▾" in bottom-right to collapse/expand

### Zoom Levels Explained

- **All**: Shows only years with major events grouped
- **Year**: Shows years and months with events
- **Month**: Shows all days with events within each month
- **Week**: Shows ISO weeks (Monday-Sunday) with clear date ranges like "W45 (Nov 3–9)"
- **Day**: Shows every single day (best for detailed planning and full content)

### Natural Event Markers

Colored circles on the timeline indicate natural events:

- **FM** (Orange) - Full Moon
- **NM** (Dark gray) - New Moon
- **EQ** (Green) - Equinox (Spring/Fall)
- **SOL** (Red) - Solstice (Summer/Winter)
- **LONG** (Yellow) - Longest Day of Year
- **SHORT** (Dark blue) - Shortest Day of Year

Hover over any marker to see its full name.

### Personal Events

Your events appear as:

- **Blue dot + gray box** - Point events (single date)
- **Colored bar** - Span events (duration with start and end dates)

**Interactions:**
- Hover over any event to see its description
- Click on an event (in Day view) to open the detail panel with full content
- Tags appear as blue pills below event titles

### Adding Your Events

Edit `personal-events.md` in your text editor. Each event follows this format:

```markdown
## 2026-03-15 | Event Title
Description: Short description shown on hover
Tags: work, important, deadline
End: 2026-03-20
---
Full content here in markdown format.

You can use **bold**, *italic*, and [links](https://example.com).
Write as much as you need!
```

**Field Guide:**

- `## YYYY-MM-DD | Title` - **Required**: Date and title (must have pipe separator)
- `Description:` - Optional: Short text for hover tooltip
- `Tags:` - Optional: Comma-separated categories
- `End:` - Optional: Makes it a span event (colored bar)
- `---` - Optional: Separator before full content
- Content after `---` - Optional: Full markdown text (shown in detail panel)

**Important Notes:**

- Keep one blank line between events
- Dates **must** be in YYYY-MM-DD format
- The pipe `|` separator between date and title is required
- If you don't add an End date, it will be a point event (dot)
- If you add an End date, it will be a span event (bar)

### Example Events

**Simple deadline:**
```markdown
## 2026-05-15 | Project Due
Tags: work, deadline
```

**Vacation span:**
```markdown
## 2026-07-01 | Summer Vacation
Description: Two weeks in Hawaii
Tags: travel, vacation, personal
End: 2026-07-14
---
Family trip to Maui and Big Island.
Flights booked on United.
Hotel: [Grand Wailea](https://example.com)
```

**Multi-day project:**
```markdown
## 2025-11-04 | Write Blog Post
Description: Draft to publication
Tags: writing, research
End: 2025-11-16
---
Goal: Complete draft on LLM evaluation methods.

Schedule:
- Nov 4-8: Outline and research
- Nov 9-15: First draft
- Nov 16: Publish
```

## Troubleshooting

**Events not showing?**
- Check that your date format is YYYY-MM-DD
- Make sure there's a pipe `|` between date and title
- Verify the file is saved as `personal-events.md` in the same folder as the HTML file
- Refresh your browser after saving changes
- Open browser console (F12) and look for errors

**Week view looks wrong?**
- This has been fixed! Each week should now show one header like "W45 (Nov 3–9)"
- Weeks follow ISO standard (Monday to Sunday)
- Weeks that span year boundaries show the year: "W01 2026 (Dec 29–Jan 4)"

**Legend blocking content?**
- This has been fixed! Legend is now bottom-right
- Click "Legend ▾" to collapse it
- It will never cover your timeline content

**Today button doesn't work?**
- Make sure today's date falls within the timeline range (Oct 29, 2025 - Apr 29, 2027)
- If today is outside this range, you'll see an alert message

**Browser compatibility:**
- Works best in Chrome, Safari, Firefox, Edge
- Must be opened as a local file (file:// URL)
- Some browsers may block local file loading - if so, use Chrome

## Time Range

The timeline currently displays: **October 29, 2025 to April 29, 2027** (18 months)

To extend this range, edit the JavaScript in the HTML file:
1. Search for `const startDate = parseISODateLocal('2025-10-29');`
2. Change the dates as needed
3. Save and refresh

## Technical Details

### Date Parsing Fix
The timeline now uses local date parsing (noon local time) to avoid timezone issues. This ensures your events appear on the correct days regardless of your timezone.

### ISO Week Numbering
Weeks follow the ISO 8601 standard:
- Weeks run Monday to Sunday
- Week 1 is the first week with a Thursday
- Week numbers may differ slightly from other calendars at year boundaries

### Sample Data
The included `personal-events.md` has sample events for testing. Replace them with your own events or use them as templates.

## Tips for Best Experience

1. **Start in Month or Week view** to get an overview
2. **Use tags** to categorize events (work, personal, travel, etc.)
3. **Add End dates** to show duration visually
4. **Use the description field** for quick context on hover
5. **Save full details** and links in the content section after `---`
6. **Review regularly** - Update your personal-events.md file as plans change
7. **Collapse the legend** when you don't need it for more screen space
8. **Use Today button** for quick navigation to current date

## Customization

All code is in the single `life-timeline.html` file. You can customize:

- **Colors**: Search for hex codes like `#3498db` and change them
- **Date range**: Change `startDate` and `endDate` values
- **Natural events**: Edit the `naturalEvents` object
- **Timeline styling**: Modify the CSS in the `<style>` section

## Support

This is a standalone tool - no internet required, no account needed, no data collection.
Your data stays in the `personal-events.md` file on your computer.

Enjoy planning your life around natural rhythms and personal goals!
