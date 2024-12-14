Karussell Beispiel

Ein einfaches Karussell-Beispiel in HTML, CSS und JavaScript, das Bilder horizontal scrollt. Das Projekt eignet sich als Grundlage für interaktive Bildgalerien oder Banner auf einer Website.

Projektübersicht

Das Karussell zeigt eine Reihe von Bildern, die mithilfe von Buttons durchblättert werden können. Es verwendet grundlegende Frontend-Technologien wie:

HTML: Markup-Struktur des Karussells.

CSS: Styling des Karussells und der Buttons.

JavaScript: Funktionalität zur Navigation durch die Bilder.

Funktionen

Horizontales Scrollen zwischen Bildern.

Vor- und Zurück-Navigation über Buttons.

Sanfter Übergang zwischen Bildern.

Verzeichnisstruktur

project-folder/
|-- index.html
|-- style.css       (optional, falls CSS ausgelagert wird)
|-- script.js       (optional, falls JavaScript ausgelagert wird)
|-- image1.png
|-- image2.png
|-- image3.jpg

Installation

Klone das Repository oder lade die Dateien herunter.

Stelle sicher, dass sich alle Bilddateien (z. B. image1.png, image2.png, image3.jpg) im gleichen Verzeichnis wie die HTML-Datei befinden.

Öffne die Datei index.html in einem Browser.

Nutzung

Klicke auf die Pfeil-Buttons (← und →), um zwischen den Bildern zu navigieren.

Die Bilder scrollen horizontal mit einem sanften Übergang.

Anpassung

Bilder: Ersetze image1.png, image2.png, image3.jpg mit deinen eigenen Bildern. Achte darauf, dass sie eine Breite von 300px und eine Höhe von 200px haben oder passe die CSS-Einstellungen entsprechend an.

Größe des Karussells:

Passe die Breite und Höhe der .carousel und .carousel img Klassen in der CSS-Datei an.

Animation:

Ändere die Dauer der Animation, indem du den Wert der CSS-Eigenschaft transition im .carousel-images-Block anpasst.

Beispiel-Code

HTML

<div class="carousel">
    <div class="carousel-images">
        <img src="image1.png" alt="Bild 1">
        <img src="image2.png" alt="Bild 2">
        <img src="image3.jpg" alt="Bild 3">
    </div>
    <div class="carousel-buttons">
        <button id="prev">←</button>
        <button id="next">→</button>
    </div>
</div>

CSS

.carousel {
    width: 300px;
    overflow: hidden;
    position: absolute;
    margin-left: 50%;
}
.carousel-images {
    display: flex;
    transition: transform 0.5s ease;
}
.carousel img {
    width: 300px;
    height: 200px;
}
.carousel-buttons {
    position: absolute;
    top: 50%;
    width: 100%;
    display: flex;
    justify-content: space-between;
}

JavaScript

const prevButton = document.getElementById('prev');
const nextButton = document.getElementById('next');
const carouselImages = document.querySelector('.carousel-images');
let index = 0;

prevButton.addEventListener('click', () => {
    index = (index > 0) ? index - 1 : carouselImages.children.length - 1;
    carouselImages.style.transform = `translateX(${-index * 300}px)`;
});

nextButton.addEventListener('click', () => {
    index = (index < carouselImages.children.length - 1) ? index + 1 : 0;
    carouselImages.style.transform = `translateX(${-index * 300}px)`;
});

Anforderungen

Ein moderner Browser (Chrome, Firefox, Safari, Edge).

Lizenz

Dieses Projekt steht unter der MIT-Lizenz.