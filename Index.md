HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Variables & Design System</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- Header Section -->
    <header class="site-header">
        <h1>Design System & Tokens</h1>
        <p>Built using reusable CSS custom properties (variables) for consistent scaling and themes.</p>
    </header>

    <main class="container">

        <!-- Card Component -->
        <section class="card">
            <h2>Card Component Title</h2>
            <p>This card uses design tokens for background colors, padding, margins, and typography sizes. Changing a single variable in `:root` instantly updates this element across the entire project.</p>
            
            <div class="button-group">
                <button class="btn btn-primary">Primary Action</button>
                <button class="btn btn-secondary">Secondary Action</button>
            </div>
        </section>

        <!-- Second Card Component to Verify Global Updates -->
        <section class="card">
            <h2>Another Card Component</h2>
            <p>Notice how multiple cards, buttons, and headings share the exact same token scale, keeping the UI completely synchronized and maintainable.</p>
            <button class="btn btn-primary">Explore More</button>
        </section>

    </main>

    <footer>
        <p>&copy; 2026 Design System Practice</p>
    </footer>

</body>
</html>

CSS
:root {
    /* Color Palette Tokens */
    --color-primary: #3498db;
    --color-secondary: #2ecc71;
    --color-bg: #f4f6f8;
    --color-surface: #ffffff;
    --color-text: #2c3e50;
    --color-text-muted: #7f8c8d;

    /* Spacing Tokens */
    --spacing-sm: 8px;
    --spacing-md: 16px;
    --spacing-lg: 24px;
    --spacing-xl: 32px;

    /* Font Size Tokens */
    --font-size-sm: 0.875rem;
    --font-size-md: 1rem;
    --font-size-lg: 1.25rem;
    --font-size-xl: 2rem;
}

/* ==========================================
   GLOBAL STYLES USING TOKENS
   ========================================== */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: var(--color-bg);
    color: var(--color-text);
    line-height: 1.6;
    padding: var(--spacing-lg);
}

/* Header */
.site-header {
    text-align: center;
    margin-bottom: var(--spacing-xl);
}

.site-header h1 {
    font-size: var(--font-size-xl);
    color: var(--color-text);
    margin-bottom: var(--spacing-sm);
}

.site-header p {
    font-size: var(--font-size-md);
    color: var(--color-text-muted);
}

/* Layout Container */
.container {
    max-width: 700px;
    margin: 0 auto;
}

/* Card Component */
.card {
    background-color: var(--color-surface);
    padding: var(--spacing-lg);
    margin-bottom: var(--spacing-lg);
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.04);
}

.card h2 {
    font-size: var(--font-size-lg);
    color: var(--color-text);
    margin-bottom: var(--spacing-md);
}

.card p {
    font-size: var(--font-size-md);
    color: var(--color-text-muted);
    margin-bottom: var(--spacing-lg);
}

/* Buttons */
.button-group {
    display: flex;
    gap: var(--spacing-sm);
}

.btn {
    padding: var(--spacing-sm) var(--spacing-md);
    font-size: var(--font-size-sm);
    font-weight: 600;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: opacity 0.2s ease;
}

.btn-primary {
    background-color: var(--color-primary);
    color: #ffffff;
}

.btn-secondary {
    background-color: var(--color-secondary);
    color: #ffffff;
}

.btn:hover {
    opacity: 0.9;
}

/* Footer */
footer {
    text-align: center;
    color: var(--color-text-muted);
    font-size: var(--font-size-sm);
    margin-top: var(--spacing-xl);
}