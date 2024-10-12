function analyserPhrase(phrase) {
    let longueur = 0;   // Compteur de la longueur de la phrase
    let mots = 0;       // Compteur de mots
    let voyelles = 0;   // Compteur de voyelles
    let voyellesListe = "aeiouyAEIOUY";  // Liste des voyelles
    let estDansMot = false; // Vérification si on est dans un mot

    for (let i = 0; i < phrase.length; i++) {
        let char = phrase[i];
        
        // Comptage du nombre de caractères
        longueur++;

        // Comptage des mots
        if (char !== ' ' && char !== '.') {
            if (!estDansMot) {
                mots++;
                estDansMot = true; // Début d'un nouveau mot
            }
        } else {
            estDansMot = false; // Fin du mot
        }

        // Comptage des voyelles
        if (voyellesListe.includes(char)) {
            voyelles++;
        }
        
        // Si le caractère est un point, fin de la phrase
        if (char === '.') {
            break;
        }
    }

    console.log("Longueur de la phrase :", longueur);
    console.log("Nombre de mots :", mots);
    console.log("Nombre de voyelles :", voyelles);
}

// Exemple d'utilisation
let phrase = "Bonjour tout le monde.";
analyserPhrase(phrase);
