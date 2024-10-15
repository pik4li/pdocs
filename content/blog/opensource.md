---
title: "Opensource"
description: ""
summary: ""
date: 2024-10-15T22:08:25+02:00
lastmod: 2024-10-15T22:08:25+02:00
draft: false
toc: true
weight: 50
categories: []
tags: []
contributors: []
pinned: true
homepage: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

# Open Source: Warum ich konsequent auf freie Software setze

Proprietäre Software von großen Anbietern wie Microsoft und VMware dominiert in vielen Unternehmen, aber für mich führt kein Weg an Open Source vorbei. Diese Entscheidung kommt nicht von ungefähr – Open-Source-Lösungen bieten entscheidende Vorteile in Sachen **Sicherheit**, **Flexibilität** und **Kostenersparnis**. Im Folgenden gehe ich näher darauf ein und zeige, warum Open Source für mich nicht nur eine Alternative, sondern oft die bessere Wahl ist.

## Sicherheit und Transparenz

Während bei proprietärer Software der Quellcode geschlossen ist, kann bei Open Source jeder den Code einsehen. Das bedeutet, dass Sicherheitslücken oft schneller gefunden und behoben werden, weil die ganze Community daran arbeitet. Ich selbst habe schon häufiger erlebt, dass Bugs bei Open-Source-Projekten in wenigen Tagen behoben wurden – oft viel schneller als bei kommerziellen Lösungen.

Beispiel: Für meinen Homelab bin ich von Hyper-V auf Proxmox umgestiegen. Das Resultat? Bessere Performance, niedrigere Ressourcenbelastung und vor allem weniger Sicherheitsbedenken. Mit Open Source habe ich volle Kontrolle über das System und die Möglichkeit, Fehler und Schwachstellen direkt anzugehen.

## Kostenersparnis: Keine versteckten Gebühren

Im Gegensatz zu großen Anbietern, bei denen Lizenzgebühren, Abos und Supportkosten anfallen, ist Open Source kostenlos nutzbar. Das spart bares Geld – und es gibt keine versteckten Kosten in Form von Telemetriedaten, die den Herstellern Einblick in Ihr Nutzerverhalten gewähren.

Ein konkretes Beispiel: Ein Kunde von mir nutzte einen kostenpflichtigen Cloud-Passwortmanager. Nachdem wir auf KeePass umgestellt haben, spart er nun jährlich eine Menge Geld, und die Daten liegen sicher auf seinem eigenen Gerät.

## Flexibilität: Anpassungen, wann immer nötig

Open Source ermöglicht es mir, Software exakt auf meine Bedürfnisse zuzuschneiden. Mein Linux-Desktop mit Hyprland ist komplett nach meinen Vorstellungen konfiguriert. Und das Beste: Ich kann die Konfiguration jederzeit anpassen oder erweitern, ohne auf Updates oder Genehmigungen eines Anbieters angewiesen zu sein.

Dasselbe gilt für Docker – die Containerisierungslösung, die ich für fast alle meine Anwendungen nutze. Ob Vaultwarden, BookStack oder Traefik: Mit Docker kann ich meine Anwendungen isoliert und sicher betreiben, ohne dass sie sich gegenseitig beeinflussen.

## Open Source als Lernplattform

Open Source hat für mich nicht nur beruflich, sondern auch persönlich eine immense Bedeutung. Mit Tools wie Git konnte ich tiefere Einblicke in die Softwareentwicklung gewinnen. Ich sehe mir regelmäßig die Commits und Pull Requests anderer Entwickler an und lerne daraus neue Lösungsansätze. Das inspiriert mich, selbst kreativ zu werden und meine eigenen Projekte kontinuierlich zu verbessern.

## Proprietäre Software? Nicht immer die beste Wahl

Natürlich gibt es Szenarien, in denen proprietäre Software nötig ist – zum Beispiel bei der Nutzung von Microsoft 365 oder Teams in größeren Unternehmen. Doch wann immer es geht, setze ich auf Open Source. Hier ist eine kurze Übersicht von Open-Source-Alternativen zu gängigen proprietären Lösungen:

| **Kommerzielle Software** | **Open-Source-Alternative** |
| ------------------------- | --------------------------- |
| Microsoft Office          | LibreOffice, OnlyOffice     |
| Windows Server            | Ubuntu Server, CentOS       |
| VMware                    | Proxmox                     |
| Microsoft Edge/Chrome     | Firefox                     |
| Cloud-Passwortmanager     | KeePass                     |
| Adobe Photoshop           | GIMP                        |
| Slack/MS Teams            | Mattermost, Rocket.Chat     |

### Warum Microsoft Edge keine gute Wahl ist

Microsoft Edge ist vielleicht in vielen Windows-Systemen als Standardbrowser voreingestellt, doch das bedeutet nicht, dass er die beste Option ist. Microsoft hat in der Vergangenheit immer wieder die Leistungsmessungen zugunsten von Edge angepasst, um ihn schneller und ressourcenschonender wirken zu lassen. In der Praxis sieht das jedoch anders aus: Der Browser ist überladen ("bloated") und beansprucht bei längerer Nutzung deutlich mehr RAM und CPU-Ressourcen als nötig.

Open-Source-Browser wie der [Zen-Browser](https://zen-browser.app/) bieten hier einen klaren Vorteil: Sie verzichten auf unnötigen Ballast und fokussieren sich auf Performance und Benutzerfreundlichkeit. In meinen Tests konnte ich feststellen, dass Zen-Browser-Seiten um bis zu 30% schneller lädt als Edge und dabei signifikant weniger RAM verbraucht.

Ein kurzer Feature-Vergleich zeigt, wo die Unterschiede liegen:

| **Feature**                     | **Microsoft Edge**          | **Zen-Browser (Open Source)**        |
| ------------------------------- | --------------------------- | ------------------------------------ |
| **Werbetracking**               | Ja, umfangreich integriert  | Nein, standardmäßig blockiert        |
| **RAM-Verbrauch (bei 10 Tabs)** | Hoch (>1GB)                 | Niedrig (<500MB)                     |
| **Anpassungsmöglichkeiten**     | Begrenzt                    | Umfangreich durch freie Add-Ons      |
| **Geschwindigkeit**             | Durchschnittlich            | Hervorragend, optimiert für Speed    |
| **Transparenz**                 | Keine Einblicke in den Code | Quellcode einsehbar und anpassbar    |
| **Erweiterte Telemetrie**       | Aktiviert                   | Keine, da keine Daten erhoben werden |

Wer auf unnötige Funktionen und versteckte Telemetrie verzichten will, ist mit einem Open-Source-Browser definitiv besser beraten. Die Freiheit, den Code selbst anzupassen und genau zu wissen, welche Daten wohin fließen, schafft Vertrauen und sorgt für eine bessere Performance – und das ganz ohne die Ressourcenverschwendung, die viele kommerzielle Browser mit sich bringen.

---

## Fazit: Open Source als Zukunft der IT

Open Source ist für mich nicht nur eine Alternative, sondern oft die erste Wahl. Es bietet mehr Sicherheit, Flexibilität und Anpassungsmöglichkeiten, als es die großen Anbieter jemals könnten. Wer unabhängig und effizient arbeiten möchte, sollte Open Source eine Chance geben – die Vorteile sprechen für sich!
