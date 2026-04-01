# Personal Portfolio Rebrand Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Convert the Say Studio app-studio landing page into Vortana Say's personal portfolio showcasing apps, books, and articles.

**Architecture:** Single-file modification of `index.html`. All changes are to the existing embedded HTML/CSS/JS. No new files, no build tools, no framework changes. The site remains a static GitHub Pages site.

**Tech Stack:** HTML5, CSS3 (embedded), vanilla JavaScript, Google Fonts (Inter)

---

## File Map

- Modify: `index.html` (all tasks touch this single file)

The modification is broken into 7 sequential tasks, each targeting an isolated section of the HTML so changes don't conflict.

---

### Task 1: Update `<head>` Meta Tags and Title

**Files:**
- Modify: `index.html:1-18`

- [ ] **Step 1: Replace meta tags and title**

Change the `<head>` section meta tags from Say Studio branding to personal portfolio branding:

```html
<meta name="description" content="Vortana Say - Software engineer, author, and creator. Apps, books, and articles on Android development and machine learning.">
<meta name="keywords" content="Vortana Say, Android developer, machine learning, Prompter Buddy, ML for Android Engineers, software engineer portfolio">
<meta name="author" content="Vortana Say">

<title>Vortana Say | Software Engineer & Creator</title>
```

Lines 6-10 in the current file. Replace the existing `<meta name="description">`, `<meta name="keywords">`, `<meta name="author">`, and `<title>` tags.

- [ ] **Step 2: Commit**

```bash
git add index.html
git commit -m "chore: update meta tags for personal portfolio rebrand"
```

---

### Task 2: Update Navigation

**Files:**
- Modify: `index.html:596-609` (nav HTML)

- [ ] **Step 1: Replace nav logo and links**

Replace the entire `<nav>` inner content. Change logo from "Say Studio" with "S" icon to "Vortana Say" with "V" icon. Add Books and Articles nav links.

Old (lines 597-608):
```html
<div class="nav-container">
    <a href="#" class="logo">
        <div class="logo-icon">S</div>
        <span>Say Studio</span>
    </a>
    <ul class="nav-links">
        <li><a href="#apps">Apps</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#contact">Contact</a></li>
    </ul>
    <button class="mobile-menu-btn">&#9776;</button>
</div>
```

New:
```html
<div class="nav-container">
    <a href="#" class="logo">
        <div class="logo-icon">V</div>
        <span>Vortana Say</span>
    </a>
    <ul class="nav-links">
        <li><a href="#apps">Apps</a></li>
        <li><a href="#books">Books</a></li>
        <li><a href="#articles">Articles</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#contact">Contact</a></li>
    </ul>
    <button class="mobile-menu-btn">&#9776;</button>
</div>
```

- [ ] **Step 2: Commit**

```bash
git add index.html
git commit -m "chore: update nav to personal branding with books and articles links"
```

---

### Task 3: Update Hero Section

**Files:**
- Modify: `index.html:612-630` (hero HTML)

- [ ] **Step 1: Replace hero content**

Change from studio branding to personal branding. Replace the hero section inner content.

Old (lines 613-629):
```html
<div class="hero-content">
    <div class="hero-badge">
        <span class="hero-badge-dot"></span>
        <span>Indie App Studio</span>
    </div>
    <h1>Say Studio</h1>
    <p class="hero-tagline">Apps designed with purpose. We build thoughtful mobile experiences that make a difference in everyday life.</p>
    <div class="hero-cta">
        <a href="#apps" class="btn btn-primary">
            <span>View Our Apps</span>
            <span>&rarr;</span>
        </a>
        <a href="#contact" class="btn btn-secondary">
            <span>Get in Touch</span>
        </a>
    </div>
</div>
```

New:
```html
<div class="hero-content">
    <div class="hero-badge">
        <span class="hero-badge-dot"></span>
        <span>Software Engineer & Creator</span>
    </div>
    <h1>Vortana Say</h1>
    <p class="hero-tagline">I build Android apps, write about machine learning, and create resources for developers who want to ship ML-powered products.</p>
    <div class="hero-cta">
        <a href="#apps" class="btn btn-primary">
            <span>View My Work</span>
            <span>&rarr;</span>
        </a>
        <a href="#books" class="btn btn-secondary">
            <span>Read My Book</span>
        </a>
    </div>
</div>
```

- [ ] **Step 2: Commit**

```bash
git add index.html
git commit -m "chore: update hero section for personal portfolio"
```

---

### Task 4: Update Apps Section (Remove "Coming Soon" Placeholder)

**Files:**
- Modify: `index.html:633-697` (apps section HTML)

- [ ] **Step 1: Update section header text**

Change the section header from studio language to personal language.

Old (lines 635-639):
```html
<div class="section-header">
    <span class="section-label">Our Apps</span>
    <h2 class="section-title">Crafted with Care</h2>
    <p class="section-desc">Each app is designed to solve real problems with elegant, intuitive solutions.</p>
</div>
```

New:
```html
<div class="section-header">
    <span class="section-label">Apps</span>
    <h2 class="section-title">Apps I've Built</h2>
    <p class="section-desc">Mobile apps designed to solve real problems with elegant, intuitive solutions.</p>
</div>
```

- [ ] **Step 2: Remove the "Coming Soon" placeholder card**

Delete the entire placeholder card (lines 677-694):
```html
<!-- Placeholder for future apps -->
<div class="app-card" style="border-style: dashed; opacity: 0.6;">
    ...
</div>
```

This removes the dashed "Coming Soon" card, leaving only the Prompter Buddy card. New apps can be added later by copying the Prompter Buddy card pattern.

- [ ] **Step 3: Commit**

```bash
git add index.html
git commit -m "chore: update apps section, remove coming soon placeholder"
```

---

### Task 5: Add Books Section (New Section After Apps)

**Files:**
- Modify: `index.html` — insert after the closing `</section>` of the apps section (after line 697)
- Modify: `index.html` CSS — add `.books` and `.book-card` styles

- [ ] **Step 1: Add CSS for books section**

Add the following CSS rules inside the `<style>` tag, after the existing `.store-btn svg` rule (after line 397) and before the ABOUT SECTION comment:

```css
/* ═══════════════════════════════════════════════════════════════════════
   BOOKS SECTION
   ═══════════════════════════════════════════════════════════════════════ */
.book-card {
    background: var(--bg-card);
    border: 1px solid var(--border);
    border-radius: var(--radius-lg);
    padding: 32px;
    display: grid;
    grid-template-columns: auto 1fr;
    gap: 32px;
    align-items: start;
    transition: all 0.3s;
}

.book-card:hover {
    border-color: var(--border-light);
    transform: translateY(-4px);
    box-shadow: var(--shadow-lg);
}

.book-cover {
    width: 180px;
    border-radius: var(--radius);
    box-shadow: var(--shadow-lg);
}

.book-details h3 {
    font-size: 1.25rem;
    font-weight: 600;
    margin-bottom: 8px;
}

.book-meta {
    color: var(--text-muted);
    font-size: 0.875rem;
    margin-bottom: 16px;
}

.book-description {
    color: var(--text-secondary);
    font-size: 0.95rem;
    line-height: 1.7;
    margin-bottom: 20px;
}

.book-highlights {
    list-style: none;
    margin-bottom: 24px;
}

.book-highlights li {
    color: var(--text-secondary);
    font-size: 0.9rem;
    padding: 4px 0;
    padding-left: 20px;
    position: relative;
}

.book-highlights li::before {
    content: "~";
    position: absolute;
    left: 0;
    color: var(--accent);
}

.book-links {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
}

@media (max-width: 768px) {
    .book-card {
        grid-template-columns: 1fr;
        justify-items: center;
        text-align: center;
    }

    .book-highlights li {
        text-align: left;
    }

    .book-links {
        justify-content: center;
    }
}
```

- [ ] **Step 2: Add books section HTML**

Insert the following HTML immediately after the apps `</section>` closing tag (after line 697):

```html
<!-- Books Section -->
<section id="books">
    <div class="container">
        <div class="section-header">
            <span class="section-label">Books</span>
            <h2 class="section-title">Written for Builders</h2>
            <p class="section-desc">Practical guides for developers who learn by building real projects.</p>
        </div>

        <div class="book-card">
            <img src="https://public-files.gumroad.com/variants/profile_KXB3Z2JVDGXL5QTMVXOCOTRFWK34/d2a77bd6bab3c265a1fe47df07b tried multiple placeholders"
                 alt="ML for Android Engineers Book Cover"
                 class="book-cover"
                 onerror="this.style.background='linear-gradient(135deg, var(--accent), #c084fc)'; this.style.width='180px'; this.style.height='240px'; this.alt='Book Cover';">
            <div class="book-details">
                <h3>Machine Learning for Android Engineers</h3>
                <span class="book-meta">From Theory to On-Device Inference &bull; 134 pages &bull; 6 chapters</span>
                <p class="book-description">
                    Build FinRisk -- a complete credit risk assessment app running a trained ML model entirely on-device.
                    No server, no API calls, no internet required. Train in Python, convert to TFLite, run inference
                    in under 15ms on Android with Clean Architecture + Hilt + Compose.
                </p>
                <ul class="book-highlights">
                    <li>Complete end-to-end project: Python training to Android inference</li>
                    <li>Models are 1.8 KB and 2.6 KB -- smaller than most app icons</li>
                    <li>Every Kotlin class and Python function explained line by line</li>
                    <li>Production chapter: testing, crash reporting, feature flags, model updates</li>
                </ul>
                <div class="book-links">
                    <a href="https://7422889060748.gumroad.com/l/ml-android-engineers" target="_blank" class="store-btn">
                        <svg viewBox="0 0 24 24" fill="currentColor" width="20" height="20">
                            <path d="M3 18.5V5a3 3 0 0 1 3-3h12a1 1 0 0 1 1 1v18a1 1 0 0 1-1 1H6.5A3.5 3.5 0 0 1 3 18.5zM5 18.5A1.5 1.5 0 0 0 6.5 20H17V4H6a1 1 0 0 0-1 1v13.5z"/>
                        </svg>
                        <span>Gumroad</span>
                    </a>
                    <a href="https://a.co/d/00TWUseZ" target="_blank" class="store-btn">
                        <svg viewBox="0 0 24 24" fill="currentColor" width="20" height="20">
                            <path d="M1.04 17.52q.1-.16.32-.02a21.308 21.308 0 0 0 10.88 2.9 21.524 21.524 0 0 0 7.74-1.46q.38-.14.56.2.18.36-.18.6a14.258 14.258 0 0 1-8.14 2.5 15.314 15.314 0 0 1-10.68-3.76q-.28-.22-.02-.48l.02-.02zm2.08-2.4q1.1 1.3 2.98 1.3a4.2 4.2 0 0 0 3.34-1.66q.98-1.34.6-3.14h.04a7.804 7.804 0 0 1 3.4.76q.96.5.96 1.26-.02.78-1.08 1.74a15.91 15.91 0 0 1-3.94 2.5q-.24.14-.12.38t.38.14a11.226 11.226 0 0 0 5.54-2.66q1.26-1.2 1.04-2.22-.2-1.02-1.8-1.7a12.996 12.996 0 0 0-4.4-1.06q-.24-.02-.48-.02.04-.44.04-.9a7.68 7.68 0 0 0-.24-2.18q-.34-1-.82-1a.72.72 0 0 0-.42.16 1.632 1.632 0 0 0-.36.66q-.24.72-.24 1.88 0 .86.08 1.44a18.56 18.56 0 0 0-3.86 1.46 4.652 4.652 0 0 0-2.44 3.46q-.14 1.06.72 2.36z"/>
                        </svg>
                        <span>Amazon</span>
                    </a>
                    <a href="https://7422889060748.gumroad.com/l/ml-android-preview" target="_blank" class="store-btn">
                        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" width="20" height="20">
                            <path d="M12 3v12M8 11l4 4 4-4M4 17v2a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2v-2"/>
                        </svg>
                        <span>Free Chapter 1</span>
                    </a>
                </div>
            </div>
        </div>
    </div>
</section>
```

**Note on book cover image:** The `<img>` tag includes an `onerror` fallback that renders a gradient placeholder if the image URL fails. After deploying, replace the `src` with the actual Gumroad cover image URL. To get it: open the Gumroad product page, right-click the cover image, and copy the image URL.

- [ ] **Step 3: Commit**

```bash
git add index.html
git commit -m "feat: add books section with ML for Android Engineers"
```

---

### Task 6: Add Articles Section (New Section After Books)

**Files:**
- Modify: `index.html` — insert after the books `</section>`
- Modify: `index.html` CSS — add `.articles-grid` and `.article-card` styles

- [ ] **Step 1: Add CSS for articles section**

Add the following CSS after the books section CSS (before the ABOUT SECTION comment):

```css
/* ═══════════════════════════════════════════════════════════════════════
   ARTICLES SECTION
   ═══════════════════════════════════════════════════════════════════════ */
.articles {
    background: var(--bg-secondary);
}

.articles-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 24px;
    margin-bottom: 40px;
}

.article-card {
    background: var(--bg-card);
    border: 1px solid var(--border);
    border-radius: var(--radius-lg);
    padding: 28px;
    transition: all 0.3s;
    display: flex;
    flex-direction: column;
}

.article-card:hover {
    border-color: var(--border-light);
    transform: translateY(-4px);
    box-shadow: var(--shadow-lg);
}

.article-platform {
    display: inline-block;
    padding: 4px 10px;
    background: var(--accent-glow);
    color: var(--accent);
    border-radius: 100px;
    font-size: 0.75rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    margin-bottom: 12px;
    width: fit-content;
}

.article-card h3 {
    font-size: 1.1rem;
    font-weight: 600;
    margin-bottom: 8px;
    line-height: 1.4;
}

.article-date {
    color: var(--text-muted);
    font-size: 0.8rem;
    margin-bottom: 12px;
}

.article-excerpt {
    color: var(--text-secondary);
    font-size: 0.9rem;
    line-height: 1.6;
    flex-grow: 1;
    margin-bottom: 16px;
}

.article-read-more {
    color: var(--accent);
    font-size: 0.9rem;
    font-weight: 500;
    transition: color 0.2s;
}

.article-read-more:hover {
    color: var(--accent-hover);
}

.articles-profiles {
    display: flex;
    justify-content: center;
    gap: 16px;
    flex-wrap: wrap;
}

@media (max-width: 768px) {
    .articles-grid {
        grid-template-columns: 1fr;
    }
}
```

- [ ] **Step 2: Add articles section HTML**

Insert the following HTML immediately after the books `</section>`:

```html
<!-- Articles Section -->
<section id="articles" class="articles">
    <div class="container">
        <div class="section-header">
            <span class="section-label">Articles</span>
            <h2 class="section-title">Recent Writing</h2>
            <p class="section-desc">Thoughts on Android development, machine learning, and building real products.</p>
        </div>

        <div class="articles-grid">
            <a href="https://medium.com/@sayvortana.itc/i-built-an-ml-powered-android-app-in-1-8-kb-heres-why-i-turned-it-into-a-book-b4043abbd489" target="_blank" class="article-card">
                <span class="article-platform">Medium</span>
                <h3>I Built an ML-Powered Android App in 1.8 KB -- Here's Why I Turned It Into a Book</h3>
                <span class="article-date">March 2026</span>
                <p class="article-excerpt">The story behind building a credit risk classifier that runs on-device, and why I wrote a book to teach other Android engineers to do the same.</p>
                <span class="article-read-more">Read article &rarr;</span>
            </a>

            <a href="https://pub.towardsai.net/from-cs230-theory-to-production-android-building-a-privacy-first-credit-risk-classifier-4d7259df00ec" target="_blank" class="article-card">
                <span class="article-platform">Towards AI</span>
                <h3>From CS230 Theory to Production Android: Building a Privacy-First Credit Risk Classifier</h3>
                <span class="article-date">February 2026</span>
                <p class="article-excerpt">Taking deep learning theory from Stanford's CS230 and applying it to a production Android app with on-device inference.</p>
                <span class="article-read-more">Read article &rarr;</span>
            </a>

            <a href="https://proandroiddev.com/android-studio-journeys-from-demo-to-enterprise-scale-testing-part-1-ab64f7da68e4" target="_blank" class="article-card">
                <span class="article-platform">ProAndroidDev</span>
                <h3>Android Studio Journeys: From Demo to Enterprise-Scale Testing</h3>
                <span class="article-date">September 2025</span>
                <p class="article-excerpt">A deep dive into Android Studio's Journeys feature and how to scale it from simple demos to enterprise-grade test coverage.</p>
                <span class="article-read-more">Read article &rarr;</span>
            </a>

            <a href="https://medium.com/@sayvortana.itc/breaking-the-monolith-a-practical-step-by-step-guide-to-modularizing-your-android-app-part-1-568b34e08d5f" target="_blank" class="article-card">
                <span class="article-platform">Medium</span>
                <h3>Breaking the Monolith: A Step-by-Step Guide to Modularizing Your Android App</h3>
                <span class="article-date">September 2025</span>
                <p class="article-excerpt">A practical 4-part series on modularizing Android apps, from identifying module boundaries to migrating shared code.</p>
                <span class="article-read-more">Read series &rarr;</span>
            </a>
        </div>

        <div class="articles-profiles">
            <a href="https://medium.com/@sayvortana.itc" target="_blank" class="store-btn">
                <svg viewBox="0 0 24 24" fill="currentColor" width="20" height="20">
                    <path d="M13.54 12a6.8 6.8 0 01-6.77 6.82A6.8 6.8 0 010 12a6.8 6.8 0 016.77-6.82A6.8 6.8 0 0113.54 12zm7.42 0c0 3.54-1.51 6.42-3.38 6.42-1.87 0-3.39-2.88-3.39-6.42s1.52-6.42 3.39-6.42 3.38 2.88 3.38 6.42M24 12c0 3.17-.53 5.75-1.19 5.75-.66 0-1.19-2.58-1.19-5.75s.53-5.75 1.19-5.75C23.47 6.25 24 8.83 24 12z"/>
                </svg>
                <span>All articles on Medium</span>
            </a>
            <a href="https://vsaytech.hashnode.dev/" target="_blank" class="store-btn">
                <svg viewBox="0 0 24 24" fill="currentColor" width="20" height="20">
                    <path d="M22.351 8.019l-6.37-6.37a5.63 5.63 0 00-7.962 0l-6.37 6.37a5.63 5.63 0 000 7.962l6.37 6.37a5.63 5.63 0 007.962 0l6.37-6.37a5.63 5.63 0 000-7.962zM12 15.953a3.953 3.953 0 110-7.906 3.953 3.953 0 010 7.906z"/>
                </svg>
                <span>All articles on Hashnode</span>
            </a>
        </div>
    </div>
</section>
```

- [ ] **Step 3: Commit**

```bash
git add index.html
git commit -m "feat: add articles section with featured posts and profile links"
```

---

### Task 7: Update About, Contact, and Footer Sections

**Files:**
- Modify: `index.html:700-788` (about, contact, footer HTML)

- [ ] **Step 1: Update About section**

Replace the about section content. Change from studio language to personal bio. Update stats to reflect personal achievements.

Old about text and stats (lines 702-736):
```html
<div class="about-content">
    <div class="about-text">
        <h2>About Say Studio</h2>
        <p>Say Studio is an indie app development studio...</p>
        <p>We believe in building apps with purpose...</p>
        <p>Every app we create goes through careful iteration...</p>
    </div>
    <div class="about-stats">
        <div class="stat-card">
            <div class="stat-number">1+</div>
            <div class="stat-label">Apps Published</div>
        </div>
        <div class="stat-card">
            <div class="stat-number">4.5&#9733;</div>
            <div class="stat-label">Average Rating</div>
        </div>
        <div class="stat-card">
            <div class="stat-number">10K+</div>
            <div class="stat-label">Happy Users</div>
        </div>
        <div class="stat-card">
            <div class="stat-number">2020</div>
            <div class="stat-label">Founded</div>
        </div>
    </div>
</div>
```

New:
```html
<div class="about-content">
    <div class="about-text">
        <h2>About Me</h2>
        <p>
            I'm a software engineer specializing in Android development and on-device
            machine learning. I build apps, write technical books, and publish articles
            to help developers ship ML-powered products.
        </p>
        <p>
            My work focuses on making machine learning practical and accessible for
            mobile developers -- no PhD required. I believe the best way to learn
            is by building real projects, not reading papers.
        </p>
        <p>
            When I'm not coding, I'm writing about Android architecture,
            modularization, and the intersection of ML and mobile development.
        </p>
    </div>
    <div class="about-stats">
        <div class="stat-card">
            <div class="stat-number">1</div>
            <div class="stat-label">Book Published</div>
        </div>
        <div class="stat-card">
            <div class="stat-number">1</div>
            <div class="stat-label">App on Play Store</div>
        </div>
        <div class="stat-card">
            <div class="stat-number">10+</div>
            <div class="stat-label">Articles Written</div>
        </div>
        <div class="stat-card">
            <div class="stat-number">10K+</div>
            <div class="stat-label">App Users</div>
        </div>
    </div>
</div>
```

- [ ] **Step 2: Update Contact section text**

Change from studio language to personal.

Old (lines 744-746):
```html
<span class="section-label">Contact</span>
<h2>Let's Connect</h2>
<p>Have questions, feedback, or partnership inquiries? We'd love to hear from you.</p>
```

New:
```html
<span class="section-label">Contact</span>
<h2>Let's Connect</h2>
<p>Have questions, feedback, or want to collaborate? I'd love to hear from you.</p>
```

- [ ] **Step 3: Update Footer**

Change copyright text from studio to personal.

Old (line 781):
```html
<p class="footer-text">&copy; 2024 Say Studio. All rights reserved.</p>
```

New:
```html
<p class="footer-text">&copy; 2026 Vortana Say. All rights reserved.</p>
```

- [ ] **Step 4: Commit**

```bash
git add index.html
git commit -m "chore: update about, contact, and footer for personal branding"
```

---

## Post-Implementation Notes

- **Book cover image:** After deploying, get the actual cover image URL from the Gumroad product page (right-click cover > Copy Image Address) and replace the `src` in the book card `<img>` tag.
- **Adding new articles:** Copy one `<a class="article-card">` block, update the href, platform, title, date, excerpt, and link text.
- **Adding new apps:** Copy the Prompter Buddy `.app-card` block and update the content.
- **Adding new books:** Copy the `.book-card` block and update the content.
