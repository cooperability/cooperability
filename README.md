## Skillset

A map of the shields below, grouped by what kind of thing each one is — not a diagram of cooperability.com.

```mermaid
flowchart LR
  classDef built fill:#dff5e1,stroke:#2e7d32,color:#1b3d20

  subgraph skills ["At a glance"]
    direction LR
    links(["Links"]):::built
    fe["Frontend"]:::built
    be["Backend"]:::built
    db[("Databases")]:::built
    ops{{"DevOps"}}:::built
    tools["Tooling"]:::built
    os["OS"]:::built
  end
```

**Shapes:** stadium = a public entry · rectangle = code you run · cylinder = data at rest · hexagon = someone else's system. GitHub renders mermaid natively. VS Code's built-in preview shows the fence as a code block unless the [Markdown Preview Mermaid Support](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-mermaid) extension is installed.

Icon-only nodes and click-to-magnify are **not** something GitHub mermaid can do today (`click` is stripped; icon packs need JavaScript the README renderer never runs). The working substitute: open a group to magnify it into named, typed nodes.

<details>
<summary>Links</summary>

```mermaid
flowchart LR
  web(["cooperability.com"])
  resume[/Resume/]
  li{{LinkedIn}}
```

</details>

<details>
<summary>Frontend</summary>

```mermaid
flowchart LR
  html5[HTML5]
  css[CSS]
  ts[TypeScript]
  react[React]
  next["Next.js"]
  tw[Tailwind]
  shadcn["shadcn/ui"]
  redux[Redux]
  svelte[Svelte]
```

</details>

<details>
<summary>Backend and databases</summary>

```mermaid
flowchart LR
  py[Python]
  tsbe[TypeScript]
  node["Node.js"]
  dj[Django]
  pg[(PostgreSQL)]
  mongo[(MongoDB)]
  neo[(Neo4j)]
```

</details>

<details>
<summary>DevOps</summary>

```mermaid
flowchart LR
  git[Git]
  gl{{GitLab}}
  docker[Docker]
  tf[Terraform]
  k8s[Kubernetes]
  gcp{{"Google Cloud"}}
  rail{{Railway}}
  vercel{{Vercel}}
  fb{{Firebase}}
  heroku{{Heroku}}
  cci{CircleCI}
```

</details>

<details>
<summary>Tooling</summary>

```mermaid
flowchart LR
  vite[Vite]
  eslint[ESLint]
  jest[Jest]
  wb[Workbox]
  prettier[Prettier]
  poetry[Poetry]
  dep{Dependabot}
  gha{"GitHub Actions"}
```

</details>

<details>
<summary>OS</summary>

```mermaid
flowchart LR
  android[Android]
  ios[iOS]
  linux[Linux]
  mac[macOS]
  win[Windows]
```

</details>

<details>
<summary>Proposed mermaid features (the icon-only click-to-magnify)</summary>

What mermaid would need so the glance diagram *is* the shields, and clicking DevOps magnifies that shape in place:

1. **`reveal: click` on subgraphs.** Mermaid 11.17 can *declare* `@{ view: collapsed }`, but that is a static re-render, not a click. Hosted READMEs still strip `click`. Compile `reveal: click` to real SVG toggle where JS runs, and to `<details>` where it does not (GitHub, GitLab).
2. **Icon-only nodes with kind preserved.** `icon` / `img` shapes exist, but GitHub does not register Iconify packs, and Font Awesome renders as the literal `fa:fa-*` text. Inline simple-icons at render time, and let `form` be the same kind-shape vocabulary (stadium, cylinder, hexagon, diamond) — not only square/circle/rounded.
3. **`labelMode: icon | hover | expand`.** Glance = icon + shape; magnify = every badge name. One source file, two views, no second diagram.

How that interaction is supposed to feel:

```mermaid
stateDiagram-v2
  [*] --> Glance
  Glance --> Magnified: click DevOps
  Magnified --> Glance: click to collapse
```

How a hosted README should degrade when the renderer cannot run JS:

```mermaid
flowchart LR
  src[/Skillset source/]
  live["mermaid.live"]
  gh{{"GitHub README"}}
  src --> live
  src --> gh
  live -->|"proposed reveal click"| ui[In-place magnify]
  gh -->|"today: click stripped"| svg[["Static SVG"]]
  gh -->|"proposed fallback"| html[["details summary"]]
```

Proposed source that would replace the glance diagram plus the `<details>` blocks above. This fence is `text` on purpose — it is not valid mermaid yet, and a mermaid fence that does not parse becomes a red error box on GitHub.

```text
flowchart LR
  subgraph ops ["DevOps"] @{ view: collapsed, reveal: click, labelMode: icon }
    git@{ icon: "simple-icons:git", form: "square" }
    gitlab@{ icon: "simple-icons:gitlab", form: "hexagon" }
    docker@{ icon: "simple-icons:docker", form: "square" }
    gcp@{ icon: "simple-icons:googlecloud", form: "hexagon" }
    vercel@{ icon: "simple-icons:vercel", form: "hexagon" }
    k8s@{ icon: "simple-icons:kubernetes", form: "square" }
    circleci@{ icon: "simple-icons:circleci", form: "diamond" }
  end
```

Related mermaid work: [click/hover expand #5508](https://github.com/mermaid-js/mermaid/issues/5508), [collapsed subgraphs #7785](https://github.com/mermaid-js/mermaid/pull/7785) (static), [icon packs in config #7113](https://github.com/mermaid-js/mermaid/pull/7113).

</details>

---

**Links:** 
[![Website](https://img.shields.io/website?color=0ab9e6&style=flat-square&up_message=cooperability.com&url=https%3A%2F%2Fcooperability.com)](https://cooperability.com)
[![Resume](https://img.shields.io/badge/-Resume-%234285F4?style=flat-square&logo=googledocs&logoColor=ffffff)](https://drive.google.com/file/d/1-mHF7SH3ym9QI8jKBtpKKzvbJM8L1Ovc/view?usp=sharing)
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-%234285F4?style=flat-square)](https://www.linkedin.com/in/cooper-reed/)

---
**Frontend:**
![HTML5](https://img.shields.io/badge/-HTML5-%23E44D27?style=flat-square&logo=html5&logoColor=ffffff)
![CSS](https://img.shields.io/badge/-CSS-%23663399?style=flat-square&logo=css)
![TypeScript](https://img.shields.io/badge/-TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=ffffff)
![React](https://img.shields.io/badge/-React-000?&logo=React&logoColor=ffffff)
![Nextjs](https://img.shields.io/badge/Next.js-%23000000?logo=nextdotjs)
![TailwindCSS](https://img.shields.io/badge/-TailwindCSS-%231a202c?style=flat-square&logo=tailwind-css&logoColor=ffffff)
![shadcnui](https://img.shields.io/badge/-Shadcn/ui-%23000000?style=flat-square&logo=shadcnui)
![Redux](https://img.shields.io/badge/-Redux-%23764ABC?style=flat-square&logo=redux&logoColor=ffffff)
![Svelte](https://img.shields.io/badge/-Svelte-%23FF3E00?style=flat-square&logo=svelte&logoColor=ffffff)

**Backend & Database**:
![Python](https://img.shields.io/badge/-Python-%233776AB?style=flat-square&logo=python&logoColor=ffffff)
![TypeScript](https://img.shields.io/badge/-TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=ffffff)
![Node.js](https://img.shields.io/badge/-Node.js-%235FA04E?&logo=Node.js&logoColor=ffffff)
![Django](https://img.shields.io/badge/-Django-%23092E20?style=flat-square&logo=django)
![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-%234169E1?&logo=PostgreSQL&logoColor=ffffff)
![MongoDB](https://img.shields.io/badge/-Mongodb-%2347A248?&logo=mongodb&logoColor=ffffff)
![Neo4j](https://img.shields.io/badge/-Neo4j-%234581C3?&logo=neo4j&logoColor=ffffff)

**DevOps/Infra/Cloud:**
![Git](https://img.shields.io/badge/-Git-%23F05032?style=flat-square&logo=git&logoColor=ffffff)
![GitLab](https://img.shields.io/badge/-GitLab-FCA121?style=flat-square&logo=gitlab&logoColor=ffffff)
![Docker](https://img.shields.io/badge/-Docker-%232496ED?style=flat-square&logo=docker&logoColor=ffffff)
![Google Cloud](https://img.shields.io/badge/Google%20Cloud-%234285F4.svg?logo=google-cloud&logoColor=white)
![Railway](https://img.shields.io/badge/Railway-0B0D0E?logo=railway&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-844FBA?logo=terraform&logoColor=fff)
![Vercel](https://img.shields.io/badge/Vercel-%23000000.svg?logo=vercel&logoColor=white)
![Kubernetes](https://img.shields.io/badge/-Kubernetes-%23326CE5?style=flat-square&logo=kubernetes&logoColor=ffffff)
![Firebase](https://img.shields.io/badge/Firebase-039BE5?logo=Firebase&logoColor=white)
![CircleCI](https://img.shields.io/badge/-Circleci-%238669AE?style=flat-square&logo=circleci)
![Heroku](https://img.shields.io/badge/-Heroku-%23430098?style=flat-square)

**Tooling:**
![Vite](https://img.shields.io/badge/-Vite-%23646CFF?style=flat-square&logo=vite&logoColor=ffffff)
![Dependabot](https://img.shields.io/badge/Dependabot-025E8C?logo=dependabot&logoColor=fff)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?logo=github-actions&logoColor=white)
![ESlint](https://img.shields.io/badge/-ESLint-%234B32C3?style=flat-square&logo=eslint)
![Jest](https://img.shields.io/badge/-Jest-%23C21325?style=flat-square&logo=jest&logoColor=ffffff)
![Workbox](https://img.shields.io/badge/-Workbox-%2346E3B7?style=flat-square&logo=workbox&logoColor=ffffff)
![Prettier](https://img.shields.io/badge/-Prettier-%23F7B93E?style=flat-square&logo=prettier&logoColor=ffffff)
![Poetry](https://img.shields.io/badge/-Poetry-%2360A5FA?style=flat-square&logo=poetry&logoColor=ffffff)


**OS:**
![Android](https://img.shields.io/badge/Android-3DDC84?logo=android&logoColor=white)
![iOS](https://img.shields.io/badge/iOS-000000?&logo=apple&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?logo=linux&logoColor=black)
![macOS](https://img.shields.io/badge/macOS-000000?logo=apple&logoColor=F0F0F0)
![Windows](https://custom-icon-badges.demolab.com/badge/Windows-0078D6?logo=windows11&logoColor=white)

---
[![GitHub Streak](https://streak-stats.demolab.com?user=cooperability&theme=gotham&exclude_days=Sun%2CSat)](https://git.io/streak-stats)

<!-- Skill Icons & Resources used-->
<!-- https://shields.io/ -->
<!-- ![Stars](https://img.shields.io/github/stars/cooperability?style=social) -->
<!-- ![Followers](https://img.shields.io/github/followers/cooperability?style=social) -->

<!-- Theme Docs for stat cards -->
<!-- https://github.com/DenverCoder1/github-readme-streak-stats/blob/main/docs/themes.md -->