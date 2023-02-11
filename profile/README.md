## Oi pessoal 👋
Memoriagame é uma concepção de um jogo de memória 100% modular, funcional, orientado a eventos, interface gráfica, objeto, cdn, rota - tudo isso via client. 

## Arquitetura do jogo
Self-hosted, git-submodules, offline/online web-component, css-variables, cdn, unhosted, serverless. 

## O que significa a arquitetura do jogo?
- Significa como o jogo foi feito, desenvolvido, criado. 
- Isso é importante exclusivamente aos desenvolvedores e usuários. 
- Por exemplo, a arquitetura acima diz que você tem acesso aos dados locais e remotos da aplicação. 
- Assim como, de forma geral, é utilizada apis públicas externas para o jogo sem que haja necessidade de um servidor central ou interno. 
- Assim como, todos os arquivos referentes à aplicação são externos e distribuídos. 
- Ao mesmo tempo que são, altamente modulados, componentizados pelo lado client.
- De forma geral, tudo isso serve para maior privacidade, segurança, controle, anonimato.
- Funciona online e offline.
- todo o código é divido em sub-modulo git.

## Demonstração
*demo.js*
```javascript
// _setCSSVariable('--cardImageBack1', './back1.jpg');
// _setCSSVariable('--cardImageBack2', './back.png');
// _setCSSVariable('--cenario', './cenario.png');
// _setCSSVariable('--cenario1', './cenario1.png');
// _setCSSVariable('--cardImageBack1', 'https://cdn.jsdelivr.net/gh/memoriagame/assets/public/css/back1.jpg');
// _setCSSVariable('--cardImageBack2', 'https://cdn.jsdelivr.net/gh/memoriagame/assets/public/css/back.png');
// _setCSSVariable('--cenario', 'https://cdn.jsdelivr.net/gh/memoriagame/assets/public/css/cenario.png');
// _setCSSVariable('--cenario1', 'https://cdn.jsdelivr.net/gh/memoriagame/assets/public/css/cenario1.png');
```

*styles.css*
```css
@import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap');

:root {
  --cardImageBack1: url('https://cdn.jsdelivr.net/gh/memoriagame/assets/public/css/back1.jpg');
  --cardImageBack2: url('https://cdn.jsdelivr.net/gh/memoriagame/assets/public/css/back.png');
  --cenario: url('https://cdn.jsdelivr.net/gh/memoriagame/assets/public/css/cenario.png');
  --cenario1: url('https://cdn.jsdelivr.net/gh/memoriagame/assets/public/css/cenario1.jpg');
}

* {
    background-image: var(--cenario); /* background-image: url('./cenario.png'); */
}
```

*ajax.js*
```javascript
HTTPAjax('https://cdn.jsdelivr.net/gh/memoriagame/assets/public/css/back1.jpg', 200)
// |-> https://cdn.jsdelivr.net/gh/memoriagame/assets/public/css/back1.jpg
// else  |-> https://cdn.jsdelivr.net/gh/memoriagame/assets/back1.jpg
 
HTTPAjax('https://cdn.jsdelivr.net/gh/memoriagame/assets/public/css/back.png', 200)
// |-> https://cdn.jsdelivr.net/gh/memoriagame/assets/public/css/back.png
// else  |-> https://cdn.jsdelivr.net/gh/memoriagame/assets/back1.jpg

HTTPAjax('https://cdn.jsdelivr.net/gh/memoriagame/assets/public/css/cenario.png', 200)
// |-> https://cdn.jsdelivr.net/gh/memoriagame/assets/public/css/cenario.png
// else  |-> https://cdn.jsdelivr.net/gh/memoriagame/assets/cenario.png
 
HTTPAjax('https://cdn.jsdelivr.net/gh/memoriagame/assets/public/css/cenario1.png', 200)
// |-> https://cdn.jsdelivr.net/gh/memoriagame/assets/public/css/cenario1.png
// else  |-> https://cdn.jsdelivr.net/gh/memoriagame/assets/cenario1.png
```

```javacript
const createCarta = (personagens, selectTypeCard) => {
  const carta = createElement('div', 'carta');  
  const front = createElement('img', 'face front');
  const back = createElement('img', 'face back');
  front.src = `https://memoriagame.github.io/assets/theme/character/pokemon/${personagens}+".png"` // `./css/image/${personagens}.png`; 
  carta.appendChild(front); 
  back.src = selectTypeCardNow(selectTypeCard); 
  carta.appendChild(back);
  carta.addEventListener('click', reveleCarta);
  carta.setAttribute('data-personagens', personagens);
  return carta;
}
```

## Rede cdn para arquivos estáticos
- js: 
   - `https://cdn.jsdelivr.net/gh/memoriagame/js/app/memoria.js`
- css: 
   - `https://cdn.jsdelivr.net/gh/memoriagame/css/memoriagame/styles.css`
   - `https://cdn.jsdelivr.net/gh/memoriagame/css/rating-stars/styles.css`
- png: 
  - `https://cdn.jsdelivr.net/gh/memoriagame/assets/public/css/squirtle.png`
  - `https://cdn.jsdelivr.net/gh/memoriagame/assets/public/css/togeppi.png`
  - `https://cdn.jsdelivr.net/gh/memoriagame/assets/public/css/eve.png`
  - `https://cdn.jsdelivr.net/gh/memoriagame/assets/public/css/chikorita.png`
- mp3: 
  - `https://cdn.jsdelivr.net/gh/memoriagame/assets/public/music/tema.mp3`

## Recursos
Esse jogo também tem diversas apis "recurso de multi-apis" implementadas e utilizadas

## Apis utilizadas
Api unsplash, freemusic, themoviedb, pokeapi.co, anime-com, assets, fonts.googleapis, hatscripts.github.io/flags
  
### Temas do jogo
- anime/desenho: jogo da memória relacionado aos personagens do anime/manga/desenho prefiro como: one-piece, pokemon, naruto, yu-yu-hakusho, simpsons, ricky and morty, pica-pau, scooby-doo, futurama etc
- literatura: jogo da memória relacionado a poetas/poetisas de todos os países
- geografia: jogo da memória relacionado a informações gerais, específicas do país, estado, cidade, região etc

## Técnicas utilizadas/tecnologias
Api restfull, ajax, http, status http, fetch etc

## A Organização e o jogo MemoriaGame
<img src="https://cdn-icons-png.flaticon.com/512/3813/3813720.png" alt="logo" id="3813720" class="flaticon" align="left" width="120" height="120" hspace="50"/>

MemoriaGame é um projeto de código aberto para jogar o jogo memória em github-pages. A Organização MemoriaGame tem como objetivo incluir mais fases no jogo ou mais recursos de desenvolvimento para que o jogo seja jogado por maior número de pessoas. A licença da Organização e de todos projetos é uma versão personalizada da licença de Código Aberto MIT. 

| 🌐 | Join  👋  | Twitter | Instagram |
| -- | -- | -- | -- |
| [memoriagame.github.io](https://memoriagame.github.io) | [memoriagame.so/join](https://memoriagame.github.io/join) |[@memoriagame_team](http://twitter.com/memoriagame_team) | [@memoriagame_team](http://instagram.com/memoriagame_team/) |


<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
