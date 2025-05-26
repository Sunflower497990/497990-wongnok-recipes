<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ชุมชนแบ่งปันสูตรอาหาร - Sunflower</title>
    <link rel="stylesheet" href="css/style.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <header>
        <nav class="navbar">
            <div class="container">
                <a href="#" class="navbar-brand">ชุมชนแบ่งปันสูตรอาหาร 🌻</a>
                <button class="navbar-toggler" aria-label="Toggle navigation">
                    <i class="fas fa-bars"></i>
                </button>
                <div class="navbar-menu">
                    <ul class="navbar-nav">
                        <li><a href="#hero">หน้าหลัก</a></li>
                        <li><a href="#recipes">ค้นหาสูตร</a></li>
                        <li><a href="#details">รายละเอียด</a></li>
                        <li><a href="#create-recipe">สร้างสูตรอาหาร</a></li>
                        <li><a href="#login">เข้าสู่ระบบ</a></li>
                    </ul>
                </div>
            </div>
        </nav>
    </header>

    <main>
        <section id="hero" class="hero-section">
            <div class="container">
                <h1>ค้นพบสูตรอาหารใหม่ๆ ได้ทุกวัน</h1>
                <p>แบ่งปันและค้นหาสูตรอาหารจานโปรดของคุณได้ที่นี่</p>
                <div class="search-bar">
                    <input type="text" id="searchInput" placeholder="ค้นหาสูตรอาหาร หรือ วัตถุดิบ...">
                    <button id="searchButton"><i class="fas fa-search"></i> ค้นหา</button>
                </div>
            </div>
        </section>

        <section id="recipes" class="recipes-section">
            <div class="container">
                <h2>สูตรอาหารแนะนำ 🍲</h2>
                <div class="filter-options">
                    <span>มุมมอง</span>
                    <button class="filter-btn active" data-filter="all">ทั้งหมด</button>
                    <button class="filter-btn" data-filter="by-member">ตามสมาชิก</button>
                    <button class="filter-btn" data-filter="by-rating">ตามเรตติ้ง</button>
                </div>
                <div id="recipeGrid" class="recipe-grid">
                    </div>
            </div>
        </section>

        <section id="details" class="details-section">
            <div class="container">
                <h2>รายละเอียดการใช้งาน</h2>
                <div class="details-grid">
                    <div class="viewer-details">
                        <h3><i class="fas fa-eye"></i> Viewer</h3>
                        <ul>
                            <li><i class="fas fa-user-plus"></i> Registration</li>
                            <li><i class="fas fa-search"></i> Search</li>
                        </ul>
                    </div>
                    <div class="member-details">
                        <h3><i class="fas fa-users"></i> Member</h3>
                        <ul>
                            <li><i class="fas fa-edit"></i> Create / Read / Update / Delete recipes (เฉพาะสูตรของตัวเอง)</li>
                            <li><i class="fas fa-star-half-alt"></i> Rating (ยกเว้นสูตรของตัวเอง, สามารถให้ Rating ได้สูตรละ 1 ครั้งเท่านั้น)</li>
                            <li><i class="fas fa-search-plus"></i> Search</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <section id="recipe-detail-modal" class="modal">
            <div class="modal-content">
                <span class="close-button">&times;</span>
                <h2 id="modalRecipeName">ชื่อสูตรอาหาร</h2>
                <img id="modalRecipeImage" src="" alt="รูปภาพอาหาร" style="width:100%; max-height: 300px; object-fit: cover; border-radius: 8px; margin-bottom: 15px;">
                <p><strong>ผู้โพสต์:</strong> <span id="modalRecipeAuthor"></span></p>
                <p><strong>เวลาในการปรุง:</strong> <span id="modalRecipeTime"></span></p>
                <p><strong>ระดับความยาก:</strong> <span id="modalRecipeDifficulty"></span></p>
                <h3><i class="fas fa-carrot"></i> ส่วนผสม:</h3>
                <ul id="modalRecipeIngredients"></ul>
                <h3><i class="fas fa-utensils"></i> ขั้นตอนการทำ:</h3>
                <div id="modalRecipeInstructions"></div>
                <button class="save-recipe-btn"><i class="fas fa-save"></i> บันทึกสูตรนี้</button>
            </div>
        </section>

         <section id="create-recipe" class="create-recipe-section">
            <div class="container">
                <h2><i class="fas fa-plus-circle"></i> สร้างสูตรอาหารของคุณ</h2>
                <form id="createRecipeForm">
                    <div>
                        <label for="recipeName">ชื่อสูตรอาหาร:</label>
                        <input type="text" id="recipeName" name="recipeName" required>
                    </div>
                    <div>
                        <label for="recipeTime">เวลาในการปรุง (เช่น 30 นาที):</label>
                        <input type="text" id="recipeTime" name="recipeTime" required>
                    </div>
                     <div>
                        <label for="recipeDifficulty">ระดับความยาก:</label>
                        <select id="recipeDifficulty" name="recipeDifficulty">
                            <option value="ง่าย">ง่าย</option>
                            <option value="ปานกลาง">ปานกลาง</option>
                            <option value="ยาก">ยาก</option>
                        </select>
                    </div>
                    <div>
                        <label for="recipeIngredients">ส่วนผสม (หนึ่งอย่างต่อบรรทัด):</label>
                        <textarea id="recipeIngredients" name="recipeIngredients" rows="5" required></textarea>
                    </div>
                    <div>
                        <label for="recipeInstructions">ขั้นตอนการทำ:</label>
                        <textarea id="recipeInstructions" name="recipeInstructions" rows="8" required></textarea>
                    </div>
                    <div>
                        <label for="recipeImage">รูปภาพอาหาร (URL):</label>
                        <input type="url" id="recipeImage" name="recipeImage" placeholder="https://example.com/image.jpg">
                    </div>
                    <button type="submit" class="submit-recipe-btn">เผยแพร่สูตรอาหาร</button>
                </form>
            </div>
        </section>
    </main>

    <footer>
        <div class="container">
            <p>ชุมชนแบ่งปันสูตรอาหาร 🌻</p>
            <p>ติดต่อ: pmo.digital@pea.co.th</p>
        </div>
    </footer>

    <script src="js/script.js"></script>
</body>
</html>

/* css/style.css */
@import url('https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;500;700&display=swap');

:root {
    --primary-color: #FFC107; /* Sunflower Yellow */
    --secondary-color: #FD7E14; /* Bright Orange */
    --accent-color: #FFA000; /* Golden Yellow/Orange Accent */
    --text-color: #4A3B00; /* Dark Brownish Yellow for text */
    --light-text-color: #FFFFFF;
    --bg-color: #FFFDE7; /* Very Light Yellow Background */
    --card-bg: #FFF8E1; /* Light Yellow Card Background */
    --footer-bg: #795548; /* Brown (like sunflower center/soil) */
    --shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
    --border-radius: 12px;
    --font-family: 'Kanit', sans-serif;

    /* RGB versions for opacity, if needed. Calculate these based on the hex. */
    --primary-color-rgb: 255, 193, 7;
    --secondary-color-rgb: 253, 126, 20;
}

html {
  scroll-behavior: smooth;
}

body {
    font-family: var(--font-family);
    line-height: 1.7;
    color: var(--text-color);
    background-color: var(--bg-color);
    margin: 0;
    padding: 0;
    font-size: 16px;
    font-weight: 400; /* Default font weight */
}

.container {
    width: 90%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 15px;
}

h1, h2, h3, h4, h5, h6 {
    color: var(--secondary-color);
    margin-bottom: 0.8em;
    font-weight: 700; /* Kanit Bold */
}

h1 { font-size: 2.8em; }
h2 { font-size: 2.2em; }
h3 { font-size: 1.8em; }

a {
    text-decoration: none;
    color: var(--primary-color);
    transition: color 0.3s ease;
    font-weight: 500; /* Kanit Medium for links */
}

a:hover {
    color: var(--accent-color);
}

img {
    max-width: 100%;
    height: auto;
    display: block;
    border-radius: calc(var(--border-radius) / 2);
}

button, .btn {
    padding: 12px 25px;
    border: none;
    border-radius: var(--border-radius);
    cursor: pointer;
    font-size: 1em;
    font-weight: 700; /* Kanit Bold for buttons */
    transition: background-color 0.3s ease, transform 0.2s ease;
    font-family: var(--font-family);
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}
button:hover, .btn:hover {
    transform: translateY(-2px);
}

/* Navbar */
.navbar {
    background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
    color: var(--light-text-color);
    padding: 1rem 0;
    position: sticky;
    top: 0;
    z-index: 1000;
    box-shadow: 0 3px 10px rgba(0,0,0,0.15);
}

.navbar .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.navbar-brand {
    font-size: 1.8em;
    font-weight: 700; /* Kanit Bold */
    color: var(--light-text-color);
}

.navbar-menu {
    display: flex;
}

.navbar-nav {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
}

.navbar-nav li {
    margin-left: 25px;
}

.navbar-nav a {
    color: var(--light-text-color);
    font-weight: 500; /* Kanit Medium */
    padding: 8px 12px;
    border-radius: 8px;
    text-shadow: 1px 1px 2px rgba(0,0,0,0.2);
}

.navbar-nav a:hover, .navbar-nav a.active {
    background-color: rgba(255,255,255,0.25);
}

.navbar-toggler {
    display: none;
    background: none;
    color: var(--light-text-color);
    font-size: 1.5rem;
    border: none;
    cursor: pointer;
}

/* Hero Section */
.hero-section {
    background: linear-gradient(135deg, rgba(var(--primary-color-rgb), 0.85), rgba(var(--secondary-color-rgb), 0.85)), url('https://images.unsplash.com/photo-1528502601017-8a586487a96b?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1770&q=80') no-repeat center center;
    background-size: cover;
    color: var(--light-text-color);
    text-align: center;
    padding: 100px 20px;
    min-height: 60vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.hero-section h1 {
    font-size: 3.5em;
    margin-bottom: 0.5em;
    color: var(--light-text-color);
    text-shadow: 2px 2px 5px rgba(0,0,0,0.4);
    font-weight: 700; /* Kanit Bold */
}

.hero-section p {
    font-size: 1.4em;
    margin: 10px auto 2em auto;
    max-width: 700px;
    font-weight: 400; /* Kanit Regular */
}

.search-bar {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    max-width: 600px;
    margin: 0 auto;
    background-color: rgba(255, 255, 255, 0.9);
    padding: 10px;
    border-radius: var(--border-radius);
    box-shadow: var(--shadow);
}

.search-bar input[type="text"] {
    flex-grow: 1;
    padding: 15px;
    border: 1px solid #ddd;
    border-radius: var(--border-radius) 0 0 var(--border-radius);
    font-size: 1em;
    outline: none;
    color: var(--text-color);
    font-family: var(--font-family); /* Ensure Kanit is applied */
}
.search-bar input[type="text"]::placeholder {
    color: #aaa;
    font-family: var(--font-family);
}


.search-bar button {
    background-color: var(--accent-color);
    color: var(--light-text-color);
    border-radius: 0 var(--border-radius) var(--border-radius) 0;
    padding: 15px 22px;
}
.search-bar button:hover {
    background-color: #d98800;
}


/* Recipes Section, Details Section, Create Recipe Section */
.recipes-section, .details-section, .create-recipe-section {
    padding: 60px 0;
}

.recipes-section h2, .details-section h2, .create-recipe-section h2 {
    text-align: center;
    margin-bottom: 40px;
}

.filter-options {
    text-align: center;
    margin-bottom: 30px;
}

.filter-options span {
    margin-right: 10px;
    font-weight: 700; /* Kanit Bold */
    color: var(--text-color);
}

.filter-btn {
    background-color: #FFE082;
    color: var(--text-color);
    margin: 0 8px;
    box-shadow: none;
    font-weight: 500; /* Kanit Medium */
}

.filter-btn.active, .filter-btn:hover {
    background-color: var(--secondary-color);
    color: white;
}

.recipe-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 30px;
}

.recipe-card {
    background-color: var(--card-bg);
    border-radius: var(--border-radius);
    box-shadow: var(--shadow);
    overflow: hidden;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    display: flex;
    flex-direction: column;
    border: 1px solid #FFECB3;
}

.recipe-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 12px 28px rgba(0,0,0,0.18);
}

.recipe-card img {
    width: 100%;
    height: 220px;
    object-fit: cover;
    border-bottom: 3px solid var(--accent-color);
}

.recipe-card-content {
    padding: 20px;
    flex-grow: 1;
    display: flex;
    flex-direction: column;
}

.recipe-card-content h3 {
    font-size: 1.5em;
    margin-top: 0;
    color: var(--secondary-color);
    font-weight: 700; /* Kanit Bold */
}

.recipe-meta {
    font-size: 0.9em;
    color: #757575;
    margin-bottom: 15px;
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    font-weight: 400; /* Kanit Regular */
}
.recipe-meta span {
    display: flex;
    align-items: center;
}
.recipe-meta i {
    margin-right: 6px;
    color: var(--accent-color);
}

.recipe-card-content p { /* Author text */
    font-size: 0.95em;
    color: #616161;
    margin-bottom: 10px;
    flex-grow: 1;
    font-weight: 400; /* Kanit Regular */
}

.recipe-card-actions {
    margin-top: auto;
    padding-top: 15px;
    border-top: 1px solid #FFECB3;
}

.recipe-card-actions .btn {
    background-color: var(--secondary-color);
    color: var(--light-text-color);
    width: 100%;
    text-align: center;
}
.recipe-card-actions .btn:hover {
    background-color: var(--primary-color);
    color: var(--text-color);
}

.no-results {
    grid-column: 1 / -1;
    text-align: center;
    font-size: 1.2em;
    color: var(--text-color);
    padding: 20px;
    font-weight: 500; /* Kanit Medium */
}


/* Modal Styling */
.modal {
    display: none;
    position: fixed;
    z-index: 1001;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    overflow: auto;
    background-color: rgba(0,0,0,0.7);
}

.modal-content {
    background-color: var(--card-bg);
    margin: 5% auto;
    padding: 35px;
    border: 1px solid var(--accent-color);
    width: 90%;
    max-width: 700px;
    border-radius: var(--border-radius);
    box-shadow: 0 8px 25px rgba(0,0,0,0.3);
    position: relative;
    animation: slideInModal 0.4s ease-out;
}

@keyframes slideInModal {
    from {transform: translateY(-60px); opacity: 0;}
    to {transform: translateY(0); opacity: 1;}
}

.close-button {
    color: #aaa;
    float: right;
    font-size: 32px;
    font-weight: 700; /* Kanit Bold */
    position: absolute;
    top: 15px;
    right: 25px;
}

.close-button:hover,
.close-button:focus {
    color: var(--secondary-color);
    text-decoration: none;
    cursor: pointer;
}

.modal-content h2 {
    margin-top: 0;
    color: var(--secondary-color);
    font-weight: 700; /* Kanit Bold */
}
.modal-content h3 {
    color: var(--primary-color);
    margin-top: 20px;
    margin-bottom: 10px;
    display: flex;
    align-items: center;
    font-weight: 700; /* Kanit Bold */
}
.modal-content h3 i {
    margin-right: 8px;
}
.modal-content ul {
    list-style: none;
    padding-left: 0;
}
.modal-content ul li {
    padding: 5px 0;
    border-bottom: 1px dashed #FFECB3;
    font-weight: 400; /* Kanit Regular */
}
.modal-content ul li:last-child {
    border-bottom: none;
}
.modal-content .save-recipe-btn {
    background-color: var(--accent-color);
    color: var(--light-text-color);
    margin-top: 25px;
    padding: 12px 25px;
}
.modal-content .save-recipe-btn:hover {
    background-color: darken(var(--accent-color), 10%);
}


/* Details Section Styles */
.details-section {
    background-color: #FFF9C4;
}

.details-section h2 {
    color: var(--secondary-color);
}

.details-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    gap: 30px;
    padding: 25px;
    background-color: var(--card-bg);
    border-radius: var(--border-radius);
    box-shadow: var(--shadow);
}

.viewer-details, .member-details {
    padding: 25px;
    border-radius: var(--border-radius);
    border: 1px solid var(--primary-color);
    background-color: #FFFFF0;
}

.viewer-details h3, .member-details h3 {
    color: var(--secondary-color);
    margin-top: 0;
    margin-bottom: 20px;
    border-bottom: 2px solid var(--accent-color);
    padding-bottom: 10px;
    display: flex;
    align-items: center;
    font-weight: 700; /* Kanit Bold */
}
.viewer-details h3 i, .member-details h3 i {
    margin-right: 10px;
    font-size: 1.2em;
}

.viewer-details ul, .member-details ul {
    list-style: none;
    padding: 0;
}

.viewer-details li, .member-details li {
    margin-bottom: 12px;
    color: var(--text-color);
    font-size: 1.05em;
    display: flex;
    align-items: flex-start;
    font-weight: 400; /* Kanit Regular */
}

.viewer-details li i, .member-details li i {
    color: var(--accent-color);
    margin-right: 10px;
    margin-top: 4px;
}


/* Create Recipe Form */
.create-recipe-section {
    background-color: var(--bg-color);
}
.create-recipe-section h2 i {
    margin-right: 10px;
    color: var(--secondary-color);
}

#createRecipeForm div {
    margin-bottom: 25px;
}

#createRecipeForm label {
    display: block;
    margin-bottom: 8px;
    font-weight: 700; /* Kanit Bold */
    color: var(--text-color);
}

#createRecipeForm input[type="text"],
#createRecipeForm input[type="url"],
#createRecipeForm textarea,
#createRecipeForm select {
    width: 100%;
    padding: 15px;
    border: 1px solid #FFD54F;
    border-radius: var(--border-radius);
    box-sizing: border-box;
    font-size: 1em;
    font-family: var(--font-family); /* Ensure Kanit is applied */
    background-color: #FFFFF0;
    color: var(--text-color);
    font-weight: 400; /* Kanit Regular for input text */
}
#createRecipeForm input[type="text"]:focus,
#createRecipeForm input[type="url"]:focus,
#createRecipeForm textarea:focus,
#createRecipeForm select:focus {
    border-color: var(--secondary-color);
    box-shadow: 0 0 0 0.2rem rgba(var(--secondary-color-rgb), 0.25);
    outline: none;
}

#createRecipeForm textarea {
    resize: vertical;
    min-height: 120px;
}

.submit-recipe-btn {
    background-color: var(--secondary-color);
    color: var(--light-text-color);
    padding: 15px 30px;
    font-size: 1.1em;
    width: 100%;
}
.submit-recipe-btn:hover {
    background-color: var(--primary-color);
    color: var(--text-color);
}

/* BacktoTop */
.m-backtotop {
    @include transition(all 0.3s ease-in-out);
    position: fixed;
    bottom: -50px;
    right: 20px;
    width: 50px;
    height: 50px;
    background: #222;
    border-radius: 25px;
    text-align: center;
    border: 2px solid #fff;
    box-shadow: 0 2px 3px rgba(0, 0, 0, 0.1);
    opacity: 0;
    overflow: hidden;
		color:#fff;

    &.active {
      bottom: 15px;
      opacity: 1;
    }

    & > div {
      @include transition(all 0.3s ease-in-out);
      &.arrow {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translateY(-50%) translateX(-50%);
        opacity: 1;
      }
      &.text {
        @include font-size(0.5, 1);
        text-transform: uppercase;
        font-weight: 900;
        font-family: $f-body;
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translateY(50%) translateX(-50%);
        opacity: 0;
        margin-top: 1px;
      }
    }

    &:hover {
      transform: scale(1.1);
			bottom:20px;
      cursor: pointer;
      background: darken(#222, 15%);
			box-shadow: 0 10px 5px rgba(0, 0, 0, 0.1);

      & > div {
        &.arrow {
          transform: translateY(-150%) translateX(-50%);
          opacity: 0;
        }
        &.text {
          transform: translateY(-50%) translateX(-50%);
          opacity: 1;
        }
      }
    }
  }

/* Footer */
footer {
    background-color: var(--footer-bg);
    color: #FFFDE7;
    text-align: center;
    padding: 35px 0;
    margin-top: 50px;
}

footer p {
    margin: 8px 0;
    font-size: 0.95em;
    font-weight: 400; /* Kanit Regular */
}
footer a {
    color: var(--primary-color);
    font-weight: 500; /* Kanit Medium */
}
footer a:hover {
    color: var(--light-text-color);
}

/* Responsive Design */
@media (max-width: 992px) {
    .recipe-grid {
        grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    }
    .hero-section h1 { font-size: 2.8em; }
    .hero-section p { font-size: 1.2em; }
}


@media (max-width: 768px) {
    .navbar-menu {
        display: none;
        flex-direction: column;
        width: 100%;
        position: absolute;
        top: 75px;
        left: 0;
        background: linear-gradient(180deg, var(--primary-color), var(--secondary-color));
        padding: 15px 0;
        box-shadow: 0 5px 10px rgba(0,0,0,0.15);
    }
    .navbar-menu.active {
        display: flex;
    }
    .navbar-nav {
        flex-direction: column;
        width: 100%;
    }
    .navbar-nav li {
        margin: 10px 0;
        text-align: center;
    }
    .navbar-toggler {
        display: block;
    }

    .hero-section h1 { font-size: 2.4em; }
    .hero-section p { font-size: 1.1em; }
    .search-bar { flex-direction: column; padding: 15px; }
    .search-bar input[type="text"] {
        border-radius: var(--border-radius) var(--border-radius) 0 0;
        margin-bottom: 10px;
        width: calc(100% - 30px);
    }
    .search-bar button {
        border-radius: 0 0 var(--border-radius) var(--border-radius);
        width: calc(100% - 30px);
    }

    .recipe-grid {
        grid-template-columns: 1fr;
    }
    .details-grid {
        grid-template-columns: 1fr;
    }
    .modal-content {
        width: 90%;
        margin: 10% auto;
        padding: 25px;
    }
    h1 { font-size: 2.2em; }
    h2 { font-size: 1.8em; }
}

@media (max-width: 576px) {
    body { font-size: 15px; }
    .hero-section { padding: 60px 15px; min-height: 50vh;}
    .hero-section h1 { font-size: 2em; }
    .hero-section p { font-size: 1em; }

    .filter-options {
        display: flex;
        flex-direction: column;
    }
    .filter-btn {
        margin: 8px 0;
    }
    .container { width: 95%; }
    button, .btn { padding: 10px 20px; }
    #createRecipeForm input, #createRecipeForm textarea, #createRecipeForm select { padding: 12px; }
}
// js/script.js
document.addEventListener('DOMContentLoaded', () => {
    const recipeGrid = document.getElementById('recipeGrid');
    const searchInput = document.getElementById('searchInput');
    const searchButton = document.getElementById('searchButton');
    const filterBtns = document.querySelectorAll('.filter-btn');
    const modal = document.getElementById('recipe-detail-modal');
    const closeModalButton = document.querySelector('.modal .close-button');
    const navbarToggler = document.querySelector('.navbar-toggler');
    const navbarMenu = document.querySelector('.navbar-menu');
    const createRecipeSection = document.getElementById('create-recipe'); // For potentially hiding/showing

    // --- Navbar Toggler ---
    if (navbarToggler && navbarMenu) {
        navbarToggler.addEventListener('click', () => {
            navbarMenu.classList.toggle('active');
        });
    }


    // Hide create recipe section initially if not logged in (conceptual)
    if (createRecipeSection) {
        // In a real app, check login status here
        // createRecipeSection.style.display = 'none'; // Example: hide by default
    }


    // --- Sample Recipe Data (Replace with API call) ---
    let recipes = [
        {
            id: 1,
            name: "ไก่ย่างเขาสวนกวาง",
            image: "https://www.thaifranchisecenter.com/document/franchise/picture/document_6473_p3_20201120144446.jpg",
            author: "ครัวคุณต๋อย",
            time: "90 นาที",
            difficulty: "ปานกลาง",
            rating: 4.7,
            ingredients: ["ไก่ทั้งตัว", "ตะไคร้", "กระเทียม", "รากผักชี", "พริกไทย", "ซอสปรุงรส", "น้ำตาลปี๊บ"],
            instructions: "1. โขลกเครื่องหมักให้ละเอียด\n2. หมักไก่ทิ้งไว้ 2 ชั่วโมง\n3. นำไปย่างด้วยไฟอ่อนจนสุกเหลือง",
            postedByMember: "คุณเอ"
        },
        {
            id: 2,
            name: "ส้มตำปูปลาร้า",
            image: "https://img.kapook.com/u/2016/surauch/cook1/j1_1.jpg",
            author: "เจ๊น้อยแซ่บเวอร์",
            time: "20 นาที",
            difficulty: "ง่าย",
            rating: 4.9,
            ingredients: ["มะละกอดิบ", "พริกขี้หนู", "กระเทียม", "น้ำปลาร้า", "น้ำปลา", "มะนาว", "น้ำตาลปี๊บ", "ปูเค็ม", "มะเขือเทศ", "ถั่วฝักยาว"],
            instructions: "1. ตำพริกกระเทียมพอแตก\n2. ใส่มะละกอ ปรุงรสด้วยน้ำปลาร้า น้ำปลา มะนาว น้ำตาลปี๊บ\n3. ใส่ปู มะเขือเทศ ถั่วฝักยาว ตำคลุกเคล้าให้เข้ากัน",
            postedByMember: "คุณบี"
        },
        {
            id: 3,
            name: "ต้มยำกุ้งน้ำข้น",
            image: "https://sg.fiverrcdn.com/photos/112566478/original/386e485f0d4853746792abe5e592480ec32c41d1.jpg?1527930323",
            author: "Wongnok Kitchen",
            time: "30 นาที",
            difficulty: "ปานกลาง",
            rating: 4.5,
            ingredients: ["กุ้งแม่น้ำ", "ข่า", "ตะไคร้", "ใบมะกรูด", "เห็ดฟาง", "พริกขี้หนู", "น้ำพริกเผา", "นมข้นจืด", "มะนาว", "น้ำปลา"],
            instructions: "1. ต้มน้ำใส่ข่า ตะไคร้ ใบมะกรูด\n2. พอน้ำเดือดใส่กุ้ง เห็ด\n3. ปรุงรสด้วยน้ำพริกเผา นมข้นจืด น้ำปลา มะนาว พริกขี้หนู",
            postedByMember: "คุณเอ"
        },
        {
            id: 4,
            name: "ผัดกะเพราหมูกรอบ",
            image: "https://img.wongnai.com/p/1920x0/2021/01/17/c95146b336274b0283b92b6943d289d8.jpg",
            author: "ร้านตามสั่ง",
            time: "25 นาที",
            difficulty: "ง่าย",
            rating: 4.8,
            ingredients: ["หมูกรอบ", "ใบกะเพรา", "พริก", "กระเทียม", "น้ำมันหอย", "ซีอิ๊วขาว", "น้ำตาลทราย"],
            instructions: "1. เจียวกระเทียมพริกให้หอม\n2. ใส่หมูกรอบลงผัด\n3. ปรุงรสด้วยน้ำมันหอย ซีอิ๊วขาว น้ำตาล\n4. ใส่ใบกะเพรา ผัดเร็วๆ ปิดไฟ",
            postedByMember: "คุณซี"
        },
      {
        id: 5,
            name: "แกงเขียวหวาน",
            image: "https://recipe.ajinomoto.co.th/_next/image?url=https%3A%2F%2Fwww.ajinomoto.co.th%2Fstorage%2Fphotos%2Fshares%2FRecipe%2FMenu%2F3-19Greencurry%2F61a8f392ef73e.jpeg&w=1920&q=75",
            author: "ร้านตามสั่ง",
            time: "30 นาที",
            difficulty: "ง่าย",
            rating: 4.6,
            ingredients: ["หัวกะทิ" , "น้ำปลา" , "พริกแกงเขียวหวาน" , "อกไก่" , "หางกะทิ" , "น้ำตาลปี๊บ" , "รสดี" , "ใบมะกรูด" , "มะเขือเปราะ" , "มะเขือพวง" , 
            "พริกชี้ฟ้าแดง" , "ใบโหระพา"],
            instructions: "1.นำหัวกะทิเทลงกระทะ รอจนกะทิเดือด แล้วจึงใส่พริกแกงเขียวหวานลงไปผัดให้แตกมัน\n2.ใส่เนื้อไก่ลงไปผัดให้เข้ากับพริกแกง จนเนื้อไก่พอสุก\n3.เติมหางกะทิลงไป รอจนกะทิเดือด\n4.ปรุงรสด้วยน้ำปลา และน้ำตาลปี๊บ และรสดี คนให้ละลายเข้ากัน\n5.ใส่ใบมะกรูด มะเขือเปราะ และมะเขือพวงลงไป รอจนเขียวหวานไก่เดือดอีกครั้ง ปิดไฟ\n6.ใส่พริกชี้ฟ้าแดง และใบโหระพาลงไป และคนแกงเขียวหวานไก่สูตรโบราณให้เข้ากัน ตักเสิร์ฟพร้อมข้าวสวย",
            postedByMember: "คุณดี"
      },
      {
        id: 6,
            name: "แกงจืดเต้าหู้หมูสับ",
            image: "https://assets.unileversolutions.com/recipes-v3/242153-default.jpg?im=AspectCrop=(720,459);Resize=(720,459)",
            author: "ร้านตามสั่ง",
            time: " 15 นาที",
            difficulty: "ง่าย",
            rating: 4.9,
            ingredients: ["น้ำ" , "หมูสับ" , "ซีอิ๊ว" , "พริกไทยขาวป่น" , "กะหล่ำปลีจีน" ,"เต้าหู้ไข่" , "ต้นหอม" , "ผักชี" , "คนอร์ซุปก้อนหมู"],
            instructions: "1.หมักหมูสับด้วยผงพริกไทยขาวและซีอิ๋วเป็นเวลา 10 นาที\n2.ล้างผักด้วยสะอาด และตัดกะหล่ำปลีเป็นก้อนสีเหลี่ยม 3 ซม. ต้นหอมและผักชี ตัดเป็นขนาด 1 ซม. และเตรียมไว้ก่อน\n3.ต้มน้ำเดือดในปริมาณที่ระบุเอาไว้\n4.ใส่คนอร์ซุปก้อนหมูลงไปในน้ำเดือดและคนจนกว่าจะเข้ากับน้ำแกง\n5.ปั้นหมูที่หมักแล้วเป็นก้อนกลมเล็กๆ และตักไปใส่น้ำแกงที่เดือดแล้วด้วยช้อนเป็นเวลา 2 นาที\n6.ใส่กะหล่ำปลีที่เตรียมไว้แล้ว เป็นเวลา 2 นาทีจนกว่าจะนิ่ม\n7.ใส่เต้าหู้ไข่ และใช้เวลาเพิ่มอีก 1 นาที\n8.ลองชิมและใส่ซีอิ๋วเพิ่มเติมตามรสชาติ\n9.โรยแกงที่เสร็จแล้วด้วยผักชีและต้นหอม",
            postedByMember: "คุณเอ"
      },
      {
        id: 7,
            name: "ข้าวหน้าไก่",
            image: "https://www.pholfoodmafia.com/wp-content/uploads/2021/08/4Chicken-gravy-with-rice.jpg",
            author: "ร้านล็อคงาทิ้น",
            time: " 35 นาที",
            difficulty: "ปานกลาง",
            rating: 4.4,
            ingredients: ["สะโพกไก่เลาะกระดูกหั่นชิ้น" , "แป้งมัน" , "พริกไทยป่น" , "ซีอิ้วดำ" , "น้ำตาลทรายแดง" , "น้ำมันพืช" , "น้ำมันพืชสำหรับผัด" , "กระเทียมสับ" , "เหล้าจีน" , "เห็ดหอมแห้ง" , "น้ำแช่เห็ดหอม" , "ซีอิ้วขาว" , "น้ำมันงา" , "น้ำตาลทราย" , "อายิโนะโมะโต๊ะ" , "แป้งข้าวโพด" , "ข้าวหอมมะลิหุงสุก" , "ไข่ต้ม" , "พริกชี้ฟ้าเขียวหั่นแว่น" , "ต้นหอมตัดปลาย" ],
            instructions: "1.ใส่สะโพกไก่เลาะกระดูกหั่นชิ้นลงในภาชนะ ตามด้วยแป้งมัน พริกไทยป่น น้ำมันพืช และซีอิ๊วดำ เคล้าผสมให้เข้ากันหมักเตรียมไว้\n2.ใส่น้ำมันพืช ลงในภาชนะนำขึ้นตั้งไฟพอร้อนใส่เนื้อไก่ลงจี่จนขึ้นสีน้ำตาล ใส่กระเทียมสับและเหล้าจีน ลงไปผัดจนมีกลิ่นหอม ใส่เห็ดหอมแห้งแช่น้ำหั่นเส้น และน้ำแช่เห็ดหอมลงไป คนให้เข้ากัน ตุ๋นประมาณ 15 นาที\n3.ปรุงรสด้วยพริกไทยป่น น้ำตาลทราย ซีอิ๊วขาว น้ำมันงาและอายิโนะโมะโต๊ะ คนให้เข้ากัน ต้มต่อพอเดือด\n4.ใส่แป้งข้าวโพดละลายน้ำคนผสมให้เข้ากัน รอจนกระทั่งเดือดอีกครั้ง ปิดไฟ\n5.นำส่วนผสมหน้าไก่ราดบน ข้าวหอมมะลิหุงสุก รับประทานคู่กับไข่ต้ม พริกชี้ฟ้าเขียวหั่นแว่น และต้นหอมตัดปลายพร้อมเสิร์ฟ",
            postedByMember: "คุณจี"
      },
      {
        id: 8,
            name: "ห่อหมกปลาช่อน ห่อหมกปลากราย",
            image: "https://i.ytimg.com/vi/NtFgQ2yNyGg/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD&rs=AOn4CLAfGsR7C3xXcOytfWGR-EqFzqraZQ",
            author: "กินได้อร่อยด้วย",
            time: " 50 นาที",
            difficulty: "ปานกลาง",
            rating: 4.6,
            ingredients: ["เนื้อปลาช่อน" , "เนื้อปลากรายขูด" , "ไข่ไก่" , "พริกแกงเผ็ด" , "กะทิ" , "น้ำปลา" , "น้ำตาลปี๊บ" , "ใบยอ" , "ใบโหระพา" , "ใบมะกรูด" , "พริกชี้ฟ้าแดง" , "กะทิ (ราดหน้า)" , "แป้งข้าวเจ้า" ],
            instructions: "1.ทำถ้วยใบตองสำหรับใส่ห่อหมก\n2.นำใบยอ ใบมะกรูด พริกชี้ฟ้าแดง มาซอย พักไว้ จากนั้นนำปลาช่อนมาแร่เป็นชิ้นบางๆ พักไว้\n3.เตรียมภาชนะสำหรับผสมเครื่อง ใส่เนื้อปลากรายขูด พริกแดงเผ็ด ไข่ไก่หนึ่งฟอง น้ำปลา น้ำตาลปี๊ป ใช้ไม้พายคลุกส่วนผสมทุกอย่างให้เข้ากันดี\n4.เติมกะทิลงไป ค่อยๆ ใส่ทีละนิด คนจนทุกอย่างเข้ากันดี\n5.ใส่เนื้อปลาช่อนที่แร่เป็นชิ้นไว้ลงไป คนให้เข้ากันอีกครั้ง พักไว้\n6.นำใบยอและใบโหระพาใส่ในถ้วยใบตองที่เราเตรียมไว้ เทห่อหมกลงไป ใช้ไฟแรงในการนึ่ง 12 นาที\n7.เตรียมกะทิสำราดด้านบน เทน้ำกะทิและแป้งข้าวจ้าวลงไปในหม้อ คนผสมให้เข้ากัน นะไปต้มให้สุก นำไปราดบนห่อหมกที่นึ่งจนสุกดีแล้ว\n8.แต่งหน้าด้านบนด้วยใบมะกรูดและพริกชี้ฟ้าซอย เป็นอันเสร็จ",
            postedByMember: "คุณเอฟ"
      },
      {
         id: 9,
            name: "ทอดมันกุ้ง",
            image: "https://i.ytimg.com/vi/ga-I52j3i14/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD&rs=AOn4CLDXjNZqiX7NszLW9AG3Q3NDP4zahQ",
            author: "กินได้อร่อยด้วย",
            time: " 20 นาที",
            difficulty: "ปานกลาง",
            rating: 4.8,
            ingredients: ["เนื้อกุ้ง" , "แป้งทอดกรอบ" , "เกล็ดขนมปัง" , "เกลือ" , "พริกไทย" ],
            instructions: "1.นำกุ้งมาล้างทำความสะอาด แล้วปอกเปลือกออกให้หมด\n2.นำกุ้งมาสับให้ละเอียด โดยการใช้มีดอีโต้ตบกุ้งก่อน\n3.นำเนื้อกุ้งไปใส่ชามผสม ปรุงรสด้วยเกลือป่น พริกไทย และแป้งทอดกรอบ\n4.ใช้มือนวดเนื้อกุ้งและเครื่องปรุงเข้ากันดี\n5.นวดกุ้งสักพักใหญ่ จนเนื้อกุ้งเหนียว เด้ง เนื้อเนียนผสมกับแป้งดี\n6.เตรียมเกล็ดขนมปังโดยเทลงใส่ถาด\n7.แป้งชิ้นทอดมันตามชอบ แล้วนำไปคลุกเกล็ดขนมปัง\n8.ตั้งกระทะ ใส่น้ำมัน ใช้ไฟกลางรอจนน้ำมันร้อน\n9.ใส่ทอดมันกุ้งลงไปทอดจนได้สีเหลืองทอง ตักขึ้นมาพักสะเด็ดน้ำมัน พร้อมทาน",
            postedByMember: "คุณเอฟ"
      },
      { id: 10,
            name: "กะหล่ำปลีผัดน้ำปลา",
            image: "https://i.ytimg.com/vi/h3iwdEzqQWk/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD&rs=AOn4CLA-W6C7T_A21xenDlSzy1Szc2w1Bg",
            author: "TrueID",
            time: " 10 นาที",
            difficulty: "ง่าย",
            rating: 4.6,
            ingredients: ["กะหล่ำปลี" , "กระเทียม" , "น้ำปลา" , "น้ำมันหอย" , "น้ำมันพืช" , "เกลือป่น" , "แป้งทอดกรอบ"],
            instructions: "1.แกะกะหล่ำปลีเป็นใบๆ แล้วฉีกออกขนาดพอประมาน ล้างน้ำให้สะอาดแช่เย็นทิ้งไว้\n2.นำกระเทียมมาสับคลุกกับเกลือป่น และแป้งทอดกรอบเล็กน้อย จากนั้นนำไปเจียวให้เหลืองกรอบ พักไว้\n3.ตั้งน้ำมันในกะทะให้ร้อน นำกะหล่ำปลีลงไปผัดปรุงรสด้วยน้ำปลา น้ำมันหอยเล็กน้อย\n4.พอผักสลบเล็กน้อยตักใส่จานโรยด้วยกะเทียมเจียว",
            postedByMember: "คุณพี"
      },
      {
         id: 11,
            name: "กุ้งอบวุ้นเส้น",
            image: "https://img.wongnai.com/p/1920x0/2018/11/14/1d1c2509896d4d8794c17b5b58379fd6.jpg",
            author: "TrueID",
            time: " 1 ชั่วโมง",
            difficulty: "ปานกลาง",
            rating: 4.3,
            ingredients: ["กุ้งก้ามกราม" , "หมูสามชั้น" , "วุ้นเส้น" , "ต้นหอม" , "ขึ้นช่าย" , "ขิงแก่" , "กระเทียม" , "รากผักชี" , "ชวงเจีย(พริกหอม)" , "พริกไทยป่น" , "น้ำเปล่า" , "ซอสหอยนางรม" , "ซีอิ้วขาว" , "ซีอิ้วดำ(หวาน)" , "น้ำมันงา" , "น้ำตาลทราย" , "เหล้าจีน"],
            instructions: "1.เริ่มจากผสมน้ำซอสสำหรับอบวุ้นเส้น โดยใส่ น้ำเปล่า ซอสหอยนางรม ซีอิ้วขาว ซีอิ้วดำหวน น้ำมันงา และน้ำตาลทราย แล้วคนส่วนผสมให้เข้ากัน และน้ำตาลทรายละลายหมด (ไม่ต้องต้ม)\n2.ใส่กุ้งลงไปแช่ในน้ำซอสที่ผสมไว้ แล้วพักไว้\n3. นำกระทะมาตั้งไฟ ใช้ไฟกลางแล้วใส่หมูสามชั้นลงไป คั่วหมูสามชั้นไปเรื่อยๆ เพื่อรีดน้ำมันออกมา\n4.พอน้ำมันออกมาพอสมควร ให้ใส่กระเทียม รากผักชี และขิงแก่ลงไปในกระทะ แล้วผัดให้หอม\n5.ใส่ชวงเจียตาลงไป (ถ้าไม่มีใส่พริกไทยเม็ดแทนได้) ผัดจนหอม\n6.เมื่อเครื่องเทศหอมดีแล้ว ให้ใส่น้ำซอสที่ผสมไว้ลงไปในกระทะ รอน้ำเดือดลองชิมรสชาติดู (เน้นให้รสจัด เค็มนำ)\n7.ใส่กุ้งตามลงไป (ถ้าใช้กุ้งตัวเล็กให้ใส่กุ้งพร้อมวุ้นเส้นได้เลย) พอกุ้งเปลี่ยนสีใส่วุ้นเส้นที่แช่น้ำไว้แล้ว ลงไปในกระทะ คนให้เข้ากัน จากนั้นใส่พริกไทยป่นลงไป ปริมาณตามชอบ\n8.คอยคนจนวุ้นเส้นสุกดี และดูดน้ำซอสเข้าไปหมด\n9.ปิดเตา โรยผักตกแต่ง พร้อมรับประทาน",
            postedByMember: "คุณเจ"
      },
      {
         id: 12,
            name: "หอยลายผัดพริกเผา",
            image: "https://many-menu.com/wp-content/uploads/2020/06/841270AB-C980-4EB5-AAD6-DA658E875D0E.jpeg",
            author: "Aroistory",
            time: " 30 นาที",
            difficulty: "ง่าย",
            rating: 4.1,
            ingredients: ["หอยลาย" , "กระเทียมสับหยาบ" , "พริกเผา" , "น้้ำตาลทราย" , "ซีอิ้วขาว" , "น้ำมันหอย" , "น้ำเปล่า" , "พริกขี้หนู" , "ใบโหระพา"],
            instructions: "1.นำหอยลายมาล้างให้สะอาด จากนั้นนำหอยไปลวกในน้ำเดือดให้สุก แล้วนำขั้นมาพักให้สะเด็ดน้ำ\n2.เด็ดใบโหระพาแล้วล้างให้สะอาด\n3.ตั้งกระทะ ใส่น้ำมันและกระเทียมผัดให้พอได้กลิ่นหอม จากนั้นใส่น้ำพริกเผาผัดให้เข้ากัน\n4.ใส่หอยลายลงไป จากนั้นผัดให้เข้ากัน\n5.จากนั้นปรุงรสตามชอบ ด้วย น้ำตาลทราย ซีอิ้วขาว และน้ำมันหอย แล้วผัดให้เข้ากัน จากนั้นเติมน้ำเปล่า\n6.ใส่พริหขี้หนูเพิ่มรสเผ็ด และใบโหระพา จากนั้นผัดต่ออักสักพัก แล้วตักใส่จาน พร้อมรับทาน",
            postedByMember: "คุณเค"
      },
      {
         id: 13,
            name: "ปูผัดผงกะหรี่",
            image: "https://food.mthai.com/app/uploads/2017/01/iStock-611778670.jpg",
            author: "ครัวพิศพิไล",
            time: " 40 นาที",
            difficulty: "ปานกลาง",
            rating: 4.8,
            ingredients: ["ปูม้า" , "น้ำพริกเผา" , "ผงกะหรี่" , "น้ำมันหอย" , "เหล้าจีน" , "ซอสปรุงรส" , "น้ำปลา" , "กระเทียมสับหยาบ" , "พริกสด" , "พริกไทยป่น" , "น้ำตาลทราย" , "น้ำมันพืช" , "นมข้นจืด" , "น้ำ" , "หอมหัวใหญ่" , "ขึ้นช่าย" , "ต้นหอม" , "ไข่ไก่"],
            instructions: "1.เริ่มจากการเตรียมชามผสม สำหรับทำน้ำปรุง ตอกไข่ใส่ลงไป ตีไข่ให้แตก ใส่น้ำพริกเผา  น้ำตาลทราย ซอสปรุงรส  น้ำมันหอย น้ำปลา นมข้นจืด เหล้าจีน คนส่วนผสมให้เข้ากันดี พักไว้ก่อน\n2.ตั้งกระทะ เปิดไฟกลาง ใส่น้ำมันพืชลงไป เมื่อน้ำมันร้อนดีแล้ว ใส่กระเทียมลงไปผัดให้พอให้มีกลิ่นหอม แล้วใส่ผงกะหรี่ตามลงไปผัดเพื่อให้มีกลิ่นหอม ตามด้วยพริกไทยป่นผัดต่อสักพัก\n3.เมื่อเริ่มมีกลิ่นหอมดีแล้ว ใส่น้ำปรุงที่เตรียมไว้ลงไป แต่ยังไม่ต้องคน ให้ใส่ปูม้า หอมใหญ่ พริกแดงซอย แล้วปิดฝา รอให้เดือดหรือให้ไข่ข้นขึ้นก่อนค่อยคน\n4.คนให้เข้ากัน ผัดไปมาจนปูเปลี่ยนเป็นสีส้ม แสดงว่าปูสุกแล้ว ชิมรสปรุงให้ได้ตามชอบ แล้วจึงปิดไฟใส่ต้นหอมซอย ใบขึ้นฉ่ายลงไป ผัดให้พอผักสลด ตักใส่จานเสิร์ฟ",
            postedByMember: "คุณเจ"
      },
      {
         id: 14,
            name: "พะแนงไก่",
            image: "https://cms.dmpcdn.com/food/2021/10/12/7e8c8750-2b36-11ec-bfd9-97090d4e24ba_original.jpg",
            author: "TrueID",
            time: " 20 นาที",
            difficulty: "ง่าย",
            rating: 4.8,
            ingredients: ["เนื้อไก่" , "พริกแกง" , "กะทิ" , "มะเขือพวง" , "พริกชี้ฟ้าซอย" , "ใบมะกรูดฉีก" , "ใบมะกรูดซอย" , "น้ำตาลปี๊บ" , "น้ำปลา"],
            instructions: "1.นำกะทิประมาณ 200 มล.ลงไปผัดให้แตกมัน ตามด้วยพริกแกง ผัดให้เข้ากันดี\n2.เมื่อพริกแกงและกะทิเข้ากันดีแล้ว ใส่ไก่ลงไปผัดให้สุก แล้วเติมกะทิส่วนที่เหลือลงไป ให้แกงเดือดดี\n3.ใส่มะเขือพวง และมะกรูดฉีกลงไป เมื่อมะเขือพวงสุกดีแล้ว ปรุงรสด้วยน้ำปลา และน้ำตาลปี๊บ ชิมดูรสชาติให้ได้ตามชอบ รสชาติจะออกเผ็ดหวาน เค็มเล็กน้อย\n4.เมื่อผัดเข้ากันดีแล้ว ตักใส่ชามเสิร์ฟ แล้วตกแต่งหน้าด้วยใบมะกรูดซอย และพริกชี้ฟ้าซอย",
            postedByMember: "คุณเอ็ม"
      },
      {
         id: 15,
            name: "ขาหมูพะโล้โบราณ",
            image: "https://i.ytimg.com/vi/aPEREizpbXs/sddefault.jpg",
            author: "กินได้อร่อยด้วย",
            time: " 3 ชั่วโมง",
            difficulty: "ยาก",
            rating: 4.9,
            ingredients: ["ขาหมู" , "ไข่เป็ด" , "ผักกาดดอง(เปรี้ยว)" , "รากผักชี" , "กระเทียม" , "พริกไทย" , "น้ำเปล่า" , "ซอสถั่วเหลือง คิคโคแมน (โชยุญี่ปุ่น)" , "น้ำตาลปี๊บ" , "ผักคะน้า" , "กระเทียม(น้ำจิ้ม)" , "พริกแดงจินดา(น้ำจิ้ม)" ,"น้ำส้มสายชู(น้ำจิ้ม)" , "น้ำตาลทราย(น้ำจิ้ม)" ,"เกลือ(น้ำจิ้ม)"],
            instructions: "1.ตั้งเตาต้มน้ำให้เดือด แล้วใส่เกลือลงไป จากนั้นเอาไข่เป็ดลงไปต้มให้สุก\n2.เทคนิคทำให้ไข่แดงอยู่ตรงกลางใบ คือ ช่วงแรกของการต้มไข่ให้หมั่นคนไข่ให้ทั่ว\n3.นำรากผักชี กระเทียม และพริกไทย มาโขลกรวมกันให้ละเอียด\n4.ตั้งกระทะให้ท่วม รอจนน้ำมันพอร้อน นำขาหมูที่ล้างทำความสะอาดและพักให้สะเด็ดน้ำลงไปทอด\n5.ทอดพอให้หนังหมูและเนื้อส่วนนอกตึงและสุกขึ้นมา ปิดเตาแล้วนำขาหมูมาพักไว้\n6.เตรียมหม้อตุ๋นขาหมู ใส่น้ำมันพืช และสามเกลอที่โขลกไว้ลงไปผัดให้หอม จากนั้นตักขึ้นมาพักไว้\n7.ใส่น้ำตาลปี๊บ และน้ำเปล่าเล็กน้อยลงในหม้อ ผัดด้วยไฟกลางจนน้ำตาลละลาย และสีเข้มขึ้้นจนคล้ายคาราเมล\n8.ใส่ซอสถั่วเหลือง (โชยุญี่ปุ่น) ลงไปผัดให้เข้ากับน้ำตาลปี๊บ เร่งไฟเป็นไฟแรง\n9.ใส่สามเกลอตามลงไปผัดให้เข้ากัน\n10.ใส่ขาหมูที่ทอดไว้ลงไป ตามด้วยผักกาดดองที่ล้างทำความสะอาดแล้ว\n11.จากนั้นใส่น้ำเปล่าลงไป คนส่วนผสมให้เข้ากัน แล้วรอให้น้ำกลับมาเดือดอีกครั้ง\n12.ลดไปลงเหลือไฟกลางแลัวใส่ผักคะน้า ใส่ไข่ต้มลงไป ใช้ไฟกลางค่อนอ่อน ตุ๋นขาหมูต่อไปอีกประมาณ 3.30 ชั่วโมง\n13.ชิมรสชาติให้ได้รสชาติที่ต้องการ พร้อมเสิร์ฟ\n14.นำส่วนผสมทั้งหมดมาปั่นหรือโขลกรวมกัน(น้ำจิ้ม)\n15.ปั่นให้ส่วนผสมละเอียดเข้ากันดี(น้ำจิ้ม)\n16.ตักใส่ถ้วยพร้อมเสิร์ฟ(น้ำจิ้ม)",
            postedByMember: "คุณเอ็ก"
      },
      {
         id: 16,
            name: "สเต๊กหมูพริกไทยดำ ซอสเกรวี่",
            image: "https://i.ytimg.com/vi/Q1u4TZLPIcY/maxresdefault.jpg",
            author: "กินได้อร่อยด้วย",
            time: " 6 ชั่วโมง",
            difficulty: "ปานกลาง",
            rating: 4.5,
            ingredients: ["สันคอหมู" , "เกลือ" , "นมข้นจืด" , "น้ำมันมะกอก" , "พริกไทยดำ" , "สับปะรด" , "น้ำสต๊อก" , "น้ำตาลทราย" , "ซีอิ้วญี่ปุ่น" , "ซอสมะเขือเทศ" , "พริกไทยดำ" , "แป้งสาลี" , "น้ำ"],
            instructions: "1.เริ่มหมักหมู ใส่เกลือ นมข้นจืด น้ำมันพืช พริกไทยดำ สับปะรด ลงในชามผสม คนให้เข้ากันดี\n2.นำหมูมาคลุกเคล้ากับซอสให้เข้ากันดี ปิดด้วยพลาสติกแรป นำไปแช่ตู้เย็น 4-6 ชั่วโมง\n3.เปิดเตาตั้งกระทะ โดยที่ยังไม่ต้องใส่น้ำมัน รอจนกระทะร้อนได้ที่ เทน้ำมันลงไปเล็กน้อย\n4.นำสเต็กหมูลงไปทอด ด้วยไฟกลางค่อนไปอ่อน ปล่อยทิ้งไว้จนหมูออกขาว พลิกกลับด้าน จากนั้นนำฝาปิด และอบไปเรื่อยๆ ประมาณ 3-4 นาที\n5.เปิดฝา ทอดต่ออีกสักพักเพื่อไล่ความชื้นจนสุกดีอีกประมาณ 10 นาที นำขึ้นมาพักไว้\n6.ทำซอสเกรวี่ โดยใช้กระทะเดิมที่ทอดหมู ไม่ต้องล้างออก เติมน้ำสต็อกหมูลงไป ตามด้วยน้ำตาลทราย ซีอิ๊วญี่ปุ่น ซอสมะเขือเทศ เปิดเตา\n7.รอจนเดือด นำแป้งสาลีผสมน้ำเตรียมไว้ ชิมรสชาติให้ได้ตามชอบ ใส่พริกไทยดำลงไป\n8.ใส่แป้งสาลีลงไป ค่อยๆ ทะยอยใส่ ตามชอบ เคี่ยวไปเรื่อยๆ ให้แป้งสุกดี\n9.นำเสิร์ฟพร้อมสลัดผักสด เฟรนช์ฟรายส์ทอดตามชอบ",
            postedByMember: "คุณไก่"
      },
      {
         id: 17,
            name: "น้ำพริกมะขามหมูสับ",
            image: "https://cms.dmpcdn.com/food/2021/08/23/af9d9120-03f6-11ec-8ecc-6db5b2ed6d3d_original.jpg",
            author: "ครัวบ้านสวนทวี",
            time: " 30 นาที",
            difficulty: "ง่าย",
            rating: 4.0,
            ingredients: ["มะขามอ่อน" , "หมูสับ" , "พริกขี้หนู" , "หอมแดง" , "กระเทียม" , "เกลือ" , "กะปิ" , "น้ำตาลปี๊บ"],
            instructions: "1.นำมะขามอ่อนมาแช่น้ำประมาณ 15 นาที แล้วล้างให้สะอาด\n2.ตัดหัว-ท้าย มะขาม ส่วนที่แข็งๆ ออก\n3.นำมะขามอ่อน มาโขลกให้แหลก แล้วใส่เกลือลงไป ตำต่อจนละเอียด\n4.ใส่หอมแดง และกระเทียมตามลงไปตำ ค่อยๆตำจนละเอียด\n5.จากนั้นใส่กำปิตามลงไป แล้วตำให้เข้ากัน\n6.ใส่พริกขี้หนู แล้วตำต่อให้ละเอียดเข้ากันดี\n7.ใส่หมูสับลงไปตำๆ คลุก ให้หมูเข้ากันดีกับน้ำพริก\n8.ตั้งกระทะใส่น้ำมัน พอน้ำมันเริ่มร้อนให้ใส่น้ำพริกลงไปผัด\n9.ใช้ไฟกลางผัดให้เนื้อหมูสุก ถ้าน้ำพริกแห้งไปให้ใส่น้ำล้างครกตามลงไปเล็กน้อย\n10.ผัดต่อจนน้ำพริกแห้ง และมีสีเข้มขึ้น ลงไฟเหลือไฟอ่อน ปรุงรสด้วยน้ำตาลปี๊บ ผัดจนน้ำตาลละลายเข้ากันดี\n11.ตักน้ำพริกใส่ชาม พร้อมเสิร์ฟคู่ผักสด",
            postedByMember: "คุณน้อย"
      },
      { id: 18,
            name: "ปีกไก่ทอด",
            image: "https://cms.dmpcdn.com/food/2021/04/13/1cab0110-9c39-11eb-8b27-db7c51a78b67_original.jpg",
            author: "ครัวบ้านสวนทวี - Baan Suan Tawee Cooking",
            time: " 10นาที",
            difficulty: "ง่าย",
            rating: 4.8,
            ingredients: ["ปีกบนไก่เต็ม" , "ผงปรุงรส" , "เกลือ" , "พริกไทย" , "น้ำปลา"],
            instructions: "1.นำปีกไก่มาล้างทำความสะอาด แล้วทิ้งไว้ให้สะเด็ดน้ำ\n2.หมักปีกไก่ด้วย ผงปรุงรส เกลือ พริกไทย และน้ำปลา แล้วขยำให้ส่วนผสมเข้ากันดีกับไก่\n3.นำไก่มาวางบนตะแกรง แล้วนำไปตากแดด 1 แดด (ประมาณ 2-3 ชั่วโมง) จนหนังไก่แห้ง และมีความตึง เพื่อให้ทอดแล้วจะได้หนังไก่ที่กรอบ\n4.ตั้งน้ำมันให้ร้อนจัด จากนั้นนำไก่ลงทอด แล้วลดไฟลงเหลือไฟกลาง\n5.คอยพลิกไก่ จนไก่มีสีเหลืองทอง นำไก่ขึ้นมาพักให้สะเด็ดน้ำมัน พร้อมเสิร์ฟ",
            postedByMember: ""
      }
    ];

    function displayRecipes(recipesToDisplay) {
        if (!recipeGrid) return;
        recipeGrid.innerHTML = '';
        if (!recipesToDisplay || recipesToDisplay.length === 0) {
            recipeGrid.innerHTML = '<p class="no-results">🚫 ไม่พบสูตรอาหารที่ตรงกับเงื่อนไขของคุณ</p>';
            return;
        }

        recipesToDisplay.forEach(recipe => {
            const card = document.createElement('div');
            card.classList.add('recipe-card');
            card.innerHTML = `
                <img src="${recipe.image}" alt="${recipe.name}" onerror="this.onerror=null;this.src='https://via.placeholder.com/500x220.png?text=No+Image+Available';">
                <div class="recipe-card-content">
                    <h3>${recipe.name}</h3>
                    <div class="recipe-meta">
                        <span><i class="fas fa-clock"></i> ${recipe.time}</span>
                        <span><i class="fas fa-star"></i> ${recipe.rating}/5</span>
                        <span><i class="fas fa-tachometer-alt"></i> ${recipe.difficulty}</span>
                    </div>
                    <p>โดย: ${recipe.author}</p>
                    <div class="recipe-card-actions">
                        <button class="btn view-recipe-btn" data-id="${recipe.id}">ดูสูตรอาหาร</button>
                    </div>
                </div>
            `;
            recipeGrid.appendChild(card);
        });

        document.querySelectorAll('.view-recipe-btn').forEach(button => {
            button.addEventListener('click', (e) => {
                const recipeId = parseInt(e.target.dataset.id);
                const selectedRecipe = recipes.find(r => r.id === recipeId);
                if (selectedRecipe) {
                    showRecipeDetail(selectedRecipe);
                }
            });
        });
    }

    function showRecipeDetail(recipe) {
        if (!modal) return;
        document.getElementById('modalRecipeName').textContent = recipe.name;
        const modalImage = document.getElementById('modalRecipeImage');
        modalImage.src = recipe.image;
        modalImage.alt = recipe.name;
        modalImage.onerror = function() {
            this.onerror=null;
            this.src='https://via.placeholder.com/700x300.png?text=Image+Not+Found';
        };

        document.getElementById('modalRecipeAuthor').textContent = recipe.author;
        document.getElementById('modalRecipeTime').textContent = recipe.time;
        document.getElementById('modalRecipeDifficulty').textContent = recipe.difficulty;

        const ingredientsList = document.getElementById('modalRecipeIngredients');
        ingredientsList.innerHTML = '';
        recipe.ingredients.forEach(ing => {
            const li = document.createElement('li');
            li.textContent = ing;
            ingredientsList.appendChild(li);
        });

        document.getElementById('modalRecipeInstructions').innerHTML = recipe.instructions.replace(/\n/g, '<br>');
        modal.style.display = 'block';
    }

    if (closeModalButton) {
        closeModalButton.onclick = () => {
            if (modal) modal.style.display = 'none';
        }
    }
    window.onclick = (event) => {
        if (event.target == modal) {
            if (modal) modal.style.display = 'none';
        }
    }

    function handleSearch() {
        if (!searchInput) return;
        const searchTerm = searchInput.value.toLowerCase().trim();
        const filteredRecipes = recipes.filter(recipe =>
            recipe.name.toLowerCase().includes(searchTerm) ||
            recipe.ingredients.some(ing => ing.toLowerCase().includes(searchTerm)) ||
            recipe.author.toLowerCase().includes(searchTerm)
        );
        displayRecipes(filteredRecipes);
    }

    if (searchButton) searchButton.addEventListener('click', handleSearch);
    if (searchInput) {
        searchInput.addEventListener('keyup', (event) => {
            if (event.key === 'Enter') {
                handleSearch();
            }
        });
    }

    if (filterBtns) {
        filterBtns.forEach(btn => {
            btn.addEventListener('click', () => {
                filterBtns.forEach(b => b.classList.remove('active'));
                btn.classList.add('active');
                const filterType = btn.dataset.filter;
                let currentRecipes = [...recipes]; // Start with all recipes or apply search term if present

                if (searchInput && searchInput.value.trim() !== '') {
                     const searchTerm = searchInput.value.toLowerCase().trim();
                     currentRecipes = recipes.filter(recipe =>
                        recipe.name.toLowerCase().includes(searchTerm) ||
                        recipe.ingredients.some(ing => ing.toLowerCase().includes(searchTerm)) ||
                        recipe.author.toLowerCase().includes(searchTerm)
                    );
                }


                if (filterType === 'by-member') {
                    // Simple sort by author. Real grouping/filtering by specific member might be complex.
                    currentRecipes.sort((a, b) => a.postedByMember.localeCompare(b.postedByMember));
                } else if (filterType === 'by-rating') {
                    currentRecipes.sort((a, b) => b.rating - a.rating);
                }
                // 'all' will use currentRecipes which is either all or search-filtered
                displayRecipes(currentRecipes);
            });
        });
    }

    const createRecipeForm = document.getElementById('createRecipeForm');
    if (createRecipeForm) {
        createRecipeForm.addEventListener('submit', function(event) {
            event.preventDefault();
            // Basic validation (can be more extensive)
            if (!this.recipeName.value || !this.recipeTime.value || !this.recipeIngredients.value || !this.recipeInstructions.value) {
                alert("กรุณากรอกข้อมูลที่จำเป็นให้ครบถ้วน");
                return;
            }

            const newRecipe = {
                id: recipes.length > 0 ? Math.max(...recipes.map(r => r.id)) + 1 : 1, // More robust ID
                name: this.recipeName.value,
                image: this.recipeImage.value || "https://via.placeholder.com/500x220.png?text=Recipe+Image",
                author: "ผู้ใช้ปัจจุบัน", // Placeholder - replace with actual logged-in user
                time: this.recipeTime.value,
                difficulty: this.recipeDifficulty.value,
                rating: 0, // New recipes
                ingredients: this.recipeIngredients.value.split('\n').map(ing => ing.trim()).filter(ing => ing !== ''),
                instructions: this.recipeInstructions.value,
                postedByMember: "ผู้ใช้ปัจจุบัน" // Placeholder
            };
            recipes.unshift(newRecipe); // Add to the beginning of the array for immediate visibility
            alert(`สูตร "${newRecipe.name}" ของคุณถูกเพิ่มแล้ว!`);
            displayRecipes(recipes);
            this.reset();
            // Potentially scroll to the new recipe or to the top of the list
            if (recipeGrid) recipeGrid.scrollIntoView({ behavior: 'smooth' });
        });
    }

    // Initial display
    displayRecipes(recipes);
});
