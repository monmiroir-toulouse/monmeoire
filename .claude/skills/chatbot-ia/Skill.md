# Skill : Chatbot IA

## Objectif
Intégrer un chatbot automatique dans le site "Mon Miroir" (HTML/CSS pur).

## Contexte
- Site : HTML/CSS simple (index.html)
- Couleurs : Bleu #1A3A5C, Or #C9A84C, Blanc #F9F6F0
- Thème : IA & Tribunal pour Enfants de Toulouse

## HTML à ajouter avant </body>
<div id="chatbot-widget">
  <button id="chat-toggle" onclick="toggleChat()">💬</button>
  <div id="chat-box">
    <div id="chat-header">
      <span>Mon Miroir — Assistant</span>
      <button onclick="toggleChat()">✕</button>
    </div>
    <div id="chat-messages">
      <div class="bot-msg">Bonjour ! Je suis l'assistant de Mon Miroir. Comment puis-je vous aider ?</div>
    </div>
    <div id="chat-input-area">
      <input type="text" id="chat-input" placeholder="Posez votre question..." onkeydown="if(event.key==='Enter') sendMsg()">
      <button onclick="sendMsg()">➤</button>
    </div>
  </div>
</div>

## CSS à ajouter
#chatbot-widget { position:fixed; bottom:30px; left:30px; z-index:9999; }
#chat-toggle { background:#C9A84C; border:none; border-radius:50%; width:60px; height:60px; font-size:24px; cursor:pointer; box-shadow:0 4px 15px rgba(0,0,0,0.3); }
#chat-box { display:none; width:320px; background:#1A3A5C; border-radius:16px; overflow:hidden; box-shadow:0 8px 30px rgba(0,0,0,0.4); margin-bottom:10px; flex-direction:column; }
#chat-header { background:#C9A84C; color:#1A3A5C; padding:14px 16px; display:flex; justify-content:space-between; font-weight:bold; }
#chat-messages { padding:16px; height:250px; overflow-y:auto; display:flex; flex-direction:column; gap:10px; }
.bot-msg { background:rgba(255,255,255,0.1); color:#F9F6F0; padding:10px 14px; border-radius:12px; font-size:14px; max-width:85%; }
.user-msg { background:#C9A84C; color:#1A3A5C; padding:10px 14px; border-radius:12px; font-size:14px; max-width:85%; align-self:flex-end; }
#chat-input-area { display:flex; padding:12px; gap:8px; border-top:1px solid rgba(255,255,255,0.1); }
#chat-input { flex:1; background:rgba(255,255,255,0.1); border:1px solid rgba(201,168,76,0.4); border-radius:20px; padding:8px 14px; color:#F9F6F0; font-size:14px; }

## JavaScript à ajouter
function toggleChat() {
  const box = document.getElementById('chat-box');
  box.style.display = box.style.display === 'flex' ? 'none' : 'flex';
}

const reponses = {
  "bonjour": "Bonjour ! Bienvenue sur Mon Miroir.",
  "contact": "Contactez-nous : mohamedanaya@hotmail.fr ou WhatsApp 06 67 01 83 42",
  "miroir": "Mon Miroir est un projet IA lié au Tribunal pour Enfants de Toulouse.",
  "default": "Je n'ai pas compris. Utilisez le formulaire de contact pour plus d'aide."
};

function sendMsg() {
  const input = document.getElementById('chat-input');
  const msgs = document.getElementById('chat-messages');
  const text = input.value.trim();
  if (!text) return;
  msgs.innerHTML += '<div class="user-msg">'+text+'</div>';
  input.value = '';
  const key = Object.keys(reponses).find(k => text.toLowerCase().includes(k));
  setTimeout(() => {
    msgs.innerHTML += '<div class="bot-msg">'+(reponses[key]||reponses.default)+'</div>';
    msgs.scrollTop = msgs.scrollHeight;
  }, 600);
}
