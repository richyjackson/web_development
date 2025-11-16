# Lesson 3: Links and Navigation

## The Anchor Element

Links are created using the `<a>` (anchor) element:

```html
<a href="https://www.example.com">Visit Example.com</a>
```

- **href**: The destination URL (hypertext reference)
- **Link text**: The clickable text displayed to users

## Types of Links

### External Links

Link to other websites:

```html
<a href="https://www.google.com">Go to Google</a>
<a href="https://www.github.com">GitHub</a>
```

### Internal Links

Link to other pages on your own website:

```html
<a href="about.html">About Us</a>
<a href="contact.html">Contact</a>
<a href="/blog/article.html">Read Article</a>
```

### Relative vs Absolute Paths

```html
<!-- Absolute path (full URL) -->
<a href="https://www.example.com/page.html">Absolute Link</a>

<!-- Relative path (from current location) -->
<a href="page.html">Same directory</a>
<a href="folder/page.html">Subdirectory</a>
<a href="../page.html">Parent directory</a>
<a href="../../page.html">Two levels up</a>
```

## Link Targets

Control where links open:

```html
<!-- Open in the same tab (default) -->
<a href="page.html">Same Tab</a>

<!-- Open in a new tab -->
<a href="https://www.example.com" target="_blank">New Tab</a>

<!-- Open in a new tab with security (recommended) -->
<a href="https://www.example.com" target="_blank" rel="noopener noreferrer">
    Secure New Tab
</a>
```

**Always use `rel="noopener noreferrer"` with `target="_blank"` for security.**

## Anchor Links (Jump Links)

Link to specific sections on the same page:

```html
<!-- Link -->
<a href="#section1">Jump to Section 1</a>
<a href="#section2">Jump to Section 2</a>

<!-- Destinations -->
<h2 id="section1">Section 1</h2>
<p>Content for section 1...</p>

<h2 id="section2">Section 2</h2>
<p>Content for section 2...</p>

<!-- Back to top link -->
<a href="#top">Back to Top</a>
```

## Email and Phone Links

### Email Links

```html
<a href="mailto:info@example.com">Send us an email</a>

<!-- With subject and body -->
<a href="mailto:info@example.com?subject=Hello&body=I have a question">
    Email with subject
</a>
```

### Phone Links

```html
<a href="tel:+1234567890">Call us: (123) 456-7890</a>
```

## Download Links

Allow users to download files:

```html
<a href="document.pdf" download>Download PDF</a>
<a href="image.jpg" download="my-image.jpg">Download Image</a>
```

## Link Styling with Title Attribute

Add tooltips to links:

```html
<a href="https://www.example.com" title="Visit Example website">
    Example
</a>
```

## Image Links

Make images clickable:

```html
<a href="https://www.example.com">
    <img src="logo.png" alt="Example Logo">
</a>
```

## Navigation Menus

### Basic Navigation

```html
<nav>
    <a href="index.html">Home</a>
    <a href="about.html">About</a>
    <a href="services.html">Services</a>
    <a href="contact.html">Contact</a>
</nav>
```

### Unordered List Navigation

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

### Nested Navigation (Dropdown)

```html
<nav>
    <ul>
        <li><a href="index.html">Home</a></li>
        <li>
            <a href="products.html">Products</a>
            <ul>
                <li><a href="products/electronics.html">Electronics</a></li>
                <li><a href="products/clothing.html">Clothing</a></li>
                <li><a href="products/books.html">Books</a></li>
            </ul>
        </li>
        <li><a href="contact.html">Contact</a></li>
    </ul>
</nav>
```

## Breadcrumb Navigation

Show the user’s location in the site hierarchy:

```html
<nav aria-label="Breadcrumb">
    <ol>
        <li><a href="/">Home</a></li>
        <li><a href="/products">Products</a></li>
        <li><a href="/products/electronics">Electronics</a></li>
        <li aria-current="page">Laptops</li>
    </ol>
</nav>
```

## Link Best Practices

1. **Use descriptive link text**: Don’t use “click here”
1. **Make links obvious**: Users should know what’s clickable
1. **Open external links in new tabs**: Keep users on your site
1. **Test all links**: Broken links frustrate users
1. **Use meaningful anchor IDs**: `#contact-form` not `#section3`

### Good vs Bad Link Text

```html
<!-- Bad -->
<a href="report.pdf">Click here</a> to download the report.

<!-- Good -->
Download the <a href="report.pdf">annual financial report</a>.
```

## Complete Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Links and Navigation Demo</title>
</head>
<body>
    <header>
        <h1>My Website</h1>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>
    
    <main>
        <section id="home">
            <h2>Welcome</h2>
            <p>Visit our <a href="https://blog.example.com" target="_blank" rel="noopener noreferrer">blog</a> for more information.</p>
        </section>
        
        <section id="about">
            <h2>About Us</h2>
            <p>Learn more about our company.</p>
        </section>
        
        <section id="contact">
            <h2>Contact</h2>
            <p>Email: <a href="mailto:info@example.com">info@example.com</a></p>
            <p>Phone: <a href="tel:+1234567890">+1 (234) 567-890</a></p>
        </section>
    </main>
    
    <footer>
        <p><a href="#home">Back to Top</a></p>
    </footer>
</body>
</html>
```

## Practice Exercises

1. Create a navigation menu with at least 4 links
1. Add anchor links to create a table of contents for a long page
1. Create email and phone links for a contact section
1. Build a breadcrumb navigation for a multi-level site structure
1. Make an image clickable that links to another page

## Next Lesson

In Lesson 4, we’ll learn about images and multimedia in HTML.
