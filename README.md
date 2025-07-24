# Bootstrap Calculator

A lightweight, standalone JavaScript calculator library that renders a fully functional calculator UI using Bootstrap 5 classes. No dependencies required except Bootstrap CSS.

![Calculator Demo](https://img.shields.io/badge/Bootstrap-5.3+-blue) ![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow) ![License](https://img.shields.io/badge/License-MIT-green)

## ✨ Features

- 🚀 **Zero Dependencies** - Only requires Bootstrap 5 CSS
- 📱 **Responsive Design** - Works perfectly on mobile and desktop
- ⌨️ **Keyboard Support** - Full keyboard navigation and input
- 🎨 **Customizable** - Easy to override styling with CSS
- 🔢 **Mathematical Accuracy** - Proper operator precedence and safe evaluation
- 📊 **Percentage Calculations** - Correctly handles percentage operations (e.g., 1200+18% = 1416)
- 🛡️ **Error Handling** - Smart error recovery and validation
- 🔄 **Multiple Instances** - Create multiple calculators on the same page
- 🎯 **Lightweight** - Under 10KB minified

## 🚀 Quick Start

### 1. Include Bootstrap 5 CSS
```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
```

### 2. Include the Calculator Library
```html
<script src="bootstrap-calculator.js"></script>
```

### 3. Create a Container
```html
<div id="my-calculator"></div>
```

### 4. Initialize the Calculator
```javascript
const calculator = new BootstrapCalculator('#my-calculator');
calculator.init();
```

## 📖 Complete Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator Demo</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>
    <div class="container mt-5">
        <div class="row justify-content-center">
            <div class="col-md-6">
                <div id="calculator-container"></div>
            </div>
        </div>
    </div>

    <script src="bootstrap-calculator.js"></script>
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const calc = new BootstrapCalculator('#calculator-container');
            calc.init();
        });
    </script>
</body>
</html>
```

## 🔧 API Reference

### Constructor
```javascript
new BootstrapCalculator(containerSelector)
```
- `containerSelector` (string): CSS selector for the container element

### Methods

#### `init()`
Initializes the calculator and renders the UI.
```javascript
calculator.init();
```

#### `clear()`
Clears the calculator display.
```javascript
calculator.clear();
```

#### `getValue()`
Returns the current display value as a string.
```javascript
const currentValue = calculator.getValue();
console.log(currentValue); // "123.45"
```

#### `setValue(value)`
Sets the display to a specific value.
```javascript
calculator.setValue('1234');
calculator.setValue(42.5);
```

#### `destroy()`
Removes the calculator UI and cleans up event listeners.
```javascript
calculator.destroy();
```

## ⌨️ Keyboard Support

The calculator supports full keyboard input when focused:

| Key | Action |
|-----|--------|
| `0-9` | Number input |
| `.` | Decimal point |
| `+` `-` `*` `/` | Mathematical operators |
| `%` | Percentage |
| `=` or `Enter` | Calculate result |
| `Escape` or `C` | Clear |
| `Backspace` | Delete last character |

## 🎨 Customization

The calculator uses standard Bootstrap 5 classes, making it easy to customize:

```css
/* Custom display styling */
.calculator-wrapper .calc-display {
    background-color: #2d3748;
    color: #e2e8f0;
    font-family: 'Courier New', monospace;
}

/* Custom button styling */
.calculator-wrapper .calc-btn {
    height: 60px;
    border-radius: 8px;
    transition: all 0.2s ease;
}

/* Number buttons specifically */
.calculator-wrapper .number-btn {
    background-color: #f8f9fa;
}

/* Operator buttons */
.calculator-wrapper .btn-outline-primary {
    border-color: #007bff;
}
```

### Available CSS Classes

- `.calculator-wrapper` - Main wrapper
- `.calc-display` - Display input field
- `.calc-btn` - All calculator buttons
- `.number-btn` - Number buttons only
- Standard Bootstrap button classes (`btn-primary`, `btn-light`, etc.)

## 🧮 Mathematical Features

### Operator Precedence
The calculator follows standard mathematical order of operations:
- Multiplication (`×`) and Division (`÷`) are calculated before Addition (`+`) and Subtraction (`−`)
- Example: `2+3×4` = `14` (not `20`)

### Percentage Calculations
- **Addition/Subtraction**: `1200+18%` calculates as `1200 + (18% of 1200)` = `1416`
- **Standalone**: `18%` calculates as `18 ÷ 100` = `0.18`

### Error Handling
- Division by zero: Shows "Error: Invalid result"
- Invalid expressions: Shows "Error: Invalid expression"
- Automatic error recovery when starting new calculations

## 🔄 Multiple Instances

Create multiple calculators on the same page:

```javascript
// Calculator 1
const calc1 = new BootstrapCalculator('#calculator-1');
calc1.init();

// Calculator 2
const calc2 = new BootstrapCalculator('#calculator-2');
calc2.init();

// They operate independently
calc1.setValue('100');
calc2.setValue('200');
```

## 📱 Browser Support

- ✅ Chrome 60+
- ✅ Firefox 55+
- ✅ Safari 12+
- ✅ Edge 79+
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

*Requires ES6 class support and Bootstrap 5 compatible browsers*

## 🚫 What's NOT Included

This calculator intentionally keeps things simple and doesn't include:
- Scientific functions (sin, cos, log, etc.)
- Memory functions (M+, M-, MR, MC)
- History/previous calculations
- Complex number support
- Parentheses for grouping

## 🤝 Contributing

Contributions are welcome! Please feel free to submit issues and pull requests.

### Development Setup
1. Clone the repository
2. Open `index.html` in your browser
3. Make changes to `bootstrap-calculator.js`
4. Test thoroughly across different browsers

## 📄 License

MIT License - feel free to use in commercial and personal projects.

---

**Made with ❤️ and Bootstrap 5**

*If you find this useful, please give it a ⭐ on GitHub!*