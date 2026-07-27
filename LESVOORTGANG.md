# Git-les: voortgang

Oefen-repo voor het leren van git/GitHub. Status op dit moment: op branch `main`,
working tree clean, 3 branches aanwezig (`main`, `recept`, `weekmenu` — beide al
gemerged in main, fast-forward).

## Behandeld en begrepen

- **Mentale model**: working directory → staging area (`git add`) → local
  repository (`git commit`) → later: remote/GitHub (`git push`/`git pull`)
- **Git vs GitHub**: git = lokaal versiebeheer-programma, GitHub = hosting-dienst
  erbovenop voor samenwerken
- **Basiscommando's**: `git status`, `git add`, `git commit -m "..."`, `git log
  --oneline`, `git diff`
- **Wat een commit is**: snapshot + hash + boodschap + verwijzing naar parent-commit
  (vormt een keten)
- **HEAD**: pointer die aangeeft op welke branch/commit je nu staat
  (`HEAD -> main`)
- **Branches**: `git checkout -b <naam>` (nieuwe branch), `git checkout <naam>`
  (wisselen), `git branch` (overzicht, `*` = huidige)
- **Merge**: `git merge <branch>` — hier steeds fast-forward (geen conflicten)
- Per ongeluk in vim beland via `git commit` zonder `-m` → opgelost met `Esc`,
  `:q!`

## Geleerde commando's

| Commando | Wat het doet |
|---|---|
| `git init` | Start een nieuwe git-repository in de huidige map |
| `git status` | Toont wat er veranderd is en in welke fase (untracked / staged / clean) |
| `git add <bestand>` | Zet een bestand in de staging area, klaar voor de volgende commit |
| `git commit -m "boodschap"` | Legt de staged wijzigingen vast als een nieuwe commit in de geschiedenis |
| `git log` | Toont de volledige commit-geschiedenis |
| `git log --oneline` | Compacte versie: één regel per commit (hash + boodschap) |
| `git diff` | Toont regel voor regel wat er gewijzigd is t.o.v. de laatste commit (nog niet gestaged) |
| `git branch` | Toont alle branches, `*` markeert de huidige |
| `git checkout -b <naam>` | Maakt een nieuwe branch aan én schakelt er meteen naartoe |
| `git checkout <naam>` | Schakelt naar een bestaande branch |
| `git merge <branch>` | Voegt de opgegeven branch samen in de branch waar je nu op staat |

## Nog te doen

1. **Merge conflicts** — wat er gebeurt als git een samenvoeging niet automatisch
   kan oplossen, en hoe je die oplost
2. **GitHub**:
   - Remote koppelen (`git remote add origin ...`)
   - `git push` / `git pull`
   - Een repo aanmaken op GitHub (via `gh` CLI, al geïnstalleerd en ingelogd)
   - `git clone`
   - Pull requests — het centrale samenwerk-mechanisme
   - Fork vs. clone
   - Issues (kort)

## Hervatten

Zeg gewoon "we waren bezig met de git-les, ga verder met merge conflicts" (of
"... met GitHub") en de les kan verdergaan vanaf hier.
