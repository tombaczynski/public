---
layout: plik
---

[↑ W górę](./index.md)

# Przykładowa stacja

```mermaid
%%{init: {'flowchart': { 'useMaxWidth': false, 'defaultRenderer': 'dagre', 'curve': 'basis'}}}%%
flowchart LR

    subgraph biala["Biała"]
        direction LR
        bi_du_2
        bi_du_1
    end

    subgraph du1["Dubno - Du1 "]
        direction LR
        rozjazd7["Rozjazd 7"]
        rozjazd1["Rojzazd 1"]
        rozjazd6["Rozjazd 6"]
        rozjazd2["Rozjazd 2"]
        rozjazd3["Rozjazd 3"]
        rozjazd4["Rozjazd 4"]
        rozjazd5["Rozjazd 5"]
        wykolejnica1["Wykolejnica Wk1"]
    end

    subgraph du["Dubno - Du"]
        direction LR
        rozjazd100["Rozjazd 100"]
        rozjazd19["Rozjazd 19"]
        rozjazd18["Rozjazd 18"]
        rozjazd17["Rozjazd 17"]
        rozjazd16["Rozjazd 16"]
        rozjazd15["Rozjazd 15"]
        rozjazd14["Rozjazd 14"]
        rozjazd13["Rozjazd 13"]
        rozjazd12["Rozjazd 12"]
        rozjazd11["Rozjazd 11"]
        wykolejnica11["Wykolejnica Wk11"]
        zak_trzeciego
    end

    subgraph krowica["Krowica"]
        direction LR
        kr_du["Krowica"]
    end

    subgraph osowiec["Osowiec"]
        direction LR
        Os_Du_1
        Os_Du_2
    end


du1 ~~~ du
du ~~~ krowica

bi_du_2 ===|"Tor nr 2"| rozjazd1
rozjazd1     === rozjazd6
rozjazd6     === rozjazd7
bi_du_1 ===|"Tor nr 1"| rozjazd2
rozjazd2     === rozjazd3
rozjazd5      -------|"Tor trzeci"| rozjazd11
rozjazd1     --- rozjazd2
rozjazd4     --- rozjazd6
rozjazd3     === rozjazd4
rozjazd3     --- rozjazd5
rozjazd5     --- wykolejnica1

rozjazd14     --- rozjazd19
rozjazd11     --- rozjazd12
rozjazd12     --- rozjazd13
rozjazd12     --- zak_trzeciego
rozjazd4      ===|"Tor pierwszy"| rozjazd13
rozjazd7      -------|"Tor czwarty" | rozjazd14
rozjazd14     --- rozjazd15
rozjazd7      ===|"Tor drugi"   | rozjazd15
rozjazd13     === rozjazd16
rozjazd16     --- rozjazd17
rozjazd17     === rozjazd18
rozjazd18     --- rozjazd19
rozjazd19     --- kr_du
rozjazd15     === rozjazd17
wykolejnica11 --- rozjazd11
wykolejnica1 ---|"Tor piąty"| wykolejnica11
rozjazd16     ---- Os_Du_1
rozjazd18     ---- Os_Du_2




classDef transparent1 fill:none,stroke:none
class przewiert_0_1,przewiert_1_1,przewiert_1_2,TP-Link_not_conntected transparent1

classDef non_apparent fill:none,stroke:none,width:0px,height:0px
class pierscien_czarny,szary_kabel,from_router,swiatlowod_15m,pierscien_zolty,jasno_siwy,pierscien_czarny_p,FTTH_p non_apparent

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
useMaxWidth: false,
theme: 'default'
});
});
</script>
<style>
/* Dodatkowa ochrona przed brzydkim stylowaniem tła w niektórych motywach GitHub Pages */
.mermaid {
background: transparent !important;
display: block; 
width: max-content; 
overflow-x: auto;
margin: 1.5rem 0;
}
</style>