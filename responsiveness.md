# 📱 Responsive Web Design (Basic Notes)

## 1️⃣ What is Responsive Web Design?

Responsive Web Design means a website automatically adjusts its layout to look good on:

- Mobile 📱
- Tablet 📲
- Laptop 💻
- Desktop 🖥

It changes layout based on screen size.

---

## 2️⃣ Important Step (Viewport)

Always add this inside the `<head>` tag:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Without this, mobile devices show the desktop layout in zoomed form.

---

## 3️⃣ Avoid Fixed Width

❌ Wrong way:

```css
.container {
    width: 1200px;
}
```

Small screens will cause overflow.

---

## 4️⃣ Use Percentage Width

✅ Correct way:

```css
.container {
    width: 90%;
    margin: auto;
}
```

Percentage width adjusts automatically according to screen size.

---

## 5️⃣ Media Queries (Basic)

Media query is used to apply CSS for specific screen sizes.

```css
@media (max-width: 600px) {
    body {
        background-color: lightblue;
    }
}
```

Meaning: If screen width is 600px or less, apply this CSS.

---

## 6️⃣ Simple Responsive Layout Example

### HTML

```html
<div class="container">
    <div class="box">Box 1</div>
    <div class="box">Box 2</div>
    <div class="box">Box 3</div>
</div>
```

### CSS

```css
.container {
    display: flex;
}

.box {
    width: 33%;
    padding: 20px;
    border: 1px solid black;
}

@media (max-width: 600px) {
    .container {
        flex-direction: column;
    }

    .box {
        width: 100%;
    }
}
```

On desktop → Boxes appear in one row.  
On mobile → Boxes appear one below another.

---

## 7️⃣ Responsive Images

```css
img {
    max-width: 100%;
    height: auto;
}
```

This prevents images from overflowing.

---

## 8️⃣ Important Points

- Use viewport meta tag  
- Avoid fixed pixel width  
- Use percentage (%)  
- Use media queries  
- Test using browser developer tools  

---

✅ These are the basic concepts of Responsive Web Design.
