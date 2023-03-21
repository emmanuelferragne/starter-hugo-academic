+++
title = "Analyse phonétique de la variation inter-locuteurs au moyen de réseaux de neurones convolutifs : voyelles seules et séquences courtes de parole"
publishDate = 2022-05-18T00:00:00  # Schedule page publish date.
draft = false

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date = 2022-06-16T16:00:00
#time_end = 2019-06-05T15:18:00

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["Cédric Gendrot", "Emmanuel Ferragne", "Anaïs Chanclu"]

# Abstract and optional shortened version.
abstract = "Des réseaux de neurones convolutifs ont été entraînés sur des spectrogrammes de voyelles /ɑ̃/ et de séquences aléatoires de 2 secondes extraites de 44 locuteurs du corpus NCCFr afin d’obtenir une classification de ces derniers. Ces deux modèles présentent une répartition équivalente des locuteurs dans l'espace acoustique, ce qui suggère que la classification a été faite sur des critères indépendants des phonèmes précis extraits. De multiples mesures phonétiques ont été effectuées afin de tester leur corrélation avec les représentations obtenues : la f0 apparait comme le paramètre le plus pertinent, suivie par plusieurs paramètres liés à la qualité de la voix. Des zones d’activation (Grad-CAM : Gradient-weighted Class Activation Mapping) ont été calculées a posteriori afin de montrer les zones spectrales et temporelles utilisées par le réseau. Une analyse quantitative de ces cartes d'activation a donné lieu à des représentations des locuteurs qui ne sont pas corrélées aux mesures phonétiques."
abstract_short = "... réseaux de neurones convolutifs ont été entraînés sur des spectrogrammes de voyelles /ɑ̃/ et de séquences aléatoires de 2 secondes..."

# Name of event and optional event URL.
event = "Journées d'Études sur la Parole"
event_url = "https://jep2022.univ-nantes.fr/"

# Location of event.
location = "Noirmoutier"

# Is this a featured talk? (true/false)
featured = false

# Projects (optional).
#   Associate this talk with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["deep-learning"]` references 
#   `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects = ["voxcrim"]
#projects = []

# Tags (optional).
#   Set `tags = []` for no tags, or use the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Phonetics", "Deep Learning"]

# Slides (optional).
#   Associate this talk with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references 
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides = ""

# Links (optional).
url_pdf = ""
url_slides = ""
url_video = ""
url_code = ""

# Does the content use math formatting?
math = true

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
[image]
  # Caption (optional)
  #caption = "Photo by Leo Wieling on Unsplash"

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Smart"
+++
