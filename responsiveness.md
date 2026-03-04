# Responsive Web Design 

---

# 1️⃣ What is Responsiveness?

Responsive website = Website that looks good on:

* 📱 Mobile
* 📲 Tablet
* 💻 Laptop
* 🖥 Desktop

It changes layout automatically based on screen size.

---

# 2️⃣ Very First Step 

Always add this inside <head>

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Without this → Mobile will show zoomed desktop version ❌

---

# 3️⃣ Problem: Fixed Width (Not Responsive)

❌ Wrong Way

```css
.container {
    width: 1200px;
}
```

If screen is 400px → content will overflow.

---

# 4️⃣ Correct Way: Flexible Width

✅ Use % instead of px

```css
.container {
    width: 90%;
    margin: auto;
}
```

Better version:

```css
.container {
    width: 90%;
    max-width: 1200px;
    margin: auto;
}
```

Now it adjusts automatically.

---

# 5️⃣ Media Queries 

Media query = Apply CSS only for certain screen size.

Basic Syntax:

```css
@media (max-width: 600px) {
    body {
        background: lightblue;
    }
}
```

Means: If screen ≤ 600px → apply this CSS

---

# 6️⃣ Real Layout Example

HTML:

```html
<div class="container">
    <div class="box">Box 1</div>
    <div class="box">Box 2</div>
    <div class="box">Box 3</div>
</div>
```

CSS (Desktop View):

```css
.container {
    display: flex;
}

.box {
    width: 33%;
    padding: 20px;
    background: lightgray;
    border: 1px solid black;
}
```

Now on desktop → 3 boxes in one row.

---

# 7️⃣ Make It Responsive for Mobile

```css
@media (max-width: 768px) {
    .container {
        flex-direction: column;
    }

    .box {
        width: 100%;
    }
}
```

Now on mobile → Boxes stack vertically.

---

# 8️⃣ Flexbox (Best for Responsive)

```css
.container {
    display: flex;
    flex-wrap: wrap;
}

.box {
    flex: 1 1 300px;
    margin: 10px;
}
```

Meaning:

* Minimum width = 300px
* If space less → moves to next line

No media query needed here ✅

---

# 9️⃣ Grid (Even Better)

```css
.container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
}
```

What happens?

* Each box minimum 250px
* Automatically adjusts columns
* Fully responsive 🔥

---

# 🔟 Responsive Images

Problem: Image overflow

Solution:

```css
img {
    max-width: 100%;
    height: auto;
}
```

Now image never goes outside container.

---

# 1️⃣1️⃣ Responsive Text

Bad:

```css
h1 {
    font-size: 40px;
}
```

Better:

```css
h1 {
    font-size: 5vw;
}
```

Best:

```css
h1 {
    font-size: clamp(1.5rem, 4vw, 3rem);
}
```

clamp(min, preferred, max)

---

# 1️⃣2️⃣ Complete Simple Responsive Page

```html
<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
body {
    margin: 0;
    font-family: Arial;
}

.container {
    display: flex;
    flex-wrap: wrap;
}

.box {
    flex: 1 1 300px;
    padding: 20px;
    background: lightgray;
    margin: 10px;
    text-align: center;
}

@media (max-width: 600px) {
    body {
        background: lightblue;
    }
}

</style>
</head>
<body>

<div class="container">
    <div class="box">Box 1</div>
    <div class="box">Box 2</div>
    <div class="box">Box 3</div>
</div>

</body>
</html>
```

---

# 1️⃣3️⃣ Important Points

* Use viewport meta tag
* Avoid fixed width (px)
* Use % , vw , rem
* Use media queries
* Use Flexbox or Grid
* Test in Chrome DevTools

---

# 1️⃣4️⃣ Example 1: Responsive Navbar

```html
<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
body {
    margin: 0;
    font-family: Arial;
}

.navbar {
    display: flex;
    justify-content: space-between;
    background-color: black;
    padding: 15px;
}

.navbar a {
    color: white;
    text-decoration: none;
    margin: 0 10px;
}

.menu {
    display: flex;
}

/* Mobile */
@media (max-width: 600px) {
    .menu {
        flex-direction: column;
        align-items: center;
    }
}

</style>
</head>
<body>

<div class="navbar">
    <div>Logo</div>
    <div class="menu">
        <a href="#">Home</a>
        <a href="#">About</a>
        <a href="#">Contact</a>
    </div>
</div>

</body>
</html>
```

---

# 1️⃣5️⃣ Example 2: Responsive Card Layout 

```html
<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
body {
    font-family: Arial;
    margin: 0;
}

.container {
    display: flex;
    flex-wrap: wrap;
    padding: 20px;
}

.card {
    flex: 1 1 300px;
    background: lightgray;
    margin: 10px;
    padding: 20px;
    border-radius: 10px;
}

.card img {
    max-width: 100%;
    height: auto;
}

</style>
</head>
<body>

<div class="container">
    <div class="card">
        <img src="https://via.placeholder.com/300" alt="Image">
        <h3>Card 1</h3>
        <p>This is responsive card.</p>
    </div>

    <div class="card">
        <img src="https://via.placeholder.com/300" alt="Image">
        <h3>Card 2</h3>
        <p>This is responsive card.</p>
    </div>

    <div class="card">
        <img src="https://via.placeholder.com/300" alt="Image">
        <h3>Card 3</h3>
        <p>This is responsive card.</p>
    </div>
</div>

</body>
</html>
```

---

# 1️⃣6️⃣ Example 3: Responsive Sidebar Layout 

```html
<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
body {
    margin: 0;
    font-family: Arial;
}

.layout {
    display: flex;
}

.sidebar {
    width: 250px;
    background: black;
    color: white;
    padding: 20px;
}

.content {
    flex: 1;
    padding: 20px;
}

/* Mobile */
@media (max-width: 768px) {
    .layout {
        flex-direction: column;
    }

    .sidebar {
        width: 100%;
    }
}

</style>
</head>
<body>

<div class="layout">
    <div class="sidebar">
        <h3>Sidebar</h3>
        <p>Links</p>
    </div>

    <div class="content">
        <h1>Main Content</h1>
        <p>This layout becomes vertical on mobile.</p>
    </div>
</div>

</body>
</html>
```

---

