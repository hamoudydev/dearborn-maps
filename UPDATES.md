# Map Updates - April 30, 2026

## Camera Data Updates

### Dearborn
- **Previous:** 77 cameras
- **Updated:** 80 cameras (+3 new)
- **New cameras:**
  - +2 Dearborn Police Department cameras
  - +1 Unknown operator camera
- **Breakdown:**
  - Dearborn Police Department: 67
  - University of Michigan-Dearborn: 6
  - The Home Depot: 4
  - Unknown: 3

### Dearborn Heights  
- **New addition:** 12 cameras
- **Operator:** Dearborn Heights Police Department

### Data Files
- `/src/data/cameras.json` - Updated Dearborn cameras (80 total)
- `/src/data/cameras-dearborn-heights.json` - NEW file (12 cameras)
- `/src/data/boundary-dearborn-heights.json` - NEW file (approximate boundary)

## UI/UX Changes

### Sidebar Implementation
Replaced top dropdown controls with a left sidebar for better organization and scalability.

**Features:**
- City selector dropdown (Dearborn / Dearborn Heights)
- Search box
- Operator filter
- Manufacturer filter
- Statistics panel (visible/total counts)
- Data table toggle button

**Benefits:**
- More vertical space for filters
- Easier to add new filter types
- Better mobile experience with collapsible sidebar
- Cleaner map view

### Mobile Responsiveness
- Sidebar hidden by default on mobile (< 768px)
- Hamburger menu button to open sidebar
- Sidebar slides in from left
- Close button in sidebar header on mobile

### City Switching
- Select between Dearborn and Dearborn Heights
- Map automatically centers on selected city
- Boundary updates to show selected city
- Filters rebuild with city-specific operators/manufacturers
- Camera count updates dynamically

## Technical Changes

### Files Modified
1. `/src/components/SurveillanceMap.astro`
   - Added multi-city data imports
   - Replaced controls panel with sidebar layout
   - Added city switching logic
   - Updated filter UI rebuild functions

2. `/src/styles/global.css`
   - Added sidebar styles
   - Updated search box styles for sidebar context
   - Added mobile sidebar responsiveness
   - Removed legacy controls and stats panel styles

## Testing

To test the changes:
```bash
bun run dev
# or
npm run dev
```

Visit http://localhost:4321/surveillance

**Test items:**
- [ ] Sidebar appears on desktop
- [ ] City selector switches between Dearborn and Dearborn Heights
- [ ] Filters work correctly for each city
- [ ] Camera counts update when switching cities
- [ ] Boundaries update when switching cities
- [ ] Mobile: Sidebar hidden by default
- [ ] Mobile: Hamburger button shows/hides sidebar
- [ ] All 80 Dearborn cameras visible
- [ ] All 12 Dearborn Heights cameras visible

## Next Steps (Optional Improvements)

1. **Better Dearborn Heights Boundary:** Replace approximate boundary with actual city boundary from OpenStreetMap
2. **Additional Cities:** Add more nearby cities (Allen Park, Melvindale, River Rouge, etc.)
3. **Filter Enhancements:** Add mount type, power source, direction range filters
4. **Date Filter:** Add installation date filtering (if data available)
5. **Export Functionality:** Add CSV/GeoJSON export for filtered camera list

