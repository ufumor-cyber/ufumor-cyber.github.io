
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Umor Faruk Photography</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
    }

    body {
      background-color: #0d0d0d;
      color: #f0f0f0;
    }

    header {
      text-align: center;
      padding: 40px 0;
      background: linear-gradient(90deg, #000, #111, #000);
      box-shadow: 0 0 20px #111;
    }

    header h1 {
      font-size: 2.5rem;
      letter-spacing: 2px;
      color: #00c3ff;
    }

    header p {
      color: #aaa;
      font-size: 1rem;
      margin-top: 5px;
    }

    .upload-section {
      text-align: center;
      padding: 30px;
      background: #111;
      border-top: 1px solid #222;
      border-bottom: 1px solid #222;
    }

    .upload-section input {
      background: #222;
      border: none;
      color: #f0f0f0;
      padding: 10px 20px;
      border-radius: 8px;
      cursor: pointer;
      transition: background 0.3s ease;
    }

    .upload-section input:hover {
      background: #00c3ff;
      color: #000;
    }

    .gallery {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 15px;
      padding: 40px;
      animation: fadeIn 1.5s ease-in-out;
    }

    .gallery img {
      width: 100%;
      height: 280px;
      object-fit: cover;
      border-radius: 10px;
      transition: transform 0.4s ease, box-shadow 0.4s ease;
    }

    .gallery img:hover {
      transform: scale(1.05);
      box-shadow: 0 0 15px #00c3ff;
    }

    footer {
      text-align: center;
      padding: 20px;
      font-size: 0.9rem;
      color: #888;
      background: #111;
      border-top: 1px solid #222;
    }

    @keyframes fadeIn {
      from {opacity: 0; transform: translateY(20px);}
      to {opacity: 1; transform: translateY(0);}
    }
  </style>
</head>
<body>

  <header>
    <h1>Umor Faruk Photography</h1>
    <p>Capturing moments through my lens</p>
  </header>

  <section class="upload-section">
    <h2>📸 Upload Your Photos</h2><br>
    <input type="file" id="photoUpload" accept="image/*" multiple>
  </section>

  <section class="gallery" id="gallery">
    <!-- Uploaded photos and sample photos will appear here -->
    <img src="https://source.unsplash.com/600x400/?nature,light" alt="Sample Photo 1">
    <img src="https://source.unsplash.com/600x400/?portrait,shadow" alt="Sample Photo 2">
    <img src="https://source.unsplash.com/600x400/?street,night" alt="Sample Photo 3">
  </section>

  <footer>
    © 2025 Umor Faruk Photography | All rights reserved
  </footer>

  <script>
    const uploadInput = document.getElementById('photoUpload');
    const gallery = document.getElementById('gallery');

    uploadInput.addEventListener('change', function(event) {
      const files = event.target.files;
      for (let i = 0; i < files.length; i++) {
        const file = files[i];
        const reader = new FileReader();

        reader.onload = function(e) {
          const img = document.createElement('img');
          img.src = e.target.result;
          img.alt = 'Uploaded Photo';
          gallery.prepend(img); // Adds new photo at the top
        }

        reader.readAsDataURL(file);
      }
    });
  </script>

</body>
</html>