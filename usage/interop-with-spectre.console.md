---
description: Can Terminaux and Spectre.Console be together?
icon: ghost
---

# Interop with Spectre.Console

If you are using [Spectre.Console](https://www.nuget.org/packages/Spectre.Console), you might notice that there are some features that are roughly similar to what Terminaux implements if we're talking about ideas and concepts. While Spectre.Console focuses on CLI, Terminaux focuses on both CLI and TUI. However, the graphical part of Spectre.Console, such as table rendering, is implemented differently in both libraries.

In a separate library, [Terminaux.Spectre](https://www.nuget.org/packages/Terminaux.Spectre/), you can perform translation operations. Please note that, when installing this package, Spectre.Console is also installed as a dependency.

<figure><img src="../.gitbook/assets/image (149).png" alt=""><figcaption></figcaption></figure>

You can translate Terminaux's renderables into Spectre.Console's renderables, but you can't translate the other way around due to how Spectre.Console implements them. The following translation methods are supported:

* `Mark` -> [`Markup`](https://spectreconsole.net/markup)&#x20;
* `BoxFrame` -> [`Panel`](https://spectreconsole.net/widgets/panel)

{% hint style="info" %}
You can't use Terminaux's writers to write the resulting Spectre's [`IRenderable`](https://spectreconsole.net/api/spectre.console.rendering/irenderable/). You'll have to use the [`AnsiConsole`](https://spectreconsole.net/api/spectre.console/ansiconsole/) class.
{% endhint %}
