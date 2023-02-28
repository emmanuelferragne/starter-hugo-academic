+++
title = "Données COVID-19"
subtitle = "Quelques visualisations"

date = 2020-03-25T00:00:00
lastmod = 2020-03-25T00:00:00
draft = false

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["Admin"]

tags = ["Data Science", "Deep Learning"]
summary = "Quelques visualisations"
[image]
  # Caption (optional)
  #caption = "Photo by Vlah Dumitru on Unsplash"

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = ""

  # Show image only in page previews?
  preview_only = false

+++


La crise que nous traversons est aussi l'occasion de mettre à profit de nombreuses techniques de visualisations des données et de *machine learning*.  Les données de Santé publique France que j'ai utilisées sont téléchargeables [ici] (https://www.data.gouv.fr/fr/datasets/donnees-hospitalieres-relatives-a-lepidemie-de-covid-19/). La représentation ci-dessous montre le nombre d'hospitalisations liées au COVID-19 comptabilisées chaque jour par région :

<div class="flourish-embed flourish-bar-chart-race" data-src="visualisation/1757900" data-url="https://flo.uri.sh/visualisation/1757900/embed"><script src="https://public.flourish.studio/resources/embed.js"></script></div>

L'animation suivante montre le nombre d'hospitalisations par jour liées au COVID-19 dans 3 départements très touchés et 3 départements peu touchés (choisir la vue 'Ranks' pour mieux voir ces derniers) :

<div class="flourish-embed flourish-chart" data-src="visualisation/1764467" data-url="https://flo.uri.sh/visualisation/1764467/embed"><script src="https://public.flourish.studio/resources/embed.js"></script></div>

C'est aussi l'occasion de se souvenir du principe d' **intégrité graphique** d'Edward Tufte : sans que l'intention soit malhonnête, un graphique peut déformer notre perception des données. Le graphique ci-dessous montre le nombre de décès du COVID-19 (à partir du moment où le 10e décès est survenu) dans les 9 pays les plus touchés (données de l'[Université Johns Hopkins] (https://data.humdata.org/dataset/novel-coronavirus-2019-ncov-cases)) le 2 avril 2020. La représentation de gauche (celle trouvée dans la presse) montrait la France dans le tiers supérieur, non loin de l'Italie, alors que les chiffres sont très différents (FR: 4043 IT: 13155). L'échelle logarithmique "écrase" par définition les valeurs élevées mais permet de mieux distinguer les courbes des pays ayant des valeurs plus basses. A l'inverse, la même figure avec une échelle linéaire (graphe de droite) reflète plus fidèlement les chiffres bruts. On y voit clairement qu'il y a 3 fois plus de décès en Italie qu'en France. Chaque version est un compromis. Comme dans de nombreux domaines de la perception humaine, l'échelle logarithmique se rapproche peut-être davantage de la manière dont nous "ressentons" ces chiffres.

![linVsLog] (linVsLog.png)

Le graphique suivant montre le lien entre la population d'un département et le (logarithme du) nombre de décès liés au COVID-19 enregistrés. La courbe bleue matérialise l'équation qui résume au mieux ce lien :

*logarithme-nombre-décès = 0,098 × nombre d'habitants<sup>0,293</sup>*

![popVsDC] (lienPopDC.png)

Le cartogramme de diffusion[^1] est une représentation que j'aime particulièrement. Dans celui-ci, j'ai déformé les régions de France métropolitaine de sorte que la taille des régions reflète le nombre d'hospitalisations au 7 avril 2020 :

![cartogramme] (cartogram.png)
Sans surprise, l'Île de France (en orange clair) occupe une bonne partie de l'espace, ainsi que la région Grand Est (en vert). 

Les méthodes de l'intelligence artificielle (en particulier, le **deep learning**) sont également mises à contribution. Ce qui suit n'a absolument aucune valeur médicale[^2] mais n'est pas dénué d'intérêt pédagogique. J'ai confié à un réseau de neurones convolutif la tâche d'apprendre automatiquement la disctinction entre radiographies du thorax montrant des cas de COVID-19 et radiographies du thorax de patients[^3] sans pathologie (115 images de chaque). Sur cet ensemble limité, l'algorithme parvient à distinguer les deux types de radiographies dans 100% des cas. La méthode Grad-CAM met en surbrillance les régions des images sur lesquelles l'algorithme s'appuie pour faire sa classification :

![gradCamRadio] (gradCamRadio.png)

- Avec ce type d'algorithme, on retiendra que l'expert humain n'a pas à dire ce qu'il doit aller chercher dans l'image ; il s'en charge tout seul :thumbsup:

- C'est le même algorithme qui peut être utilisé tel quel dans des domaines très variés ; nous l'avons utilisé pour l'étude de la prononciation dans [cette publication](https://www.isca-speech.org/archive/Interspeech_2019/abstracts/2851.html), et dans [celle-là](https://icphs2019.org/icphs2019-fullpapers/pdf/full-paper_792.pdf) :thumbsup:

- Grad-CAM et les méthodes assimilées permettent de comprendre les choix de l'algorithme :thumbsup:, montrant parfois (comme dans notre publication [ici](https://www.isca-speech.org/archive/Interspeech_2019/abstracts/2851.html)) qu'il peut prendre de bonnes décisions pour de mauvaises raisons  :thumbsdown:

[^1]: Gastner MT, Seguy V, More P. Fast flow-based algorithm for creating density-equalizing map projections. Proc Natl Acad Sci USA 115(10):E2156–E2164 (2018).
[^2]: D'abord et surtout parce que je ne suis pas médecin. Ensuite, mon échantillon est de taille limitée. Et puis cela n'a pas été soumis à la critique de plusieurs experts (condition absolue pour toute étude scientifique). Et enfin, parce que je soupçonne fortement un biais dans les données.
[^3]: Les données COVID proviennent de [ce site](https://github.com/ieee8023/covid-chestxray-dataset) d'où je n'ai extrait que les vues postéro-antérieures. Les images de sujets sains ont été extraites de façon aléatoire de [cet ensemble de données](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia).


