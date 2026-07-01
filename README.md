## Analyse pédagogique — Pont vers le Jour 3

**1. Que devient la colonne de filtrage de 300px sur un smartphone de 360px ?**
La grille CSS (`grid-template-columns: 300px 1fr`) impose une largeur fixe de 300px 
à la colonne de filtres, quelle que soit la taille de l'écran. Sur un écran de 360px, 
cela laisse à peine 60px pour la seconde colonne, donc le panneau de filtres occupe 
presque tout l'écran et pousse le reste du contenu hors de la zone visible.

**2. Le tableau reste-t-il lisible ou provoque-t-il une barre de défilement horizontale ?**
Le tableau devient illisible : ses 5 colonnes (Horodatage, ID Événement, IP Source, 
Type d'Attaque, Action Parefeu) nécessitent plus de largeur que ce que l'écran offre. 
Une barre de défilement horizontale apparaît, ce qui rend la consultation des logs 
peu pratique sur mobile — l'utilisateur doit scroller latéralement pour lire chaque ligne.

**3. Pourquoi Grid/Flexbox ont besoin d'instructions conditionnelles supplémentaires ?**
CSS Grid et Flexbox positionnent les éléments selon les règles qu'on leur donne, 
mais ils ne changent pas ces règles automatiquement en fonction de la taille de 
l'écran. Une valeur fixe comme `300px` reste 300px sur toutes les tailles d'écran. 
Pour adapter la mise en page (par exemple, passer la grille en une seule colonne 
sur mobile avec `grid-template-columns: 1fr`), il faut utiliser des **media queries** 
(`@media (max-width: 768px) { ... }`), qui permettent d'appliquer des styles 
différents selon la largeur de la fenêtre. C'est précisément ce que nous verrons 
au Jour 3 : le responsive design.
