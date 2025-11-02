<script>
const user = "FOSSBOSS";
const repo = "Esoterica";
const path = "svgs"; // folder name with your SVGs

async function showSVGs() {
  const url = `https://api.github.com/repos/${user}/${repo}/contents/${path}`;
  const res = await fetch(url);
  const files = await res.json();
  const container = document.getElementById("gallery");

  files
    .filter(f => f.name.endsWith(".svg"))
    .forEach(f => {
      const img = document.createElement("img");
      img.src = f.download_url;
      container.appendChild(img);
    });
}

showSVGs();
</script>

# Esoterica
Esoteric symbols in vector image format, from historical lore and mythologies.
Symbols from Arsenic to Zeus, in inkscape svg format, measured in millimeters,    
with zero margin, red stroke, and transparent fill these images should be perfect 
for laser cutting, or whatever art project you want.
