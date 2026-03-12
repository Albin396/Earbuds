
Overview
A dark-luxury, single-file product website for EBuds, a premium earbuds concept brand. The aesthetic is "Obsidian Noir" — deep blacks, warm off-white typography, and a CSS film-grain noise overlay. No build step required; open the .html file directly in any browser.
Fonts:

Unbounded — headings (geometric / futuristic)
DM Sans — body text (clean sans-serif)
Architecture
Two-page SPA model. Pages are toggled via a showPage(id) JavaScript function — no separate HTML files, no page reload.
Page 1 — Home (#home)
SectionDescriptionHeroTwo-column layout. Left: animated headline, stats, CTAs. Right: floating product image with animated SVG rings and spec chips.MarqueeScrolling ticker strip.AboutBrand story with a scroll-triggered image reveal via IntersectionObserver.FeaturesProduct feature highlights.Specs TableTabbed comparison for 4 products: QC Ultra, Powerbeats, TE-W1, CCA.ReviewsCustomer testimonials.FAQAccordion-style frequently asked questions.NewsletterEmail signup section.Product StripHorizontal product lineup row.CTA SectionFull-width call-to-action banner.FooterLinks, legal, social icons.
Page 2 — Shop (#shop)
Product collection/browsing page with a Swiper.js slider, slide counter display, and scroll progress track.

Design System
TokenValueUsage--black#040404Page background--black2#0a0a0aSecondary background--black3#111111Tertiary background--white#f0eeebPrimary text--white2rgba(240,238,235,0.6)Secondary text--white3rgba(240,238,235,0.2)Muted text / borders--linergba(240,238,235,0.08)Subtle dividers--td1.5sTransition duration--tecubic-bezier(0.76,0,0.24,1)Easing curve

JavaScript Features
Custom cursor — Small dot that expands to a rounded square on hover. Uses mix-blend-mode: difference. Separate .cursor and .cursor-trail elements tracked via mousemove.
Nav scroll effect — Backdrop-blur frosted glass background activates after scroll. Adds .scrolled class to <nav>.
SPA navigation — showPage(id) hides all .page elements, then shows the target. 10ms setTimeout ensures display:block resolves before .active triggers CSS transitions.
Scroll reveal — IntersectionObserver animates the about image on entry. Threshold: 0.3. Unobserves after first trigger.
Spec tabs — Click to switch between 4 product spec panels. Toggles .active class on .specs-panel elements.
Hero animations — Staggered CSS @keyframe entrance: lineReveal, slideUp, fadeUp, heroImgReveal, heroFloat — each with separate animation-delay values.
SVG rings — Two counter-rotating decorative rings. Outer: 25s linear. Inner: 15s linear reverse.

Assets & Dependencies
TypeDetailProduct imagesBase64-encoded inline — fully self-containedSwiper.jsCDN (swiper-bundle.min.css) — Shop page sliderGoogle FontsCDN — Unbounded + DM SansExternal JSNone beyond Swiper. No jQuery, no bundler, no build step.
