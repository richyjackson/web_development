# Lesson 8: Metadata and SEO

## What is Metadata?

Metadata is data about your HTML document that doesn’t appear on the page but helps browsers, search engines, and social media platforms understand your content.

## The Head Section

All metadata goes in the `<head>` section:

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Title</title>
    <!-- More metadata here -->
</head>
```

## Essential Meta Tags

### Character Encoding

```html
<meta charset="UTF-8">
```

Ensures proper display of special characters and emojis.

### Viewport

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Makes your site responsive on mobile devices.

### Title

```html
<title>Page Title - Site Name</title>
```

- Appears in browser tabs
- Shows in search results
- Should be 50-60 characters
- Include keywords naturally

### Description

```html
<meta name="description" content="A concise description of your page content, ideally 150-160 characters, that appears in search results.">
```

- Appears in search engine results
- Should be compelling and accurate
- 150-160 characters ideal
- Include target keywords

### Keywords (Less Important Now)

```html
<meta name="keywords" content="HTML, web development, tutorial, SEO">
```

**Note: Most search engines ignore this now, but it doesn’t hurt to include.**

### Author

```html
<meta name="author" content="John Doe">
```

## Linking External Resources

### Stylesheets

```html
<link rel="stylesheet" href="styles.css">
<link rel="stylesheet" href="https://cdn.example.com/library.css">
```

### Favicon

```html
<link rel="icon" type="image/png" href="favicon.png">
<link rel="icon" type="image/x-icon" href="favicon.ico">
<link rel="apple-touch-icon" sizes="180x180" href="apple-touch-icon.png">
```

### Canonical URL

Prevent duplicate content issues:

```html
<link rel="canonical" href="https://www.example.com/page">
```

### Alternate Language Versions

```html
<link rel="alternate" hreflang="es" href="https://example.com/es/page">
<link rel="alternate" hreflang="fr" href="https://example.com/fr/page">
```

## Open Graph (Social Media)

Control how your page appears when shared on social media:

```html
<!-- Facebook, LinkedIn, etc. -->
<meta property="og:title" content="Your Page Title">
<meta property="og:description" content="Description of your page">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:url" content="https://example.com/page">
<meta property="og:type" content="website">
<meta property="og:site_name" content="Your Site Name">
```

## Twitter Cards

Customize appearance on Twitter:

```html
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:site" content="@yourusername">
<meta name="twitter:title" content="Your Page Title">
<meta name="twitter:description" content="Description of your page">
<meta name="twitter:image" content="https://example.com/image.jpg">
```

## Robots Meta Tag

Control search engine crawling:

```html
<!-- Allow indexing and following links (default) -->
<meta name="robots" content="index, follow">

<!-- Prevent indexing -->
<meta name="robots" content="noindex, nofollow">

<!-- Allow indexing but don't follow links -->
<meta name="robots" content="index, nofollow">

<!-- Prevent caching -->
<meta name="robots" content="noarchive">
```

## Theme Color

Set browser theme color (mobile):

```html
<meta name="theme-color" content="#4285f4">
```

## Structured Data (JSON-LD)

Help search engines understand your content:

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "Article Title",
  "author": {
    "@type": "Person",
    "name": "John Doe"
  },
  "datePublished": "2024-01-15",
  "image": "https://example.com/image.jpg"
}
</script>
```

### Organization Schema

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Company Name",
  "url": "https://www.example.com",
  "logo": "https://www.example.com/logo.png",
  "contactPoint": {
    "@type": "ContactPoint",
    "telephone": "+1-234-567-8900",
    "contactType": "Customer Service"
  }
}
</script>
```

### Local Business Schema

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": "Business Name",
  "image": "https://example.com/photo.jpg",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "123 Main St",
    "addressLocality": "City",
    "addressRegion": "State",
    "postalCode": "12345",
    "addressCountry": "US"
  },
  "telephone": "+1-234-567-8900"
}
</script>
```

## Complete SEO-Optimized Head

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Basic Meta Tags -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    
    <!-- SEO Meta Tags -->
    <title>Professional Web Development Services | YourCompany</title>
    <meta name="description" content="Expert web development services including responsive design, custom websites, and modern web applications. Get a free consultation today.">
    <meta name="keywords" content="web development, responsive design, HTML, CSS, JavaScript">
    <meta name="author" content="YourCompany">
    
    <!-- Canonical URL -->
    <link rel="canonical" href="https://www.example.com/services">
    
    <!-- Robots -->
    <meta name="robots" content="index, follow">
    
    <!-- Open Graph / Facebook -->
    <meta property="og:type" content="website">
    <meta property="og:url" content="https://www.example.com/services">
    <meta property="og:title" content="Professional Web Development Services">
    <meta property="og:description" content="Expert web development services including responsive design, custom websites, and modern web applications.">
    <meta property="og:image" content="https://www.example.com/images/og-image.jpg">
    <meta property="og:site_name" content="YourCompany">
    
    <!-- Twitter -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:url" content="https://www.example.com/services">
    <meta name="twitter:title" content="Professional Web Development Services">
    <meta name="twitter:description" content="Expert web development services including responsive design, custom websites, and modern web applications.">
    <meta name="twitter:image" content="https://www.example.com/images/twitter-image.jpg">
    
    <!-- Favicons -->
    <link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
    <link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png">
    <link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
    
    <!-- Theme Color -->
    <meta name="theme-color" content="#4285f4">
    
    <!-- Stylesheets -->
    <link rel="stylesheet" href="styles.css">
    
    <!-- Structured Data -->
    <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "Organization",
      "name": "YourCompany",
      "url": "https://www.example.com",
      "logo": "https://www.example.com/logo.png"
    }
    </script>
</head>
<body>
    <!-- Page content -->
</body>
</html>
```

## SEO Best Practices

### Content Optimization

1. **Use semantic HTML**: Helps search engines understand structure
1. **One H1 per page**: Should match or be similar to title tag
1. **Proper heading hierarchy**: H1 → H2 → H3 (don’t skip levels)
1. **Alt text for images**: Describe images for accessibility and SEO
1. **Internal linking**: Link to other relevant pages on your site
1. **Quality content**: Original, valuable, well-written content

### Technical SEO

```html
<!-- Language declaration -->
<html lang="en">

<!-- Clean URLs -->
<!-- Good: /services/web-development -->
<!-- Bad: /page.php?id=123&cat=services -->

<!-- Mobile-friendly -->
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<!-- Fast loading -->
<!-- Optimize images, minify CSS/JS, use CDN -->

<!-- HTTPS -->
<!-- Always use secure protocol -->
```

### URL Structure

```html
<!-- Good URLs -->
https://example.com/blog/html-tutorial
https://example.com/products/web-hosting

<!-- Bad URLs -->
https://example.com/p?id=123
https://example.com/page.php?cat=blog&post=456
```

## Sitemap

Create an XML sitemap:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://www.example.com/</loc>
    <lastmod>2024-01-15</lastmod>
    <changefreq>weekly</changefreq>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://www.example.com/about</loc>
    <lastmod>2024-01-10</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.8</priority>
  </url>
</urlset>
```

Reference in HTML:

```html
<link rel="sitemap" type="application/xml" href="/sitemap.xml">
```

## Robots.txt

Control crawler access (place at root: `/robots.txt`):

```
User-agent: *
Allow: /
Disallow: /admin/
Disallow: /private/

Sitemap: https://www.example.com/sitemap.xml
```

## Practice Exercises

1. Add comprehensive metadata to an existing HTML page
1. Create Open Graph and Twitter Card meta tags for social sharing
1. Implement JSON-LD structured data for your website
1. Optimize page title and description for SEO
1. Create a robots.txt file for your website
1. Generate an XML sitemap for a multi-page site

## Next Lesson

In Lesson 9, we’ll explore HTML5 APIs and advanced features.
