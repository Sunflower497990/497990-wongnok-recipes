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
