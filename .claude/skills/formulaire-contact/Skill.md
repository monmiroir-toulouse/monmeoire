# Skill : Ajouter un Formulaire de Contact

## Objectif
Ajouter une section formulaire de contact dans le site "Mon Miroir" via Formspree (gratuit, sans serveur).

## Contexte du projet
- Site : HTML/CSS simple (index.html)
- Couleurs : Bleu #1A3A5C, Or #C9A84C, Blanc #F9F6F0

## Étapes

### 1. Créer un compte Formspree
- Aller sur https://formspree.io
- Créer un compte avec mohamedanaya@hotmail.fr
- Créer un formulaire et copier l'ID (format: XXXXXXXX)

### 2. HTML à ajouter
<section id="contact" style="background:#1A3A5C; padding:80px 20px;">
  <div style="max-width:600px; margin:0 auto; text-align:center;">
    <h2 style="color:#C9A84C;">Nous contacter</h2>
    <form action="https://formspree.io/f/FORM_ID" method="POST" class="contact-form">
      <input type="text" name="nom" placeholder="Votre nom" required>
      <input type="email" name="email" placeholder="Votre email" required>
      <textarea name="message" placeholder="Votre message..." rows="5" required></textarea>
      <button type="submit">Envoyer</button>
    </form>
  </div>
</section>

### 3. CSS à ajouter
.contact-form input, .contact-form textarea { width:100%; padding:14px; margin-bottom:16px; border:1px solid #C9A84C; border-radius:8px; background:rgba(255,255,255,0.05); color:#F9F6F0; font-size:16px; box-sizing:border-box; }
.contact-form button { background:#C9A84C; color:#1A3A5C; border:none; padding:14px 40px; border-radius:30px; font-size:16px; font-weight:bold; cursor:pointer; }

### 4. Lien navigation
Ajouter dans le menu : <a href="#contact">Contact</a>

## Résultat
Les messages arrivent directement sur mohamedanaya@hotmail.fr
