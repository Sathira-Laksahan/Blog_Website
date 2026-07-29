# Modern Hugo Blog Site Revamp (Blowfish Theme) Implementation Plan

මෙම plan එක මගින් ඔබගේ **Blowfish Hugo Blog Website** එක සාම්ප්‍රදායික Hugo blog එකක පෙනුමෙන් මිදී, **WordPress Premium Theme** එකක පෙනුම ඇති ඉතා modern, responsive, SEO-optimized, සහ Monetization-ready (Google Adsense, Analytics, Search Console) වෙබ් අඩවියක් බවට පත්කිරීමට අවශ්‍ය සියලුම පියවර ආවරණය කරයි.

---

## 1. Core Architecture & Pages Structure (පිටු සැකස්ම)

වෙබ් අඩവියේ ව්‍යුහය පහත පරිදි සකස් කරනු ලැබේ:

| Page / Section | Page Path | Description & Purpose |
| :--- | :--- | :--- |
| **Home Page** | `/` | Hero section, Featured articles, Topic cards, Recent Posts Grid, Newsletter CTA. |
| **Blog / Articles** | `/posts/` | Grid/Card view එකෙන් සියලුම ලිපි, Pagination, Search & Filter. |
| **Categories** | `/categories/` | මාතෘකා අනුව ලිපි වෙන්කර පෙන්වන Taxonomy archive එක. |
| **Tags** | `/tags/` | Tag අනුසාරයෙන් ලිපි සොයාගැනීමට. |
| **About Us / Author** | `/about/` | Author profile, Bio, Skills, Mission සහ Social Media links (Google Adsense සඳහා අත්‍යවශ්‍යයි). |
| **Contact Us** | `/contact/` | Contact details / feedback form (Google Adsense & User Trust සඳහා අත්‍යවශ්‍යයි). |
| **Privacy Policy** | `/privacy-policy/` | Adsense සහ Legal Compliance සඳහා අත්‍යවශ්‍ය නීතිමය පිටුව. |
| **Terms & Conditions** | `/terms/` | වෙබ් අඩවියේ කොන්දේසි ඇතුළත් පිටුව. |

---

## 2. Modern UI / UX Design & Color Scheme (පෙනුම සහ වර්ණ)

### Color Palette (වර්ණ සංයෝජනය)
- **Primary Accent**: Royal Indigo / Electric Blue (`#4F46E5` / `#3B82F6`) - Premium Modern Look
- **Secondary Accent**: Emerald Mint / Cyan (`#10B981` / `#06B6D4`) - Highlights, Badges, CTA buttons
- **Dark Mode Background**: Deep Slate (`#0F172A` / `#1E293B`) - Soft dark background for eye comfort
- **Light Mode Background**: Crisp Clean White & Soft Grey (`#FFFFFF` / `#F8FAFC`)
- **Text & Typography**: Modern Sans-Serif (Inter / Outfit font hierarchy), High contrast & clear readability.

### Layout & Visual Enhancements (WordPress-like feel)
- **Header**: Fixed Glassmorphism Blur Header (`fixed-fill-blur`), Logo/Site Name, Navigation Links, Search Bar, Light/Dark Mode Switch.
- **Hero Section**: High-impact headline, sub-headline, Author badge, Quick search or Featured banner card.
- **Card Design**: Rounded corner cards (`rounded-xl` / `rounded-2xl`), subtle hover shadow & lift effect, category badges with distinctive colors, read-time & publish date.
- **Article Detail Page**: Large Hero image, Breadcrumbs, Sticky Table of Contents (TOC), Author Bio Box at bottom, Related Posts, Social Share buttons.
- **Footer**: Modern multi-column footer with quick links, categories, copyright, privacy links, and back-to-top button.

---

## 3. SEO, Google Tools & Monetization Integration

1. **Google Analytics (GA4)**: `config/_default/hugo.toml` හෝ layout head එක හරහා `googleAnalytics = "G-XXXXXXXXXX"` සම්බන්ධ කිරීම.
2. **Google Search Console**: `params.toml` හි `[verification]` කොටසට Google Verification Meta Tag / File එකතු කිරීම සහ `sitemap.xml`, `robots.txt` සක්‍රිය කිරීම.
3. **Google Adsense**:
   - Adsense Auto Ads Code එක layout head එකට එකතු කිරීම (`[advertisement]` params).
   - In-article ad slots සහ Sidebar/Header ad slots සකස් කර තැබීම.
   - Adsense Approval සඳහා අවශ්‍ය `About`, `Contact`, `Privacy Policy`, `Terms` පිටු සහ `ads.txt` සැකසීම.
4. **Social Sharing & Meta Tags (OpenGraph / Twitter)**: Social media වල share කරද්දි ලස්සනට preview thumbnail, title, description පෙන්නන්න OpenGraph meta tags සකස් කිරීම.

---

## Proposed Technical Changes

Below are the key configuration and code changes to execute after your approval:

### Site Configuration (`config/_default/`)

#### [MODIFY] [hugo.toml](file:///c:/Users/sathi/Desktop/HUGO/sathira_dev/config/_default/hugo.toml)
- Set base configuration, site title, Google Analytics ID parameter placeholder, enable robots.txt, outputs RSS/JSON/HTML, sitemap configuration.

#### [MODIFY] [params.toml](file:///c:/Users/sathi/Desktop/HUGO/sathira_dev/config/_default/params.toml)
- Set `colorScheme = "blowfish"` / custom appearance.
- Header layout set to `fixed-fill-blur`.
- Homepage layout set to `background` or `hero` with card view enabled.
- Article settings: Enable `showBreadcrumbs`, `showTableOfContents`, `showReadingTime`, `showAuthor`, `showRelatedContent`, `showTaxonomies`.
- Verification (Google Search Console) & Adsense blocks setup.

#### [MODIFY] [menus.en.toml](file:///c:/Users/sathi/Desktop/HUGO/sathira_dev/config/_default/menus.en.toml)
- Configure top header navigation (`Home`, `Articles`, `Categories`, `About`, `Contact`).
- Configure footer menu links (`Privacy Policy`, `Terms`, `Categories`, `Contact`).

#### [MODIFY] [languages.en.toml](file:///c:/Users/sathi/Desktop/HUGO/sathira_dev/config/_default/languages.en.toml)
- Setup Author profile details (Name, Headline, Bio, Avatar image path, Social media links for Twitter, GitHub, LinkedIn, YouTube, Facebook, Email).

---

### Content & Pages Setup (`content/`)

#### [NEW] [content/_index.md](file:///c:/Users/sathi/Desktop/HUGO/sathira_dev/content/_index.md)
- Custom homepage configuration with hero section details and featured content flags.

#### [NEW] [content/posts/_index.md](file:///c:/Users/sathi/Desktop/HUGO/sathira_dev/content/posts/_index.md)
- Blog articles section landing page with card view enabled.

#### [NEW] Sample Posts (`content/posts/welcome-to-my-blog/index.md`, `content/posts/getting-started-with-tech/index.md`)
- Rich sample articles with cover photos, tags, categories, code snippets, TOC, and author metadata to showcase the WordPress-style look immediately.

#### [NEW] [content/about/_index.md](file:///c:/Users/sathi/Desktop/HUGO/sathira_dev/content/about/_index.md)
- Complete About Author / Site profile page.

#### [NEW] [content/contact/_index.md](file:///c:/Users/sathi/Desktop/HUGO/sathira_dev/content/contact/_index.md)
- Contact form / information page.

#### [NEW] [content/privacy-policy/_index.md](file:///c:/Users/sathi/Desktop/HUGO/sathira_dev/content/privacy-policy/_index.md)
- Adsense compliant privacy policy.

---

### Styling & Assets (`assets/` & `static/`)

#### [NEW] [assets/css/custom.css](file:///c:/Users/sathi/Desktop/HUGO/sathira_dev/assets/css/custom.css)
- Custom CSS enhancements for glassmorphism, micro-animations, smooth hover card elevation, gradient text effects, and custom scrollbars.

#### [NEW] Asset Images (`static/images/` or `assets/img/`)
- Brand avatars, logo placeholder, hero background asset, article feature images (generated via tool).

---

## Verification Plan

### Automated Tests & Hugo Build Check
- Execute `hugo` command in terminal to ensure 0 build errors, clean HTML generation, valid sitemap, RSS feed, and JSON search index creation.

### Visual & Interactive Verification
- Run local development server (`hugo server -D`) and inspect on desktop and mobile viewports.
- Verify light/dark mode switcher, sticky blurred header, article TOC, search functionality, category tags, author cards, and responsive grid layouts.
