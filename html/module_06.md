# Lesson 6: Forms and Input

## The Form Element

Forms collect user input and send it to a server:

```html
<form action="/submit" method="POST">
    <!-- Form inputs go here -->
</form>
```

- **action**: URL where form data is sent
- **method**: `GET` (data in URL) or `POST` (data in request body)

## Text Input

### Basic Text Input

```html
<label for="username">Username:</label>
<input type="text" id="username" name="username">
```

### Input with Attributes

```html
<label for="email">Email:</label>
<input type="email" 
       id="email" 
       name="email" 
       placeholder="Enter your email"
       required
       maxlength="50">
```

Common attributes:

- **id**: Unique identifier (links to label)
- **name**: Field name sent to server
- **placeholder**: Hint text inside input
- **required**: Field must be filled
- **maxlength**: Maximum character limit
- **value**: Default value

## Input Types

### Email

```html
<label for="email">Email:</label>
<input type="email" id="email" name="email" required>
```

### Password

```html
<label for="password">Password:</label>
<input type="password" id="password" name="password" minlength="8" required>
```

### Number

```html
<label for="age">Age:</label>
<input type="number" id="age" name="age" min="18" max="100" step="1">
```

### Date

```html
<label for="birthday">Birthday:</label>
<input type="date" id="birthday" name="birthday">
```

### Time

```html
<label for="appointment">Appointment Time:</label>
<input type="time" id="appointment" name="appointment">
```

### Tel (Telephone)

```html
<label for="phone">Phone:</label>
<input type="tel" id="phone" name="phone" pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}">
```

### URL

```html
<label for="website">Website:</label>
<input type="url" id="website" name="website">
```

### Search

```html
<label for="search">Search:</label>
<input type="search" id="search" name="search">
```

### Color

```html
<label for="color">Favorite Color:</label>
<input type="color" id="color" name="color" value="#ff0000">
```

### Range (Slider)

```html
<label for="volume">Volume:</label>
<input type="range" id="volume" name="volume" min="0" max="100" value="50">
```

### File Upload

```html
<label for="file">Upload File:</label>
<input type="file" id="file" name="file" accept=".pdf,.doc,.docx">
```

## Checkboxes

Select multiple options:

```html
<p>Choose your hobbies:</p>
<input type="checkbox" id="reading" name="hobby" value="reading">
<label for="reading">Reading</label>

<input type="checkbox" id="sports" name="hobby" value="sports">
<label for="sports">Sports</label>

<input type="checkbox" id="music" name="hobby" value="music" checked>
<label for="music">Music</label>
```

## Radio Buttons

Select one option from a group:

```html
<p>Choose your gender:</p>
<input type="radio" id="male" name="gender" value="male">
<label for="male">Male</label>

<input type="radio" id="female" name="gender" value="female">
<label for="female">Female</label>

<input type="radio" id="other" name="gender" value="other">
<label for="other">Other</label>
```

**Note: Radio buttons with the same `name` attribute form a group.**

## Textarea

Multi-line text input:

```html
<label for="message">Message:</label>
<textarea id="message" 
          name="message" 
          rows="5" 
          cols="50"
          placeholder="Enter your message here..."
          maxlength="500"></textarea>
```

## Select (Dropdown)

Choose from a list of options:

```html
<label for="country">Country:</label>
<select id="country" name="country">
    <option value="">-- Select a country --</option>
    <option value="usa">United States</option>
    <option value="uk">United Kingdom</option>
    <option value="canada">Canada</option>
    <option value="australia">Australia</option>
</select>
```

### Pre-selected Option

```html
<select id="color" name="color">
    <option value="red">Red</option>
    <option value="blue" selected>Blue</option>
    <option value="green">Green</option>
</select>
```

### Option Groups

```html
<label for="car">Choose a car:</label>
<select id="car" name="car">
    <optgroup label="German Cars">
        <option value="bmw">BMW</option>
        <option value="mercedes">Mercedes</option>
    </optgroup>
    <optgroup label="Japanese Cars">
        <option value="toyota">Toyota</option>
        <option value="honda">Honda</option>
    </optgroup>
</select>
```

### Multiple Selection

```html
<label for="fruits">Choose fruits (hold Ctrl/Cmd):</label>
<select id="fruits" name="fruits" multiple size="4">
    <option value="apple">Apple</option>
    <option value="banana">Banana</option>
    <option value="orange">Orange</option>
    <option value="grape">Grape</option>
</select>
```

## Buttons

### Submit Button

```html
<button type="submit">Submit Form</button>
<!-- or -->
<input type="submit" value="Submit Form">
```

### Reset Button

```html
<button type="reset">Reset Form</button>
```

### Regular Button

```html
<button type="button" onclick="alert('Clicked!')">Click Me</button>
```

## Fieldset and Legend

Group related form elements:

```html
<fieldset>
    <legend>Personal Information</legend>
    
    <label for="fname">First Name:</label>
    <input type="text" id="fname" name="fname">
    
    <label for="lname">Last Name:</label>
    <input type="text" id="lname" name="lname">
</fieldset>
```

## Datalist

Provide autocomplete suggestions:

```html
<label for="browser">Choose a browser:</label>
<input list="browsers" id="browser" name="browser">

<datalist id="browsers">
    <option value="Chrome">
    <option value="Firefox">
    <option value="Safari">
    <option value="Edge">
</datalist>
```

## Form Validation

### HTML5 Built-in Validation

```html
<!-- Required field -->
<input type="text" name="username" required>

<!-- Email format -->
<input type="email" name="email" required>

<!-- Minimum length -->
<input type="password" name="password" minlength="8" required>

<!-- Pattern matching -->
<input type="text" name="zipcode" pattern="[0-9]{5}" title="5-digit ZIP code">

<!-- Number range -->
<input type="number" name="age" min="18" max="120">
```

### Custom Validation Messages

```html
<input type="text" 
       id="username" 
       name="username" 
       required
       oninvalid="this.setCustomValidity('Please enter your username')"
       oninput="this.setCustomValidity('')">
```

## Complete Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Registration Form</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 600px;
            margin: 50px auto;
            padding: 20px;
        }
        label {
            display: block;
            margin-top: 15px;
            font-weight: bold;
        }
        input, select, textarea {
            width: 100%;
            padding: 8px;
            margin-top: 5px;
            box-sizing: border-box;
        }
        button {
            margin-top: 20px;
            padding: 10px 20px;
            background-color: #4CAF50;
            color: white;
            border: none;
            cursor: pointer;
            font-size: 16px;
        }
        button:hover {
            background-color: #45a049;
        }
        fieldset {
            margin-top: 20px;
            border: 2px solid #ddd;
            padding: 15px;
        }
    </style>
</head>
<body>
    <h1>Registration Form</h1>
    
    <form action="/submit" method="POST">
        <fieldset>
            <legend>Personal Information</legend>
            
            <label for="fname">First Name:</label>
            <input type="text" id="fname" name="fname" required>
            
            <label for="lname">Last Name:</label>
            <input type="text" id="lname" name="lname" required>
            
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>
            
            <label for="phone">Phone:</label>
            <input type="tel" id="phone" name="phone" pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}" placeholder="123-456-7890">
            
            <label for="birthday">Date of Birth:</label>
            <input type="date" id="birthday" name="birthday">
        </fieldset>
        
        <fieldset>
            <legend>Account Details</legend>
            
            <label for="username">Username:</label>
            <input type="text" id="username" name="username" minlength="4" required>
            
            <label for="password">Password:</label>
            <input type="password" id="password" name="password" minlength="8" required>
            
            <label for="country">Country:</label>
            <select id="country" name="country" required>
                <option value="">-- Select a country --</option>
                <option value="usa">United States</option>
                <option value="uk">United Kingdom</option>
                <option value="canada">Canada</option>
            </select>
        </fieldset>
        
        <fieldset>
            <legend>Preferences</legend>
            
            <label>Interests:</label>
            <input type="checkbox" id="tech" name="interest" value="tech">
            <label for="tech">Technology</label>
            
            <input type="checkbox" id="sports" name="interest" value="sports">
            <label for="sports">Sports</label>
            
            <input type="checkbox" id="art" name="interest" value="art">
            <label for="art">Art</label>
            
            <label for="bio">Bio:</label>
            <textarea id="bio" name="bio" rows="4" placeholder="Tell us about yourself..."></textarea>
        </fieldset>
        
        <button type="submit">Register</button>
        <button type="reset">Clear Form</button>
    </form>
</body>
</html>
```

## Best Practices

1. **Always use labels**: Link labels to inputs with `for` and `id`
1. **Use appropriate input types**: Better UX and validation
1. **Provide clear instructions**: Use placeholders and helper text
1. **Validate input**: Use HTML5 validation attributes
1. **Make forms accessible**: Use semantic HTML and ARIA when needed
1. **Group related fields**: Use `<fieldset>` and `<legend>`
1. **Give feedback**: Show errors and success messages clearly

## Practice Exercises

1. Create a contact form with name, email, subject, and message fields
1. Build a survey form with various input types (radio, checkbox, select)
1. Make a login form with username and password fields
1. Create a job application form with file upload capability
1. Build a feedback form with a rating scale using radio buttons
1. Add proper validation to all your forms

## Next Lesson

In Lesson 7, we’ll learn about semantic HTML and page structure.
