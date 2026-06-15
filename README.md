# Sukoon

A minimal, premium startpage with Swiss typography, calm aesthetics, and thoughtful micro-interactions.

> *Sukoon* (सुकून) — Urdu/Hindi for peace, tranquility.

<!-- Add your screenshot here: save as assets/img/sukoon-light.png -->
<!-- ![Sukoon](assets/img/sukoon-light.png) -->

---

## Features

- Geist variable font for clean, modern typography
- Typewriter greeting with natural keystroke jitter and punctuation pauses
- Phosphor Icons via fast CDN class-based rendering
- Swiss date and weather stack with centered typographic layout
- Symmetric accent color system across clock, greeting, date, and weather
- Staggered fade-and-slide-up entry animations on load
- Dark and light mode with smooth icon rotation and tactile feedback
- Expanding underline hover effect on list links
- Configurable 12h/24h clock with zero-padding
- Minimal weather widget via OpenWeatherMap
- Three layout modes: bento, lists, buttons

## Quick Start

1. Fork this repo
2. Copy `config.example.js` to `config.js` and edit it
3. Enable GitHub Pages (Settings > Pages > Source > `gh-pages` branch)

## Installation

### GitHub Pages

1. Fork this repo
2. Copy `config.example.js` to `config.js` and add your weather API key and personal links
3. Go to Settings > Pages > Source and select the `gh-pages` branch
4. Set `https://<your-username>.github.io/sukoon/` as your browser homepage

To deploy updates from `master` to `gh-pages`:

```bash
git checkout gh-pages
git merge master
git push origin gh-pages
git checkout master
```

### Local

Clone the repo and open `index.html` directly, or serve it locally:

```bash
git clone https://github.com/divyanshchandhok/sukoon.git
cd sukoon
cp config.example.js config.js
# Edit config.js with your values
open index.html
```

### Docker

```bash
docker-compose up -d
```

Or manually:

```bash
docker run -it -d -p 80:80 -v ./config.js:/usr/share/nginx/html/config.js sukoon
```

## Customization

All configuration lives in `config.js`. Copy `config.example.js` to get started.

### General

| Setting | Default | Description |
|---|---|---|
| `name` | `'YourName'` | Your name, shown in the greeting |
| `imageBackground` | `false` | Use `assets/background.jpg` as background |
| `openInNewTab` | `true` | Open links in new tabs |
| `twelveHourFormat` | `true` | 12h clock; set `false` for 24h |

### Greetings

| Setting | Default |
|---|---|
| `greetingMorning` | `'Good morning,'` |
| `greetingAfternoon` | `'Good afternoon,'` |
| `greetingEvening` | `'Good evening,'` |
| `greetingNight` | `'Good night, sleep well.'` |

### Layout

| Setting | Default | Description |
|---|---|---|
| `layout` | `'bento'` | `'bento'`, `'lists'`, or `'buttons'` |

### Weather

Get an API key from [OpenWeatherMap](https://openweathermap.org/).

| Setting | Default | Description |
|---|---|---|
| `weatherKey` | `''` | Your OpenWeatherMap API key |
| `weatherUnit` | `'C'` | `'C'` for Celsius, `'F'` for Fahrenheit |
| `language` | `'en'` | [Language code](https://openweathermap.org/current#multi) |
| `trackLocation` | `true` | Use browser geolocation |
| `defaultLatitude` | `'0.0'` | Fallback latitude |
| `defaultLongitude` | `'0.0'` | Fallback longitude |

### Theme

| Setting | Default | Description |
|---|---|---|
| `autoChangeTheme` | `true` | Enable automatic theme switching |
| `changeThemeByOS` | `true` | Follow OS dark/light preference |
| `changeThemeByHour` | `false` | Switch by time of day |
| `hourDarkThemeActive` | `'18:30'` | Dark mode activates after this time |
| `hourDarkThemeInactive` | `'07:00'` | Dark mode deactivates after this time |

### Colors

Edit CSS variables in `app.css`:

```css
:root {
  --accent: #537060;      /* Forest sage green */
  --background: #f5f5f5;  /* Background */
  --cards: #e4e6e6;       /* Card surfaces */
  --fg: #3a3a3a;          /* Text color */
  --sfg: #494949;         /* Secondary text */
}

.darktheme {
  --accent: #8fa89b;      /* Eucalyptus pale green */
  --background: #19171a;
  --cards: #201e21;
  --fg: #d8dee9;
  --sfg: #2c292e;
}
```

### Links

Edit `firstButtonsContainer`, `secondButtonsContainer`, `firstlistsContainer`, and `secondListsContainer` in `config.js`. Use [Phosphor Icons](https://phosphoricons.com/) names (e.g., `github-logo`, `spotify-logo`).

## Credits

Sukoon is based on [Bento](https://github.com/migueravila/bento) by [Miguel Avila](https://avila.sh), licensed under [GPL-3.0](https://www.gnu.org/licenses/gpl-3.0).

## License

[GPL-3.0](License)
