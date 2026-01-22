# TripScout - Group Trip Travel Cards

A beautiful, responsive web application for displaying and comparing travel destination options for group trips. Features interactive cards with detailed information about each destination including budget breakdowns, visa requirements, activities, and package holiday links.

## Features

- 🎨 **Beautiful UI**: Modern card-based design with custom gradients and animations
- 📱 **Responsive**: Works perfectly on desktop, tablet, and mobile devices
- ✈️ **Comprehensive Info**: Each card displays:
  - Destination title and subtitle
  - Visa status and requirements
  - Budget breakdown (flights, accommodation, activities)
  - Best travel season
  - Top activities and attractions
  - Links to activities and package holidays
- 🎯 **Easy to Update**: All destination data is stored in a simple JavaScript array

## Getting Started

### Prerequisites

- A modern web browser (Chrome, Firefox, Safari, Edge)
- A local web server (optional, but recommended for development)

### Installation

1. Clone or download this repository
2. Open `index.html` in your web browser

**Note**: For best results, serve the file through a local web server:
```bash
# Using Python 3
python -m http.server 8000

# Using Node.js (http-server)
npx http-server

# Using PHP
php -S localhost:8000
```

Then open `http://localhost:8000` in your browser.

## Project Structure

```
tripscout/
├── index.html          # Main HTML file with embedded data and card rendering logic
├── countries.json       # JSON file with country data (optional, data is embedded in HTML)
└── README.md           # This file
```

## Data Structure

Each destination is represented as an object with the following structure:

```javascript
{
  "id": "albania",                    // Unique identifier (used for CSS classes)
  "title": "ALBANIA",                  // Main destination title
  "subtitle": "Ksamil & Saranda",      // Subtitle/location
  "titleSize": "text-5xl",             // Tailwind text size class
  "overlayOpacity": "opacity-10",      // Overlay opacity for header
  "badge": {                           // Optional badge (e.g., "TOP PICK")
    "text": "#1 TOP PICK",
    "bgColor": "bg-white",
    "textColor": "text-blue-600"
  },
  "visaStatus": {                      // Visa information
    "text": "VISA FREE ✅",
    "bgColor": "bg-green-100",
    "textColor": "text-green-500"
  },
  "description": "\"The Maldives of Europe...\"",  // Quote/description
  "bestSun": "June - September",       // Best travel season
  "budget": {                          // Budget breakdown
    "total": "£450 - £550",
    "flights": "£180 - £250",
    "stayFun": "~£260"                 // OR "visaCost" or "allIncl"
  },
  "budgetColor": "blue",               // Color theme for budget section
  "voteYesItems": [                    // Reasons to vote yes (2 items)
    "Instagram-perfect turquoise water",
    "VIP beach clubs for cheap prices"
  ],
  "activities": [                      // Top 3 activities
    "Speedboat to Twin Islands",
    "The Blue Eye Spring Tour",
    "Gjirokastër City Day Trip"
  ],
  "activityColor": "blue",             // Color theme for activities
  "activitiesLink": "https://...",     // Link to activities page
  "tripPackagesLink": "https://...",   // Link to package holidays
  "visaCheck": "None",                 // Visa check details
  "visaCheckColor": "green",           // Color for visa check text
  "buttonColor": "bg-blue-600",        // Vote button color
  "buttonHoverColor": "hover:bg-blue-700",  // Vote button hover color
  "borderClass": "border-2 border-red-100"  // Optional border class
}
```

## Updating Destination Data

To add or modify destinations:

1. Open `index.html` in your editor
2. Find the `countries` array (starts around line 69)
3. Add a new country object or modify an existing one
4. Make sure to include all required fields

### Adding a New Destination

1. Add a new object to the `countries` array
2. Add the corresponding CSS gradient class in the `<style>` section:
   ```css
   .bg-your-country { 
     background: linear-gradient(135deg, #color1 0%, #color2 100%) !important; 
     background-color: transparent !important; 
   }
   ```
3. Add the country to the `countryBgClasses` mapping object

### Updating Links

- **Activities Link**: Update the `activitiesLink` field with the GetYourGuide URL
- **Package Holidays Link**: Update the `tripPackagesLink` field with the LoveHolidays URL

## Color Themes

The following color themes are available for `budgetColor` and `activityColor`:
- `blue`
- `gray`
- `emerald`
- `pink`
- `red`
- `yellow`
- `orange`

Each theme provides consistent styling for budget boxes, activity icons, and links.

## Customization

### Changing Layout

To change the number of cards per row, modify the grid classes in the container:
- 1 column: `grid-cols-1`
- 2 columns: `grid-cols-1 md:grid-cols-2` (current)
- 3 columns: `grid-cols-1 md:grid-cols-2 lg:grid-cols-3`

### Styling

All custom styles are in the `<style>` tag in the `<head>` section. The project uses:
- **Tailwind CSS** (via CDN) for utility classes
- **Font Awesome** for icons
- **Google Fonts** (Oswald & Inter) for typography

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## License

This project is open source and available for personal and commercial use.

## Contributing

Feel free to submit issues, fork the repository, and create pull requests for any improvements.

## Notes

- The data is currently embedded directly in the HTML file to avoid CORS issues when opening the file directly
- All links open in new tabs (`target="_blank"`)
- The VOTE buttons are currently non-functional (can be extended with JavaScript functionality)

