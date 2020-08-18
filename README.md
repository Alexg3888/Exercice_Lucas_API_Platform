# Exercice_Lucas_API_Platform

Enoncé :
Le 24/08, m'envoyer un lien GitHub vers un fichier Markdown expliquant les extensions Doctrine dans API Platform Note : Je ne veux pas de PDF, ni de document Word. Vous repasserez sur l'intérêt des interfaces et le polymorphisme. Vous parlerez également de l'auto-configuration dans le container de services de Symfony

- Les extensions Doctrine dans API Platform :
Elles permettent de faciliter/simplifier la création d’une API et ainsi concentrer le développeur sur la partie métier. API Platform fournit un moyen de créer ses propres extensions de doctrine, permettant de modifier les requêtes de collection et d'élément pour les ressources API.
L’intérêt est que cela permet de personnaliser ou de créer une logique de requête conditionnelle sur les requêtes générées par les contrôleurs par défaut fournis par API Platform. Il n'est pas nécessaire de créer un contrôleur personnalisé si on souhaite simplement modifier la requête correspondante.

- Les interfaces :
Une interface est une sorte de contrat qui indique ce que la classe qui l'implémente offre comme service. C’est une sorte de classe abstraite qui a pour rôle décrire un comportement à notre objet. Les interfaces regroupent la signature des méthodes, donc ça spécifie les méthodes avec les paramètres d’entrées, les retours, les paramètres de sorties, qui pourront être utilisées sur l’instance d’une classe. 
En implémentant une interface, l’intérêt est qu’une classe est obligée de définir toutes les méthodes de l’interface. Elles permettent également de structurer le code.

- Le polymorphisme :
Le polymorphisme est un mécanisme qui permet de modifier le comportement d’une classe fille par rapport à sa classe mère. Il permet à des types et a des interfaces d’hériter de parents plus généralisés. 
L’intérêt du polymorphisme est de pouvoir manipuler plusieurs classes sans se soucier du type de l’objet, car toutes ces classes se manipulent de la même façon étant donné qu’elles héritent de la même interface (ou classe abstraite). Cela permet aussi d’éviter des erreurs, comme appeler la fonction avec un mauvais type, là il n’y a pas d’ambigüité sur le type de paramètre utilisé.

- L'auto-configuration dans le container de services de Symfony :
Pour cela, on utilise le fichier qui permet une configuration par défaut « services.yml » dans « app/config ». Cela permet de configurer automatiquement toutes les classes du dossier « src » en tant que service, sans avoir à le configurer manuellement. Les classes sont alors autowiré. Cela s’applique également aux interfaces.
L’Autowiring (câblage-automatique) permet de gérer les services dans le conteneur de service avec une configuration minimale. Il lit les Type-Hinting (les indications de type) du constructeur (ou d'autres méthodes) et passe automatiquement les services corrects à chaque méthode. L’intérêt est que si Symfony n’arrive pas à déterminer qu’elle dépendance doit être transmise, alors une exception exploitable sera remontée. Cela signifie qu’on est sûr qu'une dépendance appropriée a été injectée. Pour cela, l’Autowiring recherche un service dont l’Id correspond au Type-Hinting. D’autre part, en utilisant le Type-Hinting avec une interface plutôt qu'une classe, on peut rendre le choix de la dépendance plus flexible. Et si on utilise que les méthodes de l'interface, alors on gagne cette flexibilité tout en utilisant l'objet en toute sécurité.
