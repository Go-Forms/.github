<p align="center">
  <img src="https://raw.githubusercontent.com/Go-Forms/GoForms/main/site/assets/logo.svg" width="110" alt="">
</p>

<h1 align="center">GoForms</h1>

<p align="center"><strong>If you know WinForms, you already know GoForms.</strong></p>

<p align="center">
  <a href="https://go-forms.github.io/GoForms/">Website</a> ·
  <a href="https://github.com/Go-Forms/GoForms/tree/main/docs">Documentation</a> ·
  <a href="https://github.com/Go-Forms/GoFormsShowcase">Showcase</a>
</p>

---

A form. Controls at `X, Y, Width, Height`. Docking and anchoring that survive
a resize. Events you attach with `.Handle(…)`. And a drag-and-drop designer
that writes plain, readable Go — not a resource blob you are never meant to
open.

Rendering, windowing and input are handled by [Fyne](https://fyne.io)
underneath, so it draws fast on Windows, Linux and macOS. Everything above
that line is WinForms.

```go
mf.btnGreet = goforms.NewButton("Greet")
mf.btnGreet.SetBounds(20, 60, 100, 30)
mf.btnGreet.Click.Handle(mf.btnGreet_Click)
mf.AddControl(mf.btnGreet)
```

### The repositories

| | |
|---|---|
| **[GoForms](https://github.com/Go-Forms/GoForms)** | The framework: 34 controls, layout, events, dialogs, theming. |
| **[GoFormsDesigner](https://github.com/Go-Forms/GoFormsDesigner)** | The VS Code extension — visual designer and project scaffolding. |
| **[GoFormsShowcase](https://github.com/Go-Forms/GoFormsShowcase)** | One form per subject, with a live event log. Run it to see the whole framework. |
| **[GoFormsDemo](https://github.com/Go-Forms/GoFormsDemo)** | A smaller sample, closer to a real project's first few forms. |

MIT licensed.
