# Dearborn Maps

Interactive data visualization maps for the City of Dearborn, Michigan.

![Built with Astro](https://img.shields.io/badge/built%20with-Astro-purple) ![Mapbox](https://img.shields.io/badge/maps-Mapbox-blue)

## Maps

### Surveillance Map
Visualizes Automated License Plate Recognition (ALPR) cameras and surveillance infrastructure using data from OpenStreetMap.

- ALPR cameras with direction cones
- Filter by operator and manufacturer
- Data table with fly-to functionality
- Click popups with camera details

### Election Data Map
Displays voting precincts and election results with interactive comparison features.

- Precinct boundaries with election results
- **Nov 2026 General**: statewide, federal, legislative, education-board, county, school-board and ballot-proposal races (all parties; judicial races and straight-party ticket omitted)
- **Nov 2025 Municipal**: Mayor, City Clerk, City Council, Proposal 1
- **Nov 2024 General** (official Wayne County canvass): President, U.S. Senate, U.S. House, State House, education boards, county offices, Dearborn Schools board, Wayne RESA millage
- **Turnout** by precinct (2024, 2026) and **how people voted** — early, election day, absentee (2024)
- Each year is drawn on its own precinct boundaries; comparisons across years combine precincts to the coarser year's boundaries
- Color by precinct winner (margin intensity) or by any single candidate's vote share
- Compare mode across races and years, by vote share or raw votes
- Citywide vote totals by candidate

## Tech Stack

- **[Astro](https://astro.build)** - Static site framework
- **[Mapbox GL JS](https://docs.mapbox.com/mapbox-gl-js/)** - Interactive mapping
- **[OpenStreetMap](https://www.openstreetmap.org)** - Surveillance data source
- **[Michigan SOS](https://www.michigan.gov/sos)** - Election data source

## Setup

### Prerequisites

- [Bun](https://bun.sh) or Node.js
- [Mapbox account](https://www.mapbox.com) (free tier works)

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/dearborn-maps.git
cd dearborn-maps

# Install dependencies
bun install

# Create environment file
cp .env.example .env

# Add your Mapbox token to .env
# PUBLIC_MAPBOX_TOKEN=pk.your_token_here

# Start development server
bun run dev
```

Open [http://localhost:4321](http://localhost:4321)

### Build for Production

```bash
bun run build
```

Output is in the `dist/` folder.

## Project Structure

```
dearborn-maps/
├── src/
│   ├── pages/
│   │   ├── index.astro              # Home page
│   │   ├── surveillance.astro       # Surveillance map
│   │   └── election-data.astro      # Election data map
│   ├── components/
│   │   ├── Map.astro                # Surveillance map component
│   │   └── PrecinctMap.astro        # Election map component
│   ├── data/
│   │   ├── cameras.json             # ALPR camera data
│   │   ├── boundary.json            # Dearborn city boundary
│   │   ├── precincts.json           # Voting precinct boundaries
│   │   └── election-data-template.json  # Election results
│   └── styles/
│       └── global.css               # Styles
├── .env.example
├── astro.config.mjs
├── package.json
└── README.md
```

## Data Sources

- **Surveillance**: [OpenStreetMap](https://www.openstreetmap.org) under [ODbL license](https://opendatacommons.org/licenses/odbl/)
- **Election Data**: [Michigan Secretary of State](https://www.michigan.gov/sos)
- **Boundaries**: OpenStreetMap and Wayne County GIS

## License

- **Code**: MIT License
- **Map Data**: [OpenStreetMap](https://www.openstreetmap.org/copyright) - ODbL
- **Map Tiles**: [Mapbox](https://www.mapbox.com) - See their terms

## Acknowledgments

- [OpenStreetMap contributors](https://www.openstreetmap.org)
- [DeFlock](https://deflock.me) for surveillance mapping inspiration
- Wayne County and Michigan SOS for election data
