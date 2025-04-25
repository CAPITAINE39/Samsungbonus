<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Partage pour recevoir</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      text-align: center;
      padding: 50px;
      background: linear-gradient(to right, #ffecd2, #fcb69f);
      color: #2c3e50;
    }
    h1 {
      font-size: 2.8em;
      color: #d35400;
      margin-bottom: 10px;
    }
    p {
      font-size: 1.2em;
      margin: 12px;
    }
    .share-btn {
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
    }
    .share-btn:hover {
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
      margin: 10px 0;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
      text-align: left;
      max-width: 600px;
      margin-left: auto;
      margin-right: auto;
    }
  </style>
</head>
<body>

  <h1>Débloque tes Mégas !</h1>
  <p>Partage à <strong>15 amis</strong> et <strong>5 groupes</strong> pour débloquer tes Mégas.</p>
  <p>Tu les recevras dans <strong>quelques minutes</strong>.</p>
  <p><strong>100 Mo par ami invité</strong></p>

  <a class="share-btn" href="https://wa.me/?text=Gagne%20des%20Mégas%20gratuits%20ici%20:%20https://tonsite.com"
     onclick="incrementerCompteur();">Partager sur WhatsApp</a>

  <div id="compteur">Tu as partagé à 0 amis. Encore 15 !</div>

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

  <p>Après avoir partagé, ferme la page. Tes Mégas arrivent bientôt !</p>

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
      }
    }
  </script>

</body>
</html>
