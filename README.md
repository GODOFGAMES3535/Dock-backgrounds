# Dock-backgrounds
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Docks Background — 1,002,500 Gradients</title>
  <style>
    :root {
      --mx: 50%;
      --my: 50%;
    }

    * {
      box-sizing: border-box;
    }

    body {
      position: relative;
      isolation: isolate;
      overflow-x: hidden;
      margin: 0;
      padding: 28px;
      color: #f4f4f5;
      font: 16px/1.5 system-ui, sans-serif;
      background: #17171c;
    }

    body::before {
      content: "";
      position: fixed;
      inset: 0;
      z-index: -1;
      background:
        radial-gradient(circle at 15% 25%, #ff38a8 0, transparent 32%),
        radial-gradient(circle at 82% 18%, #3b82ff 0, transparent 36%),
        radial-gradient(circle at 55% 82%, #27edbd 0, transparent 38%),
        linear-gradient(125deg, #8a4fff, #ff4f81, #ffb84d);
    }

    body::after {
      content: "";
      position: fixed;
      inset: 0;
      z-index: 10;
      pointer-events: none;
      opacity: .35;
      background: radial-gradient(
        220px circle at var(--mx) var(--my),
        rgba(255, 255, 255, .28),
        transparent 70%
      );
    }

    h1 { margin-top: 0; }
    p { color: #e8e8ee; }

    #controls {
      display: flex;
      align-items: center;
      flex-wrap: wrap;
      gap: 10px;
      margin-bottom: 12px;
    }

    input[type="number"],
    input[type="search"],
    select {
      min-height: 36px;
      border: 1px solid #555560;
      border-radius: 7px;
      padding: 7px 9px;
      background: rgba(34, 34, 41, .9);
      color: white;
    }

    input[type="number"] { width: 130px; }
    input[type="search"] { width: min(250px, 100%); }

    #favoriteFilter {
      display: inline-flex;
      align-items: center;
      gap: 6px;
    }

    main {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(170px, 1fr));
      gap: 12px;
    }

    article {
      overflow: hidden;
      border: 1px solid rgba(255,255,255,.16);
      border-radius: 10px;
      background: rgba(20,20,28,.94);
      contain: content;
      content-visibility: auto;
      contain-intrinsic-size: auto 190px;
      animation: card-reveal .35s ease both;
      transition: transform .18s ease, border-color .18s ease, box-shadow .18s ease;
    }

    article:hover {
      transform: translateY(-4px);
      border-color: rgba(255,255,255,.45);
      box-shadow: 0 12px 30px rgba(0,0,0,.35), 0 0 18px rgba(157,118,255,.25);
    }

    @keyframes card-reveal {
      from { opacity: 0; transform: translateY(8px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .preview {
      display: block;
      width: 100%;
      aspect-ratio: 16 / 10;
      border: 0;
      background: var(--gradient);
      cursor: zoom-in;
    }

    .details {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 6px;
      padding: 8px;
    }

    h2 {
      margin: 0;
      overflow: hidden;
      font-size: 12px;
      white-space: nowrap;
      text-overflow: ellipsis;
    }

    .actions {
      display: flex;
      flex-wrap: wrap;
      justify-content: flex-end;
      gap: 5px;
      padding: 0 8px 8px;
    }

    button {
      border: 0;
      border-radius: 6px;
      padding: 7px 9px;
      background: #fff;
      color: #17171c;
      font-size: 12px;
      font-weight: 650;
      cursor: pointer;
    }

    button:hover {
      background: #dedee5;
    }

    button:disabled {
      cursor: default;
      opacity: .7;
    }

    .favorite-button[aria-pressed="true"] {
      background: #ffd5e6;
      color: #a0004c;
    }

    #progress {
      margin: 8px 0 12px;
      color: #e8e8ee;
      font-size: 14px;
    }

    #loadMore {
      display: block;
      margin: 20px auto;
      padding: 10px 16px;
    }

    dialog {
      width: min(95vw, 1100px);
      max-width: none;
      padding: 12px;
      border: 1px solid rgba(255,255,255,.25);
      border-radius: 12px;
      background: #191920;
      color: white;
    }

    dialog::backdrop {
      background: rgba(0,0,0,.82);
      backdrop-filter: blur(4px);
    }

    .dialog-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 12px;
      padding-bottom: 10px;
    }

    #largePreview {
      min-height: 55vh;
      border-radius: 8px;
      background: var(--gradient);
    }

    @media (max-width: 600px) {
      body { padding: 18px; }
      main { grid-template-columns: repeat(auto-fill, minmax(145px, 1fr)); }
    }

    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after {
        scroll-behavior: auto !important;
        animation-duration: .01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: .01ms !important;
      }
    }
  </style>
</head>
<body>
  <h1>1,002,500 Gradient Backgrounds</h1>
  <p>Scroll to load more gradients. Search and favorites filter the gradients loaded so far.</p>

  <div id="controls">
    <input id="jump" type="number" min="1" max="1002500" value="1"
           aria-label="Gradient number">
    <button id="jumpButton" type="button">Jump</button>
    <button id="randomButton" type="button">Random gradient</button>
    <input id="search" type="search" placeholder="Search loaded gradients"
           aria-label="Search loaded gradients">
    <label id="favoriteFilter">
      <input id="favoritesOnly" type="checkbox">
      Favorites only
    </label>
    <label for="downloadSize">PNG size:</label>
    <select id="downloadSize">
      <option value="1280x720">1280 × 720</option>
      <option value="1920x1080" selected>1920 × 1080</option>
      <option value="3840x2160">3840 × 2160</option>
    </select>
  </div>

  <div id="progress" aria-live="polite"></div>
  <main id="gallery"></main>
  <button id="loadMore" type="button">Load more gradients</button>

  <dialog id="previewDialog">
    <div class="dialog-header">
      <strong id="previewTitle"></strong>
      <button id="closePreview" type="button">Close</button>
    </div>
    <div id="largePreview"></div>
  </dialog>

  <script>
    const colorNames = [
      "Ruby", "Crimson", "Scarlet", "Cherry", "Garnet",
      "Rose", "Pink", "Coral", "Peach", "Orange",
      "Amber", "Gold", "Yellow", "Lemon", "Lime",
      "Green", "Emerald", "Mint", "Teal", "Aqua",
      "Cyan", "Sky", "Blue", "Sapphire", "Azure",
      "Indigo", "Navy", "Purple", "Violet", "Lavender",
      "Lilac", "Magenta", "Fuchsia", "Berry", "Plum"
    ];

    const themes = [
      "Aurora", "Sunset", "Ocean", "Forest", "Candy",
      "Galaxy", "Lagoon", "Meadow", "Bloom", "Mist"
    ];

    const total = 1002500;
    const pageSize = 50;
    const favoriteStorageKey = "gradient-gallery-favorites";

    let loadedUntil = 0;
    let loadedStart = 0;
    let observer;

    const gallery = document.getElementById("gallery");
    const jumpInput = document.getElementById("jump");
    const searchInput = document.getElementById("search");
    const favoritesOnlyInput = document.getElementById("favoritesOnly");
    const progress = document.getElementById("progress");
    const loadMoreButton = document.getElementById("loadMore");
    const previewDialog = document.getElementById("previewDialog");
    const largePreview = document.getElementById("largePreview");
    const previewTitle = document.getElementById("previewTitle");

    let favorites = loadFavorites();

    function loadFavorites() {
      try {
        return new Set(JSON.parse(localStorage.getItem(favoriteStorageKey) || "[]"));
      } catch {
        return new Set();
      }
    }

    function saveFavorites() {
      try {
        localStorage.setItem(favoriteStorageKey, JSON.stringify([...favorites]));
      } catch {
        progress.textContent = "Favorites could not be saved in this browser.";
      }
    }

    let pointerFrame = false;
    window.addEventListener("pointermove", (event) => {
      if (pointerFrame) return;
      pointerFrame = true;

      requestAnimationFrame(() => {
        document.documentElement.style.setProperty("--mx", `${event.clientX}px`);
        document.documentElement.style.setProperty("--my", `${event.clientY}px`);
        pointerFrame = false;
      });
    }, { passive: true });

    function getGradient(index) {
      const hue = (index * 137.508) % 360;
      const colors = [
        `hsl(${Math.round(hue)} 85% 55%)`,
        `hsl(${Math.round((hue + 40) % 360)} 82% 62%)`,
        `hsl(${Math.round((hue + 80) % 360)} 78% 68%)`
      ];

      const name = index === 153
        ? "Blue Forest"
        : `${colorNames[index % colorNames.length]} ${themes[index % themes.length]} ${String(index + 1).padStart(7, "0")}`;

      return { name, colors };
    }

    function applyFilters() {
      const query = searchInput.value.trim().toLowerCase();
      const favoritesOnly = favoritesOnlyInput.checked;

      for (const card of gallery.children) {
        const cardName = card.dataset.name.toLowerCase();
        const isFavorite = favorites.has(card.dataset.gradientNumber);
        const matchesSearch = !query || cardName.includes(query);
        card.hidden = !(matchesSearch && (!favoritesOnly || isFavorite));
      }

      updateProgress();
      updateObserver();
    }

    function createCard(index) {
      const gradientNumber = String(index + 1);
      const { name, colors } = getGradient(index);
      const cssGradient = `linear-gradient(125deg, ${colors.join(", ")})`;

      const card = document.createElement("article");
      const preview = document.createElement("button");
      const details = document.createElement("div");
      const title = document.createElement("h2");
      const actions = document.createElement("div");
      const favoriteButton = document.createElement("button");
      const copyButton = document.createElement("button");
      const downloadButton = document.createElement("button");

      card.dataset.gradientNumber = gradientNumber;
      card.dataset.name = `${gradientNumber} ${name}`;

      preview.type = "button";
      preview.className = "preview";
      preview.style.setProperty("--gradient", cssGradient);
      preview.setAttribute("aria-label", `Preview ${name}`);
      preview.addEventListener("click", () => openPreview(name, cssGradient));

      details.className = "details";
      title.textContent = `${gradientNumber.padStart(7, "0")}. ${name}`;
      title.title = name;
      details.appendChild(title);

      actions.className = "actions";

      favoriteButton.type = "button";
      favoriteButton.className = "favorite-button";
      favoriteButton.textContent = favorites.has(gradientNumber) ? "♥ Saved" : "♡ Favorite";
      favoriteButton.setAttribute("aria-pressed", String(favorites.has(gradientNumber)));
      favoriteButton.addEventListener("click", () => {
        if (favorites.has(gradientNumber)) {
          favorites.delete(gradientNumber);
        } else {
          favorites.add(gradientNumber);
        }

        saveFavorites();
        favoriteButton.textContent = favorites.has(gradientNumber) ? "♥ Saved" : "♡ Favorite";
        favoriteButton.setAttribute("aria-pressed", String(favorites.has(gradientNumber)));
        applyFilters();
      });

      copyButton.type = "button";
      copyButton.textContent = "Copy CSS";
      copyButton.addEventListener("click", async () => {
        const css = `background: ${cssGradient};`;

        try {
          await navigator.clipboard.writeText(css);
        } catch {
          const temporaryInput = document.createElement("textarea");
          temporaryInput.value = css;
          temporaryInput.style.position = "fixed";
          temporaryInput.style.opacity = "0";
          document.body.appendChild(temporaryInput);
          temporaryInput.select();
          document.execCommand("copy");
          temporaryInput.remove();
        }

        copyButton.textContent = "Copied!";
        setTimeout(() => { copyButton.textContent = "Copy CSS"; }, 1200);
      });

      downloadButton.type = "button";
      downloadButton.textContent = "PNG";
      downloadButton.addEventListener("click", () => download(name, colors));

      actions.append(favoriteButton, copyButton, downloadButton);
      card.append(preview, details, actions);

      return card;
    }

    function updateProgress() {
      const visibleCount = [...gallery.children].filter((card) => !card.hidden).length;
      const range = loadedUntil > loadedStart
        ? `#${loadedStart + 1}–#${loadedUntil}`
        : "none";

      progress.textContent =
        `Loaded ${gallery.children.length} gradients (${range}); ${visibleCount} match the current filters.`;
    }

    function updateObserver() {
      if (!observer) return;

      if (searchInput.value.trim() || favoritesOnlyInput.checked || loadedUntil >= total) {
        observer.unobserve(loadMoreButton);
      } else {
        observer.observe(loadMoreButton);
      }
    }

    function appendBatch() {
      if (loadedUntil >= total) return;

      const end = Math.min(loadedUntil + pageSize, total);
      const fragment = document.createDocumentFragment();

      for (let index = loadedUntil; index < end; index++) {
        fragment.appendChild(createCard(index));
      }

      gallery.appendChild(fragment);
      loadedUntil = end;

      applyFilters();

      if (loadedUntil >= total) {
        loadMoreButton.textContent = "All gradients loaded";
        loadMoreButton.disabled = true;
        if (observer) observer.disconnect();
      }
    }

    function jumpToGradient(number = Number(jumpInput.value)) {
      const gradientNumber = Math.max(1, Math.min(total, Number(number) || 1));
      const batchStart = Math.floor((gradientNumber - 1) / pageSize) * pageSize;

      searchInput.value = "";
      favoritesOnlyInput.checked = false;
      gallery.replaceChildren();
      loadedStart = batchStart;
      loadedUntil = batchStart;
      loadMoreButton.disabled = false;
      loadMoreButton.textContent = "Load more gradients";

      appendBatch();
      jumpInput.value = gradientNumber;

      requestAnimationFrame(() => {
        gallery.querySelector(
          `[data-gradient-number="${gradientNumber}"]`
        )?.scrollIntoView({ behavior: "smooth", block: "center" });
      });
    }

    function openPreview(name, cssGradient) {
      previewTitle.textContent = name;
      largePreview.style.setProperty("--gradient", cssGradient);

      if (typeof previewDialog.showModal === "function") {
        previewDialog.showModal();
      }
    }

    document.getElementById("closePreview").addEventListener("click", () => {
      previewDialog.close();
    });

    previewDialog.addEventListener("click", (event) => {
      if (event.target === previewDialog) previewDialog.close();
    });

    document.getElementById("jumpButton").addEventListener("click", () => {
      jumpToGradient();
    });

    jumpInput.addEventListener("keydown", (event) => {
      if (event.key === "Enter") jumpToGradient();
    });

    document.getElementById("randomButton").addEventListener("click", () => {
      jumpToGradient(Math.floor(Math.random() * total) + 1);
    });

    searchInput.addEventListener("input", applyFilters);
    favoritesOnlyInput.addEventListener("change", applyFilters);
    loadMoreButton.addEventListener("click", appendBatch);

    if ("IntersectionObserver" in window) {
      observer = new IntersectionObserver((entries) => {
        if (entries.some((entry) => entry.isIntersecting)) appendBatch();
      }, { rootMargin: "600px" });
    }

    function download(name, colors) {
      const [width, height] = document.getElementById("downloadSize")
        .value.split("x").map(Number);

      const canvas = document.createElement("canvas");
      canvas.width = width;
      canvas.height = height;

      const context = canvas.getContext("2d");
      const gradient = context.createLinearGradient(0, height, width, 0);

      colors.forEach((color, index) => {
        gradient.addColorStop(index / (colors.length - 1), color);
      });

      context.fillStyle = gradient;
      context.fillRect(0, 0, width, height);

      const link = document.createElement("a");
      link.download = `gradient-${name.toLowerCase().replaceAll(" ", "-")}.png`;
      link.href = canvas.toDataURL("image/png");
      link.click();
    }

    appendBatch();
  </script>
</body>
</html>