# Prompt: Build an Interactive 3D Portfolio Website

## Project Overview
Create a stunning, modern portfolio website featuring animated 3D scenes, smooth GSAP-powered scroll interactions, and a responsive design. This portfolio should help developers, designers, or freelancers stand out with an immersive digital presence.

## Tech Stack Requirements
- **Three.js** - For 3D graphics and rendering
- **React Three Fiber** - React renderer for Three.js
- **Drei** - Useful helpers for React Three Fiber
- **GSAP (GreenSock)** - For smooth animations and scroll interactions
- **Tailwind CSS v4** - For styling and responsive design
- **Vite** - As the build tool
- **React 19** - Frontend framework
- **EmailJS** - For contact form functionality

## Core Features to Implement

### 1. Animated Hero Section
- Create a split-layout hero with text content on the left and a 3D model/scene on the right
- Implement a sliding word animation that cycles through different descriptors (e.g., "Ideas", "Designs", "Code")
- Add GSAP fade-in animations for headline text with staggered timing
- Include an animated counter component showing metrics (years experience, projects completed, etc.)
- Position a 3D room/scene with:
  - OrbitControls for user interaction (disable panning, control zoom based on device)
  - Particle effects floating in the scene
  - Dynamic lighting setup (ambient + point lights)
  - Responsive scaling for mobile/tablet devices

### 2. Navigation Bar
- Fixed position navigation that changes appearance on scroll
- Transparent when at top, solid background when scrolled
- Desktop menu with hover underline animations
- Mobile-responsive hamburger menu
- Smooth scroll to sections on nav click
- Call-to-action button for contact

### 3. Project Showcase Section
- Display featured projects in an asymmetric grid layout
- Large featured project on one side (60% width on desktop)
- Smaller project cards stacked on the other side (40% width)
- Each project card should include:
  - Project image with hover effects
  - Project title
  - Technology badges/tags
  - Brief description
- Implement parallax or reveal animations on scroll

### 4. Logo Marquee/Showcase
- Create an infinite horizontal scrolling marquee of client/company logos
- Use CSS animations for smooth continuous movement
- Ensure logos are properly sized and spaced
- Make responsive for different screen sizes

### 5. Feature Cards Section
- Grid layout of service/feature cards (3 columns on desktop)
- Each card should have:
  - Icon or visual element
  - Title
  - Description
  - Hover effects with glow/border animations
- Implement rotating gradient border effect on hover using conic-gradient and CSS custom properties

### 6. Experience Timeline
- Vertical timeline layout showing work history
- Central timeline line with gradient colors
- Company logos at each timeline point
- Alternating left/right content layout on desktop
- Stacked layout on mobile
- Include:
  - Company name and logo
  - Job title
  - Date range
  - Key achievements/responsibilities

### 7. Tech Stack Section
- Grid display of technologies used (5 columns on desktop)
- Each tech item should include:
  - Technology icon/logo
  - Technology name
  - Animated reveal effect on scroll
- Implement creative hover animations where background slides up to reveal info

### 8. Testimonials Section
- Carousel or grid of client testimonials
- Each testimonial card includes:
  - Client photo/avatar
  - Client name and role
  - Company logo
  - Testimonial text
  - Rating stars
- Add subtle animations and hover effects

### 9. Contact Section
- Clean contact form with:
  - Name input
  - Email input
  - Message textarea
  - Submit button with loading state
- Integration with EmailJS for form submission
- Alternative contact methods (email link, social media)
- Form validation and success/error messages

### 10. Footer
- Multi-column layout with:
  - Copyright information
  - Quick links
  - Social media icons with hover effects
- Consistent styling with the rest of the site

## Design System

### Color Palette
- Primary background: Black (#000000)
- Secondary backgrounds: Dark grays (#1c1c21, #0e0e10, #282732)
- Text primary: White (#ffffff)
- Text secondary: Light blue-gray (#d9ecff)
- Accent colors: Blue tones (#839cb5, #2d2d38)
- Gradient accents for special effects

### Typography
- Font Family: "Mona Sans" (or similar modern sans-serif)
- Heading sizes: 30px mobile, 60px desktop for hero
- Body text: Responsive sizing with Tailwind
- Font weights: Variable from 200-900

### Layout Principles
- Mobile-first responsive design
- Use of viewport units (dvw, dvh) for full-screen sections
- Generous whitespace and padding
- Grid-based layouts (1-4 columns depending on section)
- Flexbox for alignment and distribution

## Animation Specifications

### GSAP Animations
- Fade-in animations with y-axis translation
- Staggered timing for multiple elements
- Scroll-triggered animations using ScrollTrigger
- Smooth easing (power2.inOut, cubic-bezier curves)

### CSS Animations
- Word slider animation for hero text (21s infinite loop)
- Marquee scrolling animation (60s linear infinite)
- Button hover effects with background transitions
- Card glow effects using pseudo-elements

### 3D Animations
- Camera positioning and movement
- Object rotation and scaling
- Particle systems for ambient effects
- Dynamic lighting changes

## Component Architecture

### Reusable Components
1. **Button** - Styled CTA button with variants
2. **NavBar** - Responsive navigation
3. **TitleHeader** - Section headers with consistent styling
4. **GlowCard** - Card with hover glow effects
5. **AnimatedCounter** - Number counter animation
6. **ExpContent** - Experience timeline item
7. **3D Model Components** - Modular 3D scenes

### Section Components
Each major section should be its own component:
- Hero
- ShowcaseSection (Projects)
- LogoShowcase
- FeatureCards
- Experience
- TechStack
- Testimonials
- Contact
- Footer

## Responsive Breakpoints
- Mobile: < 768px
- Tablet: 768px - 1024px
- Desktop: > 1024px
- Large Desktop: > 1280px

## Performance Considerations
1. Lazy load 3D models and heavy assets
2. Use Suspense for async 3D components
3. Optimize images and use appropriate formats
4. Implement code splitting for routes/sections
5. Reduce 3D complexity on mobile devices
6. Use will-change sparingly for animations

## Accessibility Requirements
- Semantic HTML structure
- ARIA labels for interactive elements
- Keyboard navigation support
- Sufficient color contrast
- Alt text for images
- Focus states for all interactive elements

## File Structure
```
src/
├── App.jsx
├── main.jsx
├── index.css
├── components/
│   ├── Button.jsx
│   ├── NavBar.jsx
│   ├── AnimatedCounter.jsx
│   ├── GlowCard.jsx
│   ├── TitleHeader.jsx
│   └── models/
│       ├── hero_models/
│       ├── tech_logos/
│       └── contact/
├── sections/
│   ├── Hero.jsx
│   ├── ShowcaseSection.jsx
│   ├── LogoShowcase.jsx
│   ├── FeatureCards.jsx
│   ├── Experience.jsx
│   ├── TechStack.jsx
│   ├── Testimonials.jsx
│   ├── Contact.jsx
│   └── Footer.jsx
└── constants/
    └── index.js
```

## Environment Variables
Set up EmailJS integration:
```
VITE_APP_EMAILJS_SERVICE_ID=your_service_id
VITE_APP_EMAILJS_TEMPLATE_ID=your_template_id
VITE_APP_EMAILJS_PUBLIC_KEY=your_public_key
```

## Implementation Steps
1. Set up Vite + React project with Tailwind CSS v4
2. Install and configure Three.js, React Three Fiber, and Drei
3. Set up GSAP with React integration
4. Create the design system (colors, typography, utilities)
5. Build reusable UI components
6. Develop the Hero section with 3D elements
7. Create remaining sections one by one
8. Implement responsive design for all breakpoints
9. Add animations and micro-interactions
10. Integrate EmailJS for contact form
11. Test across devices and browsers
12. Optimize performance
13. Deploy to hosting platform

## Additional Notes
- Ensure smooth 60fps animations
- Test 3D performance on lower-end devices
- Provide fallbacks for users with reduced motion preferences
- Keep code modular and reusable
- Document complex 3D setups
- Use ESLint and Prettier for code quality

---

This prompt provides a comprehensive guide for creating a professional 3D portfolio website similar to the reference project. Adjust specific content, colors, and features to match your personal brand and requirements.
