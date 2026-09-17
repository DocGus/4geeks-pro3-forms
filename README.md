# 💳 Payment Form — 4Geeks

<div style="background:#111827; color:#ffffff; padding:12px 16px; border-left:4px solid #60a5fa; border-radius:10px; margin:12px 0; font-weight:500;">
Visual recreation of a payment form using HTML5 and CSS3.
</div>

![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-local-000000?logo=flask&logoColor=white)
![Git](https://img.shields.io/badge/Git-version--control-F05032?logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-repository-181717?logo=github&logoColor=white)

## 📌 Description

This project is part of the exercises from **4Geeks Academy**.

The goal is to recreate a payment form from a visual reference using **HTML5 and CSS3**, while practicing form creation, input types, HTML5 validation, semantic structure, and CSS organization.

The project started using the [official 4Geeks Academy template](https://github.com/4GeeksAcademy/html-hello), which includes a local server based on Flask.

## 🚀 How to Run

### Requirements

- Python 3
- Web browser
- Git

### Create the Virtual Environment

From the project directory:

```bash
python3 -m venv venv
```

Activate the virtual environment:

On Linux/macOS:

```bash
source venv/bin/activate
```

When the virtual environment is active, the terminal displays:

```bash
(venv)
```

### Install Flask

With the virtual environment activated:

```bash
pip install flask
```

### Start the local server

Run:

```bash
python server.py
```

The server will be available at:

```text
http://localhost:3000
```

To stop the server:

```text
Ctrl + C
```

### Deactivate the virtual environment

When you finish working:

```bash
deactivate
```

## 🛠️ Technologies Used

| Technology | Use |
| --- | --- |
| HTML5 | Structure and forms |
| CSS3 | Design, layout, and styling |
| Python 3 | Runtime environment |
| Flask | Local development server |
| Git | Version control |
| GitHub | Remote repository |

## 🧱 Project Structure

```text
4geeks-pro3-forms/
├── index.html
├── style.css
├── server.py
├── learn.json
├── README.md
├── README.es.md
├── README.cn.md
├── .gitignore
└── venv/
```

During development, a virtual environment is also used. It is kept out of version control through `.gitignore`.

The `index.html` file contains the form structure, while `style.css` contains the styles.

The stylesheet is connected using:

```html
<link rel="stylesheet" href="style.css">
```

## 📝 Form Structure

The form was divided into different blocks:

```text
Payment Form
├── Title
├── Alert message
├── Card information
│   ├── Card #
│   ├── CVC #
│   └── Amount
├── Personal information
│   ├── First Name
│   ├── Last Name
│   ├── City
│   ├── State
│   └── Postal Code
├── Payment methods
│   ├── Mastercard
│   ├── Visa
│   └── American Express
├── Message
├── Buttons
│   ├── Cancel
│   └── Send
```

## 🧩 HTML5 Forms

One of the main goals of the project was to practice different types of form elements.

### Text Input

`type="text"` was used for fields such as first name, last name, city, and card number:

```html
<input
    type="text"
    id="first-name"
    name="first-name"
    placeholder="First Name"
    required
>
```

### Numeric Input

The payment amount uses:

```html
<input
    type="number"
    id="amount"
    name="amount"
    placeholder="Amount"
    min="0"
    step="0.01"
    required
>
```

This allows numeric values and specifies cent increments using `step="0.01"`.

## ✅ HTML5 Validation

The form uses built-in HTML5 validation tools.

Among them:

- `required`
- `minlength`
- `maxlength`
- `min`
- `step`
- `pattern`

For example, the CVC field uses a regular expression to accept between 3 and 4 digits:

```html
<input
    type="text"
    id="cvc"
    name="cvc"
    pattern="[0-9]{3,4}"
    maxlength="4"
    required
>
```

The postal code uses a similar validation to accept five numbers:

```html
<input
    type="text"
    id="postal-code"
    name="postal-code"
    pattern="[0-9]{5}"
    maxlength="5"
    required
>
```

Validation is performed directly by the browser before submitting the form.

## ☑️ Radio Buttons

To select the payment method, radio buttons were used.

The three elements share the same `name` attribute, so only one option can be selected:

```html
<input
    type="radio"
    name="card-type"
    value="mastercard"
    required
>
```

Available options:

- Mastercard
- Visa
- American Express

## 🔽 Select

To select the state, a `select` element was used:

```html
<select
    id="state"
    name="state"
    required
>
    <option value="">Pick a state</option>
    <option value="california">California</option>
    <option value="texas">Texas</option>
</select>
```

The `required` attribute prevents the form from being submitted without selecting a state.

## 🎨 CSS Concepts Practiced

### Box Model

Fundamental box model concepts were practiced:

- `margin`
- `padding`
- `border`
- `width`
- `box-sizing`

For example:

```css
* {
    box-sizing: border-box;
}
```

This ensures that the width and height of elements include their content, padding, and border.

### Flexbox

Flexbox was used to organize the different form fields horizontally:

```css
.row {
    display: flex;
    gap: 20px;
    margin-bottom: 20px;
}
```

The fields use:

```css
.field {
    flex: 1;
}
```

This allows the fields to distribute themselves within the available space.

### Responsive Design

A `@media` rule was also added to adapt the form to smaller screens:

```css
@media (max-width: 700px) {
    .row {
        flex-direction: column;
    }
}
```

On smaller screens, the fields switch from horizontal to vertical layout.

## 📄 HTML and CSS Separation

Initially, the styles were placed inside the `index.html` file.

Later, a separate stylesheet was created:

- `style.css`

It was connected from the `<head>` element:

```html
<link rel="stylesheet" href="style.css">
```

This separation keeps the HTML structure and CSS styles organized in separate files.

## 🖥️ Local Server with Flask

During development, the server provided by the 4Geeks Academy template was used through Flask.

The virtual environment is activated with:

```bash
source venv/bin/activate
```

Flask is installed with:

```bash
pip install flask
```

The server is started with:

```bash
python server.py
```

The application is then available at:

```text
http://localhost:3000
```

The `server.py` file uses Flask to serve `index.html` and the other static files in the project, including `style.css`.

## 📚 What I Learned

- Create forms using HTML5.
- Use different input types.
- Use `select`, `textarea`, and radio buttons.
- Apply HTML5 validation with attributes.
- Use `required`, `pattern`, `min`, `step`, `minlength`, and `maxlength`.
- Connect an HTML file to an external CSS stylesheet.
- Use Flexbox to organize elements.
- Apply Box Model concepts.
- Create a basic responsive design using `@media`.
- Create and use a Python virtual environment.
- Install and use Flask.
- Run a project using `server.py`.
- View a project through a local server.
- Use Git and GitHub during development.

## 🔄 Development Process

1. Create the repository from the 4Geeks Academy template.
2. Clone the project and open it in VS Code.
3. Recover and prepare the `index.html` file.
4. Build the payment form structure.
5. Add different HTML5 form fields.
6. Add HTML5 validation.
7. Create the initial styles.
8. Create the `style.css` file.
9. Separate the style rules from the HTML document.
10. Connect `index.html` to `style.css`.
11. Create the `venv` virtual environment.
12. Install Flask.
13. Run `server.py`.
14. Check the form in the browser.
15. Track modifications with Git.
16. Create commits and sync the project with GitHub.

## 🎯 Result

A functional recreation of a payment form using HTML5 and CSS3.

The project provides practice with form creation, native browser validation, Flexbox, Box Model, separation of HTML and CSS responsibilities, basic responsive design, and running applications through a local Flask server.

## 👨‍💻 Author

Gustavo A. Santoyo B.

Project developed as part of the Full Stack development learning process at 4Geeks Academy.

## 📖 Original Template

The project was started using the official HTML template from 4Geeks Academy.
