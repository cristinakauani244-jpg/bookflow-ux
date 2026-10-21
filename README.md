# BookFlow — Sistema Nacional de Bibliotecas Universitárias

> Relatório técnico de Experiência do Usuário (UX) para uma plataforma de biblioteca digital universitária **acessível** e em conformidade com a **Lei Brasileira de Inclusão (Lei nº 13.146/2015)** e com as diretrizes **WCAG 2.1 (nível AA)**.

![Status](https://img.shields.io/badge/etapa-2%20(Figma%20→%20Lovable)-2d6a4f)
![Acessibilidade](https://img.shields.io/badge/WCAG-2.1%20AA-d4a017)
![Tipo](https://img.shields.io/badge/projeto-acad%C3%AAmico-1b4332)

**Universidade Cidade de São Paulo (UNICID)** · Disciplina: Interface e Jornada do Usuário · Engenharia de Software e ADS

---

## Equipe

- Arthur Lanzoni Quim
- Kauani Cristina Silva Rolim
- Vinicius de Souza Vicente

---

## Sobre o projeto

O BookFlow nasce para resolver as barreiras de acesso da plataforma legada do SNBU, onde a **taxa de abandono chegava a 78%** nas etapas de refinamento de pesquisa. O trabalho documenta todo o processo de design, desde a sessão colaborativa até o MVP, e a migração do protótipo do **Figma** para um produto funcional no **Lovable**.

🔗 **Protótipo no Figma:** _(cole o link aqui)_
🔗 **Produto no Lovable:** _(cole o link aqui, se houver)_
 **Relatório completo:** [`docs/relatorio1.docx`](docs/relatorio1.docx)

---

## Conteúdo do relatório

1. [Sessão de design colaborativo](#1--sessão-de-design-colaborativo)
2. [Personas](#2--personas)
3. [Jornada futura (To-Be)](#3--jornada-futura-to-be)
4. [Matriz esforço × impacto](#4--matriz-esforço--impacto)
5. [Protótipo de baixa fidelidade](#5--protótipo-de-baixa-fidelidade)
6. [Plano de teste de conceito](#6--plano-de-teste-de-conceito)
7. [MVP Canvas](#7--mvp-canvas)

---

## 1 · Sessão de design colaborativo

Três dinâmicas conduzidas de forma integrada:

| Dinâmica | O que foi feito |
| --- | --- |
| **Design Studio** | Cada integrante esboçou fluxos para busca e acessibilidade, com votação silenciosa por pontos de afinidade |
| **Mapa de Jornada Colaborativo** | Construção coletiva das jornadas To-Be e identificação de pontos de dor |
| **Revisão de Critérios de Conformidade** | Alinhamento das decisões de interface com WCAG 2.1 AA e a LBI |

**Decisões da sessão:** fluxos primários de navegação, painel de ajuste rápido de acessibilidade na home, identidade visual **verde-floresta com acento dourado** (contraste mínimo de 4,5:1) e persistência das preferências por perfil via **Supabase Auth**.

---

## 2 · Personas

| Persona | Perfil | Necessidade principal | Prioridade |
| --- | --- | --- | --- |
| **Fernanda, 24** — Cegueira total | Ciências Sociais · teclado + leitor de tela (NVDA/VoiceOver) | Skip links, filtros .BRF e audiolivro na 1ª tela, alt text em todas as imagens | 🔴 Crítica |
| **Renato, 51** — Baixa visão severa | Pós-graduação em História · tablet com 200% de zoom | Alto contraste em até 2 toques; fonte de até 24pt sem quebrar o layout | 🟠 Alta |
| **Isabela, 20** — Dislexia e TDAH | Pedagogia · perde o foco com textos densos | Text-to-Speech com realce sincronizado, fonte OpenDyslexic, máx. 4 ações por tela | 🟠 Alta |

As personas foram construídas com base em pesquisas de acessibilidade no ensino superior brasileiro (Sassaki, 2010; Melo e Baranauskas, 2006).

---

## 3 · Jornada futura (To-Be)

```
Chegada e Orientação → Personalização de Perfil → Busca Inteligente → Consumo Autônomo → Retenção e Retorno
```

1. **Chegada:** painel de acessibilidade rápida na tela inicial (Voz Alta, Alto Contraste, Aumentar Texto, Libras)
2. **Personalização:** perfil configurado em até 3 interações e salvo no Supabase
3. **Busca:** por título, autor ou ISBN, com filtros de formato acessível (E-book, Áudio, Braille, PDF estruturado)
4. **Consumo:** Acessar Online, Baixar PDF Acessível ou Ouvir Audiolivro, com grade de compatibilidade assistiva
5. **Retenção:** histórico, favoritos e avisos de novos formatos acessíveis

---

## 4 · Matriz esforço × impacto

| Funcionalidade | Esforço | Impacto | Classificação |
| --- | :---: | :---: | --- |
| Filtros de formato acessível na home | Baixo | Muito alto | ⚡ Ganho rápido |
| Skip links e navegação completa por teclado | Baixo | Muito alto | ⚡ Ganho rápido |
| Painel de preferências persistido por perfil | Médio | Alto | ✅ MVP |
| Text-to-Speech com realce de palavra | Médio | Alto | ✅ MVP |
| Grade de compatibilidade assistiva por livro | Médio | Alto | ✅ MVP |
| Dicionário de Libras com IA generativa | Alto | Médio | 🔮 Pós-MVP |
| Reconhecimento automático de tecnologias assistivas | Alto | Alto | 🔮 Pós-MVP |

---

## 5 · Protótipo de baixa fidelidade

Seis telas em paleta verde-floresta, focadas em hierarquia da informação e navegação para tecnologias assistivas:

| Tela | Descrição |
| --- | --- |
| 01 · Login | E-mail institucional, SSO universitário e login social |
| 02 · Cadastro | Formulário em duas etapas com barra de progresso |
| 03 · Home | Busca centralizada, painel de acessibilidade rápida e livros em destaque |
| 04 · Acervo | Resultados paginados com filtros de formato e contador |
| 05 · Configurações de acessibilidade | Painel segmentado em Visão, Áudio e Navegação |
| 06 · Detalhe do livro | Metadados, botões de consumo e grade 2×2 de compatibilidade |

**Fluxo principal:** Tela Inicial → Ajustes de Acessibilidade → Busca com Filtro Inclusivo → Detalhe + Acesso ao Conteúdo

**Arquitetura de informação:** Início · Acervo · Área de Acessibilidade · Minha Conta

>  _Adicione aqui os prints das telas, por exemplo:_ `![Home](imagens/home.png)`

---

## 6 · Plano de teste de conceito

- **Participantes:** 6 a 8 pessoas do ecossistema universitário, 50% sem limitações declaradas e 50% com deficiência visual ou cognitiva, recrutadas pelos Núcleos de Inclusão e Acessibilidade (NIAs) da UNICID
- **Sessões:** até 45 minutos, com 5 tarefas (login, ativar Voz Alta e Alto Contraste, buscar "Design de Interação" filtrando por audiolivro, ver recursos de acessibilidade do livro, salvar nos favoritos)

| Métrica | Meta |
| --- | --- |
| Taxa de conclusão de tarefas (TCT) | ≥ 85% sem ajuda do facilitador |
| System Usability Scale (SUS) | ≥ 70 pontos ("Bom") |
| Tempo médio de busca (leitor de tela) | ≤ 90 segundos |
| Erros de navegação corrigíveis | Máx. 2 por sessão |

---

## 7 · MVP Canvas

**Três capacidades centrais**, todas com suporte a tecnologias assistivas desde o primeiro deploy:

1.  **Biblioteca digital** com busca por título, autor e ISBN e filtros por formato (.BRF, .MP3, PDF acessível, e-book)
2.  **Painel de acessibilidade por perfil**: Visão (fonte, contraste, espaçamento), Áudio (voz alta, velocidade, descrição de imagens) e Navegação (skip links, indicador de foco, Libras)
3.  **Agente de IA** para busca e recomendação acessível, chamado exclusivamente pelo backend

**Valor por segmento**

- **Gestores do SNBU:** conformidade com a LBI, documentada e auditável por tela
- **Estudantes com deficiência visual:** independência no acesso ao acervo
- **Estudantes com dislexia e TDAH:** menos carga cognitiva, com leitura em voz alta sincronizada e fontes alternativas

** Segurança do agente de IA**

- Chave de API só em variáveis de ambiente do backend (Supabase Edge Functions), nunca no frontend nem no repositório
- Validação de entrada: máx. 500 caracteres, rejeição de caracteres de controle e sanitização
- Prompt de sistema com escopo restrito (acervo e acessibilidade) e proteção contra *prompt injection*
- Testes adversariais documentados com capturas de tela
- Mensagens de erro que não vazam prompt, stack trace ou dados sensíveis

---

## Tecnologias e ferramentas

`Figma` · `Lovable` · `Supabase (Auth e Edge Functions)` · `WCAG 2.1 AA` · `LBI`

##  Estrutura do repositório

```
.
├── README.md
├── docs/
│   └── relatorio1.docx
└── imagens/
    └── (prints das telas do protótipo)
```

##  Referências

- ABNT. **NBR 14724**: informação e documentação — trabalhos acadêmicos — apresentação. Rio de Janeiro, 2011.
- BARBOSA, S. D. J.; SILVA, B. S. da. **Interação humano-computador**. Rio de Janeiro: Elsevier, 2010.
- BRASIL. [Lei nº 13.146, de 6 de julho de 2015](https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2015/lei/l13146.htm) (Lei Brasileira de Inclusão).
- MELO, A. M.; BARANAUSKAS, M. C. C. Design e avaliação de tecnologia web-acessível para crianças. In: SBMídia, 12., 2006, Natal. **Anais**. Natal: SBC, 2006. p. 121-130.
- SASSAKI, R. K. **Inclusão**: construindo uma sociedade para todos. 8. ed. Rio de Janeiro: WVA, 2010.
- W3C. [**Web Content Accessibility Guidelines (WCAG) 2.1**](https://www.w3.org/TR/WCAG21/). 2018.

---

<sub>Trabalho acadêmico desenvolvido na UNICID.</sub>
