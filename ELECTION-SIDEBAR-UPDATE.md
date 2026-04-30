# Election Map Sidebar Update

## Summary

Updated the election data map to use a **left sidebar** layout (matching the surveillance map) instead of the top race selector.

## Changes Made

### UI/UX Improvements

**Before:**
- Race selector at top center of page
- Stats panel on bottom left
- Legend on bottom right
- Compare button in race selector

**After:**
- **Unified left sidebar** containing:
  - Compare mode toggle button
  - Race selector (normal mode)
  - Candidate dropdown (when applicable)
  - Compare mode selectors (2 race/candidate pairs)
  - Legend with color-coded candidates
  - Vote totals for selected race
- Mobile: Hamburger button to show/hide sidebar
- Cleaner map view with more space

### Features

✅ **Compare Mode Toggle** - Enable/disable comparison view from sidebar
✅ **Race Selection** - Dropdown for Mayor, City Clerk, City Council, Proposals
✅ **Candidate Selection** - Shows when viewing City Council by candidate
✅ **Comparison Selectors** - Two sets of race/candidate dropdowns for head-to-head comparison
✅ **Dynamic Legend** - Shows candidates and their colors within sidebar
✅ **Vote Totals** - Displays total votes by candidate in sidebar
✅ **Mobile Responsive** - Sidebar collapses on mobile devices

### Ready for Presidential Data

The sidebar is **prepared to accept presidential election data** when you provide the CSV:
- Just add a new race option: `<option value="president">President</option>`
- The existing comparison and visualization logic will work automatically
- Can compare presidential results against Mayor, City Council, etc.

## Files Modified

1. `/src/components/PrecinctMap.astro`
   - Replaced race-selector, stats, and legend with sidebar layout
   - Updated event listeners for sidebar controls
   - Added mobile sidebar toggle handlers
   - Modified candidate dropdown wrapper handling

2. `/src/styles/global.css`
   - Added `.election-sidebar` specific styles
   - Added `.compare-toggle-btn` and comparison section styles
   - Added `.legend-items` and `.vote-totals-sidebar` styles
   - Hid legacy `.race-selector` and old positioning
   - Added mobile responsiveness for election sidebar

## Testing

To test:
```bash
bun run dev
# Visit: http://localhost:4321/election-data
```

**Test checklist:**
- [ ] Sidebar visible on left side
- [ ] Compare mode toggle works
- [ ] Race selector changes map colors
- [ ] City Council candidate dropdown appears/hides correctly
- [ ] Compare mode shows two selection panels
- [ ] Legend updates based on selected race
- [ ] Vote totals display correctly
- [ ] Mobile: Hamburger button shows/hides sidebar
- [ ] All existing races still work (Mayor, City Clerk, City Council, Proposal)

## Next: Adding Presidential Data

When you provide the CSV file with presidential election results:

1. **CSV Format Needed:**
```csv
Precinct,Trump,Harris,Kennedy,Stein,Oliver,Other
1,123,456,12,5,3,2
2,234,567,15,8,4,1
...
```

2. **I'll add:**
   - Process CSV into the election data structure
   - Add "President" option to race selector
   - Add candidate colors for presidential candidates
   - Ensure comparison mode works with presidential race

The sidebar is already fully prepared for this addition!
