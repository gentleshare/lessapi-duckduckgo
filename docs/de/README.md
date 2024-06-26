# LessAPI-DuckDuckGo
[![GitHub](https://img.shields.io/github/license/lessapi-dev/lessapi-duckduckgo?style=for-the-badge)](https://github.com/lessapi-dev/lessapi-duckduckgo)
[![Docker](https://img.shields.io/docker/pulls/lessapi/lessapi-duckduckgo?style=for-the-badge)](https://hub.docker.com/r/lessapi/lessapi-duckduckgo)

[English](./../../README.md) |
[简体中文](./../zhs/README.md) |
[繁體中文](./../zht/README.md) |
[日本語](./../ja/README.md) |
[한국어](./../ko/README.md) |
[Русский](./../ru/README.md) |
[Deutsch](./../de/README.md) |
[Français](./../fr/README.md) |
[Español](./../es/README.md) |
[Italiano](./../it/README.md) |
[Português](./../pt/README.md)

(Aktuelle Sprachdokumente wurden durch KI übersetzt generiert, im Zweifelsfall bitte auf die Dokumente in vereinfachtem
Chinesisch oder Englisch verweisen.)

---

## Einführung

LessAPI-DuckDuckGo ist ein Suchmaschinen-API-Dienst.
Basierend auf playwright und der DuckDuckGo-Suchmaschine, wird nach der Verpackung ein einfacher API-Endpunkt
implementiert.
Einfach, leicht, zuverlässig, Docker-Deployment, einfach zu warten.

## Status

> Experimentell in der Entwicklung, nicht empfohlen für die Verwendung in Produktionsumgebungen.

## Nutzung

### OpenAPI-Standarddokument (Swagger 3.0)

[OpenAPI-Standarddokument (Swagger 3.0)](../../resource/openapi.json)

### Textsuche `GET /search/text`

**Anforderungsparameter:**

- keyword: Suchschlüsselwort (Pflichtfeld)
- region: Region (optional) z.B. en-US, fr-FR, zh-CN, ru-RU, usw. Standardwert ist en-US
- maxCount: Maximale Rückgabeanzahl (optional) Standardwert ist 20
- viaProxyUrl: Adresse des Proxys, der vom Browser verwendet wird (optional) z.B. http://proxy.server:3000 Standardwert
  ist leer

**Anfragebeispiel:**

```shell
curl 'http://127.0.0.1:8080/search/text?keyword=hello&maxCount=2'
```

**Antwortbeispiel:**

```json
{
  "code": "success",
  "data": {
    "results": [
      {
        "order": 1,
        "title": "Adele - Hello (Official Music Video) - YouTube",
        "url": "https://www.youtube.com/watch?v=YQHsXMglC9A",
        "description": "Listen to \"Easy On Me\" here: http://Adele.lnk.to/EOMPre-order Adele's new album \"30\" before its release on November 19: https://www.adele.comShop the \"Adele..."
      },
      {
        "order": 2,
        "title": "Hello Definition & Meaning - Merriam-Webster",
        "url": "https://www.merriam-webster.com/dictionary/hello",
        "description": "Learn the origin, usage, and synonyms of the word hello, an expression or gesture of greeting. See examples of hello in sentences and related words from the dictionary."
      }
    ]
  }
}
```

## Lizenz

[MIT](./../../LICENSE)
