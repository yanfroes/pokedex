# Pokédex Project

<p align="center">
  <img src="./favicons/pokeball.png" alt="Pokeball" width="120" />
</p>

<p align="center">
  <img src="./images/pokemons/001.gif" alt="Bulbasaur" width="80" />
  <img src="./images/pokemons/004.gif" alt="Charmander" width="80" />
  <img src="./images/pokemons/007.gif" alt="Squirtle" width="80" />
  <img src="./images/pokemons/025.gif" alt="Pikachu" width="96" />
  <img src="./images/pokemons/151.gif" alt="Mew" width="120" />
  <img src="./images/pokemons/150.gif" alt="Mewtwo" width="140" />
</p>

A bilingual Pokédex web app (Portuguese + English) with PWA support, local Kanto data, local sprites, and language-aware audio.

## English

### Features
- Full Pokédex layout (left/right on desktop, left only on mobile).
- Language toggle (`Português` / `English`) with live UI text updates.
- Mobile responsiveness for controls, labels, and button behavior.
- PWA support (manifest + service worker + splash experience).
- First-generation sprites (`001..151`) are local in `images/pokemons`.
- `data/kanto-151.json` stores local Pokémon data for Kanto.
- Audio system uses language folders with default fallbacks.

### Data Source Strategy
- For Pokémon `1..151`:
  - App tries local data first from `data/kanto-151.json`.
  - If local entry is missing/broken, app falls back to [PokéAPI](https://pokeapi.co/).
- For Pokémon `152+`:
  - App uses PokéAPI by default.

### Audio Structure
- Portuguese primary audio folder: `audios/ptbr`
- English primary audio folder: `audios/en`
- Playback fallback order:
1. `audios/{language}/{id}.mp3`
2. `audios/{language}/default-{language}.mp3`
3. `audios/{other-language}/{id}.mp3`
4. `audios/{other-language}/default-{other-language}.mp3`

### PWA Notes
- App can be installed as a standalone PWA.
- Service worker caches app shell + `kanto-151.json` + local Kanto sprites.
- Splash/loading style uses a blue background and centered Pokéball.

### Run Locally
1. Clone this repository.
2. Serve the project with any static server.
3. Open the app in your browser.

## Português (BR)

### Funcionalidades
- Interface para Pokédex completa (esquerda/direita no desktop, apenas esquerda no mobile).
- Toggle de idioma (`Português` / `English`) com atualização dinâmica dos textos.
- Responsividade mobile para controles, labels e botões.
- Suporte a PWA (manifest + service worker + splash).
- Sprites da 1ª geração (`001..151`) são locais em `images/pokemons`.
- `data/kanto-151.json` armazena os dados locais de Kanto.
- Sistema de áudio usa pastas por idioma com fallbacks padrão.

### Estratégia de Dados
- Para Pokémon `1..151`:
  - O app tenta dados locais primeiro em `data/kanto-151.json`.
  - Se o item local estiver ausente/quebrado, faz fallback para [PokéAPI](https://pokeapi.co/).
- Para Pokémon `152+`:
  - O app usa PokéAPI como fonte padrão.

### Estrutura de Áudio
- Pasta principal de áudio em português: `audios/ptbr`
- Pasta principal de áudio em inglês: `audios/en`
- Ordem de fallback da reprodução:
1. `audios/{idioma}/{id}.mp3`
2. `audios/{idioma}/default-{idioma}.mp3`
3. `audios/{outro-idioma}/{id}.mp3`
4. `audios/{outro-idioma}/default-{outro-idioma}.mp3`

### Observações de PWA
- O app pode ser instalado como PWA standalone.
- O service worker cacheia app shell + `kanto-151.json` + sprites locais de Kanto.
- O splash/loading usa fundo azul e Pokébola centralizada.

### Como Rodar Localmente
1. Clone este repositório.
2. Sirva o projeto com qualquer servidor estático.
3. Abra o app no navegador.
