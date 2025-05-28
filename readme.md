---
# 📘 Git: Rebase, Cherry-pick, Revert e Squash

Este documento tem como objetivo explicar o funcionamento, a sintaxe e as aplicações práticas dos comandos `git rebase`, `git cherry-pick`, `git revert` e `git squash` no Git.
---

## 🔁 git rebase

### ✅ Funcionamento

O `git rebase` é usado para reaplicar commits em uma nova base. Ele reorganiza o histórico de commits de forma linear, diferente do `merge`, que preserva o histórico divergente.

### 💻 Sintaxe

```bash
git rebase <branch-base>
```

### 🎯 Aplicação

- Reorganizar commits para manter um histórico mais limpo.
- Atualizar uma feature branch com as alterações mais recentes da `main` ou `develop`.

### 🧠 Exemplo

```bash
git checkout minha-feature
git rebase main
```

---

## 🍒 git cherry-pick

### ✅ Funcionamento

O `git cherry-pick` permite aplicar um ou mais commits específicos de outra branch na branch atual.

### 💻 Sintaxe

```bash
git cherry-pick <hash-do-commit>
```

### 🎯 Aplicação

- Aplicar uma correção específica de outra branch sem mesclar todas as alterações dessa branch.
- Recuperar um commit que foi feito por engano em outra linha do tempo.

### 🧠 Exemplo

```bash
git cherry-pick a1b2c3d
```

---

## 🔙 git revert

### ✅ Funcionamento

O `git revert` cria um novo commit que desfaz as alterações de um commit anterior, mantendo o histórico intacto.

### 💻 Sintaxe

```bash
git revert <hash-do-commit>
```

### 🎯 Aplicação

- Reverter um commit específico sem reescrever o histórico.
- Desfazer mudanças em produção de forma segura.

### 🧠 Exemplo

```bash
git revert e4f5g6h
```

---

## 🧩 git squash (via rebase interativo)

### ✅ Funcionamento

"Squash" significa combinar múltiplos commits em um só. O Git permite isso via rebase interativo.

### 💻 Sintaxe

```bash
git rebase -i <hash-do-commit-anterior-aos-que-serão-squash>
```

No editor, altere `pick` para `squash` (ou `s`) nos commits que deseja combinar.

### 🎯 Aplicação

- Limpar o histórico antes de fazer merge com a branch principal.
- Agrupar várias pequenas alterações em um único commit significativo.

### 🧠 Exemplo

```bash
git rebase -i HEAD~3
```

(Combina os últimos 3 commits em 1)

---

## 📝 Observações Finais

- Sempre tenha cuidado ao usar `rebase` e `squash` em branches compartilhadas (publicadas), pois isso reescreve o histórico.
- Utilize `git log` e `git status` frequentemente para verificar o estado do repositório.
- Use `git reflog` para recuperar commits perdidos após rebase ou cherry-pick mal sucedidos.

* Estudo gerado por IA

---
