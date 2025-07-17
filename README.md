# git-readme-terminal-workflow
Documentação do workflow completo para autenticação SSH no GitHub e atualização de repositórios via terminal.

# GitHub SSH Workflow & README Update via Terminal

Este repositório documenta o processo completo de atualização de um `README.md` e configuração de workflow profissional usando Git, SSH e terminal.

---

##  Objetivo

- Atualizar o `README.md` de um repositório no GitHub via terminal.
- Praticar workflow real de versionamento e autenticação segura:
  - Clonagem de repositório
  - Edição local de arquivos
  - Commit e controle de alterações
  - Configuração de autenticação via chave SSH
  - Push usando SSH sem tokens/senhas

---

##  Ferramentas utilizadas

- Git
- GitHub
- Warp Terminal
- VS Code
- SSH (ed25519)

---

## 🚀 Workflow utilizado

```bash
# Clonar repositório
git clone git@github.com:<username>/<repo>.git
cd <repo>

# Editar README.md
code README.md

# Versionamento
git status
git add README.md
git commit -m "Atualiza README com documentação completa"

# Configuração SSH (se necessário)
ssh-keygen -t ed25519 -C "seu-email@example.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
cat ~/.ssh/id_ed25519.pub  # Copiar e adicionar no GitHub Settings > SSH keys
ssh -T git@github.com      # Teste de autenticação

# Ajuste remoto (se clonado via HTTPS)
git remote set-url origin git@github.com:<username>/<repo>.git

# Push para GitHub
git push origin main