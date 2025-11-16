# Lesson 5: Lists and Tables

## Unordered Lists

Lists with bullet points:

```html
<ul>
    <li>Coffee</li>
    <li>Tea</li>
    <li>Milk</li>
</ul>
```

### Custom List Styling

```html
<ul style="list-style-type: square;">
    <li>Square bullets</li>
</ul>

<ul style="list-style-type: circle;">
    <li>Circle bullets</li>
</ul>

<ul style="list-style-type: none;">
    <li>No bullets</li>
</ul>
```

## Ordered Lists

Lists with numbers:

```html
<ol>
    <li>First item</li>
    <li>Second item</li>
    <li>Third item</li>
</ol>
```

### Ordered List Attributes

```html
<!-- Start from a different number -->
<ol start="5">
    <li>Fifth item</li>
    <li>Sixth item</li>
</ol>

<!-- Reverse order -->
<ol reversed>
    <li>Third</li>
    <li>Second</li>
    <li>First</li>
</ol>

<!-- Different numbering types -->
<ol type="A">
    <li>Item A</li>
    <li>Item B</li>
</ol>

<ol type="a">
    <li>Item a</li>
    <li>Item b</li>
</ol>

<ol type="I">
    <li>Item I</li>
    <li>Item II</li>
</ol>

<ol type="i">
    <li>Item i</li>
    <li>Item ii</li>
</ol>
```

## Nested Lists

Lists within lists:

```html
<ul>
    <li>Fruits
        <ul>
            <li>Apples</li>
            <li>Oranges</li>
            <li>Bananas</li>
        </ul>
    </li>
    <li>Vegetables
        <ul>
            <li>Carrots</li>
            <li>Broccoli</li>
        </ul>
    </li>
</ul>
```

### Mixed Nested Lists

```html
<ol>
    <li>Main Topic 1
        <ul>
            <li>Subtopic A</li>
            <li>Subtopic B</li>
        </ul>
    </li>
    <li>Main Topic 2
        <ul>
            <li>Subtopic C</li>
            <li>Subtopic D</li>
        </ul>
    </li>
</ol>
```

## Description Lists

For term-definition pairs:

```html
<dl>
    <dt>HTML</dt>
    <dd>HyperText Markup Language - the standard language for web pages</dd>
    
    <dt>CSS</dt>
    <dd>Cascading Style Sheets - used for styling web pages</dd>
    
    <dt>JavaScript</dt>
    <dd>Programming language for interactive web pages</dd>
</dl>
```

### Multiple Definitions

```html
<dl>
    <dt>Coffee</dt>
    <dd>Black hot drink</dd>
    <dd>Popular morning beverage</dd>
    
    <dt>Milk</dt>
    <dd>White cold drink</dd>
</dl>
```

## Tables

Create structured data in rows and columns:

```html
<table>
    <tr>
        <th>Name</th>
        <th>Age</th>
        <th>City</th>
    </tr>
    <tr>
        <td>Alice</td>
        <td>25</td>
        <td>New York</td>
    </tr>
    <tr>
        <td>Bob</td>
        <td>30</td>
        <td>Boston</td>
    </tr>
</table>
```

- **`<table>`**: Container for the table
- **`<tr>`**: Table row
- **`<th>`**: Table header cell (bold and centered by default)
- **`<td>`**: Table data cell

## Table Sections

Organize tables with semantic sections:

```html
<table>
    <thead>
        <tr>
            <th>Product</th>
            <th>Price</th>
            <th>Quantity</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Laptop</td>
            <td>$999</td>
            <td>5</td>
        </tr>
        <tr>
            <td>Mouse</td>
            <td>$25</td>
            <td>15</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="2">Total Items:</td>
            <td>20</td>
        </tr>
    </tfoot>
</table>
```

## Table Attributes

### Border

```html
<table border="1">
    <!-- table content -->
</table>
```

### Cell Spacing and Padding

```html
<table border="1" cellspacing="10" cellpadding="15">
    <!-- table content -->
</table>
```

**Note: Use CSS for styling in modern HTML.**

## Spanning Cells

### Colspan (Horizontal Span)

```html
<table border="1">
    <tr>
        <th colspan="3">Monthly Savings</th>
    </tr>
    <tr>
        <th>Month</th>
        <th>Savings</th>
        <th>Total</th>
    </tr>
    <tr>
        <td>January</td>
        <td>$100</td>
        <td>$100</td>
    </tr>
</table>
```

### Rowspan (Vertical Span)

```html
<table border="1">
    <tr>
        <th>Name</th>
        <td>John</td>
    </tr>
    <tr>
        <th rowspan="2">Phone</th>
        <td>555-1234</td>
    </tr>
    <tr>
        <td>555-5678</td>
    </tr>
</table>
```

## Caption

Add a title to your table:

```html
<table border="1">
    <caption>Student Grades</caption>
    <tr>
        <th>Name</th>
        <th>Grade</th>
    </tr>
    <tr>
        <td>Alice</td>
        <td>A</td>
    </tr>
    <tr>
        <td>Bob</td>
        <td>B+</td>
    </tr>
</table>
```

## Column Groups

Style entire columns:

```html
<table border="1">
    <colgroup>
        <col span="1" style="background-color: lightblue;">
        <col span="2" style="background-color: lightgreen;">
    </colgroup>
    <tr>
        <th>Name</th>
        <th>Age</th>
        <th>City</th>
    </tr>
    <tr>
        <td>Alice</td>
        <td>25</td>
        <td>New York</td>
    </tr>
</table>
```

## Accessible Tables

Use scope for better accessibility:

```html
<table border="1">
    <tr>
        <th scope="col">Month</th>
        <th scope="col">Sales</th>
    </tr>
    <tr>
        <th scope="row">January</th>
        <td>$10,000</td>
    </tr>
    <tr>
        <th scope="row">February</th>
        <td>$12,000</td>
    </tr>
</table>
```

## Complete Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lists and Tables Demo</title>
    <style>
        table {
            border-collapse: collapse;
            width: 100%;
            margin: 20px 0;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 12px;
            text-align: left;
        }
        th {
            background-color: #4CAF50;
            color: white;
        }
        tr:nth-child(even) {
            background-color: #f2f2f2;
        }
    </style>
</head>
<body>
    <h1>Restaurant Menu</h1>
    
    <h2>Appetizers</h2>
    <ul>
        <li>Caesar Salad</li>
        <li>Garlic Bread</li>
        <li>Buffalo Wings</li>
    </ul>
    
    <h2>Main Courses</h2>
    <ol>
        <li>Grilled Salmon
            <ul>
                <li>Served with vegetables</li>
                <li>Lemon butter sauce</li>
            </ul>
        </li>
        <li>Beef Steak
            <ul>
                <li>Cooked to order</li>
                <li>Side of mashed potatoes</li>
            </ul>
        </li>
    </ol>
    
    <h2>Price List</h2>
    <table>
        <caption>Menu Prices</caption>
        <thead>
            <tr>
                <th>Item</th>
                <th>Category</th>
                <th>Price</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Caesar Salad</td>
                <td>Appetizer</td>
                <td>$8.99</td>
            </tr>
            <tr>
                <td>Grilled Salmon</td>
                <td>Main Course</td>
                <td>$18.99</td>
            </tr>
            <tr>
                <td>Beef Steak</td>
                <td>Main Course</td>
                <td>$24.99</td>
            </tr>
        </tbody>
        <tfoot>
            <tr>
                <td colspan="2"><strong>Average Price</strong></td>
                <td><strong>$17.66</strong></td>
            </tr>
        </tfoot>
    </table>
    
    <h2>Glossary</h2>
    <dl>
        <dt>Al Dente</dt>
        <dd>Pasta cooked to be firm to the bite</dd>
        
        <dt>Garnish</dt>
        <dd>Decorative addition to a dish</dd>
    </dl>
</body>
</html>
```

## Best Practices

1. **Use semantic HTML**: `<thead>`, `<tbody>`, `<tfoot>` for structure
1. **Add captions**: Describe what the table contains
1. **Use scope attributes**: Improve accessibility
1. **Don’t use tables for layout**: Use CSS Grid or Flexbox instead
1. **Keep tables simple**: Complex tables are hard to read
1. **Make tables responsive**: Consider mobile users

## Practice Exercises

1. Create a shopping list using an unordered list with nested items
1. Build a step-by-step recipe using an ordered list
1. Create a table showing a weekly schedule with days and activities
1. Use colspan and rowspan to create a complex table layout
1. Build a glossary using description lists
1. Create a navigation menu using an unordered list

## Next Lesson

In Lesson 6, we’ll learn about HTML forms and user input.
