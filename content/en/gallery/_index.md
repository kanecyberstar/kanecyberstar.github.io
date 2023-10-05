---
title: Welcome to Peckerwood's! 
---
{{< brick_intro >}}

# Gallery

 Herein lies a refined collection, a portrait-parade-pandemonium if you will, shedding light on the life and times of the ever-so-intriguing Uncle Pecker. A true window into his worldly wanderings!


{{< /brick_intro >}}


{{ $dir := string (.Get "dir") }}
<ul class="image-gallery">
{{ range (readDir (print "/static" $dir)) }}
  {{- $image := resources.Get (printf "%s/%s" $dir .Name) -}}
  {{- $imageurl := printf "%s/%s" $dir .Name -}}
  {{- $imagetitle := index (split .Name ".") 0 -}}
    <li>
      <a href="{{ ($image.Fit "1600x1600 Center q50").Permalink }}">
        <img src="{{ ($image.Fill "300x300 Center q50").Permalink }}" alt="Image {{ $imagetitle }}" />
      </a>
    </li>
{{ end }}
</ul>