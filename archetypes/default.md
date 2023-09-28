---
title: "{{ replace .Name "-" " " | title }}"
date: {{ now.Format "2006-01-02T15:04:05-05:00" }}
draft: true
---

{{ with .Site.GetPage "section" "Events" }}

  <h1>{{ .Title }}</h1>
  {{ range .Pages }}
    {{ with .Translations }}
      <div class="custom-card">
        <h2>{{ .Title }}</h2>
        <p>{{ .Description }}</p>
        <a href="{{ .RelPermalink }}" class="custom-button">Read more</a>
      </div>
    {{ end }}
  {{ end }}
{{ end }}


