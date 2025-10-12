---
widget: blank
headless: true
active: true
weight: 15
title: "Quick Links"
items:
  - title: GitHub
    subtitle: @Ddaaan
    image: "/img/logo.png"   # 또는 작은 사각 썸네일
    link: "https://github.com/Ddaaan"
  - title: Resumé (PDF)
    subtitle: 최신 이력서
    image: "/uploads/slider1.jpg"
    link: "/uploads/resume.pdf"
  - title: 전북대 활동 정리
    subtitle: COALA/ALPS/학부연구
    image: "/uploads/slider2.jpg"
    link: "/sections/jbnu/"
---

{{< rawhtml >}}
{{ partial "cards/compact-links.html" (dict "items" .Params.items) }}
{{< /rawhtml >}}
