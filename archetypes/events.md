---
title: "Events"
date: { { now.Format "2006-01-02T15:04:05-07:00" } }
featured_image: ""
description: ""
draft: true
type: events
tags: ["events"]
menu:
  main:
    weight: 7
    parent: events
some_other_value:
  { { .Site.Params.some_other_value | default "Default Value" } }
---

{{ with .Site.GetPage "section" "Events" }}

  <h1>{{ .Title }}</h1>
  {{ range .Pages }}
    {{ with .Translations }}
      <div class="custom-card">
        <h2>{{ .Title }}</h2>
        <p>{{ .Description }}</p>
        <a href="{{ .RelPermalink }}" class="custom-button">Leer más</a>
      </div>
    {{ end }}
  {{ end }}
{{ end }}
