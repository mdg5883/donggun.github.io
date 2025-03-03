# donggun.github.io{<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Donggun Min Portfolio</title>
    <style>
        body {
            background-color: #f7f7f7;
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }
        .container {
            width: 80%;
            max-width: 1200px;
            margin: auto;
            padding: 20px;
        }
        .gallery {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .gallery img {
            width: 100%;
            max-width: 800px;
            margin-bottom: 20px;
        }
        .description {
            text-align: center;
            margin-bottom: 40px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1 style="text-align:center;">Donggun Min Portfolio</h1>
        <div class="gallery" id="gallery"></div>
    </div>

    <script>
        async function loadGallery() {
            const response = await fetch('content/gallery.json');
            const images = await response.json();
            const gallery = document.getElementById('gallery');
            images.forEach(image => {
                let imgElement = document.createElement('img');
                imgElement.src = image.url;
                imgElement.alt = image.description;
                let descElement = document.createElement('div');
                descElement.className = 'description';
                descElement.innerText = image.description;
                gallery.appendChild(imgElement);
                gallery.appendChild(descElement);
            });
        }
        loadGallery();
    </script>
</body>
</html>
