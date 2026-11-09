Apartado 1:
- git init
- $ echo "Entregable practico del modulo 1 versionado de codigo, master PontIA 2026" > README.md
- git add .
- git commit -m "Commit inicial"
- git remote add origin https://github.com/gcebrianc/entregable_modulo_1.git
- git branch -M main
- git push -u origin main
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 16 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 286 bytes | 286.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/gcebrianc/entregable_modulo_1.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.

Apartado 2
{
  "id": 26754989,
  "name": "Main protegida",
  "target": "branch",
  "source_type": "Repository",
  "source": "gcebrianc/entregable_modulo_1",
  "enforcement": "active",
  "conditions": {
    "ref_name": {
      "exclude": [],
      "include": [
        "~DEFAULT_BRANCH"
      ]
    }
  },
  "rules": [
    {
      "type": "deletion"
    },
    {
      "type": "non_fast_forward"
    },
    {
      "type": "pull_request",
      "parameters": {
        "required_approving_review_count": 1,
        "dismiss_stale_reviews_on_push": false,
        "required_reviewers": [],
        "require_code_owner_review": true,
        "require_last_push_approval": false,
        "required_review_thread_resolution": false,
        "require_extra_approval_for_unattributed_changes": true,
        "allowed_merge_methods": [
          "merge",
          "squash",
          "rebase"
        ]
      }
    },
    {
      "type": "required_status_checks",
      "parameters": {
        "strict_required_status_checks_policy": false,
        "do_not_enforce_on_create": false,
        "required_status_checks": []
      }
    },
    {
      "type": "required_linear_history"
    }
  ],
  "bypass_actors": []
}

Descripcion: En un entorno compartido, lo mas importante es mantener la rama main o rama principal segura y sin que pueda ser afectada por codigo con bugs o errores. La manera de lograrlo es bloquear cualquier commit directo a la rama asi como solo poermitir incluir codigo mediante pull requests que debend e ser autorizadas por el codeowner o alguien distinto a quien genera el codigo. De esta manera todos los despliegues estan protegidos por las pruebas CI asi como los test incluidos en la rama, aportando seguridad extra con el uso de prs y revisiones por responsables directos.

Apartado 3
- git switch -c feature/gitignore
- cat .gitignore
*.log
__pycache__/
- git pull
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 2 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 947 bytes | 236.00 KiB/s, done.
From https://github.com/gcebrianc/entregable_modulo_1
   f37ef43..2dd4e70  main       -> origin/main
Updating f37ef43..2dd4e70
Fast-forward
 .gitignore | 2 ++
 1 file changed, 2 insertions(+)
 create mode 100644 .gitignore

- echo "fichero de prueba" >prueba.log
- git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

Apartado 4
- git switch -c feature/suma
Switched to a new branch 'feature/suma'

-nano operations.py
- cat operations.py
def info():
        return "Operaciones básicas"
def suma(a,b):
        return a + b
-git add operations.py
-git status
On branch feature/suma
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   operations.py
-git commit -m "Operaciones básicas y sumar"
[feature/suma fb8d9a4] Operaciones básicas y sumar
 1 file changed, 4 insertions(+)
 create mode 100644 operations.py
- git push -u origin feature/suma
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 16 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 397 bytes | 397.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote:
remote: Create a pull request for 'feature/suma' on GitHub by visiting:
remote:      https://github.com/gcebrianc/entregable_modulo_1/pull/new/feature/suma
remote:
To https://github.com/gcebrianc/entregable_modulo_1.git
 * [new branch]      feature/suma -> feature/suma
branch 'feature/suma' set up to track 'origin/feature/suma'.

-git switch -c feature/resta
Switched to a new branch 'feature/resta'
-nano operations.py
def info():
        return "Operaciones básicas"
def resta(a,b):
        return a - b

-git add operations.py
- git status
On branch feature/resta
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   operations.py
-git commit -m "Operaciones basicas y resta"
[feature/resta 56d8d44] Operaciones basicas y resta
 1 file changed, 4 insertions(+)
 create mode 100644 operations.py
- git push -u origin feature/resta
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 16 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 390 bytes | 390.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote:
remote: Create a pull request for 'feature/resta' on GitHub by visiting:
remote:      https://github.com/gcebrianc/entregable_modulo_1/pull/new/feature/resta
remote:
To https://github.com/gcebrianc/entregable_modulo_1.git
 * [new branch]      feature/resta -> feature/resta
branch 'feature/resta' set up to track 'origin/feature/resta'.

- git pull
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 2 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 1.01 KiB | 28.00 KiB/s, done.
From https://github.com/gcebrianc/entregable_modulo_1
   2dd4e70..1cd834d  main       -> origin/main
Updating 2dd4e70..1cd834d
Fast-forward
 operations.py | 4 ++++
 1 file changed, 4 insertions(+)
 create mode 100644 operations.py
 
(feature/resta)
- git merge main
Auto-merging operations.py
CONFLICT (add/add): Merge conflict in operations.py
Automatic merge failed; fix conflicts and then commit the result.
- cat operations.py
def info():
        return "Operaciones básicas"
<<<<<<< HEAD
def resta(a,b):
        return a - b
=======
def suma(a,b):
        return a + b
>>>>>>> main
- cat operations.py
def info():
        return "Operaciones básicas"
def resta(a,b):
        return a - b
def suma(a,b):
        return a + b
- git add operations.py
- git commit -m "Conflicto de operations resuelto"
[feature/resta 6c6b848] Conflicto de operations resuelto
-  git push -u origin feature/resta
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 16 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 363 bytes | 363.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/gcebrianc/entregable_modulo_1.git
   56d8d44..6c6b848  feature/resta -> feature/resta
branch 'feature/resta' set up to track 'origin/feature/resta'.
-git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

- git pull
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 1), reused 1 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 981 bytes | 57.00 KiB/s, done.
From https://github.com/gcebrianc/entregable_modulo_1
   1cd834d..8709238  main       -> origin/main
Updating 1cd834d..8709238
Fast-forward
 operations.py | 3 +++
 1 file changed, 3 insertions(+)
- git log --oneline --graph --all
* 8709238 (HEAD -> main, origin/main, origin/HEAD) Operaciones basicas y resta (#3)
| *   6c6b848 (origin/feature/resta, feature/resta) Conflicto de operations resuelto
| |\
| |/
|/|
* | 1cd834d Operaciones básicas y sumar merge
| * 56d8d44 Operaciones basicas y resta
|/
| * fb8d9a4 (origin/feature/suma, feature/suma) Operaciones básicas y sumar
|/
* 2dd4e70 fichero gitignore (#1)
| * 200ead3 (origin/feature/gitignore, feature/gitignore) fichero gitignore
|/
* f37ef43 Commit inicial

Apartado 6
- git switch -c feature/ci
Switched to a new branch 'feature/ci'

- cat demo.py
name: Workflow manual
on:
  workflow_dispatch:
    inputs:
      mensaje:
        description: 'Escribe el mensaje a imprimir'
        required: true
        type: string

jobs:
  imprimir-mensaje:
    runs-on: ubuntu-26.04
    steps:
      - name: Imprimir mensaje porconsola
        run: 'echo "El mensaje es: ${{ inputs.mensaje }}"'



 
