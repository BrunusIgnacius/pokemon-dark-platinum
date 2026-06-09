# Pokemon Dark Platinum

A mini Pokémon universe built with pure **HTML, CSS, and JavaScript (no frameworks)**. It includes trainer registration, team building via the PokeAPI, a memory game, turn-based battles, and an extra mode featuring the **StartCodingBatch** group.

---

## Screenshots

> _Reserved space for project screenshots._

### Tela de Registro
![Registro Light](screenshots/light/registro.png)
![Registrado Light](screenshots/light/registrado.png)
![Registro Dark](screenshots/dark/registro.png)
![Registrado Dark](screenshots/dark/registrado.png)

### Tela de Equipe Vazia
![Equipe Vazia Light](screenshots/light/equipeVazia.png)
![Equipe Vazia Dark](screenshots/dark/equipeVazia.png)

### Pokedex / Seleção de Equipe
![Pokedex Light](screenshots/light/selecao.png)
![Pokedex Dark](screenshots/dark/selecao.png)
![Pokedex Confirmar Light](screenshots/light/equipeEscolhida.png)
![Pokedex Confirmar Dark](screenshots/dark/equipeEscolhida.png)

### Tela de Equipe Cheia ou Quase
![Equipe Cheia Light](screenshots/light/equipeCheia.png)
![Equipe Cheia Dark](screenshots/dark/equipeCheia.png)
![Equipe Cheia Light](screenshots/light/menosUmEquipe.png)
![Equipe Cheia Dark](screenshots/dark/menosUmEquipe.png)

### Escolha de Aventura
![Modos Aventura Light](screenshots/light/escolherGame.png)
![Modos Aventura Light](screenshots/dark/escolherGame.png)

### Jogo da Memória
![Modos Memória Light](screenshots/light/escolherModo.png)
![Modos Memória Dark](screenshots/dark/modosMemoria.png)
![Memória Maluco Light](screenshots/light/memoriaAcertosIntruso.png)
![Memória Maluco Dark](screenshots/dark/memoriaAcertosIntruso.png)
![Memória Maluco Intruso Light](screenshots/light/memoriaMalucoIntruso.png)
![Memória Maluco Intruso Dark](screenshots/dark/memoriaIntruso.png)
![Memória Maluco Vitória Light](screenshots/light/memoriaVitoria.png)
![Memória Maluco Vitória Dark](screenshots/dark/vitoriaMemoria.png)

### Batalha
![Modos Batalha Light](screenshots/light/batalhaModos.png)
![Modos Batalha Dark](screenshots/dark/modosBatalha.png)
![Batalha Seleção Light](screenshots/light/escolhendoPokeBatalha.png)
![Batalha Seleção Dark](screenshots/dark/escolherPokeBatalha.png)
![Batalha Light](screenshots/light/telaBatalha.png)
![Batalha Dark](screenshots/dark/batalha.png)
![Batalha Troca Light](screenshots/light/mudarPokeBatalha.png)
![Batalha Troca Dark](screenshots/dark/trocarPokeBatalha.png)
![Batalha Fuga Light](screenshots/light/fugaBatalha.png)
![Batalha Fuga Dark](screenshots/dark/fugirBatalha.png)

### Modo Extra
![Modos Extra Light](screenshots/light/extraModos.png)
![Modos Extra Dark](screenshots/dark/modosExtra.png)
![Extra Maluco Light](screenshots/light/extraAcertosIntrusa.png)
![Extra Maluco Dark](screenshots/dark/extraAcertosIntrusa.png)
![Extra Maluco Intrusa Light](screenshots/light/extraMalucoIntrusa.png)
![Extra Maluco Intrusa Dark](screenshots/dark/extraIntrusa.png)
![Extra Maluco Vitória Light](screenshots/light/vitoriaExtra.png)
![Extra Maluco Vitória Dark](screenshots/dark/extraVitoria.png)

### Trilha Sonora
![Trilha Sonora](screenshots/light/trilhaSonora.png)
![Trilha Sonora](screenshots/dark/trilhaSonora.png)

---

## How to Run

The application should be started from `register/registrar.html`.  
Direct access to other files will trigger an automatic redirect to the correct entry point.

Recommended flow: `register/` → `index/` → `pokeTeam/` → `chooseGame/` → selected mode.


---

## Project Structure

```
PokemonDarkPlatinum/
├── register/        Trainer registration
├── index/           Pokédex and team selection (up to 6 Pokémon)
├── pokeTeam/        Built team overview
├── chooseGame/      Game mode selection hub
├── memoryGame/      Memory game (3 difficulty levels)
├── battleGame/      Turn-based battle against CPU (3 difficulty levels)
├── extraGame/       Extra mode with classmates (3 difficulty levels)
├── theme/           Light/dark theme, music, overlays, and navigation control
├── photos/          Sprites and images (trainer, backgrounds, classmates)

```

---

## Folders and Files

### `register/` — Trainer Registration
- **`registrar.html`** — Form: name, age, and avatar selector (boy / girl / Valdo / Valda).
- **`registrar.js`** — Validates the form, saves the trainer to `localStorage`, and enables the "Start Journey" button.
- **`registrar.css`** — Styles for the form and avatar cards.

### `index/` — Pokédex and Team Selection
- **`index.html`** — Main screen: header with trainer name, counter `Team: X / 6`, name search, type filter, and "Team Complete" overlay.
- **`index.js`** — Pokédex logic: consumes the [PokeAPI](https://pokeapi.co/), renders cards, manages selection (max. 6), search, filtering, and persists the team in `localStorage`.
- **`index.css`** — Styling for the card grid and filter bar.

### `pokeTeam/` — Built Team
- **`equipe.html`** — Screen displaying the selected Pokémon (up to 6).
- **`equipe.js`** — Reads the team from `localStorage` and renders detailed cards.
- **`equipe.css`** — Team grid layout.

### `chooseGame/` — Mode Hub
- **`aventura.html`** — Cards for "Memory Game", "Battle", and "Extra Mode" + internal overlays for difficulty selection (Beginner, Hard, Crazy).
- **`aventura.js`** — Handles navigation between modes and opening/closing overlays.
- **`aventura.css`** — Styling for mode cards.

### `memoryGame/` — Memory Game
Three difficulty levels, each in its own folder with its own HTML+JS and shared CSS:
- **`begginer/memoriaIniciante.{html,js}`** — Matching pairs (sprite + name) using the player's team.
- **`pro/memoriaDificil.{html,js}`** — Matching triples instead of pairs.
- **`crazy/memoriaMaluco.{html,js}`** — Find the intruder among the Pokémon.
- **`memoria.css`** — Board, card, and flip animation styles.

### `battleGame/` — Turn-based Battle
- **`battleEngine.js`** — Pure calculation functions: damage based on `Atk/Def`, type multipliers, buffs/debuffs, and CPU AI with 3 priorities (finish → buff → strongest attack).
- **`tabelaTipos.js`** — Type effectiveness table (Fire > Grass, etc.).
- **`selecao/selecao.{html,js}`** — Screen where the player selects an active Pokémon.
- **`arena/arena.{html,js}`** — Battle arena: HP bars, animations, turn log, and game end.
- **`battle.css`** — Arena, bar, and move button styles.

### `extraGame/` — Extra Mode (StartCodingBatch group)
Same mechanics as the memory game, but with **classmates' photos** instead of Pokémon:
- **`colegas.js`** — List of classmates and the "intruder" Jucieli (coordinator) — appears only in Crazy mode.
- **`begginer/extraIniciante.{html,js}`** — Matching pairs of classmates.
- **`pro/extraDificil.{html,js}`** — Matching triples of classmates.
- **`crazy/extraMaluco.{html,js}`** — Who is the intruder?
- **`extra.css`** — Styles specific to the extra mode.

### `theme/` — Shared Layer
- **`tema.{js,css}`** — Light/dark mode toggle (persisted in `localStorage`).
- **`musica.{js,css}`** — Background music player with floating button.
- **`overlays.{js,css}`** — Reusable overlay/modal system.
- **`guard.js`** — Navigation guard: if trainer or team is missing, redirects to `register/` or `index/` automatically, calculating the relative path based on page depth.

### `photos/`
- **`boy.png`, `girl.png`** — Trainer avatar sprites.
- **`bg.jpg`** — Background image.
- **`StartCodingBatch/`** — Classmate photos used in Extra Mode.

### `font/`
Fonts used in the project:
- **`PokemonSolid.ttf`**, **`PokemonHollow.ttf`** — Pokémon logo-style fonts.
- **`PixelGameFont.ttf`** — Pixel-style font for text.

---

## Technologies

- HTML5, CSS3, JavaScript (ES6+) — no frameworks
- [PokeAPI](https://pokeapi.co/) for Pokémon data and sprites
- `localStorage` to persist trainer and team across pages

---

## Credits

Project developed during the **StartCodingBatch2026** course. Pokémon sprites and data provided by the PokeAPI; class photos used with permission from classmates.
