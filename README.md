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
style.css
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
script.js
const organisms = [
  {
    id: "staph",
    name: "Staphylococcus aureus",
    type: "Bacterium",
    gram: "Gram-positive",
    morphology: "Cocci arranged in grape-like clusters.",
    growth: "Facultative anaerobe; grows under aerobic and anaerobic conditions.",
    biochemical: "Catalase-positive, coagulase-positive, usually mannitol-fermenting.",
    habitat: "Human skin and anterior nares.",
    medical: "Can cause skin infections, pneumonia, bloodstream infections and food poisoning.",
    identification: "Gram stain, catalase test, coagulase test and other laboratory identification methods."
  },
  {
    id: "ecoli",
    name: "Escherichia coli",
    type: "Bacterium",
    gram: "Gram-negative",
    morphology: "Rod-shaped bacillus, usually occurring singly.",
    growth: "Facultative anaerobe; many strains are motile.",
    biochemical: "Usually lactose-fermenting, indole-positive and oxidase-negative.",
    habitat: "Intestinal tract of humans and other warm-blooded animals.",
    medical: "Some strains cause diarrhoeal disease and urinary tract infections.",
    identification: "Gram stain, culture characteristics and biochemical identification."
  },
  {
    id: "typhi",
    name: "Salmonella enterica serovar Typhi",
    type: "Bacterium",
    gram: "Gram-negative",
    morphology: "Rod-shaped bacillus, usually motile.",
    growth: "Facultative anaerobe.",
    biochemical: "Non-lactose-fermenting; usually produces hydrogen sulfide.",
    habitat: "Human intestinal tract; may also persist in the gallbladder.",
    medical: "Causes typhoid fever, a systemic infection.",
    identification: "Laboratory identification using appropriate culture and confirmatory tests."
  }
];

let currentPage = "home";

function showPage(page) {
  document.querySelectorAll(".page").forEach(section => {
    section.classList.remove("active");
  });

  const target = document.getElementById(page);
  if (!target) return;

  target.classList.add("active");
  currentPage = page;

  if (page === "explore") searchOrganisms();
  if (page === "saved") displaySaved();
  if (page === "compare") populateCompare();
}

function searchOrganisms() {
  const input = document.getElementById("searchInput");
  const query = input.value.toLowerCase();

  const results = organisms.filter(org =>
    org.name.toLowerCase().includes(query) ||
    org.type.toLowerCase().includes(query)
  );

  const list = document.getElementById("organismList");

  if (results.length === 0) {
    list.innerHTML = "<p>No organisms found. Try another search.</p>";
    return;
  }

  list.innerHTML = results.map(org => `
    <div class="organism-card">
      <h3>${org.name}</h3>
      <p>${org.type} · ${org.gram}</p>
      <button onclick="openProfile('${org.id}')">View profile</button>
    </div>
  `).join("");
}

function openProfile(id) {
  const org = organisms.find(item => item.id === id);
  if (!org) return;

  document.getElementById("profileContent").innerHTML = `
    <h2>${org.name}</h2>
    <p><strong>Type:</strong> ${org.type}</p>
    <p><strong>Gram reaction:</strong> ${org.gram}</p>

    <div class="profile-section">
      <h3>Morphology</h3>
      <p>${org.morphology}</p>
    </div>

    <div class="profile-section">
      <h3>Growth characteristics</h3>
      <p>${org.growth}</p>
    </div>

    <div class="profile-section">
      <h3>Biochemical characteristics</h3>
      <p>${org.biochemical}</p>
    </div>

    <div class="profile-section">
      <h3>Habitat</h3>
      <p>${org.habitat}</p>
    </div>

    <div class="profile-section">
      <h3>Medical importance</h3>
      <p>${org.medical}</p>
    </div>

    <div class="profile-section">
      <h3>Identification</h3>
      <p>${org.identification}</p>
    </div>

    <button onclick="saveOrganism('${org.id}')">Save organism</button>
  `;

  showPage("profile");
}

function getSaved() {
  try {
    return JSON.parse(localStorage.getItem("savedOrganisms")) || [];
  } catch {
    return [];
  }
}

function saveOrganism(id) {
  const saved = getSaved();

  if (!saved.includes(id)) {
    saved.push(id);
    localStorage.setItem("savedOrganisms", JSON.stringify(saved));
    alert("Organism saved!");
  } else {
    alert("This organism is already saved.");
  }
}

function displaySaved() {
  const saved = getSaved();
  const list = document.getElementById("savedList");

  const items = organisms.filter(org => saved.includes(org.id));

  if (items.length === 0) {
    list.innerHTML = "<p>You have not saved any organisms yet.</p>";
    return;
  }

  list.innerHTML = items.map(org => `
    <div class="organism-card">
      <h3>${org.name}</h3>
      <button onclick="openProfile('${org.id}')">View profile</button>
      <button onclick="removeSaved('${org.id}')">Remove</button>
    </div>
  `).join("");
}

function removeSaved(id) {
  const saved = getSaved().filter(item => item !== id);
  localStorage.setItem("savedOrganisms", JSON.stringify(saved));
  displaySaved();
}

function populateCompare() {
  ["organismOne", "organismTwo"].forEach(selectId => {
    const select = document.getElementById(selectId);
    const previous = select.value;

    select.innerHTML = organisms.map(org =>
      `<option value="${org.id}">${org.name}</option>`
    ).join("");

    if (organisms.some(org => org.id === previous)) {
      select.value = previous;
    }
  });
}

function compareOrganisms() {
  const first = organisms.find(org =>
    org.id === document.getElementById("organismOne").value
  );

  const second = organisms.find(org =>
    org.id === document.getElementById("organismTwo").value
  );

  const result = document.getElementById("comparisonResult");

  if (first.id === second.id) {
    result.innerHTML = "<p>Please select two different organisms.</p>";
    return;
  }

  const fields = [
    ["Classification", "type"],
    ["Gram reaction", "gram"],
    ["Morphology", "morphology"],
    ["Growth", "growth"],
    ["Biochemical characteristics", "biochemical"],
    ["Habitat", "habitat"],
    ["Medical importance", "medical"],
    ["Identification", "identification"]
  ];

  result.innerHTML = `
    <table>
      <tr>
        <th>Feature</th>
        <th>${first.name}</th>
        <th>${second.name}</th>
      </tr>
      ${fields.map(([label, key]) => `
        <tr>
          <td>${label}</td>
          <td>${first[key]}</td>
          <td>${second[key]}</td>
        </tr>
      `).join("")}
    </table>
  `;
}

populateCompare();
