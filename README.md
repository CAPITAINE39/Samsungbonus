<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Samsung Bonus Méga</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      text-align: center;
      padding: 40px 20px;
      background: linear-gradient(to right, #ffecd2, #fcb69f);
      color: #2c3e50;
    }
    h1 {
      font-size: 2.5em;
      color: #d35400;
      margin-bottom: 10px;
    }
    p {
      font-size: 1.2em;
      margin: 12px;
    }
    .share-btn, button {
      display: inline-block;
      margin: 20px auto;
      padding: 14px 28px;
      background-color: #e74c3c;
      color: white;
      text-decoration: none;
      font-size: 18px;
      border-radius: 50px;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
      transition: all 0.3s ease-in-out;
      border: none;
      cursor: pointer;
    }
    .share-btn:hover, button:hover {
      background-color: #c0392b;
      transform: scale(1.05);
    }
    #compteur {
      font-size: 1.3em;
      margin-top: 20px;
      color: #16a085;
      font-weight: bold;
    }
    ul.gifts {
      list-style-type: none;
      padding: 0;
    }
    ul.gifts li {
      margin: 12px 0;
      font-size: 1.1em;
      background: #ffffffaa;
      padding: 10px 15px;
      border-radius: 15px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    }
    .testimonial {
      background-color: #ffffffcc;
      padding: 15px;
      border-radius: 15px;
      margin: 10px auto;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
      max-width: 600px;
      text-align: left;
    }
    #auto-msg {
      font-size: 1.2em;
      margin-top: 25px;
      font-weight: bold;
      color: #2c3e50;
      background: #fff8;
      padding: 12px;
      border-radius: 10px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
      display: inline-block;
    }
    input[type="tel"] {
      padding: 12px;
      margin-top: 15px;
      width: 250px;
      border-radius: 8px;
      border: 1px solid #ccc;
      font-size: 16px;
    }
  </style>
</head>
<body>

  <!-- Musique de fond -->
  <audio id="bg-music" autoplay loop>
    <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mp3">
  </audio>

  <!-- Son de réussite -->
  <audio id="success-sound">
    <source src="https://assets.mixkit.co/sfx/preview/mixkit-achievement-bell-600.mp3" type="audio/mp3">
  </audio>

  <h1>Débloque tes Mégas avec Samsung Bonus</h1>
  <p>Partage à <strong>15 amis</strong> et <strong>5 groupes</strong> pour débloquer tes Mégas.</p>
  <p>Tu les recevras dans <strong>quelques minutes</strong>.</p>
  <p><strong>100 Mo par ami invité</strong></p>

  <a class="share-btn" href="https://wa.me/?text=Gagne%20des%20Mégas%20gratuits%20ici%20:%20https://tonsite.com"
     onclick="incrementerCompteur();">Partager sur WhatsApp</a>

  <div id="compteur">Tu as partagé à 0 amis. Encore 15 !</div>

  <form id="form-telephone">
    <p><label for="telephone">Entrez votre numéro pour recevoir vos Mégas :</label></p>
    <input type="tel" id="telephone" name="telephone" placeholder="ex: 0991234567" required>
  </form>
  <button onclick="playSuccess()">J'ai partagé</button>

  <h2>Cadeaux Bonus</h2>
  <ul class="gifts">
    <li>+500 Mo de bonus après 10 partages</li>
    <li>+1 Go si tu partages à 10 groupes</li>
    <li>Tirage au sort : un smartphone à gagner</li>
  </ul>

  <h2>Avis des utilisateurs</h2>
  <div class="testimonial"><strong>Fatou D.</strong> : Merci beaucoup ! J’ai reçu 1 Go après avoir partagé à mes amis !</div>
  <div class="testimonial"><strong>Yannick T.</strong> : Je croyais que c’était faux, mais j’ai vraiment gagné un bonus. Bravo !</div>
  <div class="testimonial"><strong>Aline M.</strong> : Continuez comme ça ! Grâce à vous j’ai eu mes Mégas, c’est trop cool !</div>

  <h2>Témoignages en direct</h2>
  <div id="auto-msg"></div>

  <p style="margin-top: 30px;">Après avoir partagé, ferme la page. Tes Mégas arrivent bientôt !</p>

  <script>
    let partages = 0;
    function incrementerCompteur() {
      partages++;
      let restant = 15 - partages;
      if (restant > 0) {
        document.getElementById("compteur").innerText =
          `Tu as partagé à ${partages} amis. Encore ${restant} pour débloquer tes Mégas !`;
      } else {
        document.getElementById("compteur").innerText =
          `Bravo ! Tu as débloqué tes Mégas !`;
        document.getElementById("success-sound").play();
      }
    }

    function playSuccess() {
      document.getElementById("success-sound").play();
      alert("Merci pour ton partage ! Tu recevras tes Méga bientôt.");
    }

    const messages = [
      "À chaque fois je réussis mes Méga grâce à ce site.",
      "Encore une fois, j’ai reçu mes Mo, c’est incroyable !",
      "Merci à ce site, je ne reste jamais sans connexion.",
      "Ce site fonctionne vraiment, je le recommande à tous.",
      "J’ai eu mes Méga comme promis, trop fort !",
      "Franchement, ça marche à chaque fois ! Merci !"
    ];
    let index = 0;
    function afficherMessage() {
      const el = document.getElementById("auto-msg");
      el.textContent = messages[index];
      index = (index + 1) % messages.length;
    }
    setInterval(afficherMessage, 4000);
    afficherMessage();
  </script>

</body>
</html>
