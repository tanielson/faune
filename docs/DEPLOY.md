# Guia de Deploy — Faune Advogados

Passo a passo completo para colocar o site no ar.

---

## Pré-requisitos

- Conta GitHub: [github.com/signup](https://github.com/signup)
- Conta Vercel: [vercel.com/signup](https://vercel.com/signup) (use login com GitHub)
- Git instalado no computador: [git-scm.com/downloads](https://git-scm.com/downloads)

---

## Parte 1 — Subir o projeto no GitHub

### Opção A: Pelo navegador (mais fácil)

1. Acesse [github.com/new](https://github.com/new)
2. Preencha:
   - **Repository name:** `faune-advogados`
   - **Description:** "Site institucional Faune & Advogados Associados"
   - **Visibility:** Private (recomendado) ou Public
3. **NÃO** marque "Add a README" (já temos)
4. Clique em **Create repository**
5. Na tela seguinte, escolha **uploading an existing file**
6. Arraste TODOS os arquivos do projeto (não apenas alguns):
   - `index.html`
   - `README.md`
   - `vercel.json`
   - `.gitignore`
   - pasta `public/` inteira
   - pasta `docs/` inteira
7. Escreva commit message: `Initial commit — Site v1.0`
8. Clique em **Commit changes**

### Opção B: Via terminal (recomendado para versionar)

```bash
# Entre na pasta do projeto
cd caminho/para/faune-advogados

# Inicialize Git
git init

# Configure seu nome e e-mail (apenas primeira vez)
git config user.name "Seu Nome"
git config user.email "seu@email.com"

# Adicione todos os arquivos
git add .

# Faça o primeiro commit
git commit -m "Initial commit — Site v1.0"

# Renomeie o branch principal para main
git branch -M main

# Conecte ao repositório do GitHub (substitua SEU-USUARIO)
git remote add origin https://github.com/SEU-USUARIO/faune-advogados.git

# Faça o push inicial
git push -u origin main
```

---

## Parte 2 — Deploy na Vercel

### Conectar o repositório

1. Acesse [vercel.com/new](https://vercel.com/new)
2. Clique em **Continue with GitHub** (se ainda não conectou)
3. Autorize a Vercel a acessar seus repositórios
4. Localize o repositório `faune-advogados` na lista
5. Clique em **Import**

### Configurar o deploy

Na tela de configuração:

- **Project Name:** `faune-advogados` (ou outro de sua escolha)
- **Framework Preset:** **Other**
- **Root Directory:** `./` (deixa padrão)
- **Build Command:** deixe em branco
- **Output Directory:** deixe em branco
- **Install Command:** deixe em branco

Clique em **Deploy**.

⏱️ Aguarde ~30 segundos. A Vercel vai:
1. Clonar o repositório
2. Detectar que é HTML estático
3. Fazer deploy
4. Gerar uma URL pública tipo `faune-advogados.vercel.app`

✅ **Pronto! Site no ar.**

---

## Parte 3 — Conectar domínio próprio (fauneadv.com.br)

### No painel da Vercel

1. Entre no projeto
2. Vá em **Settings → Domains**
3. Digite `fauneadv.com.br` no campo
4. Clique em **Add**
5. A Vercel vai mostrar os registros DNS que você precisa configurar
6. Adicione também `www.fauneadv.com.br` (mesmo processo)

### No provedor do domínio (Registro.br ou similar)

Acesse o painel onde o domínio está registrado (provavelmente Registro.br ou GoDaddy).

**Configuração mínima necessária:**

| Tipo  | Nome | Valor                  |
|-------|------|------------------------|
| A     | @    | 76.76.21.21            |
| CNAME | www  | cname.vercel-dns.com   |

Salve as alterações.

### Aguardar propagação

DNS leva entre 5 minutos e 48h para propagar (geralmente 1-2h).

Você pode verificar o status em [dnschecker.org](https://dnschecker.org) digitando `fauneadv.com.br`.

Quando propagar, a Vercel automaticamente:
- ✅ Emite certificado SSL gratuito (Let's Encrypt)
- ✅ Configura HTTPS
- ✅ Redireciona HTTP → HTTPS
- ✅ Redireciona www → não-www (ou inverso, conforme configurado)

---

## Parte 4 — Atualizar o site no futuro

### Pelo navegador (atualizações pequenas)

1. Vá no GitHub do projeto
2. Clique no arquivo que quer editar (ex: `index.html`)
3. Clique no ícone de lápis (Edit)
4. Faça as mudanças
5. Role até o fim e clique em **Commit changes**
6. A Vercel detecta automaticamente e faz redeploy em ~30 segundos

### Via terminal (atualizações maiores)

```bash
# Entre na pasta do projeto
cd caminho/para/faune-advogados

# Faça suas alterações nos arquivos

# Veja o que mudou
git status

# Adicione as mudanças
git add .

# Commit com mensagem descritiva
git commit -m "Atualização: descrição do que mudou"

# Envia para o GitHub
git push

# Vercel detecta e faz redeploy automaticamente
```

---

## Parte 5 — Boas práticas

### Branches para experimentos

Sempre que for fazer mudanças grandes, crie um branch separado:

```bash
# Cria e entra em um branch novo
git checkout -b feature/nova-secao

# Faz alterações...

# Adiciona e commita
git add .
git commit -m "Adiciona seção de depoimentos"

# Envia o branch para GitHub
git push -u origin feature/nova-secao
```

A Vercel cria automaticamente uma **Preview URL** para cada branch, então você pode testar antes de promover para produção.

### Quando estiver tudo ok, faça merge para main

No GitHub:
1. Abra um **Pull Request** do branch para `main`
2. Revise as mudanças
3. Clique em **Merge pull request**
4. Vercel atualiza produção automaticamente

### Variáveis de ambiente (futuro)

Quando integrar com Greenn Sales, Typebot, ou outros serviços:

1. No painel Vercel: **Settings → Environment Variables**
2. Adicione cada variável (ex: `GREENN_WEBHOOK_URL`)
3. Marque os ambientes: Production, Preview, Development
4. Salve

No HTML, você não usa essas diretamente (precisa de função serverless). Por enquanto, ignore.

---

## Troubleshooting

### "Imagens não aparecem no site deployado"

**Causa:** caminho relativo errado.

**Solução:** confira se as imagens estão referenciadas como `/public/dr-gustavo.webp` no HTML (com barra no início).

### "Domínio próprio não funciona"

**Causa:** DNS ainda não propagou.

**Solução:** aguarde até 48h. Verifique propagação em [dnschecker.org](https://dnschecker.org).

### "Vercel deu erro de build"

**Causa:** algum arquivo de configuração com erro.

**Solução:** confira `vercel.json` — JSON válido sem vírgulas extras. Se persistir, remova o arquivo e tente deploy novamente (Vercel detecta HTML automaticamente).

### "Quero reverter para versão anterior"

No painel Vercel:
1. Entre no projeto
2. Aba **Deployments**
3. Encontre o deploy anterior funcionando
4. Clique nos três pontos `⋯`
5. Clique em **Promote to Production**

Reverte instantaneamente.

---

## Custos

A Vercel oferece plano **Hobby gratuito** que cobre tudo que esse projeto precisa:

- ✅ Bandwidth: 100GB/mês (mais que suficiente)
- ✅ Builds: ilimitados
- ✅ Domínio personalizado: ilimitados
- ✅ SSL/HTTPS: automático e gratuito
- ✅ Edge network global (CDN)
- ✅ Deploy previews ilimitados

**Custo total: R$ 0/mês** até o projeto crescer muito (10k+ visitas/dia).

---

## Suporte

- Documentação Vercel: [vercel.com/docs](https://vercel.com/docs)
- Documentação GitHub: [docs.github.com](https://docs.github.com)
- Status Vercel: [vercel-status.com](https://www.vercel-status.com)
