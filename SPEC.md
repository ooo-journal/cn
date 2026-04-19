# Out Of Ordinary (OOO) - Journal Website Specification

## 1. Project Overview

**Project Name:** Out Of Ordinary (OOO)
**Project Type:** Single-page academic journal website with cyberpunk aesthetics
**Core Functionality:** A satirical academic journal that appears legitimate at first glance but reveals cyberpunk styling and absurd content
**Target Users:** Academics, researchers, art enthusiasts, cyberpunk culture fans

## 2. Visual & Rendering Specification

### Color Palette
- **Background (Primary):** `#0a0c0f` (near-black with slight blue tint)
- **Card/Section Background:** `#12161a` (dark gray-blue)
- **Primary Text:** `#e0e0e0` (light gray)
- **Accent Neon Cyan:** `#00f0ff`
- **Accent Neon Magenta:** `#ff00a0`
- **Muted Text:** `#6b7280`

### Typography
- **Headings:** Georgia, Times New Roman, serif (academic feel)
- **Body:** Inter, system-ui, sans-serif (modern readability)
- **Code/Labels:** monospace (cyberpunk terminal aesthetic)

### Visual Effects
- Neon glow on interactive elements using `box-shadow` and `text-shadow`
- Animated scanning line on hover for publishing option cards
- Grid pattern background overlay at 5% opacity
- Subtle scanline animation across the page
- Data mesh highlight on article row hover

## 3. Layout Structure

### Header (Fixed Top)
- Left: Journal name "Out Of Ordinary" (large serif) + "Vol. 01 / No. 001 // 出离寻常档案馆" (small subtitle)
- Right: Glowing search input with placeholder "Search neural archive..."
- Navigation: Articles & Issues | About | Publish | Order Journal

### Main Content Area (Two-Column)
- **Left Column (70%):**
  1. About the Journal section
  2. Article Publishing Options (dual-column)
  3. Latest Oddities (article list)

- **Right Column (30%):**
  1. Submit Your Oddity button
  2. Guide for Authors
  3. CiteScore indicator
  4. Most Read/Most Odd list

### Footer
- Academic-style links: Privacy Policy, Terms and Conditions, Accessibility, Cookie Settings
- Center: Indexed in: OOO-Core, Human Oddity Database, Imaginary Citation Index

## 4. Sections Detail

### About the Journal
- Title: "About the journal"
- Content: Formal academic description about the journal's scope
- Link: "View full aims & scope" → Opens cyberpunk modal

### Publishing Options
- **Open Access (Open Mind):**
  - APC: 1 Odd Idea (non-refundable)
  - Note: Your idea will be permanently archived in the neural network.

- **Subscription (Traditional):**
  - No publication fee
  - Immediately available to those who have a curious mind (everyone)

### Article List
- 5 sample articles with:
  - Title (serif font, academic style)
  - Author (supports "Anonymous" or "A Collective Hallucination")
  - Tag (e.g., #AI-042, #Divination-007)
  - DOI or "In Press, Journal Pre-proof"

## 5. Interaction Specification

### Modal
- Opens on clicking "View full aims & scope"
- Cyberpunk styled with neon borders
- Contains additional absurd journal information
- Close button and backdrop click to close

### Hover Effects
- Publishing option cards: Neon cyan scanning line animation
- Article rows: Data mesh background highlight
- Navigation links: Neon glow
- Buttons: Enhanced glow

### Responsive Behavior
- Desktop: Two-column layout (main content + sidebar)
- Mobile (<1024px): Single column, sidebar moves below main content

## 6. Technical Implementation

- **Framework:** Vanilla HTML, Tailwind CSS (CDN), Vanilla JavaScript
- **Animations:** CSS keyframes for scanlines and glows
- **No build step required** - Single HTML file with embedded styles

## 7. Acceptance Criteria

1. ✅ Header displays journal name, search, and navigation
2. ✅ About section with modal trigger works
3. ✅ Publishing options display in dual-column with hover effects
4. ✅ Article list shows 5 sample articles with all required info
5. ✅ Sidebar contains all 4 modules
6. ✅ Footer displays all required links
7. ✅ Cyberpunk visual effects are visible (neon glow, grid background, scanlines)
8. ✅ Responsive design works on mobile
9. ✅ All interactive elements are functional
