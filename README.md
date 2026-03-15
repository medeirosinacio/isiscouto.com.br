<p align="center">
  <img src="assets/image/logo/passaro.png" width="80" alt="Isis Couto — Logo">
</p>

<h1 align="center">isiscouto.com.br</h1>

<p align="center">
  Site profissional da psicóloga <strong>Isis Couto</strong> e da <strong>Clínica Entre Afetos</strong>.<br>
  Landing page single-page, estática, rápida e sem dependências externas.
</p>

<p align="center">
  <a href="https://isiscouto.com.br">
    <img src="https://img.shields.io/badge/site-isiscouto.com.br-B57068?style=flat-square" alt="Site">
  </a>
  <img src="https://img.shields.io/badge/jekyll-3.8-success?style=flat-square" alt="Jekyll 3.8">
  <img src="https://img.shields.io/badge/tailwind_css-local-06B6D4?style=flat-square" alt="Tailwind CSS">
  <img src="https://img.shields.io/badge/hosting-GitHub_Pages-181717?style=flat-square" alt="GitHub Pages">
</p>

---

## Sobre

Site da **Isis Couto** — psicóloga clínica e organizacional (CRP 07/34586), fundadora da **Clínica Entre Afetos** em Cachoeirinha/RS.

O site é uma landing page single-page com foco em:

- **Apresentação profissional** — quem é, formação, trajetória
- **Serviços** — psicoterapia individual, atendimento online, palestras, T&D
- **Clínica Entre Afetos** — espaço multidisciplinar (psicologia + nutrição)
- **Contato** — WhatsApp direto, e-mail, Instagram

## Stack

| Camada | Tecnologia |
|--------|-----------|
| Gerador | [Jekyll](https://jekyllrb.com/) 3.8 |
| Estilo | [Tailwind CSS](https://tailwindcss.com/) (local, sem CDN) |
| Fontes | Cormorant Garamond + Inter (woff2 local) |
| Hospedagem | GitHub Pages |
| Ambiente local | Docker (make setup) |

**Zero requisições externas** — Tailwind JS, fontes e todos os assets são servidos localmente.

## Arquitetura

```
.
├── _config.yml              # Configuração Jekyll + SEO
├── _data/
│   ├── geral.yml            # Dados globais (email, telefone, redes)
│   ├── quem-sou.yml         # Bio / texto da seção Sobre
│   ├── servicos.yml         # Lista de serviços oferecidos
│   ├── clinica.yml          # Dados da Clínica Entre Afetos
│   ├── formacao.yml         # Formação acadêmica
│   └── experiencia.yml      # Trajetória profissional (timeline)
├── _includes/
│   ├── nav.html             # Navegação responsiva com menu mobile
│   ├── hero.html            # Seção hero com CTA
│   ├── sobre.html           # Seção Quem Sou
│   ├── servicos.html        # Grid de serviços
│   ├── clinica.html         # Clínica Entre Afetos
│   ├── timeline.html        # Formação + Experiência
│   ├── cta.html             # Call to action (WhatsApp + email)
│   └── footer-new.html      # Rodapé com redes sociais
├── _layouts/
│   └── default.html         # Layout principal (Tailwind, Schema.org, OG)
├── assets/
│   ├── css/fonts.css        # @font-face local
│   ├── fonts/*.woff2        # Fontes locais
│   └── js/tailwind.js       # Tailwind standalone (local)
├── index.html               # Página única (compõe os includes)
├── 404.html                 # Redirect automático para home
├── robots.txt               # SEO
└── makefile                 # Comandos de setup (Docker)
```

### Design

- **Paleta pastel** — tons de blush (rosa suave), sage (verde salvia), warm (bege quente), gold (dourado)
- **Tipografia** — Cormorant Garamond (títulos, elegante) + Inter (corpo, legível)
- **Responsivo** — mobile-first, testado em 375px, 768px e 1440px

### SEO

- Título otimizado (72 chars) + meta description (155 chars)
- Schema.org JSON-LD: `Person`, `MedicalBusiness`, `ProfessionalService`, `BreadcrumbList`, `WebSite`
- Open Graph + Twitter Card
- Geo meta tags (coordenadas de Cachoeirinha/RS)
- `robots.txt` + sitemap automático via `jekyll-sitemap`
- Área de atendimento: Cachoeirinha, Porto Alegre, Gravataí, Canoas, Alvorada

## Desenvolvimento

### Pré-requisitos

- [Docker](https://docs.docker.com/get-docker/)
- [Make](https://www.gnu.org/software/make/)

### Setup

```bash
make setup
```

O site sobe em **http://localhost:4000** com live reload.

> Em Apple Silicon (M1/M2/M3), o Makefile usa automaticamente a imagem `arm64v8/ruby:2.7`.

### Comandos disponíveis

```bash
make help     # Lista todos os comandos
make setup    # Sobe o projeto com Docker + live reload
```

## Dados editáveis

Todo o conteúdo do site vive em `_data/`. Para editar textos, serviços ou informações de contato, basta alterar os arquivos YAML:

| Arquivo | O que contém |
|---------|-------------|
| `geral.yml` | E-mail, telefone, Instagram, textos de WhatsApp |
| `quem-sou.yml` | Parágrafos da seção "Sobre" |
| `servicos.yml` | Lista de serviços (título, descrição, ícone) |
| `clinica.yml` | Nome, descrição e valores da Clínica Entre Afetos |
| `formacao.yml` | Formação acadêmica |
| `experiencia.yml` | Trajetória profissional |

## Deploy

O deploy é automático via **GitHub Pages** — basta fazer push na branch principal.

---

<p align="center">
  Desenvolvido com 🤍 por <a href="https://links.douglasmedeiros.dev">Douglas Medeiros</a>
</p>
