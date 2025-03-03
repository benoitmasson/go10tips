---
marp: true
headingDivider: []
theme: uncover
class:
  - invert
---

<!-- markdownlint-disable MD001 MD026 MD033 MD045 -->

<!-- Compile to HTML with `marp -w -s --html true .` -->

<!-- https://marpit.marp.app/markdown -->

<style>
    @import url('./deck.css');
</style>

<div class="flex vertical center">

![height:250px](./images/gopher%20prof.png)

# 1️⃣0️⃣ trucs et astuces

### à connaître avant de développer en Go

Gwendal Leclerc & Benoît Masson – OVHcloud

</div>

---

<div class="flex vertical space-between">

## Qui sommes-nous ?

<div class="horizontal space-around">
<div class="vertical start">

### Benoît

![width:200px](./images/benoit.jpg)

Développeur Domaines

</div>
<div class="vertical start">

### Gwendal

![width:200px](./images/gwendal.png)

Tech Lead Domaines

</div>
</div>

![width:300px](./images/logo%20ovhcloud.png)

</div>

---

![bg cover opacity:0.5](./images/stars.jpg)

<div class="flex vertical space-around">

# Bonnes Pratiques

</div>

---

<div class="flex vertical start">

<!-- ## 1️⃣ Structure des fichiers 🗂️ -->

</div>

---

<div class="flex vertical start">

## 2️⃣ Nommages 🔡

- Évitez les noms courts, soyez explicites
  - quelques exceptions : `i`, `err`, `ctx`, …
- N'exposez rien par défaut, attendez que ça serve
  - attention aux attributs de structure à sérialiser
- N'hésitez pas à renommer (voire refactorer avec l'aide du LS), le compilateur va vous guider

</div>

---

<div class="flex vertical start">

<!-- ## 3️⃣ Build flags 🏳️‍🌈 -->

</div>

---

<div class="flex vertical start">

## 4️⃣ Gestion d'erreurs 💥

- Gérez systématiquement vos erreurs !
  - traitements spécifiques
- Faites des early-return
  - réduit la complexité de votre code
- N'utilisez pas `panic` (ou du code qui peut paniquer)
  - sauf éventuellement dans un `main` ou un `init`

</div>

---

<div class="flex vertical start">

<!-- ## 5️⃣ Tests unitaires 🧪 -->

</div>

---

![bg cover opacity:0.5](./images/broken.jpg)

<div class="flex vertical space-around">

# Fausses bonnes idées

</div>

---

<div class="flex vertical start">

## 6️⃣ `any` 🪄

- Synonyme de `interface{}` (Go 1.18): casse le typage

- Jamais en retour de fonction, à la limite via un pointeur modifiable en paramètre

- Si pas le choix (lib externe), encapsulez l'appel dans une fonction typée
  Ex : `context.Value(key any) any`

</div>

---

<div class="flex vertical start">

## 7️⃣ Génériques, itérateurs 🫥

- Transparents pour les utilisateurs :
  ils existent mais la plupart du temps, vous ne les verrez pas

</div>

---

<div class="flex vertical start">

## 8️⃣ Channels 🚇

- Risques de deadlocks, bugs, double close… difficile à lire et à débugguer
- Privilégiez les `sync.Mutex`, `sync.WaitGroup`, …
- Si nécessaire, encapsulez-les dans des fonctions ou objets (testés)

</div>

---

<div class="flex vertical start">

## 9️⃣ Frameworks 🖼️

- Inutiles en général
- Certains, spécifiques à un besoin précis, sont ok
  - HTTP : `echo`, `gin`, …
  - ORM : `bun`, …
- Les fonctionnalités les plus utiles finissent par arriver dans la lib std

</div>

---

![bg cover opacity:0.7](./images/tools.jpg)

<div class="flex vertical space-around">

# Trucs et astuces

</div>

---

<div class="flex vertical start">

<!-- ## 1️⃣0️⃣ Packages indispensables 📦 -->

</div>

---

<div class="flex vertical start">

<!-- ## 1️⃣1️⃣ Outils indispensables 🛠️ -->

</div>

---

![bg cover](./images/question.jpg)

<div class="flex vertical space-between">

# Des questions ?

<div class="horizontal end bottom-align">
<div class="footnotes">

Images credits: [Unsplash](https://unsplash.com) & [ChatGPT](https://chatgpt.com/)
Slides: [github.com/benoitmasson/go10tips](https://github.com/benoitmasson/go10tips/)

</div>
</div>

</div>
