Git Local e Integração com GitHub

## Objetivo
Aprender a utilizar o **Git** localmente para versionar projetos, criando commits, branches e manipulando o histórico de forma segura, além de integrar o repositório ao **GitHub** e documentar práticas de colaboração.

---

## Parte 1 – Git Local (sem GitHub)

### 1. Configuração inicial

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@exemplo.com"
git config --global core.editor "code --wait"
git config --list
```

### 2. Criar e iniciar um repositório

```bash
mkdir meu_projeto
cd meu_projeto
git init
```

### 3. Alterar a branch padrão de `master` para `main`

```bash
git branch -m master main
git config --global init.defaultBranch main
```

### 4. Criar arquivos e verificar status

```bash
echo "Meu primeiro arquivo" > readme.txt
git status
```

### 5. Adicionar arquivos à área de staging

```bash
git add readme.txt
git add .
git status
```

### 6. Fazer o primeiro commit

```bash
git commit -m "Primeiro commit - adiciona readme.txt"
```

### 7. Ver histórico e detalhes

```bash
git log
git log --oneline
git show
```

### 8. Editar arquivos e registrar mudanças

```bash
echo "Adicionando nova linha" >> readme.txt
git status
git diff
git add readme.txt
git commit -m "Atualiza readme.txt com nova linha"
```

### 9. Desfazer mudanças

```bash
git restore readme.txt
git restore --staged readme.txt
```

### 10. Criar e alternar entre branches

```bash
git branch
git branch nova_funcionalidade
git switch nova_funcionalidade
```

### 11. Fazer commits em outra branch

```bash
echo "Nova feature" > feature.txt
git add feature.txt
git commit -m "Adiciona nova feature"
```

### 12. Voltar e mesclar mudanças

```bash
git switch main
git merge nova_funcionalidade
```

### 13. Excluir branches locais

```bash
git branch -d nova_funcionalidade
```

### 14. Ignorar arquivos com `.gitignore`

```
*.log
*.tmp
node_modules/
```

```bash
git add .gitignore
git commit -m "Adiciona arquivo .gitignore"
```

### 15. Visualizar informações úteis

```bash
git status
git log --oneline --graph --decorate
git diff
git show HEAD
```

### 16. Exemplo de fluxo completo

```bash
git init
echo "Aula prática Git local" > readme.txt
git add .
git commit -m "Primeiro commit"
git branch dev
git switch dev
echo "Nova versão em desenvolvimento" >> readme.txt
git add .
git commit -m "Atualiza versão dev"
git switch main
git merge dev
git log --oneline --graph
```

---

## Parte 2 – Integração com GitHub

### 2. Clonagem e Configuração Local

```bash
git clone https://github.com/SEU_USUARIO/git-local
cd git-local
git checkout -b documentacao-colaboracao
```

### 3. Integração Git Local ↔ GitHub

Comandos essenciais (auxiliados pelo GitFluence):

| Descrição no GitFluence | Comando Git | Explicação |
|--------------------------|-------------|------------|
| Push the new branch to the remote repository | `git push -u origin documentacao-colaboracao` | Envia o branch para o GitHub |
| See all my current branches | `git branch -a` | Lista branches locais e remotos |
| Check the status of my files | `git status` | Mostra arquivos modificados |

### 4. Commit e Push das Alterações

```bash
git add .
git commit -m "feat: adiciona documentação sobre integração e colaboração"
git push origin documentacao-colaboracao
```

### 5. Pull Request (PR)
- Acesse seu fork no GitHub.  
- Clique em **Compare & Pull Request**.  
- Abra o PR do branch `documentacao-colaboracao` para o `main` do repositório original.  

---
