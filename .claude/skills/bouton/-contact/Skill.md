​vous​
# Skill : Ajouter un Bouton de Contact (Email + WhatsApp)

## Objectif
Ajouter un bouton flottant sur le site "Mon Miroir" (HTML/CSS pur) permettant aux visiteurs de contacter par Email ET par WhatsApp.

## Contexte du projet
- Site : HTML/CSS simple (index.html)
- Couleurs : Bleu #1A3A5C, Or #C9A84C, Blanc #F9F6F0

## Instructions pour Claude Code

### Bouton flottant (coin bas-droite)
Ajouter juste avant </body> :
- Au clic, affiche 2 options :
  - Email → mailto:mohamedanaya@hotmail.fr
  - WhatsApp → https://wa.me/33667018342
- Style : fond or (#C9A84C), icône blanche, ombre portée

### CSS à ajouter
.contact-fab { position:fixed; bottom:30px; right:30px; z-index:9999; }
.contact-fab-btn { background:#C9A84C; color:white; border:none; border-radius:50%; width:60px; height:60px; font-size:24px; cursor:pointer; box-shadow:0 4px 15px rgba(0,0,0,0.3); }
.contact-menu { display:none; flex-direction:column; gap:10px; margin-bottom:10px; }
.contact-menu.open { display:flex; }
.contact-menu a { background:#1A3A5C; color:#F9F6F0; padding:10px 16px; border-radius:30px; text-decoration:none; font-size:14px; }

### JavaScript
function toggleContactMenu() {
  document.querySelector('.contact-menu').classList.toggle('open');
}

### HTML
<div class="contact-fab">
  <div class="contact-menu" id="contactMenu">
    <a href="mailto:mohamedanaya@hotmail.fr">📧 Email</a>
    <a href="https://wa.me/33667018342">💬 WhatsApp</a>
  </div>
  <button class="contact-fab-btn" onclick="toggleContactMenu()">✉️</button>
</div>
