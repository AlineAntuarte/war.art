## ✅ Comandos Git

```bash
# 1. Configuração (primeira vez só)
git config --global user.name "AlineAntuarte"
git config --global user.email "aline.ba@aluno.ifsc.edu.br"

# 2. Criar ou clonar repositório
git init                           # inicia um repositório local
git clone <url-do-repo>           # clona um repositório existente

# 3. Trabalhar no código
git status                         # ver alterações feitas
git diff                           # ver detalhes das alterações

# 4. Preparar (stage) e confirmar (commit)
git add <arquivo>                  # adiciona arquivo específico
git add .                          # adiciona todos os arquivos modificados
git commit -m "mensagem clara"     # registra alterações com mensagem

# 5. Sincronizar com o remoto
git pull origin main               # busca e mescla alterações do remoto :contentReference[oaicite:1]{index=1}
git push -u origin main           # envia alterações e define seguimento :contentReference[oaicite:2]{index=2}
git push origin main              # nos usos seguintes é só `git push`

# 6. Trabalhar com branches
git branch                         # mostra branches locais
git checkout -b nome-branch       # cria e muda para nova branch
git checkout nome-branch          # muda para uma branch existente
git merge nome-branch             # mescla outra branch na branch atual
git branch -d nome-branch         # apaga a branch local quando encerrada
git push origin --delete nome-branch  # apaga a branch no GitHub

# 7. Desfazer ou guardar mudanças
git reset HEAD <arquivo>          # tira do stage
git checkout -- <arquivo>         # descarta alterações não comitadas
git reset --hard                  # retorna tudo ao último commit
git revert <hash>                 # desfaz um commit criando um novo
git stash                          # guarda alterações temporariamente
git stash pop                      # recupera alterações guardadas

Aqui estão os comandos essenciais para criar branches e abrir Pull Requests (PRs), tanto do modo tradicional com Git quanto utilizando a GitHub CLI (`gh`):

—————————————————————————————————————————————————————————————————————————————————————————————————————————
—————————————————————————————————————————————————————————————————————————————————————————————————————————
—————————————————————————————————————————————————————————————————————————————————————————————————————————
```
## 🌿 1. Branches: criar, trocar e listar

* **Listar branches locais**
———————————————————————————————————————————————————
  git branch
———————————————————————————————————————————————————

* **Criar e trocar para uma nova branch**
———————————————————————————————————————————————————
  git checkout -b nome-da-branch
———————————————————————————————————————————————————

* **Trocar para uma branch existente**
———————————————————————————————————————————————————
  git checkout nome-da-branch
———————————————————————————————————————————————————

* **Criar branch sem trocar**
———————————————————————————————————————————————————
  git branch outra-branch
———————————————————————————————————————————————————

* **Remover branch (após merge)**
———————————————————————————————————————————————————
  git branch -d nome-da-branch
———————————————————————————————————————————————————

---

## 📬 2. Fluxo básico de uma feature

1. Crie a branch:
———————————————————————————————————————————————————
   git checkout -b movimento-especial
———————————————————————————————————————————————————
2. Faça alterações e adicione:
———————————————————————————————————————————————————
   git add .
   git commit -m "Implementa movimento especial no robô"
———————————————————————————————————————————————————
3. Envie para o GitHub:
———————————————————————————————————————————————————
   git push --set-upstream origin movimento-especial
———————————————————————————————————————————————————
4. Depois disso, vem o Pull Request!

---

## 🔃 3. Criar Pull Request no GitHub (via web)

Após o `git push`, geralmente aparece um link como:

```
remote: Create a pull request for 'movimento-especial' on GitHub by visiting:
remote: https://github.com/usuario/repo/pull/new/movimento-especial
```

Ou vá até o GitHub, abra a aba **Pull Requests → New Pull Request**, selecione a `base: main` e a `compare: movimento-especial`, adicione título/descrição e clique em **Create Pull Request** ([alvinalexander.com][3], [geeksforgeeks.org][4], [stackoverflow.com][5]).

---

## 💻 4. Criar PR via linha de comando com GitHub CLI (`gh`)

1. Instale a GitHub CLI (gh).
2. Autentique:
———————————————————————————————————————————————————
   gh auth login
 ———————————————————————————————————————————————————
3. Crie o PR:
———————————————————————————————————————————————————
   gh pr create --base main --head movimento-especial \
     --title "Movimento especial" \
     --body "Descrição do que faz e por que adiciona"
 ———————————————————————————————————————————————————

   Você pode já incluir `--assignee`, `--reviewer`, entre outros ([graphite.dev][6], [docs.github.com][7]).

* **Listar PRs**: `gh pr list`
* **Ver PR no navegador**: `gh pr view --web`
* **Trocar para PR localmente**: `gh pr checkout 123` ([graphite.dev][6])

---

## 🧭 5. Após aprovação (merge)

No GitHub:

* Clique em **Merge pull request**
* Delete a branch (opcionalmente)

Localmente:

```bash
git checkout main
git pull
git branch -d movimento-especial
```

---

### ✅ Resumo dos comandos

```bash
# 1. Criar branch
git checkout -b minha-funcionalidade

# 2. Desenvolver
git add .
git commit -m "Descrição da mudança"

# 3. Enviar para o GitHub
git push -u origin minha-funcionalidade

# 4a. Criar PR via web
# (siga o link ou vá no GitHub manualmente)

# 4b. Criar PR via CLI gh
gh pr create --title "Título do PR" --body "Descrição" --base main --head minha-funcionalidade

# 5. Após aprovação: merge e limpeza
git checkout main
git pull
git branch -d minha-funcionalidade
```