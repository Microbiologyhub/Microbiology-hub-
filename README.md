# Microbiology-hub-
A scientific learning and microorganisms database app
html.index
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
css
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, sans-serif;
  background: #f3f7fa;
  color: #263747;
  line-height: 1.6;
}

.header {
  background: #102b46;
  color: white;
  text-align: center;
  padding: 30px 15px;
}

.header h1 {
  font-size: 27px;
  margin-bottom: 5px;
}

.header p {
  color: #65d6c4;
}

.navigation {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  background: #174563;
  padding: 10px 5px;
  gap: 5px;
}

button {
  background: #087f8c;
  color: white;
  border: none;
  border-radius: 7px;
  padding: 11px 15px;
  cursor: pointer;
  font-size: 14px;
  margin: 5px 0;
}

button:hover {
  background: #075e69;
}

.navigation button {
  background: transparent;
  color: white;
}

.navigation button:hover {
  background: #087f8c;
}

main {
  max-width: 850px;
  margin: 25px auto;
  padding: 0 15px;
  min-height: 55vh;
}

.page {
  display: none;
}

.page.active {
  display: block;
}

h2 {
  color: #102b46;
  margin-bottom: 15px;
}

h3 {
  color: #087f8c;
  margin-bottom: 8px;
}

.welcome-card {
  background: white;
  padding: 22px;
  margin-top: 20px;
  border-radius: 12px;
  border-left: 5px solid #087f8c;
  box-shadow: 0 3px 12px #102b4612;
}

input, select {
  width: 100%;
  padding: 13px;
  margin: 10px 0;
  border: 1px solid #cbd5df;
  border-radius: 7px;
  background: white;
  font-size: 15px;
}

.organism-card {
  background: white;
  padding: 16px;
  margin: 12px 0;
  border-radius: 10px;
  box-shadow: 0 2px 8px #102b4610;
}

.organism-card h3 {
  margin-bottom: 5px;
}

.organism-card button {
  margin-top: 10px;
}

.profile-section {
  background: white;
  padding: 16px;
  margin: 12px 0;
  border-radius: 9px;
}

.profile-section h3 {
  border-bottom: 1px solid #e0e8ed;
  padding-bottom: 6px;
}

footer {
  text-align: center;
  background: #102b46;
  color: white;
  padding: 20px;
  margin-top: 30px;
  font-size: 13px;
}

#comparisonResult {
  overflow-x: auto;
  margin-top: 20px;
}

table {
  width: 100%;
  border-collapse: collapse;
  background: white;
}

th, td {
  border: 1px solid #d5e0e7;
  padding: 10px;
  text-align: left;
  min-width: 120px;
}

th {
  background: #174563;
  color: white;
}

@media (max-width: 480px) {
  .header h1 {
    font-size: 23px;
  }

  .navigation button {
    padding: 9px;
    font-size: 12px;
  }

  main {
    padding: 0 12px;
  }
}
