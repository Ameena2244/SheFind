# SheFind - Design Document

## Design Philosophy
SheFind is designed with women's safety, comfort, and ease of use as the primary considerations. The app should feel warm, trustworthy, and empowering — like it was built by a woman, for women.

## Visual Design System

### Color Palette
- **Primary Purple:** #7C3AED (Trust, safety, empowerment)
- **Light Purple:** #a855f7 (Gradients, accents)
- **White:** #ffffff (Clean, pure backgrounds)
- **Gray Scale:**
  - Text Primary: #1f2937
  - Text Secondary: #6b7280
  - Borders: #e5e7eb
  - Background: #f8fafc

### Safety Color Coding
- **Green (#10b981):** Safe toilets (4.0+ rating)
- **Yellow (#f59e0b):** Average toilets (2.5-3.9 rating)
- **Red (#ef4444):** Avoid toilets (<2.5 rating)

### Typography
- **Font Family:** 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif
- **Hierarchy:**
  - H1 (App Title): 1.5rem, weight 700
  - H2 (Modal Titles): 1.25rem, weight 600
  - Body Text: 1rem, weight 400
  - Small Text: 0.875rem, weight 400
  - Labels: 0.75rem, weight 500

## Layout & Structure

### Mobile-First Approach
- **Primary Target:** 375px - 414px (iPhone sizes)
- **Secondary Target:** 360px - 480px (Android sizes)
- **Minimum Width:** 320px
- **Touch Targets:** Minimum 44px for accessibility

### Screen Layout
```
┌─────────────────────────┐
│ Header (Purple gradient)│
│ - App title & tagline   │
│ - Language toggle       │
├─────────────────────────┤
│ Search Bar (White)      │
├─────────────────────────┤
│                         │
│ Interactive Map         │
│ (60vh height)           │
│                         │
├─────────────────────────┤
│ Bottom Navigation       │
│ Map | Rate | Community  │
└─────────────────────────┘
```

## Component Design

### Header Component
- **Background:** Linear gradient from #7C3AED to #a855f7
- **Content:** Centered app name and tagline
- **Language Toggle:** Top-right corner, semi-transparent button
- **Height:** Auto-sizing based on content + 1rem padding

### Search Component
- **Background:** White with subtle shadow
- **Input:** Rounded (25px), purple focus border
- **Placeholder:** Contextual search hints
- **Padding:** 1rem all around

### Map Component
- **Height:** 60vh (responsive to screen size)
- **Pins:** Custom colored circles with white borders
- **Popups:** Custom styled with rounded corners
- **Controls:** Default Leaflet controls positioned appropriately

### Bottom Navigation
- **Position:** Fixed at bottom
- **Background:** White with top border and shadow
- **Items:** 3 equal-width sections with icons and labels
- **Active State:** Light gray background, purple text

## Interactive Elements

### Buttons
- **Primary Button:**
  - Background: #7C3AED
  - Color: White
  - Padding: 0.75rem
  - Border-radius: 8px
  - Hover: #6d28d9

- **Floating Action Button:**
  - Size: 56px circle
  - Background: #7C3AED with shadow
  - Position: Fixed bottom-right
  - Icon: White "+" symbol

### Form Elements
- **Input Fields:**
  - Border: 2px solid #e5e7eb
  - Focus: 2px solid #7C3AED
  - Padding: 0.75rem
  - Border-radius: 8px

- **Star Rating:**
  - Size: 1.5rem
  - Color: #d1d5db (inactive), #fbbf24 (active)
  - Interactive hover states

### Modal Design
- **Overlay:** Semi-transparent black (rgba(0,0,0,0.5))
- **Content:** White rounded container (12px radius)
- **Max-width:** 400px
- **Positioning:** Centered with margin
- **Animation:** Smooth fade-in/out

## Information Architecture

### Toilet Information Hierarchy
1. **Primary Info:** Name, area, overall rating
2. **Scores:** Cleanliness and safety (side-by-side)
3. **Facilities:** Badge grid showing availability
4. **Safety Badge:** Prominent verification status
5. **Meta Info:** Review count, last reviewed
6. **Actions:** Rate button
7. **AI Tip:** Contextual advice

### Facility Badges
- **YES Badges:** Green background (#dcfce7), dark green text (#166534)
- **NO Badges:** Red background (#fef2f2), dark red text (#991b1b)
- **Layout:** Flexible grid, wrapping as needed

## Accessibility Design

### Visual Accessibility
- **Contrast Ratios:** All text meets WCAG AA standards
- **Color Independence:** Information not conveyed by color alone
- **Font Sizes:** Readable on small screens (minimum 14px)

### Motor Accessibility
- **Touch Targets:** Minimum 44px for easy tapping
- **Spacing:** Adequate space between interactive elements
- **Gestures:** Standard pinch-to-zoom, tap interactions

### Cognitive Accessibility
- **Simple Navigation:** Clear 3-tab structure
- **Consistent Patterns:** Repeated interaction patterns
- **Clear Labels:** Descriptive text for all actions
- **Feedback:** Immediate response to user actions

## Responsive Behavior

### Breakpoints
- **Mobile:** 320px - 480px (primary focus)
- **Small Tablet:** 481px - 768px (secondary)
- **Large Screens:** 769px+ (basic support)

### Adaptive Elements
- **Header Text:** Scales down on very small screens
- **Modal Size:** Adjusts to screen width with margins
- **Map Height:** Maintains 60vh for optimal viewing
- **Touch Targets:** Remain consistent across sizes

## Animation & Transitions

### Micro-Interactions
- **Button Hover:** 0.3s background color transition
- **Focus States:** 0.3s border color transition
- **Modal Appearance:** Smooth fade-in
- **Star Rating:** 0.2s color transition on hover/click

### Performance Considerations
- **CSS Transitions:** Hardware-accelerated properties only
- **Animation Duration:** Keep under 300ms for responsiveness
- **Reduced Motion:** Respect user preferences

## Localization Design

### Tamil Language Support
- **Text Direction:** Left-to-right (same as English)
- **Font Rendering:** System fonts handle Tamil characters
- **Text Length:** Account for potential length differences
- **Cultural Sensitivity:** Appropriate terminology and concepts

### Language Toggle
- **Position:** Top-right of header
- **Visual:** Clear language indicator
- **Behavior:** Instant switching without page reload
- **Persistence:** Remember user preference in localStorage

## Error States & Edge Cases

### No Search Results
- **Message:** "No toilets found near this area"
- **Styling:** Subtle, non-alarming presentation
- **Action:** Clear search to show all results

### Loading States
- **Map Loading:** Default Leaflet loading indicator
- **Form Submission:** Disable button, show processing state
- **Data Loading:** Graceful fallbacks for missing data

### Offline Behavior
- **Core Functionality:** Works after initial load
- **New Submissions:** Queue in localStorage
- **User Feedback:** Clear indication of offline status

## Success Metrics

### User Experience Goals
- **Task Completion:** Find toilet info in <30 seconds
- **User Satisfaction:** Feels safe and trustworthy
- **Accessibility:** Usable by diverse age groups
- **Performance:** Smooth interactions on mobile devices

### Design Validation
- **Visual Consistency:** All elements follow design system
- **Responsive Design:** Works across target device sizes
- **Accessibility Compliance:** Meets WCAG AA guidelines
- **Cultural Appropriateness:** Respectful and inclusive design