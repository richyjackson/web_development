# Lesson 7: Semantic HTML and Page Structure

## What is Semantic HTML?

Semantic HTML uses meaningful tags that describe their content and purpose, rather than just how they look. This improves:

- **Accessibility**: Screen readers understand content better
- **SEO**: Search engines can better index your content
- **Maintainability**: Code is easier to understand and maintain

## Non-Semantic vs Semantic

```html
<!-- Non-semantic (bad) -->
<div id="header">
    <div class="nav">...</div>
</div>
<div id="main">
    <div class="article">...</div>
</div>

<!-- Semantic (good) -->
<header>
    <nav>...</nav>
</header>
<main>
    <article>...</article>
</main>
```

## Document Structure Elements

### Header

The introductory content of a page or section:

```html
<header>
    <img src="logo.png" alt="Company Logo">
    <h1>Website Title</h1>
    <nav>
        <a href="#home">Home</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
    </nav>
</header>
```

### Nav

Navigation links:

```html
<nav>
    <ul>
        <li><a href="index.html">Home</a></li>
        <li><a href="about.html">About</a></li>
        <li><a href="services.html">Services</a></li>
        <li><a href="contact.html">Contact</a></li>
    </ul>
</nav>
```

### Main

The main content of the page (only one per page):

```html
<main>
    <h1>Welcome to Our Website</h1>
    <p>This is the main content area.</p>
</main>
```

### Article

Self-contained, independently distributable content:

```html
<article>
    <h2>Blog Post Title</h2>
    <p>Posted on <time datetime="2024-01-15">January 15, 2024</time></p>
    <p>Article content goes here...</p>
</article>
```

### Section

Thematic grouping of content:

```html
<section>
    <h2>Our Services</h2>
    <p>We offer the following services...</p>
</section>

<section>
    <h2>Our Team</h2>
    <p>Meet our amazing team...</p>
</section>
```

### Aside

Content tangentially related to the main content:

```html
<aside>
    <h3>Related Articles</h3>
    <ul>
        <li><a href="#">Article 1</a></li>
        <li><a href="#">Article 2</a></li>
    </ul>
</aside>
```

### Footer

Footer information for a page or section:

```html
<footer>
    <p>&copy; 2024 Company Name. All rights reserved.</p>
    <nav>
        <a href="#privacy">Privacy Policy</a>
        <a href="#terms">Terms of Service</a>
    </nav>
</footer>
```

## Complete Page Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Semantic HTML Example</title>
</head>
<body>
    <header>
        <h1>My Website</h1>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#blog">Blog</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>
    
    <main>
        <section id="home">
            <h2>Welcome</h2>
            <p>Welcome to my website!</p>
        </section>
        
        <section id="blog">
            <h2>Latest Blog Posts</h2>
            
            <article>
                <header>
                    <h3>First Blog Post</h3>
                    <p>Published on <time datetime="2024-01-15">January 15, 2024</time></p>
                </header>
                <p>This is the content of the first blog post...</p>
                <footer>
                    <p>Tags: <a href="#">HTML</a>, <a href="#">Web Development</a></p>
                </footer>
            </article>
            
            <article>
                <header>
                    <h3>Second Blog Post</h3>
                    <p>Published on <time datetime="2024-01-20">January 20, 2024</time></p>
                </header>
                <p>This is the content of the second blog post...</p>
            </article>
        </section>
        
        <aside>
            <h3>About the Author</h3>
            <p>Information about the author...</p>
        </aside>
    </main>
    
    <footer>
        <p>&copy; 2024 My Website. All rights reserved.</p>
        <nav>
            <a href="#privacy">Privacy</a>
            <a href="#terms">Terms</a>
        </nav>
    </footer>
</body>
</html>
```

## Additional Semantic Elements

### Figure and Figcaption

```html
<figure>
    <img src="chart.png" alt="Sales chart">
    <figcaption>Figure 1: Annual sales growth 2020-2024</figcaption>
</figure>
```

### Mark

Highlight text:

```html
<p>Search results for "HTML": <mark>HTML</mark> is the standard markup language.</p>
```

### Time

Represent dates and times:

```html
<p>The event starts at <time datetime="2024-06-15T19:00">7:00 PM on June 15th</time></p>
```

### Details and Summary

Create collapsible content:

```html
<details>
    <summary>Click to expand</summary>
    <p>This content is hidden until you click the summary.</p>
</details>
```

### Dialog

Modal or dialog box:

```html
<dialog open>
    <p>This is a dialog box</p>
    <button>Close</button>
</dialog>
```

## Accessibility Elements

### Address

Contact information:

```html
<address>
    Contact us at:<br>
    <a href="mailto:info@example.com">info@example.com</a><br>
    <a href="tel:+1234567890">+1 (234) 567-890</a>
</address>
```

### Abbreviation

```html
<p>I love working with <abbr title="HyperText Markup Language">HTML</abbr>!</p>
```

### Cite

Reference to a creative work:

```html
<p>My favorite book is <cite>To Kill a Mockingbird</cite> by Harper Lee.</p>
```

## ARIA (Accessible Rich Internet Applications)

Enhance accessibility when semantic HTML isn’t enough:

```html
<nav aria-label="Main navigation">
    <ul>
        <li><a href="#home" aria-current="page">Home</a></li>
        <li><a href="#about">About</a></li>
    </ul>
</nav>

<button aria-label="Close menu" aria-expanded="false">
    ×
</button>

<div role="alert" aria-live="polite">
    Your changes have been saved.
</div>
```

## Page Landmarks

Major page regions for screen reader users:

```html
<header role="banner">
    <!-- Site header -->
</header>

<nav role="navigation">
    <!-- Navigation -->
</nav>

<main role="main">
    <!-- Main content -->
</main>

<aside role="complementary">
    <!-- Sidebar -->
</aside>

<footer role="contentinfo">
    <!-- Footer -->
</footer>
```

**Note: HTML5 semantic elements have implicit ARIA roles, so you often don’t need to add them explicitly.**

## When to Use Each Element

### Use `<article>` for:

- Blog posts
- News articles
- User comments
- Forum posts
- Product cards

### Use `<section>` for:

- Chapters
- Tabbed content
- Thematic groupings

### Use `<aside>` for:

- Sidebars
- Related links
- Advertisements
- Author information

### Use `<header>` for:

- Site header
- Article header
- Section header

### Use `<footer>` for:

- Site footer
- Article footer
- Section footer

## Best Practices

1. **Use semantic elements instead of divs** when meaning exists
1. **One `<main>` per page**: Contains the primary content
1. **One `<h1>` per page**: The main page title
1. **Proper heading hierarchy**: Don’t skip levels
1. **Use landmarks**: Help screen reader users navigate
1. **Add ARIA when needed**: Enhance accessibility
1. **Think about meaning**: Choose tags based on content purpose, not appearance

## Common Mistakes to Avoid

```html
<!-- Bad: Using divs for everything -->
<div class="header">
<div class="navigation">
<div class="content">

<!-- Good: Using semantic elements -->
<header>
<nav>
<main>

<!-- Bad: Multiple main elements -->
<main>Content 1</main>
<main>Content 2</main>

<!-- Good: One main element -->
<main>
    <section>Content 1</section>
    <section>Content 2</section>
</main>
```

## Practice Exercises

1. Take an existing webpage with only divs and convert it to semantic HTML
1. Create a blog layout with proper semantic structure
1. Build a news website homepage using appropriate semantic elements
1. Create an e-commerce product page with semantic HTML
1. Add ARIA labels to enhance accessibility
1. Audit a webpage for proper heading hierarchy

## Next Lesson

In Lesson 8, we’ll learn about HTML metadata and SEO optimization.
