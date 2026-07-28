# Git-les: voortgang

Oefen-repo voor het leren van git/GitHub. Status op dit moment: op branch `main`,
working tree clean, gekoppeld aan remote `origin` (GitHub, `woltera/git-leren`)
en up to date. Branches aanwezig: `main`, `tak2` (`tak1` is inmiddels verwijderd
na gemerged te zijn).

## Behandeld en begrepen

- **Mentale model**: working directory → staging area (`git add`) → local
  repository (`git commit`) → remote/GitHub (`git push`/`git pull`)
- **Git vs GitHub**: git = lokaal versiebeheer-programma, GitHub = hosting-dienst
  erbovenop voor samenwerken
- **Basiscommando's**: `git status`, `git add`, `git commit -m "..."`, `git log
  --oneline`, `git diff`
- **Wat een commit is**: snapshot + hash + boodschap + verwijzing naar parent-commit
  (vormt een keten)
- **HEAD**: pointer die aangeeft op welke branch/commit je nu staat
  (`HEAD -> main`)
- **Branches**: `git checkout -b <naam>` (nieuwe branch), `git checkout <naam>`
  (wisselen), `git branch` (overzicht, `*` = huidige), `git branch -d <naam>`
  (verwijderen, alleen als al gemerged)
- **Merge**: `git merge <branch>` — zowel fast-forward (geen echte samenvoeging
  nodig) als "echte" merges met de `ort`-strategie (automatisch, geen conflict)
- **Merge conflicts**: ontstaan als twee branches dezelfde regel(s) in hetzelfde
  bestand verschillend hebben aangepast. Git markeert dit meteen bij `git merge`
  (`CONFLICT (content): ...`) en zet conflictmarkers (`<<<<<<< HEAD`, `=======`,
  `>>>>>>> branch`) in het bestand. Oplossen: bestand handmatig aanpassen
  (markers weghalen, juiste inhoud kiezen) → `git add` → `git commit`
  (git vult het merge-commit-bericht automatisch in)
- **Untracked bestanden en branches**: een bestand dat nooit is ge-`add`/`commit`
  wordt door git niet als "bij een branch horend" gezien — het blijft gewoon op
  schijf staan bij het wisselen van branch, in tegenstelling tot getrackte
  bestanden
- **Status-letters** (`git status -s` / short format): `M` = modified, `A` =
  added, `D` = deleted, `R` = renamed, `C` = copied, `U` = unmerged (conflict),
  `??` = untracked. Twee kolommen = staging-status vs. working-directory-status
- **Remote/GitHub**: `git remote add origin <url>` koppelt een lokale repo aan
  een (lege) GitHub-repo; `git push -u origin main` stuurt commits ⬆️ en
  onthoudt de koppeling zodat latere `git push`/`git pull` zonder extra opties
  kunnen; `git pull` haalt wijzigingen ⬇️ op (fetch + merge in één) en kan ook
  tot conflicten leiden
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
| `git branch -d <naam>` | Verwijdert een branch (alleen als die al gemerged is; `-D` forceert) |
| `git rm <bestand>` | Verwijdert een bestand van schijf én stageert de verwijdering |
| `git add -A` / `git add .` | Stageert meerdere/alle gewijzigde en nieuwe bestanden in één keer |
| `git diff <hash1>..<hash2>` | Toont de wijzigingen tussen twee specifieke commits |
| `git show <hash>` | Toont de wijzigingen van één specifieke commit |
| `git remote -v` | Toont welke remote(s) gekoppeld zijn en hun URL |
| `git remote add origin <url>` | Koppelt een GitHub-repo als remote met de naam `origin` |
| `git push -u origin main` | Pusht en onthoudt de koppeling voor latere `git push`/`git pull` |
| `git pull` | Haalt commits van de remote op en merget ze (fetch + merge) |

## Nog te doen

**GitHub, vervolg:**
- `git clone` — een bestaande remote-repo lokaal ophalen
- Pull requests — het centrale samenwerk-mechanisme
- Fork vs. clone
- Issues (kort)
- (optioneel) Inloggen met `gh auth login` — nu nog niet gedaan, remote is via
  de GitHub-website + `git remote add` gekoppeld

**Verder ook nog te behandelen:**
- Wijzigingen ongedaan maken: `git restore`, `git reset`, `git revert`
- `git stash` — wijzigingen tijdelijk opzij zetten
- Rebase vs. merge

## Hervatten

Zeg gewoon "we waren bezig met de git-les, ga verder met GitHub" (clone/pull
requests) of noem een van de andere nog-te-doen-onderwerpen, en de les kan
verdergaan vanaf hier.
