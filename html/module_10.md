# Lesson 10: Best Practices and Accessibility

## HTML Best Practices

### 1. Always Use DOCTYPE

```html
<!DOCTYPE html>
```

Ensures consistent rendering across browsers.

### 2. Declare Language

```html
<html lang="en">
```

Helps screen readers and translation tools.

### 3. Use Semantic HTML

```html
<!-- Bad -->
<div class="header">
    <div class="nav">...</div>
</div>

<!-- Good -->
<header>
    <nav>...</nav>
</header>
```

### 4. Close All Tags

```html
<!-- Bad -->
<p>Paragraph
<p>Another paragraph

<!-- Good -->
<p>Paragraph</p>
<p>Another paragraph</p>
```

### 5. Use Lowercase

```html
<!-- Bad -->
<DIV CLASS="container">
    <P>Text</P>
</DIV>

<!-- Good -->
<div class="container">
    <p>Text</p>
</div>
```

### 6. Quote Attribute Values

```html
<!-- Bad -->
<img src=image.jpg alt=My Image>

<!-- Good -->
<img src="image.jpg" alt="My Image">
```

### 7. Don’t Skip Heading Levels

```html
<!-- Bad -->
<h1>Main Title</h1>
<h4>Subtitle</h4>

<!-- Good -->
<h1>Main Title</h1>
<h2>Subtitle</h2>
```

### 8. Use Alt Text for Images

```html
<!-- Bad -->
<img src="photo.jpg">

<!-- Good -->
<img src="photo.jpg" alt="Sunset over mountains">

<!-- Decorative images -->
<img src="decoration.png" alt="">
```

## Accessibility (A11y)

### What is Web Accessibility?

Making websites usable by everyone, including people with disabilities:

- Visual impairments (blind, low vision, color blind)
- Hearing impairments
- Motor disabilities
- Cognitive disabilities

### POUR Principles

1. **Perceivable**: Information must be presentable to users
1. **Operable**: Interface must be usable
1. **Understandable**: Content must be clear
1. **Robust**: Works with assistive technologies

## Accessible HTML Techniques

### 1. Semantic HTML

```html
<nav>
    <ul>
        <li><a href="/">Home</a></li>
        <li><a href="/about">About</a></li>
    </ul>
</nav>

<main>
    <article>
        <h1>Article Title</h1>
        <p>Content...</p>
    </article>
</main>

<footer>
    <p>Copyright info</p>
</footer>
```

### 2. Proper Headings

```html
<h1>Main Page Title</h1>
    <h2>Section 1</h2>
        <h3>Subsection 1.1</h3>
        <h3>Subsection 1.2</h3>
    <h2>Section 2</h2>
        <h3>Subsection 2.1</h3>
```

### 3. Label Form Inputs

```html
<!-- Bad -->
<input type="text" name="email">

<!-- Good -->
<label for="email">Email Address:</label>
<input type="text" id="email" name="email">

<!-- Alternative: implicit label -->
<label>
    Email Address:
    <input type="text" name="email">
</label>
```

### 4. ARIA Labels

Use when visual labels aren’t sufficient:

```html
<button aria-label="Close dialog">×</button>

<nav aria-label="Main navigation">
    <ul>...</ul>
</nav>

<input type="search" 
       aria-label="Search the website" 
       placeholder="Search...">
```

### 5. ARIA Landmarks

```html
<header role="banner">
    <!-- Site header -->
</header>

<nav role="navigation" aria-label="Main menu">
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

### 6. Focus Management

Ensure keyboard navigation works:

```html
<!-- Make non-interactive elements focusable if needed -->
<div tabindex="0" role="button" onclick="handleClick()">
    Click me
</div>

<!-- Skip navigation link -->
<a href="#main-content" class="skip-link">Skip to main content</a>

<main id="main-content">
    <!-- Content -->
</main>
```

### 7. Color Contrast

Ensure sufficient contrast:

- Normal text: 4.5:1 contrast ratio
- Large text: 3:1 contrast ratio
- Don’t rely on color alone to convey information

```html
<!-- Bad: Using only color -->
<span style="color: red;">Error</span>

<!-- Good: Using color and text/icon -->
<span style="color: red;">
    <span aria-hidden="true">❌</span>
    Error: Invalid email address
</span>
```

### 8. Link Text

```html
<!-- Bad -->
<a href="report.pdf">Click here</a> to download the report.

<!-- Good -->
Download the <a href="report.pdf">annual financial report (PDF, 2MB)</a>.
```

### 9. Tables

```html
<table>
    <caption>Student Grades - Fall 2024</caption>
    <thead>
        <tr>
            <th scope="col">Student Name</th>
            <th scope="col">Grade</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th scope="row">Alice Johnson</th>
            <td>A</td>
        </tr>
        <tr>
            <th scope="row">Bob Smith</th>
            <td>B+</td>
        </tr>
    </tbody>
</table>
```

### 10. Live Regions

Announce dynamic content changes:

```html
<div role="alert" aria-live="assertive">
    Your form has been submitted successfully!
</div>

<div role="status" aria-live="polite">
    Loading...
</div>
```

## Keyboard Accessibility

All functionality must be accessible via keyboard:

```html
<!-- Ensure custom widgets are keyboard accessible -->
<div role="button" 
     tabindex="0"
     onclick="handleClick()"
     onkeydown="if(event.key === 'Enter' || event.key === ' ') handleClick()">
    Custom Button
</div>

<style>
/* Show focus indicator */
:focus {
    outline: 2px solid blue;
    outline-offset: 2px;
}

/* Don't remove focus outline without replacement */
/* Bad: */
/* :focus { outline: none; } */
</style>
```

## Responsive Design

Make sites work on all devices:

```html
<head>
    <!-- Viewport meta tag -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>

<!-- Responsive images -->
<img src="small.jpg"
     srcset="small.jpg 500w,
             medium.jpg 1000w,
             large.jpg 2000w"
     sizes="(max-width: 600px) 500px,
            (max-width: 1200px) 1000px,
            2000px"
     alt="Responsive image">
```

## Performance Best Practices

### 1. Optimize Images

```html
<!-- Use appropriate format -->
<img src="photo.jpg" alt="Photo"> <!-- JPEG for photos -->
<img src="logo.png" alt="Logo">  <!-- PNG for graphics -->

<!-- Lazy loading -->
<img src="image.jpg" alt="..." loading="lazy">
```

### 2. Minify HTML

Remove unnecessary whitespace and comments in production.

### 3. Defer Non-Critical Scripts

```html
<!-- Defer script loading -->
<script src="script.js" defer></script>

<!-- Or load asynchronously -->
<script src="script.js" async></script>
```

### 4. Preload Critical Resources

```html
<link rel="preload" href="styles.css" as="style">
<link rel="preload" href="font.woff2" as="font" type="font/woff2" crossorigin>
```

## Complete Accessible Page Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Accessible website example following best practices">
    <title>Accessible Website Example</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <!-- Skip link for keyboard users -->
    <a href="#main-content" class="skip-link">Skip to main content</a>
    
    <header role="banner">
        <img src="logo.png" alt="Company Logo">
        <h1>Company Name</h1>
        
        <nav role="navigation" aria-label="Main navigation">
            <ul>
                <li><a href="/" aria-current="page">Home</a></li>
                <li><a href="/about">About</a></li>
                <li><a href="/services">Services</a></li>
                <li><a href="/contact">Contact</a></li>
            </ul>
        </nav>
    </header>
    
    <main id="main-content" role="main">
        <article>
            <h2>Welcome to Our Website</h2>
            
            <section>
                <h3>Our Mission</h3>
                <p>Creating accessible, user-friendly websites for everyone.</p>
            </section>
            
            <section>
                <h3>Contact Us</h3>
                <form action="/submit" method="POST">
                    <div>
                        <label for="name">Full Name:</label>
                        <input type="text" 
                               id="name" 
                               name="name" 
                               required
                               aria-required="true">
                    </div>
                    
                    <div>
                        <label for="email">Email Address:</label>
                        <input type="email" 
                               id="email" 
                               name="email" 
                               required
                               aria-required="true"
                               aria-describedby="email-help">
                        <span id="email-help" class="help-text">
                            We'll never share your email
                        </span>
                    </div>
                    
                    <div>
                        <label for="message">Message:</label>
                        <textarea id="message" 
                                  name="message" 
                                  rows="5"
                                  required
                                  aria-required="true"></textarea>
                    </div>
                    
                    <button type="submit">Send Message</button>
                </form>
            </section>
        </article>
        
        <aside role="complementary" aria-label="Related resources">
            <h3>Related Links</h3>
            <ul>
                <li><a href="/blog">Blog</a></li>
                <li><a href="/resources">Resources</a></li>
            </ul>
        </aside>
    </main>
    
    <footer role="contentinfo">
        <p>&copy; 2024 Company Name. All rights reserved.</p>
        <nav aria-label="Footer navigation">
            <ul>
                <li><a href="/privacy">Privacy Policy</a></li>
                <li><a href="/terms">Terms of Service</a></li>
                <li><a href="/accessibility">Accessibility Statement</a></li>
            </ul>
        </nav>
    </footer>
</body>
</html>
```

## Testing Your HTML

### Tools

1. **W3C Validator**: https://validator.w3.org/
1. **WAVE**: https://wave.webaim.org/
1. **axe DevTools**: Browser extension
1. **Lighthouse**: Built into Chrome DevTools
1. **Screen Readers**: NVDA (Windows), JAWS, VoiceOver (Mac)

### Manual Testing

1. Navigate using only keyboard (Tab, Enter, Space)
1. Test with screen reader
1. Check color contrast
1. Resize text to 200%
1. Test on mobile devices
1. Disable images and check alt text

## Common Mistakes to Avoid

1. ❌ Using `<div>` and `<span>` for everything
1. ❌ Skipping alt attributes on images
1. ❌ Not labeling form inputs
1. ❌ Using placeholder as label
1. ❌ Removing focus outlines without replacement
1. ❌ Using “click here” as link text
1. ❌ Not testing with keyboard
1. ❌ Relying only on color to convey information
1. ❌ Auto-playing audio/video
1. ❌ Not providing text alternatives for non-text content

## Practice Exercises

1. Audit an existing website for accessibility issues
1. Fix accessibility problems in a provided HTML document
1. Create a fully accessible contact form
1. Build a navigation menu that works with keyboard and screen reader
1. Test your websites with different accessibility tools
1. Navigate your website using only a keyboard

## Congratulations!

You’ve completed the HTML course! You now have a solid foundation in:

- HTML structure and syntax
- Text formatting and media
- Forms and user input
- Semantic HTML and accessibility
- SEO optimization
- HTML5 APIs
- Best practices

### Next Steps

1. **Practice**: Build real projects (portfolio, blog, landing pages)
1. **Learn CSS**: Style your HTML beautifully
1. **Learn JavaScript**: Add interactivity
1. **Frameworks**: Explore React, Vue, or Angular
1. **Backend**: Learn server-side languages (Node.js, Python, PHP)
1. **Keep Learning**: Web development constantly evolves

### Resources

- MDN Web Docs: https://developer.mozilla.org/
- W3Schools: https://www.w3schools.com/
- Can I Use: https://caniuse.com/
- WebAIM: https://webaim.org/
- A11y Project: https://www.a11yproject.com/

Happy coding!
