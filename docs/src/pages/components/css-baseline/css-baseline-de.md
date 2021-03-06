---
components: CssBaseline
---

# CSS-Baseline

<p class="description">Die Material-UI bietet eine CssBaseline-Komponente, um eine elegante, konsistente und einfache Basis zu schaffen, auf der aufgebaut werden kann.</p>

Möglicherweise kennen Sie [normalize.css](https://github.com/necolas/normalize.css), eine Sammlung von HTML-Element- und Attributstil-Normalisierungen.

```jsx
import React from 'react';
import CssBaseline from '@material-ui/core/CssBaseline';

export default function MyApp() {
  return (
    <React.Fragment>
      <CssBaseline />
      {/* The rest of your application */}
    </React.Fragment>
  );
}
```

## Ansatz

### Seite

The `<html>` and `<body>` elements are updated to provide better page-wide defaults. More specifically:

- Der Rand in allen Browsern wird entfernt.
- Die Standardhintergrundfarbe des Materialdesigns wird angewendet. It's using [`theme.palette.background.default`](/customization/default-theme/?expand-path=$.palette.background) for standard devices and a white background for print devices.

### Layout

- `box-sizing` wird global auf dem `<html>` Element auf `border-box` gesetzt. Jedes Element, einschließlich `*::before` und `*::after` erbt dieser Eigenschaft. Dadurch wird sichergestellt, dass die deklarierte Breite des Elements niemals durch Auffüllung oder Rand überschritten wird.

### Typografie

- Für das `<html>`-Element wird keine Basisschriftgröße deklariert, es wird jedoch von 16px ausgegangen (Standardeinstellung des Browsers). Sie können mehr über die Auswirkungen lernen von den sich ändernden `<html>` Standard - Schriftgröße auf [der Theme Dokumentation](/customization/typography/#typography-html-font-size) Seite.
- Set the `theme.typography.body2` style on the `<body>` element.
- Set the font-weight to "bolder" for the `<b>` and `<strong>` elements. Bolder is one font weight heavier than the parent element (among the available weights of the font).
- Das Antialiasing von Schriftarten ist aktiviert, um die Roboto-Schrift besser anzuzeigen.