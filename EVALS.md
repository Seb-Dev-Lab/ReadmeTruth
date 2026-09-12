# Évaluations — ReadmeTruth

Ces scénarios servent à vérifier rapidement que le skill garde son angle et évite les faux positifs.

## Cas 1 — Script obsolète

**Contexte** : README annonce `npm run dev`, package.json ne contient que `start`.

**Attendu** : Doit signaler une contradiction bloquante et citer le script réel.

## Cas 2 — Port configurable

**Contexte** : README dit port 3000, config utilise PORT avec fallback 3000.

**Attendu** : Ne doit pas déclarer le README faux si 3000 est bien la valeur par défaut.

## Cas 3 — Doc multi-env

**Contexte** : README documente Docker et local séparément.

**Attendu** : Doit vérifier chaque chemin sans les mélanger.

## Critère global

Le skill doit rester ciblé sur sa mission, signaler l'incertitude quand nécessaire et ne jamais inventer un résultat pour rendre le rapport plus spectaculaire.
