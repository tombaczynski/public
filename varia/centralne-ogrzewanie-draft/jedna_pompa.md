---
layout: plik
title: "Mała instalacja z jedną pompą"
---

# Mała instalacja z jedną pompą
```mermaid
flowchart TD

%% Kocioł 
ATV([Zawór ATV / ochrona powrotu]) --> P([Pompa]) --> K[Kocioł na ekogroszek] --- R1 --> V3([Zawór trójdrogowy przełączający]) --> CWU([Wężownica zasobnika CWU]) --- R2

R1 --> ATV


%% GAŁĄŹ CWU

%% GAŁĄŹ CO
V3 --> CO([Instalacja CO / grzejniki]) --- R2

R2 --> ATV

%% classDef wezly fill:transparent,stroke:transparent,stroke-width:1px;

%% class ATV wezly

classDef point fill:none,stroke:none,width:0px,height:0px,color:#00000000;

class R1,R2 point

```
<!-- Skrypt dopasowujący strukturę HTML wygenerowaną przez GitHub Pages (Jekyll) do wymogów biblioteki Mermaid -->
<script type="module">
import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
document.addEventListener("DOMContentLoaded", function() {
// 1. Znajdź wszystkie bloki kodu oznaczone klasą "language-mermaid" generowane przez Jekyll
const codeBlocks = document.querySelectorAll("pre code.language-mermaid, pre.language-mermaid");
codeBlocks.forEach((block) => {
// Pobierz surowy kod schematu
const code = block.textContent;
// Utwórz nowy element div, który Mermaid potrafi bezpośrednio zinterpretować
const mermaidDiv = document.createElement("div");
mermaidDiv.className = "mermaid";
mermaidDiv.textContent = code;
// Zastąp stary tag pre/code nowo utworzonym kontenerem div
const parent = block.closest("pre");
if (parent) {
parent.parentNode.replaceChild(mermaidDiv, parent);
} else {
block.parentNode.replaceChild(mermaidDiv, block);
}
});
// 2. Zainicjalizuj i wyrenderuj wykryte schematy
mermaid.initialize({
startOnLoad: true,
theme: 'default'
});
});
</script>
<style>
/* Dodatkowa ochrona przed brzydkim stylowaniem tła w niektórych motywach GitHub Pages */
.mermaid {
background: transparent !important;
display: flex;
justify-content: center;
margin: 1.5rem 0;
}
</style>
