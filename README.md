<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Top Aussie Pokies 🎰</title>
  <style>
    body {
      background: #0d0d0d;
      color: #fff;
      font-family: 'Arial', sans-serif;
      margin: 0;
      padding: 1rem;
    }
    h1 {
      color: #ff5252;
      text-align: center;
      margin-bottom: 1rem;
    }
    .pokie-links {
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }
    .pokie {
      background: #1c1c1c;
      padding: 1rem;
      border-radius: 10px;
      border: 1px solid #444;
    }
    .pokie a {
      color: #00e676;
      text-decoration: none;
      font-size: 1.1rem;
      word-wrap: break-word;
    }
    .pokie a:hover {
      text-decoration: underline;
    }
  </style>
</head>
<body>
  <h1>🔥 Top Aussie Pokies with Bonus Links 🔥</h1>
  <div class="pokie-links" id="pokieLinks">Loading...</div>

  <script>
    async function loadLinks() {
      try {
        const response = await fetch('./links.json');
        const links = await response.json();
        const container = document.getElementById('pokieLinks');
        container.innerHTML = '';
        links.forEach(link => {
          const div = document.createElement('div');
          div.className = 'pokie';
          div.innerHTML = `<a href="${link.url}" target="_blank">${link.name}</a>`;
          container.appendChild(div);
        });
      } catch (err) {
        document.getElementById('pokieLinks').innerHTML = 'Failed to load links.';
        console.error(err);
      }
    }
    loadLinks();
  </script>
</body>
</html>
