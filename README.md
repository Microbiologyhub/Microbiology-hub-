# Microbiology-hub-
A scientific learning and microorganisms database app

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="theme-color" content="#102b46">
  <title>Microbiology Hub</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <header class="header">
    <h1>Microbiology Hub</h1>
    <p>Explore. Understand. Discover.</p>
  </header>

  <nav class="navigation">
    <button onclick="showPage('home')">Home</button>
    <button onclick="showPage('explore')">Explore</button>
    <button onclick="showPage('compare')">Compare</button>
    <button onclick="showPage('learn')">Learn</button>
    <button onclick="showPage('saved')">Saved</button>
  </nav>

  <main>
    <section id="home" class="page active">
      <h2>Welcome to Microbiology Hub</h2>
      <p>Your learning space for discovering microorganisms.</p>

      <div class="welcome-card">
        <h3>Discover the microbial world</h3>
        <p>Explore bacteria, fungi, viruses and parasites.</p>
        <button onclick="showPage('explore')">Explore organisms</button>
      </div>
    </section>

    <section id="explore" class="page">
      <h2>Explore Microorganisms</h2>
      <input
        type="search"
        id="searchInput"
        placeholder="Search microorganisms..."
        oninput="searchOrganisms()"
      >
      <div id="organismList"></div>
    </section>

    <section id="profile" class="page">
      <button onclick="showPage('explore')">← Back to Explore</button>
      <div id="profileContent"></div>
    </section>

    <section id="compare" class="page">
      <h2>Compare Microorganisms</h2>
      <label for="organismOne">First organism</label>
      <select id="organismOne"></select>

      <label for="organismTwo">Second organism</label>
      <select id="organismTwo"></select>

      <button onclick="compareOrganisms()">Compare</button>
      <div id="comparisonResult"></div>
    </section>

    <section id="learn" class="page">
      <h2>Learning Centre</h2>
      <div class="welcome-card">
        <h3>Microbiology Basics</h3>
        <p>Learn about microbial classification, morphology,
        growth and identification.</p>
      </div>
    </section>

    <section id="saved" class="page">
      <h2>Saved Organisms</h2>
      <div id="savedList"></div>
    </section>
  </main>

  <footer>
    <p>Microbiology Hub © 2026</p>
    <p>Explore. Understand. Discover.</p>
  </footer>

  <script src="script.js"></script>
</body>
</html>
