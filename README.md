# 🤥 ReadmeTruth

**Le skill qui vérifie si ton README raconte encore la vérité.**

Vérifie chaque instruction importante du README contre le vrai projet.

## Exemple d'utilisation

### Claude Code

```text
/readme-truth
```

### Codex

```text
$readme-truth
```

Tu peux aussi décrire directement la tâche en langage naturel : le skill est conçu pour être déclenché quand le problème correspond à sa description.

## Installation

### Claude Code — utilisateur

```bash
git clone https://github.com/Seb-Dev-Lab/ReadmeTruth.git ~/.claude/skills/readme-truth
```

### Claude Code — projet

```bash
git clone https://github.com/Seb-Dev-Lab/ReadmeTruth.git .claude/skills/readme-truth
```

### Codex — utilisateur

```bash
git clone https://github.com/Seb-Dev-Lab/ReadmeTruth.git ~/.agents/skills/readme-truth
```

### Codex — projet

```bash
git clone https://github.com/Seb-Dev-Lab/ReadmeTruth.git .agents/skills/readme-truth
```

## Pourquoi ce skill est volontairement petit

ReadmeTruth est un **micro-skill SebDevLab** : un problème précis, une mission claire, aucune dépendance obligatoire et pas de grosse usine à gaz.

Le cœur du projet est `SKILL.md`. Il peut être copié dans tout client compatible avec le format Agent Skills.

## Fichiers

- `SKILL.md` — comportement du skill ;
- `EVALS.md` — petits scénarios de validation ;
- `agents/openai.yaml` — métadonnées pour les clients OpenAI compatibles ;
- `LICENSE` — MIT.

## Licence

MIT — libre à utiliser, modifier et partager.
