<p align="center">
  <img src="https://raw.githubusercontent.com/Go-Forms/GoForms/main/site/assets/logo.svg" width="110" alt="">
</p>

<h1 align="center">GoForms</h1>

<p align="center"><strong>If you know WinForms, you already know GoForms.</strong></p>

<p align="center">
  <a href="https://go-forms.github.io/GoForms/">Website</a> ·
  <a href="https://go-forms.github.io/GoForms/guide.html">Guide</a> ·
  <a href="https://github.com/Go-Forms/GoForms/tree/main/docs">Reference</a> ·
  <a href="https://github.com/Go-Forms/GoFormsDesigner">Designer</a> ·
  <a href="https://github.com/Go-Forms/GoFormsShowcase">Showcase</a> ·
  <a href="https://go-forms.github.io/GoForms/ru/">По-русски</a>
</p>

<p align="center">
  <a href="https://github.com/Go-Forms/GoForms/actions/workflows/ci.yml"><img src="https://github.com/Go-Forms/GoForms/actions/workflows/ci.yml/badge.svg" alt="CI"></a>
  <a href="https://github.com/Go-Forms/GoForms/tags"><img src="https://img.shields.io/github/v/tag/Go-Forms/GoForms?sort=semver&label=framework" alt="Framework version"></a>
  <a href="https://github.com/Go-Forms/GoFormsDesigner/releases/latest"><img src="https://img.shields.io/github/v/tag/Go-Forms/GoFormsDesigner?sort=semver&label=designer" alt="Designer version"></a>
  <img src="https://img.shields.io/badge/go-1.23%2B-00ADD8" alt="Go 1.23+">
  <img src="https://img.shields.io/badge/license-MIT-blue" alt="MIT">
</p>

---

A form. Controls at `X, Y, Width, Height`. Docking and anchoring that survive
a resize. Events you attach with `.Handle(…)`. And a drag-and-drop designer
that writes plain, readable Go — not a resource blob you are never meant to
open.

Rendering, windowing and input are handled by [Fyne](https://fyne.io)
underneath, so the same forms run on Windows, Linux and macOS, in the browser
as WebAssembly, and on Android. Everything above that line is WinForms.

<p align="center">
  <img src="https://raw.githubusercontent.com/Go-Forms/GoFormsDesigner/main/images/designer-canvas.png" width="49%" alt="The designer editing a form, with the selected control's properties and events beside it">
  <img src="https://raw.githubusercontent.com/Go-Forms/GoForms/main/docs/images/form-controls.png" width="49%" alt="The showcase's controls form, running">
</p>

### A form is two files

The same split WinForms makes between `Form1.Designer.cs` and `Form1.cs`. The
designer writes the first; the second is yours and is never rewritten.

```go
// MainForm-designer.go
mf.btnGreet = goforms.NewButton("Greet")
mf.btnGreet.SetBounds(20, 60, 100, 30)
mf.btnGreet.Click.Handle(mf.btnGreet_Click)
mf.AddControl(mf.btnGreet)
```

```go
// MainForm.go
func (mf *MainForm) btnGreet_Click(sender any, e goforms.MouseEventArgs) {
	mf.lblHello.SetText("Clicked!")
}
```

### Getting started

```sh
# The framework
go get github.com/Go-Forms/GoForms

# Or see every control and layout running at once
git clone https://github.com/Go-Forms/GoFormsShowcase
cd GoFormsShowcase && go run .
```

For the designer, take the `.vsix` from its
[latest release](https://github.com/Go-Forms/GoFormsDesigner/releases/latest),
install it with `code --install-extension goforms-designer-<version>.vsix`,
then run **GoForms: Create New Project…** from the command palette.

### Where it runs

| | |
|---|---|
| **Windows, Linux, macOS** | Native windows, GPU-drawn. Built, vetted and tested on all three on every commit. |
| **Browser** | `js/wasm` build. Extra forms are hosted inside the page, file dialogs use the browser's own picker and downloads. |
| **Android** | APK build, installed onto a connected phone over adb. Forms take the whole screen, as mobile dialogs do. |

The designer builds and runs each of these with one command.

### The repositories

| | |
|---|---|
| **[GoForms](https://github.com/Go-Forms/GoForms)** | The framework: controls, layout, events, dialogs, theming. |
| **[GoFormsDesigner](https://github.com/Go-Forms/GoFormsDesigner)** | The VS Code extension: a visual designer with a toolbox of 34 controls, a theme editor, project scaffolding, and build and run for desktop, browser and Android. In English and Russian. |
| **[GoFormsShowcase](https://github.com/Go-Forms/GoFormsShowcase)** | One form per subject, with a live event log. Run it to see the whole framework. |
| **[GoFormsDemo](https://github.com/Go-Forms/GoFormsDemo)** | A smaller sample, closer to a real project's first few forms. |
| **[glfw-js](https://github.com/Go-Forms/glfw-js)** | A one-fix fork of Fyne's browser shim, so Cyrillic and other non-ASCII typing reaches WebAssembly builds. New projects use it through a `replace`. |

MIT licensed.
