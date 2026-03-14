# Amsterdam Local Companion — Codebase Diagram

## Project structure & relationships

```mermaid
flowchart TB
    subgraph root["📁 Project Root"]
        index["index.html"]
        styles["styles.css"]
        readme["README.md"]
        gitignore[".gitignore"]
    end

    subgraph images["📁 images/"]
        street["street-ams.jpg"]
        house["house-ams.jpg"]
        canal["canalview-ams.jpg"]
        enrique["enrique.jpg"]
    end

    subgraph page["index.html page structure"]
        hero["Hero (banner)"]
        activities["Activities section"]
        guide["Guide section"]
    end

    index --> styles
    index --> hero
    index --> activities
    index --> guide

    hero --> herobox["hero-text-box\n(Amsterdam + tagline)"]

    activities --> card1["Activity card 1"]
    activities --> card2["Activity card 2"]
    activities --> card3["Activity card 3"]

    card1 --> street
    card2 --> house
    card3 --> canal

    guide --> enrique
    guide --> guidetext["guide-text\n(Local Companion)"]
```

## Section → CSS mapping

```mermaid
flowchart LR
    subgraph html["index.html sections"]
        H1[".hero"]
        H2[".activities"]
        H3[".guide"]
    end

    subgraph css["styles.css"]
        C1["body, h1, h2\ncolors, typography"]
        C2[".hero, .hero-text-box\nbanner layout"]
        C3[".activities,\n.activities-container,\n.activity-item"]
        C4[".guide, .guide-text"]
    end

    H1 --> C1
    H1 --> C2
    H2 --> C3
    H3 --> C4
```

## File tree (project assets only)

```
amsterdam-local-companion-project/
├── index.html          ← Single-page app entry
├── styles.css          ← Global & section styles
├── README.md
├── .gitignore
└── images/
    ├── street-ams.jpg   (activity: wander streets)
    ├── house-ams.jpg    (activity: canal house)
    ├── canalview-ams.jpg (activity: canal cruise)
    └── enrique.jpg      (guide avatar)
```

---

*View this file in an editor or GitHub that supports Mermaid to see the diagrams rendered.*
