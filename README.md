<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>aButMusic</title>
    <link href="https://fonts.googleapis.com/css2?family=Helvetica+Neue:wght@400;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Helvetica Neue', Arial, sans-serif;
            background-color: #121212;
            margin: 0;
            padding: 0;
            color: #e0e0e0;
        }
        header {
            background-color: #1f1f1f;
            color: #e0e0e0;
            padding: 20px 0;
            text-align: center;
            font-size: 28px;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 2px;
        }
        nav {
            display: flex;
            justify-content: center;
            padding: 15px;
            background-color: #2c2c2c;
        }
        nav a {
            color: #e0e0e0;
            margin: 0 20px;
            text-decoration: none;
            text-transform: uppercase;
            font-weight: bold;
            letter-spacing: 1px;
        }
        .container {
            padding: 40px;
            max-width: 1200px;
            margin: auto;
        }
        .section-title {
            font-size: 24px;
            margin-bottom: 20px;
            border-bottom: 3px solid #2c2c2c;
            display: inline-block;
            text-transform: uppercase;
        }
        .reviews, .search, .create-review, .my-profile {
            background-color: #1f1f1f;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.5);
            border-radius: 10px;
        }
        .review-item {
            border-bottom: 1px solid #333;
            padding: 15px 0;
            position: relative;
        }
        .review-item:last-child {
            border-bottom: none;
        }
        .review-item h3 {
            margin: 0;
            font-size: 20px;
        }
        .input-field, .thoughts-box {
            width: 100%;
            padding: 15px;
            font-size: 16px;
            margin-bottom: 15px;
            border: 1px solid #333;
            border-radius: 5px;
            background-color: #2c2c2c;
            color: #e0e0e0;
        }
        .btn {
            background-color: #e0e0e0;
            color: #1f1f1f;
            padding: 15px 30px;
            border: none;
            cursor: pointer;
            text-transform: uppercase;
            font-weight: bold;
            letter-spacing: 1px;
            border-radius: 5px;
        }
        .btn:hover {
            background-color: #555;
        }
        .rating {
            margin-bottom: 15px;
        }
        .rating label {
            margin-right: 10px;
            font-weight: bold;
        }
        .file-input {
            display: none;
        }
        .file-label {
            background-color: #e0e0e0;
            color: #1f1f1f;
            padding: 15px 30px;
            cursor: pointer;
            text-transform: uppercase;
            font-weight: bold;
            letter-spacing: 1px;
            border-radius: 5px;
            display: inline-block;
        }
        .user-rating {
            display: flex;
            align-items: center;
            margin-top: 10px;
        }
        .user-rating select {
            margin-right: 10px;
        }
        .review-options {
            display: none;
            position: absolute;
            top: 10px;
            right: 10px;
        }
        .review-item:hover .review-options {
            display: block;
        }
        .review-options button {
            background: none;
            border: none;
            cursor: pointer;
            font-size: 18px;
        }
    </style>
</head>
<body>
    <header>
        aButMusic
    </header>
    <nav>
        <a href="#latest-reviews">Ultime Recensioni</a>
        <a href="#search">Cerca/Recensisci</a>
        <a href="#my-profile">Il Mio Profilo</a>
    </nav>
    <div class="container">
        <section id="latest-reviews">
            <div class="section-title">Ultime Canzoni/Album Valutati</div>
            <div class="reviews">
                <div class="review-item">
                    <h3>Album: Esempio Album 1</h3>
                    <p>Recensione: Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
                    <p>Valutazione: 8/10</p>
                    <div class="user-rating">
                        <select class="input-field">
                            <option value="1">1</option>
                            <option value="2">2</option>
                            <option value="3">3</option>
                            <option value="4">4</option>
                            <option value="5">5</option>
                            <option value="6">6</option>
                            <option value="7">7</option>
                            <option value="8">8</option>
                            <option value="9">9</option>
                            <option value="10">10</option>
                        </select>
                        <button class="btn">Valuta</button>
                    </div>
                    <div class="review-options">
                        <button onclick="editReview(this)">⋮</button>
                    </div>
                </div>
                <!-- Altre recensioni -->
            </div>
        </section>
        <section id="search">
            <div class="section-title">Cerca un Album</div>
            <div class="search">
                <input type="text" class="input-field search-box" placeholder="Cerca un album...">
                <button class="btn" onclick="searchAlbum()">Cerca</button>
                <p>Oppure <a href="#" onclick="showCreateReview()">crea una recensione</a> se l'album non è recensito.</p>
            </div>
        </section>
        <section id="create-review" class="create-review" style="display:none;">
            <div class="section-title">Crea una Recensione</div>
            <input type="text" class="input-field" placeholder="Titolo dell'Album">
            <input type="text" class="input-field" placeholder="Autore">
            <input type="text" class="input-field" placeholder="Produttore">
            <input type="text" class="input-field" placeholder="Etichetta Discografica">
            <div class="rating">
                <label for="rating-create">Valutazione:</label>
                <select id="rating-create" class="input-field">
                    <option value="1">1</option>
                    <option value="2">2</option>
                    <option value="3">3</option>
                    <option value="4">4</option>
                    <option value="5">5</option>
                    <option value="6">6</option>
                    <option value="7">7</option>
                    <option value="8">8</option>
                    <option value="9">9</option>
                    <option value="10">10</option>
                </select>
            </div>
            <label class="file-label" for="cover-upload">Carica Copertina</label>
            <input type="file" id="cover-upload" class="file-input" accept="image/png, image/jpeg">
            <textarea class="thoughts-box" placeholder="Scrivi i tuoi pensieri sull'album..."></textarea>
            <button class="btn">Invia Recensione</button>
        </section>
        <section id="my-profile" class="my-profile">
            <div class="section-title">Il Mio Profilo</div>
            <div class="reviews">
                <div class="review-item">
                    <h3>Album: Esempio Album 1</h3>
                    <p>Recensione: Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
                    <p>Valutazione: 8/10</p>
                    <div class="review-options">
                        <button onclick="editReview(this)">⋮</button>
                    </div>
                </div>
                <!-- Altre recensioni -->
            </div>
        </section>
    </div>
    <script>
        function searchAlbum() {
            const query = document.querySelector('.search-box').value;
            // Logica di ricerca album
        }

        function showCreateReview() {
            document.getElementById('create-review').style.display = 'block';
        }

        function editReview(button) {
            const reviewItem# aButMusik
