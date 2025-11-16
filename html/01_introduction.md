# Lesson 1: Introduction to HTML

## What is HTML?

HTML (HyperText Markup Language) is the standard language for creating web pages. It describes the structure and content of a webpage using elements and tags.

## Basic HTML Structure

Every HTML document follows this basic structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First Webpage</title>
</head>
<body>
    <h1>Hello, World!</h1>
    <p>This is my first webpage.</p>
</body>
</html>
```

## Understanding HTML Elements

### Anatomy of an HTML Element

```html
<tagname>Content goes here</tagname>
```

- **Opening tag**: `<tagname>`
- **Content**: The text or other elements inside
- **Closing tag**: `</tagname>`

### Self-Closing Tags

Some elements don’t have content and don’t need closing tags:

```html
<img src="image.jpg" alt="Description">
<br>
<hr>
<input type="text">
```

## Key Parts of an HTML Document

### DOCTYPE Declaration

```html
<!DOCTYPE html>
```

Tells the browser this is an HTML5 document.

### HTML Element

```html
<html lang="en">
```

The root element that wraps all content. The `lang` attribute specifies the language.

### Head Section

Contains metadata about the document:

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="A brief description of the page">
    <title>Page Title</title>
</head>
```

- **charset**: Specifies character encoding (UTF-8 supports all languages)
- **viewport**: Makes the page responsive on mobile devices
- **title**: Appears in browser tabs and search results

### Body Section

Contains all visible content:

```html
<body>
    <h1>Main Heading</h1>
    <p>A paragraph of text.</p>
</body>
```

## HTML Comments

Comments are not displayed in the browser:

```html
<!-- This is a comment -->
<!-- 
    Multi-line comment
    can span several lines
-->
```

## Creating Your First HTML File

1. Open a text editor (Notepad, VS Code, Sublime Text, etc.)
1. Copy the basic HTML structure above
1. Save the file as `index.html`
1. Open it in a web browser

## Common Mistakes to Avoid

1. **Forgetting closing tags**: Every opening tag (except self-closing ones) needs a closing tag
1. **Incorrect nesting**: Tags must be properly nested
1. **Missing DOCTYPE**: Always include `<!DOCTYPE html>`
1. **No title**: Every page should have a `<title>` element

### Correct Nesting Example

```html
<!-- Correct -->
<div>
    <p>This is <strong>bold</strong> text.</p>
</div>

<!-- Incorrect -->
<div>
    <p>This is <strong>bold</p></strong>
</div>
```

## Practice Exercises

1. Create a basic HTML page with your name as the title
1. Add a heading and a paragraph about yourself
1. Add an HTML comment explaining what the page is about
1. Validate your HTML using the [W3C Validator](https://validator.w3.org/)

## Next Lesson

In Lesson 2, we’ll explore text formatting and heading elements to structure your content.
