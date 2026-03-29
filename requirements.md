# SheFind - Requirements Document

## Project Overview
**App Name:** SheFind — Women's Safe Toilet Finder  
**Tagline:** "Find clean. Stay safe. Go confidently."  
**Target Location:** Madurai, Tamil Nadu, India

## Problem Statement
Women in Madurai avoid stepping out for long hours, skip drinking water, and suffer health issues — just because they cannot find a clean, safe public toilet nearby. There is no app built specifically for women in Tamil Nadu that solves this problem.

## Target Users
- Women of all ages in Madurai
- Tourists and visitors to Madurai
- Local residents who need reliable toilet information
- Community members who want to contribute safety information

## Functional Requirements

### Priority 1 - Must Have Features

#### 1. Interactive Map
- **FR-001:** Display interactive map centered at Madurai (Lat: 9.9252, Long: 78.1198)
- **FR-002:** Show 25 predefined toilet locations across Madurai
- **FR-003:** Use color-coded pins based on safety ratings:
  - Green pin → Rating 4.0+ (Safe)
  - Yellow pin → Rating 2.5-3.9 (Average)
  - Red pin → Rating <2.5 (Avoid)
- **FR-004:** Allow users to zoom and pan the map
- **FR-005:** Support touch gestures for mobile devices

#### 2. Toilet Detail Information
- **FR-006:** Display detailed popup when user clicks on toilet pin
- **FR-007:** Show toilet name and area information
- **FR-008:** Display overall rating as star system (1-5 stars)
- **FR-009:** Show separate cleanliness and safety scores
- **FR-010:** Display facility availability as YES/NO badges:
  - Running water
  - Lights
  - Door lock
  - Sanitary pad machine
  - Attendant
  - Wheelchair access
- **FR-011:** Show total number of reviews
- **FR-012:** Display last reviewed timestamp
- **FR-013:** Show safety verification badge:
  - Green "Women Verified Safe"
  - Yellow "Needs Caution"
  - Red "Avoid — Reported Unsafe"

#### 3. Rating System
- **FR-014:** Allow users to rate toilets on cleanliness (1-5 stars)
- **FR-015:** Allow users to rate toilets on safety (1-5 stars)
- **FR-016:** Provide facility checkboxes for user input
- **FR-017:** Include optional comment box for user feedback
- **FR-018:** Store ratings in browser localStorage
- **FR-019:** Show confirmation message: "Thank you! You just helped a woman in Madurai."

#### 4. Search Functionality
- **FR-020:** Provide search bar for area or landmark names
- **FR-021:** Filter and highlight matching toilets on map
- **FR-022:** Show "No toilets found near this area" when no results found
- **FR-023:** Support partial text matching

### Priority 2 - Nice to Have Features

#### 5. Language Support
- **FR-024:** Provide Tamil/English language toggle button
- **FR-025:** Translate all key UI labels instantly
- **FR-026:** Support specific translations:
  - Find Toilet → கழிவறை கண்டுபிடி
  - Rate this toilet → மதிப்பீடு செய்க
  - Safe → பாதுகாப்பான
  - Clean → சுத்தமான
  - Women Verified Safe → பெண்களால் சரிபார்க்கப்பட்டது

#### 6. Community Features
- **FR-027:** Provide floating "+" button for adding new toilets
- **FR-028:** Allow users to submit new toilet locations with:
  - Name/Landmark
  - Area
  - Basic facilities
- **FR-029:** Store community submissions in localStorage
- **FR-030:** Show confirmation: "Your report will help women in Madurai. Thank you!"

### Bonus Features

#### 7. AI Tips
- **FR-031:** Generate contextual tips based on toilet rating and time of day
- **FR-032:** Provide suggestions like:
  - "Usually clean in mornings — good time to visit!"
  - "Evenings get crowded, plan earlier."
  - "Avoid at night — not well lit."

## Non-Functional Requirements

### Performance
- **NFR-001:** App must load within 3 seconds on 3G connection
- **NFR-002:** Map interactions must be responsive (<200ms)
- **NFR-003:** Search results must appear within 1 second

### Usability
- **NFR-004:** App must be usable by women of all ages (18-70+)
- **NFR-005:** Interface must be intuitive without training
- **NFR-006:** Text must be readable on mobile screens
- **NFR-007:** Touch targets must be minimum 44px for accessibility

### Compatibility
- **NFR-008:** Must work on iOS Safari, Android Chrome
- **NFR-009:** Must work offline after initial load
- **NFR-010:** Must work without app store installation

### Security & Privacy
- **NFR-011:** No personal data collection required
- **NFR-012:** All data stored locally in browser
- **NFR-013:** No external API dependencies for core functionality

## Data Requirements

### Toilet Location Data
- **DR-001:** Include 25 real Madurai locations covering:
  - 5 Transport hubs (bus stands, railway, airport)
  - 5 Temples (Meenakshi Amman, etc.)
  - 5 Markets (vegetable, textile markets)
  - 5 Government buildings (hospitals, offices)
  - 5 Parks and public spaces

### Required Data Fields
- **DR-002:** Each toilet location must include:
  - Unique ID
  - Name and area
  - GPS coordinates (realistic for Madurai)
  - Overall rating (1-5)
  - Cleanliness score (1-5)
  - Safety score (1-5)
  - Facility availability (6 facilities)
  - Review count (5-150 reviews)
  - Last reviewed timestamp

## Technical Constraints
- **TC-001:** Single HTML file implementation
- **TC-002:** No build tools or frameworks
- **TC-003:** No paid APIs or cloud services
- **TC-004:** Must work by opening HTML file in browser
- **TC-005:** Use Leaflet.js via CDN for mapping
- **TC-006:** All backend simulation via localStorage

## Success Criteria
- **SC-001:** Women can find toilet information within 30 seconds
- **SC-002:** App feels trustworthy and safe to use
- **SC-003:** Community engagement through ratings and submissions
- **SC-004:** Positive user feedback on safety and cleanliness information
- **SC-005:** Successful deployment without technical setup