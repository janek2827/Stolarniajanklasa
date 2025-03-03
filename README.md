<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Stolarnia Jan Klasa - Galeria</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 0;
            padding: 0;
        }

        .header {
            background-image: url('gora.jpg');
            background-size: cover;
            background-position: center;
            height: 300px;
            width: 100%;
            position: relative;
        }

        h1 {
            color: #333;
            background-color: rgba(242, 230, 217, 0.7);
            padding: 20px;
            margin: 0;
            position: absolute;
            top: 10%;
            left: 50%;
            transform: translateX(-50%);
            font-size: 2em;
            z-index: 1;
        }

        body {
            background-image: url('tlo.jpg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            margin: 0;
            padding: 0;
        }

        .gallery {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            padding: 20px;
        }

        .gallery img {
            max-width: 100%;
            height: auto;
            border-radius: 10px;
            border: 2px solid black;
            cursor: pointer;
        }

        .image-container {
            width: 300px;
            padding: 10px;
            border-radius: 10px;
            background: none;
            box-shadow: none;
        }

        h2 {
            color: #333;
            background-color: #f2e6d9;
            padding: 10px;
            border-radius: 5px;
        }

        .scroll-container {
            width: 300px;
            overflow: hidden;
            position: relative;
            margin: 0 auto;
        }

        .images {
            display: flex;
            transition: transform 0.3s ease-in-out;
        }

        .scroll-container img {
            height: 200px;
            width: auto;
            object-fit: contain;
        }

        .scroll-button {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background-color: rgba(0, 0, 0, 0.5);
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
            font-size: 20px;
            z-index: 2;
        }

        .scroll-button.left {
            left: 10px;
        }

        .scroll-button.right {
            right: 10px;
        }

        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            max-width: 90%;
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            position: relative;
            overflow: hidden;
        }

        .modal img {
            width: 100%;
            object-fit: contain;
            max-height: 100vh;
        }

        .close-btn {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: rgba(0, 0, 0, 0.5);
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
            font-size: 20px;
            border-radius: 5px;
        }

        @media (max-width: 768px) {
            .gallery {
                flex-direction: column;
            }

            .image-container {
                width: 100%;
            }

            .scroll-container {
                flex-direction: column;
                gap: 10px;
            }
        }
    </style>
</head>
<body>
    <div class="header"></div>
    <h1>Stolarnia Jan Klasa - Galeria</h1>

    <div class="gallery">
        <div class="image-container">
            <h2>Meble</h2>
            <div class="scroll-container" id="meble">
                <div class="images">
                    <img src="szafka.jpg" alt="Szafka" onclick="openModal('szafka.jpg')">
                    <img src="stolik.jpg" alt="Stolik" onclick="openModal('stolik.jpg')">
                    <img src="witryna.jpg" alt="Witryna" onclick="openModal('witryna.jpg')">
                    <img src="xx.jpg" alt="XX" onclick="openModal('xx.jpg')">
                    <img src="olej.jpg" alt="Olej" onclick="openModal('olej.jpg')">
                    <img src="lozkos.jpg" alt="Łóżko" onclick="openModal('lozkos.jpg')">
                    <img src="biurko.jpg" alt="Biurko" onclick="openModal('biurko.jpg')">
                    <img src="biel.jpg" alt="Biel" onclick="openModal('biel.jpg')">
                </div>
                <button class="scroll-button left" onclick="scrollLeft('meble')">&#10094;</button>
                <button class="scroll-button right" onclick="scrollRight('meble')">&#10095;</button>
            </div>
        </div>
        <div class="image-container">
            <h2>Schody</h2>
            <div class="scroll-container" id="schody">
                <div class="images">
                    <img src="jesion.jpg" alt="Jesion" onclick="openModal('jesion.jpg')">
                    <img src="balustrada.jpg" alt="Balustrada" onclick="openModal('balustrada.jpg')">
                    <img src="god.jpg" alt="God" onclick="openModal('god.jpg')">
                    <img src="wyspa.jpg" alt="Wyspa" onclick="openModal('wyspa.jpg')">
                    <img src="szkl.jpg" alt="Szkl" onclick="openModal('szkl.jpg')">
                    <img src="ost.jpg" alt="Ost" onclick="openModal('ost.jpg')">
                </div>
                <button class="scroll-button left" onclick="scrollLeft('schody')">&#10094;</button>
                <button class="scroll-button right" onclick="scrollRight('schody')">&#10095;</button>
            </div>
        </div>
        <div class="image-container">
            <h2>Inne</h2>
            <div class="scroll-container" id="inne">
                <div class="images">
                    <img src="traktor.jpg" alt="Traktor" onclick="openModal('traktor.jpg')">
                    <img src="kije.jpg" alt="Kije" onclick="openModal('kije.jpg')">
                </div>
                <button class="scroll-button left" onclick="scrollLeft('inne')">&#10094;</button>
                <button class="scroll-button right" onclick="scrollRight('inne')">&#10095;</button>
            </div>
        </div>
        <div class="image-container">
            <h2>Renowacje</h2>
            <div class="scroll-container" id="renowacje">
                <div class="images">
                    <img src="skrzypce.jpg" alt="Skrzypce" onclick="openModal('skrzypce.jpg')">
                    <img src="woz.jpg" alt="Wóz" onclick="openModal('woz.jpg')">
                    <img src="gitara.jpg" alt="Gitara" onclick="openModal('gitara.jpg')">
                </div>
                <button class="scroll-button left" onclick="scrollLeft('renowacje')">&#10094;</button>
                <button class="scroll-button right" onclick="scrollRight('renowacje')">&#10095;</button>
            </div>
        </div>
    </div>

    <!-- Modal do powiększania zdjęcia -->
    <div id="myModal" class="modal" onclick="closeModal(event)">
        <div class="modal-content" id="modalContent">
            <img id="modalImg" src="" alt="">
            <button class="close-btn" onclick="closeModal(event)">X</button>
        </div>
    </div>

    <script>
        let currentImages = [];
        let currentIndex = 0;

        // Funkcja otwierająca powiększone zdjęcie
        function openModal(src) {
            const modal = document.getElementById('myModal');
            const modalImg = document.getElementById('modalImg');
            modal.style.display = "flex"; // Pokazuje modal
            modalImg.src = src; // Ustawia źródło zdjęcia w modalnym oknie

            // Znajdź kontener z którego pochodzi zdjęcie i załaduj wszystkie zdjęcia
            currentImages = Array.from(document.querySelector(`#${src.split('.')[0]}.images img`)).map(img => img.src);
            currentIndex = currentImages.indexOf(src);
        }

        // Funkcja zamykająca modalne okno
        function closeModal(event) {
            if (event.target === document.getElementById('myModal') || event.target === document.querySelector('.close-btn')) {
                const modal = document.getElementById('myModal');
                modal.style.display = "none"; // Ukrywa modalne okno
            }
        }

        // Funkcja przewijania zdjęć w lewo w kontenerach
        function scrollLeft(container) {
            const containerElement = document.querySelector(`#${container} .images`);
            const firstChild = containerElement.firstElementChild;
            containerElement.appendChild(firstChild); // Przenosi pierwsze zdjęcie na koniec
        }

        // Funkcja przewijania zdjęć w prawo w kontenerach
        function scrollRight(container) {
            const containerElement = document.querySelector(`#${container} .images`);
            const lastChild = containerElement.lastElementChild;
            containerElement.prepend(lastChild); // Przenosi ostatnie zdjęcie na początek
        }

        // Funkcja przewijania zdjęć w lewo w modalu
        function scrollLeftModal() {
            currentIndex = (currentIndex === 0) ? currentImages.length - 1 : currentIndex - 1;
            document.getElementById('modalImg').src = currentImages[currentIndex];
        }

        // Funkcja przewijania zdjęć w prawo w modalu
        function scrollRightModal() {
            currentIndex = (currentIndex === currentImages.length - 1) ? 0 : currentIndex + 1;
            document.getElementById('modalImg').src = currentImages[currentIndex];
        }

        // Funkcje do przewijania za pomocą klawiatury
        window.addEventListener('keydown', function (event) {
            if (document.getElementById('myModal').style.display === "flex") {
                if (event.key === "ArrowLeft") {
                    scrollLeftModal();
                } else if (event.key === "ArrowRight") {
                    scrollRightModal();
                }
            }
        });
    </script>
</body>
</html>
