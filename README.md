# REPO-MOVIES

Guidelines
Objectif
Descriptif
Notes
Feuille de route (ROADMAP)
Architecture
Technos
etc
MOVIE LENS EXPLORATION :
statistiques usuelles
 n categories des films ?
 LES N mieux notés categories/toutes categories confondues
 posez vous des questions
 utilisez la data pour y repondre
 (parquet)(csv) _>spark sql
CAPTAIN LOG apres-midi :
Select Comedy Movies Only
14 h 57
Display the TOP rated Comedy Movies
14 h 58
MOST Rated Comedy Movies - No matter the rating
14 h 58
BEST Rated Comedy Movies
14 h 58
ou :
changer de genre (à votre discrétion)
Comedy est juste un exemple (modifié) 
14 h 58
Most Rated Comedy Movies, grouped by Movie & Rating
14 h 59
Top Rated Comedy Movies with most ratings
15 h 01
Bonus 1 :
Créer un Dataframe à part Pour les GENRES et les ID de genre, et dénormaliser (modifié) 
Nouveau
15 h 02
Bonus 2 :
En faire de même pour tous les genres listés (automatiser via du code pour boucler autour d'une liste de genre prépopulée, ou meme un dataframe de genre distincts - préférable)

CAPTAIN LOG ce matin 4/07/2023

comprendre L’algorithme de filtrage collaboratif
Comprendre et etre capable de l'expliquer a un enfant de un enfant de 10 ANS
COMPRENDRE les mathematiques sous jacente
"ce qui se concoit bien s'enonce clairment et les mots pour le dire viennent aisment " Nicolas Boileau
REDIGER son propre ABSTRACT de L ALS MATH INCLUE /
def:
Un abstract présente en 100-150 mots
la substantifique moelle du travail.

l'intérêt de la question
la problématique
quelques mots de méthodologie
les résultats principaux
quelques conclusions et leurs implications

 Voici un exemple d'abstract pour la factorisation matricielle des moindres carrés alternés (ALS) dans le filtrage collaboratif :

"La factorisation matricielle des moindres carrés alternés (ALS) est une technique largement utilisée dans le domaine du filtrage collaboratif. Cet article explore l'application de l'algorithme ALS pour résoudre le problème de recommandation personnalisée en exploitant les évaluations des utilisateurs sur une matrice d'évaluations des utilisateurs-produits. L'approche ALS vise à décomposer cette matrice en deux matrices de facteurs latents, représentant les utilisateurs et les produits, respectivement. En utilisant un processus itératif de minimisation des moindres carrés, les matrices de facteurs latents sont ajustées pour minimiser la différence entre les évaluations réelles et les prédictions. L'aspect clé de l'ALS réside dans l'alternance entre la mise à jour des facteurs utilisateur et la mise à jour des facteurs produit, ce qui permet une convergence progressive vers une meilleure approximation de la matrice d'évaluations. L'article présente également des variantes et des extensions de l'ALS, ainsi que des méthodes pour traiter des défis tels que la gestion des valeurs manquantes et la régularisation des facteurs latents. Les résultats expérimentaux démontrent l'efficacité de l'ALS dans la génération de recommandations précises et personnalisées, ce qui en fait une technique essentielle dans le domaine du filtrage collaboratif."

 Voici l'algorithme ALS sous sa forme mathématique :

Données d'entrée :

R : Matrice d'évaluations des utilisateurs-produits de taille N x M
K : Nombre de facteurs latents
max_iterations : Nombre maximal d'itérations
alpha : Paramètre de régularisation pour contrôler la complexité du modèle
Initialisation :

Initialiser P : Matrice de facteurs utilisateur de taille N x K avec des valeurs aléatoires
Initialiser Q : Matrice de facteurs produit de taille M x K avec des valeurs aléatoires
Boucle principale :
Pour itération = 1 à max_iterations :
Pour chaque utilisateur u de 1 à N :
Fixer Q et résoudre pour P[u] en minimisant la fonction de coût :
P[u] = argmin(P[u]) ||R[u] - P[u] * Q^T ||^2 + alpha * ||P[u]||^2

Pour chaque produit i de 1 à M :
Fixer P et résoudre pour Q[i] en minimisant la fonction de coût :
Q[i] = argmin(Q[i]) ||R[:,i] - P * Q[i]^T ||^2 + alpha * ||Q[i]||^2

Sortie :

P : Matrice de facteurs utilisateur mise à jour
Q : Matrice de facteurs produit mise à jour
Dans cet algorithme, nous alternons entre la mise à jour des facteurs utilisateur (P) et la mise à jour des facteurs produit (Q) de manière itérative. Pour chaque itération, nous fixons une matrice et optimisons l'autre en utilisant la méthode des moindres carrés pour minimiser la différence entre les évaluations réelles et les prédictions.

La régularisation (contrôlée par le paramètre alpha) est utilisée pour éviter le surapprentissage et améliorer la généralisation du modèle.

Notez que la fonction de coût est formulée en utilisant la norme euclidienne (|| ||^2), mais d'autres mesures de distance peuvent également être utilisées.

en resumé :
Pourquoi c'est intéressant (L'approche ALS vise à décomposer cette matrice en deux matrices de facteurs latents, représentant les utilisateurs et les produits, respectivement. En utilisant un processus itératif de minimisation des moindres carrés, les matrices de facteurs latents sont ajustées pour minimiser la différence entre les évaluations réelles et les prédictions.)

La problématique (résoudre le problème de recommandation personnalisée en exploitant les évaluations des utilisateurs ?)

Quelques mots de méthodologie (L'approche ALS vise à décomposer cette matrice en deux matrices de facteurs latents, représentant les utilisateurs et les produits, respectivement. En utilisant un processus itératif de minimisation des moindres carrés, les matrices de facteurs latents sont ajustées pour minimiser la différence entre les évaluations réelles et les prédictions )

Résultats (Dans la matrice d’interaction utilisateur-élément clairsemée, l’évaluation prédite que l’utilisateur donnera à l’élément est calculée comme suit :ui


où H est la matrice utilisateur, W est la matrice d’éléments
L’évaluation de l’élément donnée par l’utilisateur peut être exprimée comme un produit ponctuel du vecteur latent de l’utilisateur et du vecteur latent de l’élément.iu...)

Conclusions : les implications de ces résultats .)
