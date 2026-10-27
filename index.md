The HTML File (index.html)
HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profile & Product Card Components</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <main class="card-showcase">
        
        <!-- ================= PROFILE CARD ================= -->
        <article class="card profile-card">
            <!-- Positioned Badge -->
            <span class="card-badge badge-status">Available for Hire</span>

            <header class="profile-card__header">
                <img 
                    src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&q=80&w=300" 
                    alt="Alex Morgan" 
                    class="profile-card__image"
                >
                <h2 class="profile-card__name">Alex Morgan</h2>
                <p class="profile-card__role">UI/UX Designer & Frontend Developer</p>
            </header>

            <div class="profile-card__body">
                <p class="profile-card__description">
                    Passionate about creating intuitive digital experiences, accessible web interfaces, and modern design systems.
                </p>

                <div class="profile-card__skills">
                    <span class="skill-tag">HTML5 / CSS3</span>
                    <span class="skill-tag">JavaScript</span>
                    <span class="skill-tag">Figma</span>
                    <span class="skill-tag">UI Design</span>
                </div>
            </div>

            <footer class="profile-card__footer">
                <button class="btn btn--primary btn--full-width">Contact Alex</button>
            </footer>
        </article>


        <!-- ================= PRODUCT CARD ================= -->
        <article class="card product-card">
            <!-- Positioned Badge -->
            <span class="card-badge badge-sale">25% OFF</span>

            <div class="product-card__image-container">
                <img 
                    src="https://images.unsplash.com/photo-1505740420928-5e560c06d30e?auto=format&fit=crop&q=80&w=400" 
                    alt="Wireless Noise-Canceling Headphones" 
                    class="product-card__image"
                >
            </div>

            <div class="product-card__body">
                <h2 class="product-card__title">Studio Sound Pro Headphones</h2>
                
                <div class="product-card__price-container">
                    <span class="product-card__price">$149.99</span>
                    <span class="product-card__original-price">$199.99</span>
                </div>

                <p class="product-card__description">
                    High-fidelity wireless audio with active noise cancellation, 30-hour battery life, and ultra-comfortable ear cushions.
                </p>
            </div>

            <footer class="product-card__footer">
                <button class="btn btn--accent btn--full-width">Buy Now</button>
            </footer>
        </article>

    </main>

</body>
</html>
2. The CSS File (style.css)
CSS
/* ==========================================================================
   Global Reset & Variables
   ========================================================================== */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

:root {
    --primary-color: #1e293b;
    --accent-color: #2563eb;
    --accent-hover: #1d4ed8;
    --success-color: #10b981;
    --sale-color: #ef4444;
    --bg-page: #f8fafc;
    --bg-card: #ffffff;
    --text-main: #0f172a;
    --text-muted: #64748b;
    --border-color: #e2e8f0;
    
    --radius-sm: 6px;
    --radius-md: 12px;
    --radius-full: 9999px;

    --shadow-card: 0 10px 15px -3px rgba(0, 0, 0, 0.05), 0 4px 6px -2px rgba(0, 0, 0, 0.025);
    --shadow-hover: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
}

body {
    font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
    background-color: var(--bg-page);
    color: var(--text-main);
    line-height: 1.5;
    padding: 40px 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
}

/* Container for displaying cards side-by-side */
.card-showcase {
    display: flex;
    flex-wrap: wrap;
    gap: 30px;
    justify-content: center;
    max-width: 900px;
    width: 100%;
}

/* ==========================================================================
   Base Card Styles (Box Model & Positioning Context)
   ========================================================================== */
.card {
    position: relative; /* Positioning context for absolute badges */
    background-color: var(--bg-card);
    border: 1px solid var(--border-color);
    border-radius: var(--radius-md);
    box-shadow: var(--shadow-card);
    width: 100%;
    max-width: 360px; /* Responsive container control */
    overflow: hidden;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    transition: transform 0.25s ease, box-shadow 0.25s ease;
}

.card:hover {
    transform: translateY(-5px);
    box-shadow: var(--shadow-hover);
}

/* Positioned Badges (Requirement 3) */
.card-badge {
    position: absolute;
    top: 16px;
    right: 16px;
    font-size: 0.75rem;
    font-weight: 700;
    padding: 4px 10px;
    border-radius: var(--radius-full);
    text-transform: uppercase;
    letter-spacing: 0.5px;
    z-index: 10;
}

.badge-status {
    background-color: #d1fae5;
    color: #065f46;
}

.badge-sale {
    background-color: var(--sale-color);
    color: #ffffff;
}

/* ==========================================================================
   1. Profile Card Component
   ========================================================================== */
.profile-card {
    padding: 28px 24px 24px;
    text-align: center;
}

.profile-card__header {
    margin-bottom: 16px;
}

.profile-card__image {
    width: 100px;
    height: 100px;
    border-radius: var(--radius-full);
    object-fit: cover;
    border: 4px solid var(--bg-page);
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
    margin-bottom: 12px;
}

.profile-card__name {
    font-size: 1.35rem;
    color: var(--text-main);
    font-weight: 700;
}

.profile-card__role {
    font-size: 0.875rem;
    color: var(--accent-color);
    font-weight: 600;
    margin-top: 2px;
}

.profile-card__body {
    margin-bottom: 24px;
}

.profile-card__description {
    font-size: 0.925rem;
    color: var(--text-muted);
    margin-bottom: 16px;
}

.profile-card__skills {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    justify-content: center;
}

.skill-tag {
    background-color: #f1f5f9;
    color: var(--primary-color);
    font-size: 0.775rem;
    font-weight: 600;
    padding: 4px 10px;
    border-radius: var(--radius-sm);
}

/* ==========================================================================
   2. Product Card Component
   ========================================================================== */
.product-card__image-container {
    width: 100%;
    height: 220px;
    background-color: #f1f5f9;
    overflow: hidden;
}

.product-card__image {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.3s ease;
}

.product-card:hover .product-card__image {
    transform: scale(1.05);
}

.product-card__body {
    padding: 20px 20px 16px;
    flex-grow: 1;
}

.product-card__title {
    font-size: 1.2rem;
    font-weight: 700;
    color: var(--text-main);
    margin-bottom: 8px;
}

.product-card__price-container {
    display: flex;
    align-items: baseline;
    gap: 8px;
    margin-bottom: 12px;
}

.product-card__price {
    font-size: 1.35rem;
    font-weight: 800;
    color: var(--text-main);
}

.product-card__original-price {
    font-size: 0.9rem;
    color: var(--text-muted);
    text-decoration: line-through;
}

.product-card__description {
    font-size: 0.875rem;
    color: var(--text-muted);
}

.product-card__footer {
    padding: 0 20px 20px;
}

/* ==========================================================================
   Button Components
   ========================================================================== */
.btn {
    border: none;
    padding: 12px 20px;
    font-size: 0.95rem;
    font-weight: 600;
    border-radius: var(--radius-sm);
    cursor: pointer;
    transition: background-color 0.2s ease, transform 0.1s ease;
}

.btn:active {
    transform: scale(0.98);
}

.btn--full-width {
    width: 100%;
}

.btn--primary {
    background-color: var(--primary-color);
    color: #ffffff;
}

.btn--primary:hover {
    background-color: #0f172a;
}

.btn--accent {
    background-color: var(--accent-color);
    color: #ffffff;
}

.btn--accent:hover {
    background-color: var(--accent-hover);
}