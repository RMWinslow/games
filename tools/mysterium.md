---
title: Mysterium Park Layout Generator
parent: Tools
---

# Mysterium Park Layout Generator

<!-- <style>
    .mysterium tr {width: 200px; height:20px;}
    /* .mysterium table {border-width: 1px;} */

</style> -->

<div id="mysteriumTable" class="mysterium">
    <!-- The table will be populated by JavaScript -->
</div>


This generates a random 3x3 layout for the ghost. 
Purple here represents the pink player, since there isn't a pink circle emoji.
Refresh the page to generate a new layout.

Since base Mysterium has 6 colors, while Mysterium Park has 5, 
just designate one color ahead of time to give a free redo.






<script>
    //draw a random item from a list.
    function rD(array){return array[Math.floor(Math.random()*array.length)];} 

    //Fisher–Yates shuffle
    function shuffleArray(array) {
        for (let i = array.length - 1; i > 0; i--) {
            j = Math.floor(Math.random() * (i + 1));
            [array[i], array[j]] = [array[j], array[i]];
        }
        return array;
    }

    const markers = ["⚫","⚪","🔴","🟡","🟣","🔵"," "," "," "];
    shuffledMarkers = shuffleArray(markers);
    console.log(shuffledMarkers);


    // populate table
    table = document.createElement("table");
    for (let i = 0; i < 3; i++) {
        row = document.createElement("tr");
        for (let j = 0; j < 3; j++) {
            cell = document.createElement("td");
            cell.textContent = markers[i * 3 + j];
            row.appendChild(cell);
        }
        table.appendChild(row);
    }
    document.getElementById("mysteriumTable").appendChild(table);

</script>
