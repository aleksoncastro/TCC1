---
tipo: moc
titulo: "04 — Escrita LaTeX do TCC"
tags:
  - LaTeX
  - TCC
  - UNITINS
  - Escrita
---

# 📝 Pasta: Escrita LaTeX do TCC

Esta pasta contém o **projeto LaTeX oficial** do TCC, no template exigido pela UNITINS (abnTeX2 + `unitins.sty`).

## Arquivos do Projeto

| Arquivo | Propósito | Status |
|:---|:---|:---:|
| `main.tex` | Arquivo principal — compila todo o TCC | ✅ Configurado |
| `referencias.bib` | Todas as 11 referências do TCC + DSR clássicos | ✅ Preenchido |
| `unitins.sty` | Estilo visual exigido pela UNITINS | ✅ Original |
| `capitulo1_introducao.tex` | Introdução | ⬜ A escrever |
| `capitulo2_fundamentacao.tex` | **Referencial Teórico** | 🟡 Seção 2.1 escrita |
| `capitulo3_metodologia.tex` | Metodologia DSR | ⬜ A escrever |
| `capitulo4_resultados.tex` | Resultados e Discussão | ⬜ A escrever |
| `capitulo5_conclusao.tex` | Conclusão | ⬜ A escrever |
| `pretextuais_resumo.tex` | Resumo e Abstract | ⬜ A escrever |

---

## Progresso do Referencial Teórico (Cap. 2)

```
✅ 2.1 Internet das Coisas (IoT): Conceitos e Arquitetura
   ✅ 2.1.1 Definição e Evolução da IoT
   ✅ 2.1.2 Arquitetura em Camadas dos Ecossistemas IoT
   ✅ 2.1.3 Protocolo MQTT

⬜ 2.2 Controle de Acesso em Ambientes IoT
   ⬜ 2.2.1 Modelos Tradicionais: RBAC
   ⬜ 2.2.2 ABAC e o Modelo HABACα
   ⬜ 2.2.3 Autenticação com Tokens Efêmeros

⬜ 2.3 Fechaduras Inteligentes e Controle de Acesso Físico
   ⬜ 2.3.1 Métodos Tradicionais e Suas Limitações
   ⬜ 2.3.2 Soluções IoT para Smart Locks
   ⬜ 2.3.3 Trabalhos Relacionados (tabela comparativa)

⬜ 2.4 Segurança em Sistemas IoT
   ⬜ 2.4.1 Ameaças e Vulnerabilidades
   ⬜ 2.4.2 Mecanismos de Segurança

⬜ 2.5 Design Science Research (DSR)
   ⬜ 2.5.1 Fundamentos da DSR
   ⬜ 2.5.2 DSR em Segurança IoT
   ⬜ 2.5.3 Simulação Virtual como Demonstração
```

---

## Como Compilar

> [!TIP] Compilação com PDFLaTeX
> Abra o terminal na pasta `TCC_LATEX` e execute:
> ```bash
> pdflatex main.tex
> bibtex main
> pdflatex main.tex
> pdflatex main.tex
> ```
> Ou use o **Overleaf** para compilar online sem instalar nada.

---

## Guia de Estilo (ABNT via abnTeX2)

- **Citação indireta** (paráfrase): `\cite{chave}` → (AUTOR, ANO)
- **Citação direta com nome integrado**: `\citeonline{chave}` → Autor (ANO)
- **Figura**: sempre com `\caption{}` e `\label{}`, referenciada com `(ver Figura \ref{fig:nome})`
- **Tabela**: idem, com legenda acima da tabela (padrão ABNT)
- **Subseções**: usar `\subsection{}` e `\subsubsection{}` com moderação — a ABNT desencoraja mais de 3 níveis de hierarquia

---

*Consulte a estrutura completa em [[00 - Visão Geral e Metodologia/00.4 - Estrutura do Referencial Teórico|00.4 - Estrutura do Referencial Teórico]]*
