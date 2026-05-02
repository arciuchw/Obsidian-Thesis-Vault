Key takeaways:
>Likelihood distance i tym podobne mają wadę taką, że polegają na Inception-V3 trenowanych na ImageNet, przez co może się okazać że nie będzie to okej


Metryka RL2: przepływ normalizujący stosowany do cech obrazu wydobytych przez pretrenowany ResNet-18 i obllicza root mean square distance pomiędzy wektorami przestrzeni ukrytej obrazów wygenerowanych i oryginalnych.

Startuje się ze zbiorem oryginalnych obrazów R i obrazó wygenerowanych G.

ResNet wydobywa cechy z obrazów R, robi to tylko raz i to jest lżejszy model niż incepcja albo CLIP

Normalizacja pozwala tez zredukować rozmiar przestrzeni ukrytej.

Oni to testowali na FocusPath Dataset
