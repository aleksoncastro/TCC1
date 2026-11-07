---
tipo: moc
titulo: "04 — Escrita LaTeX do TCC"
tags:
  - LaTeX
  - TCC
  - UNITINS
  - Escrita
---

# 📝 Escrita LaTeX do TCC

Este diretório contém o projeto LaTeX oficial da monografia de TCC, desenvolvido segundo as normas da ABNT (via `abntex2`) e a identidade visual da UNITINS (`unitins.sty`).

**Título do Trabalho:** Controle de Acesso IoT na Gestão Imobiliária via DSR  
**Autor:** Alêkson Castro de Souza  
**Orientadora:** Profa. Me. Tamirys Virgulino  
**Instituição:** Universidade Estadual do Tocantins (UNITINS) — Sistemas de Informação (2026)

---

## 📂 Estrutura de Arquivos e Status Atual

| Arquivo | Conteúdo e Escopo | Status |
|:---|:---|:---:|
| `main.tex` | Arquivo mestre — gerencia preâmbulo, pacotes, inclusões e bibliografia | ✅ Pronto e Otimizado |
| `unitins.sty` | Folhas de rosto, aprovação e ficha catalográfica da instituição | ✅ Configurado |
| `referencias.bib` | Base BibTeX com artigos correlatos, normas técnicas e DSR | ✅ Atualizado (20+ fontes) |
| `pretextuais_resumo.tex` | Resumo em português e *Abstract* com palavras-chave | ✅ Escrito |
| `pretextuais_siglas.tex` | Lista padronizada de abreviaturas e siglas técnicas | ✅ Escrito (23 siglas) |
| `capitulo1_introducao.tex` | Contexto, problema, questão norteadora, objetivos e justificativas | ✅ Escrito |
| `capitulo2_fundamentacao.tex` | IoT em camadas, ABAC, cripto Ed25519, fechaduras offline e estado da arte | ✅ Escrito |
| `capitulo3_metodologia.tex` | DSR (Peffers), arquitetura, NIST, Wokwi, cenários e 8 métricas quantitativas | ✅ Escrito |
| `capitulo4_resultados.tex` | Apresentação e discussão dos dados de simulação e gráficos | 🟡 Em elaboração |
| `capitulo5_conclusao.tex` | Síntese das contribuições, limitações e trabalhos futuros | 🟡 Estruturado |

---

## 📊 Detalhamento dos Capítulos Concluídos

### Capítulo 1: Introdução
- **Contextualização:** Desafios da gestão imobiliária descentralizada e atrito logístico de chaves físicas.
- **Pergunta de Pesquisa:** Alinhada à DSR (*"Como projetar e avaliar uma arquitetura de controle de acesso inteligente baseada em IoT capaz de gerenciar, de forma segura, rastreável e orientada a atributos (ABAC)..."*).
- **Objetivos:** 1 objetivo geral e 4 específicos (OE1 a OE4: Mapeamento, Modelagem, Implementação e Avaliação).
- **Justificativas:** Planos prático, técnico e acadêmico.

### Capítulo 2: Fundamentação Teórica
- **2.1 IoT e Protocolos:** Arquitetura em camadas e mensageria MQTT assíncrona.
- **2.2 Modelos de Autorização:** Do RBAC ao ABAC (modelo HABAC$\alpha$), tokens efêmeros e criptografia assimétrica de curva elíptica (Ed25519) para verificação offline.
- **2.3 Fechaduras Inteligentes e Trabalhos Relacionados:** Limitações de chaves e *lockboxes* (Quadro comparativo), análise de soluções comerciais Wi-Fi versus abordagens acadêmicas offline (BC-SNOA e OTMP-P2L), acompanhadas do quadro sinótico do estado da arte.
- **2.4 Segurança e Auditoria:** Análise de vetores de ataque (*replay*, *man-in-the-middle*, *MaaG*) e defesa em profundidade com trilha imutável de eventos.

### Capítulo 3: Metodologia e Desenvolvimento do Artefato
- **3.1 Metodologia DSR:** Paradigma de Hevner (2004) e mapeamento das 6 etapas de Peffers et al. (2007) ao cronograma da pesquisa.
- **3.2 Formalização do Problema:** Cenário de imóveis desocupados sem conectividade e 4 pilares de projeto (*Zero Local Infrastructure*, autenticidade, ABAC e rastreabilidade assíncrona).
- **3.3 Arquitetura Geral:** Visão em 4 camadas e 3 domínios físicos (Nuvem, Smartphone como *carrier/data mule* e Nó ESP32 PEP offline).
- **3.4 Modelo ABAC Formal:** Dicionário de 13 atributos conforme padrão NIST SP 800-162 e algoritmo combinador `deny_overrides`.
- **3.5 Validação Criptográfica Offline:** Analogia com terminais EMV, seleção de Curve25519/Ed25519, anatomia do token JWT/CBOR e algoritmo anti-replay com buffer circular em memória NVS.
- **3.6 Fluxo Ponta a Ponta:** Diagrama de sequência das três fases (solicitação 4G, leitura óptica QR Code na porta e sincronização assíncrona de auditoria MQTT).
- **3.7 Stack e Firmware:** FastAPI/Python 3.11, PlatformIO C/C++, mbedtls, PyNaCl e árvore de tópicos Mosquitto.
- **3.8 Prototipagem Virtual no Wokwi:** Circuito, pinout GPIO e arquivo de conexões `diagram.json`.
- **3.9 Cenários de Demonstração:** CTs de concessão nominal, negação por 4 vetores de ataque e revogação emergencial via painel administrativo.
- **3.10 Métricas de Avaliação:** Metas operacionais para 8 métricas (latência ABAC, tempo de verificação ESP32, latência ponta a ponta, consumo de RAM Heap, ocupação Flash ROM, vazão MQTT e taxa de bloqueio).

---

## 🛠️ Como Compilar o Projeto

### No VS Code (com extensão LaTeX Workshop)
1. Abra o arquivo `TCC_LATEX/main.tex`.
2. O salvamento do arquivo dispara o auto-build configurado em `.vscode/settings.json`.
3. Para compilação manual completa com referências, use o menu lateral do LaTeX Workshop e selecione a receita:
   - `📚 Completo (pdflatex + bibtex)`
4. Formatação de código: atalho `Shift + Alt + F` (utiliza o formatador `latexindent` do MiKTeX).

### Via Terminal
Na pasta `04 - Escrita LaTeX/TCC_LATEX`, execute a sequência padrão:
```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

---

## 📌 Padrões Tipográficos Adotados (ABNT / UNITINS)

- **Citações Indiretas:** `\cite{chave}` → (SILVA; SAMANIEGO; DETERS, 2023)
- **Citações com Autor Integrado ao Texto:** `\citeonline{chave}` → Vardakis et al. (2024)
- **Ilustrações e Figuras:** Título no topo (`\caption`) e indicação de fonte na base (`\fonte`), conforme NBR 14724.
- **Tabelas e Quadros:** Legenda no topo, linhas horizontais `booktabs` (`\toprule`, `\midrule`, `\bottomrule`) e largura ajustada via `tabularx`.
