# Lesson 2: Text Formatting and Headings

## Headings

HTML has six levels of headings, from most important to least:

```html
<h1>Main Heading (Most Important)</h1>
<h2>Subheading</h2>
<h3>Sub-subheading</h3>
<h4>Smaller Heading</h4>
<h5>Even Smaller Heading</h5>
<h6>Smallest Heading</h6>
```

### Best Practices for Headings

- Use only one `<h1>` per page (usually the page title)
- Don’t skip heading levels (don’t jump from `<h2>` to `<h4>`)
- Use headings to create a logical document structure
- Headings help with SEO and accessibility

## Paragraphs

Create paragraphs with the `<p>` tag:

```html
<p>This is a paragraph. It can contain multiple sentences and will wrap to the next line automatically when it reaches the edge of the container.</p>

<p>This is another paragraph. Browsers automatically add space between paragraphs.</p>
```

## Line Breaks and Horizontal Rules

### Line Breaks

```html
<p>This is line one.<br>
This is line two in the same paragraph.</p>
```

### Horizontal Rules

Create a thematic break with a horizontal line:

```html
<p>Section one content.</p>
<hr>
<p>Section two content.</p>
```

## Text Formatting Elements

### Bold and Strong

```html
<b>This text is bold (visual only)</b>
<strong>This text is strong (important, semantic meaning)</strong>
```

**Use `<strong>` for important text, `<b>` for stylistic bold without semantic importance.**

### Italic and Emphasis

```html
<i>This text is italic (visual only)</i>
<em>This text is emphasized (semantic meaning)</em>
```

**Use `<em>` for emphasized text, `<i>` for text in alternate voice or mood.**

### Other Formatting Elements

```html
<mark>Highlighted text</mark>
<small>Smaller text</small>
<del>Deleted text (strikethrough)</del>
<ins>Inserted text (underline)</ins>
<sub>Subscript text: H<sub>2</sub>O</sub>
<sup>Superscript text: E=mc<sup>2</sup></sup>
```

## Preformatted Text

Preserve spaces and line breaks:

```html
<pre>
    This text
        preserves    spaces
    and line breaks
</pre>
```

## Code and Computer Output

```html
<p>Use the <code>console.log()</code> function to print output.</p>

<p>The computer displayed: <samp>Error 404: File not found</samp></p>

<p>Press <kbd>Ctrl</kbd> + <kbd>C</kbd> to copy.</p>
```

## Blockquotes and Inline Quotes

### Blockquote

For longer quotations:

```html
<blockquote cite="https://example.com/quote-source">
    <p>The only way to do great work is to love what you do.</p>
    <footer>— Steve Jobs</footer>
</blockquote>
```

### Inline Quote

For shorter quotes within text:

```html
<p>As Albert Einstein said, <q>Imagination is more important than knowledge.</q></p>
```

## Abbreviations and Definitions

```html
<p>The <abbr title="World Wide Web">WWW</abbr> was invented by Tim Berners-Lee.</p>

<p><dfn>HTML</dfn> is the standard markup language for creating web pages.</p>
```

## Address Element

For contact information:

```html
<address>
    Written by John Doe<br>
    Email: <a href="mailto:john@example.com">john@example.com</a><br>
    123 Main Street<br>
    New York, NY 10001
</address>
```

## Practical Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Text Formatting Demo</title>
</head>
<body>
    <h1>Understanding HTML Text Formatting</h1>
    
    <h2>Introduction</h2>
    <p>This page demonstrates various <strong>HTML text formatting</strong> elements. Learning these is <em>essential</em> for web development.</p>
    
    <hr>
    
    <h2>Famous Quote</h2>
    <blockquote>
        <p>In the middle of difficulty lies opportunity.</p>
        <footer>— Albert Einstein</footer>
    </blockquote>
    
    <h2>Scientific Formula</h2>
    <p>Water is represented as H<sub>2</sub>O, and Einstein's famous equation is E=mc<sup>2</sup>.</p>
    
    <h2>Code Example</h2>
    <p>To create a variable in JavaScript, use the <code>let</code> keyword:</p>
    <pre><code>let message = "Hello, World!";
console.log(message);</code></pre>
</body>
</html>
```

## Practice Exercises

1. Create a blog post with proper heading hierarchy (h1, h2, h3)
1. Format text using bold, italic, and emphasis appropriately
1. Add a famous quote using the blockquote element
1. Create a document with scientific notation using subscript and superscript
1. Use the `<abbr>` tag to explain at least three acronyms

## Next Lesson

In Lesson 3, we’ll learn about links and navigation in HTML.
