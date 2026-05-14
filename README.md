# Faune & Advogados Associados

Site institucional do escritório **Faune & Advogados Associados**, especializado em Direito do Trabalho — Londrina/PR.

🌐 **Site em produção:** [fauneadv.com.br](https://fauneadv.com.br)

---

## 📋 Sobre o projeto

Site institucional construído como ativo de captação de leads qualificados, em conformidade rigorosa com o **Provimento 205/2021 da OAB**. Foco em SEO local, performance e conversão.

### Cliente
- **Escritório:** Faune & Advogados Associados
- **Advogado titular:** Dr. Gustavo Faune Bonini · OAB/PR
- **Localização:** Av. Madre Leônia Milito, 1500, Sala 511, Bela Suíça, Londrina/PR
- **Áreas de atuação:** Direito do Trabalho (especialidade principal), Previdenciário, Civil, Empresarial e Agronegócio

---

## 🎨 Design

**Direção visual:** Dark sophistication — fundo navy profundo (#0F1A2E) com acentos em dourado champagne (#D4A845). Inspirado em escritórios premium internacionais (Anapol Weiss, Quinn Emanuel), adaptado à realidade brasileira e à conformidade da OAB.

**Tipografia:**
- **Display:** Inter Tight (pesos 800-900) — títulos impactantes
- **Body:** Plus Jakarta Sans (pesos 300-700) — corpo de texto

**Paleta principal:**
- Background: `#0F1A2E` (navy profundo)
- Acento: `#D4A845` (dourado champagne)
- Texto: `#FFFFFF` / `rgba(255,255,255,0.78)`

---

## 🏗️ Estrutura do site

O site é uma single-page com 9 seções principais:

1. **Hero split-screen** — texto à esquerda + foto profissional do Dr. Gustavo à direita
2. **Stats** — 3 números massivos (10+ anos, 400+ processos, 5 áreas)
3. **Por que escolher** — 6 cards de diferenciais
4. **Áreas de atuação** — Trabalhista em destaque + 4 áreas conexas
5. **Método** — 4 etapas de condução de caso
6. **Sobre o Dr. Gustavo** — biografia expandida com credenciais
7. **Lead Magnet** — guia gratuito em formato PDF
8. **FAQ** — 6 perguntas educativas
9. **Contato** — formulário qualificador + dados de contato

---

## 📁 Estrutura de arquivos

```
faune-advogados/
├── index.html                  # Site completo (HTML + CSS + JS inline)
├── public/                     # Assets estáticos
│   ├── dr-gustavo.webp         # Foto profissional do advogado
│   └── logo-faune.webp         # Logo oficial do escritório
├── docs/                       # Documentação do projeto
│   └── CHANGELOG.md            # Histórico de versões
├── vercel.json                 # Configuração de deploy Vercel
├── .gitignore                  # Arquivos ignorados pelo Git
└── README.md                   # Este arquivo
```

---

## 🚀 Deploy na Vercel

### Opção 1: Deploy direto pelo dashboard (recomendado)

1. Crie conta gratuita em [vercel.com](https://vercel.com) com seu GitHub
2. Clique em **Add New → Project**
3. Importe este repositório
4. Mantenha todas as configurações padrão (Framework: **Other**)
5. Clique em **Deploy**

A Vercel detecta automaticamente HTML estático e faz o deploy em ~30 segundos. Você recebe uma URL `.vercel.app` imediatamente.

### Opção 2: Deploy via CLI

```bash
# Instalar Vercel CLI
npm i -g vercel

# Login
vercel login

# Deploy
vercel

# Deploy para produção
vercel --prod
```

### Conectar domínio personalizado (fauneadv.com.br)

1. No dashboard da Vercel, vá em **Settings → Domains**
2. Adicione `fauneadv.com.br` e `www.fauneadv.com.br`
3. A Vercel mostra os registros DNS que você precisa configurar no Registro.br ou outro provedor
4. Configure os registros A/CNAME conforme instruções
5. Aguarde a propagação DNS (até 48h, geralmente 1-2h)

---

## ⚙️ Performance e SEO

### Otimizações já implementadas
- ✅ Schema.org `LegalService` em JSON-LD para SEO local
- ✅ Meta tags Open Graph para compartilhamento em redes
- ✅ Preconnect e display=swap nas Google Fonts
- ✅ Imagens em formato WebP (compressão superior ao JPG/PNG)
- ✅ CSS inline (zero requisições adicionais)
- ✅ JavaScript mínimo (apenas interações essenciais)
- ✅ Tags semânticas (section, article, nav, footer)
- ✅ Heading hierarchy correta
- ✅ Mobile-first responsivo (breakpoints 540px e 920px)
- ✅ Smooth scroll e reveal-on-scroll
- ✅ Theme-color meta tag

### Lighthouse esperado
- Performance: 95+
- Accessibility: 95+
- Best Practices: 100
- SEO: 100

---

## 🔒 Conformidade OAB (Provimento 205/2021)

Este site segue rigorosamente o Provimento 205/2021 da OAB:

✅ Sem promessa de resultado
✅ Sem casos de êxito específicos identificáveis
✅ Sem tabela de honorários ou valores
✅ Sem comparações com outros advogados
✅ Linguagem informativa e sóbria em todo o conteúdo
✅ Disclaimer LGPD no formulário
✅ Nota explicando que nenhum diagnóstico jurídico é emitido sem análise direta de um advogado
✅ Identificação OAB/PR clara

---

## 🛠️ Próximas etapas (pós-deploy)

### Etapa 01 (em andamento)
- [x] Site institucional novo
- [ ] Reivindicação/ativação Google Meu Negócio
- [ ] Configurar GA4 + Search Console + Tag Manager
- [ ] Política de Privacidade (LGPD)
- [ ] Conectar formulário ao Greenn Sales (CRM)
- [ ] Schema.org adicional para artigos do blog

### Etapa 02
- [ ] Estrutura de tráfego pago (Meta Ads + Google Ads)
- [ ] Integração Typebot para qualificação de leads
- [ ] Automações via Make (Greenn Sales ↔ Typebot ↔ E-mail)

### Etapa 03
- [ ] Blog estruturado para artigos SEO
- [ ] Calendário editorial (25 conteúdos/mês)
- [ ] Páginas internas por área de atuação

### Etapa 04
- [ ] Livro como front-end de captação (fase 2)

---

## 📞 Contato do escritório

- **Telefone:** (43) 3024-3599
- **WhatsApp:** [(43) 99968-3380](https://wa.me/5543999683380)
- **E-mail:** contato@fauneadv.com.br
- **Endereço:** Av. Madre Leônia Milito, 1500, sala 511 — Bela Suíça, Londrina/PR, CEP 87050-260

---

## 📄 Licença

© 2026 Faune & Advogados Associados. Todos os direitos reservados.

Código-fonte de uso exclusivo do escritório. Não autorizada reprodução ou redistribuição.
