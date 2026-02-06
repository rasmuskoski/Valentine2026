// 1. Pidetään kirjaa muuttujilla
let koko = 20; // Aloituskoko YES-napille
let klikkaukset = 0; // Laskuri, montako kertaa NO on painettu

// 2. Lista gifeistä (voit vaihtaa nämä linkit omiisi)
// Ensimmäinen on se, joka näkyy kun NO-nappia painetaan kerran, jne.
const gifit = [
  "https://media.giphy.com/media/v1.Y2lkPWVjZjA1ZTQ3eXQ5dnY3dHQ4eWZqaGV5eDVqNW9vMTByaHczdDBycjhyNjhlbDQ4YyZlcD12MV9naWZzX3NlYXJjaCZjdD1n/UgotmkigDhPq8R571x/giphy.gif", // Surullinen 1
  "https://media.giphy.com/media/v1.Y2lkPWVjZjA1ZTQ3NGI1Ymp4ZmthZWFtNzgycW5zMGF6YWM4dXNvbjVsM2NldjFieDRvYSZlcD12MV9naWZzX3NlYXJjaCZjdD1n/0RDp9YjIqIGNQKX3Zk/giphy.gif", // Itku 2
  "https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExYTA4cmd0ZW00dGM1ZnE0dmljbDFrZW9oNjFvZzRwaWxiOHVvMGVxbiZlcD12MV9naWZzX3NlYXJjaCZjdD1n/pMCghhDOyRcAMPmtCS/giphy.gif", // Epätoivo 3
  "https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExcWVjZjZoajlrbXAycWQ2dGJzNnR5YjEyb2xwOXZ2YWV0N2tzZ2RrZCZlcD12MV9naWZzX3NlYXJjaCZjdD1n/OHRF8LZis06OiPDJby/giphy.gif", // Murtunut 4
  "https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExcTI4dTZ2NGU2aWZweG0zc2tzbWZ3cmhxeWs4ZWd1eTJoZGJxMWc5aCZlcD12MV9naWZzX3NlYXJjaCZjdD1n/nLGZJL5TGaquA/giphy.gif"  // Viimeinen anelu 5
];

function vastausEi() {
  // A. Kasvatetaan aina YES-nappia
  koko = koko + 30;
  document.getElementById('yesBtn').style.fontSize = koko + "px";

  // B. Tarkistetaan, onko meillä vielä jäljellä uusia gifejä listassa
  if (klikkaukset < gifit.length) {
    // Vaihdetaan kuva listasta laskurin perusteella
    document.getElementById('main-gif').src = gifit[klikkaukset];
    
    // Kasvatetaan laskuria yhdellä seuraavaa kertaa varten
    klikkaukset = klikkaukset + 1;
    
    // Vaihdetaan myös tekstiä dramatiikan lisäämiseksi
    const tekstit = ["Are you sure?", "Really?", "Think again! Kitty(Rasmus) will be sad", "Last chance! Kitty mad", "Pretty pleaseee? Kitty desperate"];
    document.querySelector('h1').innerText = tekstit[klikkaukset - 1];
  }
  // Jos klikkauksia on yli 5, kuva ei enää vaihdu, mutta YES-nappi jatkaa kasvuaan
}

function vastausKyllä() {
  document.querySelector('h1').innerText = "Wuhuu! ❤️ See you on 14th!";
  document.getElementById('main-gif').src = "https://media1.giphy.com/media/v1.Y2lkPTc5MGI3NjExNWZoeGZwOXNrdW51ZzZtaWhsYXVrZnZpdm05bHN4ZDIxZXhqNWxtcSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/ytu2GUYbvhz7zShGwS/giphy.gif";
  document.getElementById('noBtn').style.display = "none";
}
