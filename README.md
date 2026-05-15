# Agno: criando agentes e sistemas multiagente

Repositório do curso **Agno: criando agentes e sistemas multiagente** da [Alura](https://cursos.alura.com.br/course/agno-agente-ia).

**Instrutor:** Fabio Contrera  
**Plataforma:** Google Colab

---

## Sobre o curso

Neste curso você aprenderá a construir sistemas de agentes de IA do zero, partindo de um agente simples até arquiteturas agênticas completas com times, workflows e gerenciamento em produção.

O case central é o **ScoutAI FC** — uma plataforma fictícia de inteligência artificial dedicada à Seleção Brasileira masculina de futebol. Ao longo das aulas, você vai construir progressivamente os agentes que compõem esse produto: o **Treinador** (líder conversacional), o **Olheiro** (busca de dados externos), o **Analista** (visualizações táticas) e o **Auxiliar Técnico** (decisão de escalação).

Todo o conteúdo é orientado à prática, com ênfase em **profundidade técnica**, **padrões arquiteturais reutilizáveis** e **autonomia para aplicar os conceitos em domínios reais**.

---

## Ementa

### Aula 1 — Criando seu primeiro agente com Agno

**Objetivos:** Entender o que é um agente de IA e como ele difere de um LLM puro, conhecer os diferenciais do Agno, criar e personalizar um agente com identidade e comportamento definidos.

| Vídeo | Título |
|-------|--------|
| 1.1 | Apresentação |
| 1.2 | Por que usar o Agno? |
| 1.3 | Construindo seu primeiro agente |

---

### Aula 2 — Turbinando agentes com Tools

**Objetivos:** Entender o papel de ferramentas em agentes, integrar Tavily e Wikipedia como fontes externas, criar uma política de fontes e identificar falhas no uso de tools.

| Vídeo | Título |
|-------|--------|
| 2.1 | Por que agentes precisam de tools? |
| 2.2 | Integrando tools com Agno |
| 2.3 | Tornando o agente mais inteligente com tools |

---

### Aula 3 — Times de IA: como fazer agentes trabalharem juntos

**Objetivos:** Entender padrões de colaboração multiagente, implementar time com Agno, criar tools customizadas de visualização, ativar memória de sessão e integrar RAG com base interna.

| Vídeo | Título |
|-------|--------|
| 3.1 | Por que usar múltiplos agentes? |
| 3.2 | Adicionando o Analista ao time |
| 3.3 | Refinando o time + RAG no Olheiro |

---

### Aula 4 — Orquestrando agentes com workflows

**Objetivos:** Entender workflows agênticos, modelar fluxos sequenciais, paralelos, condicionais e iterativos, usar Pydantic como contrato entre etapas e implementar roteamento inteligente entre time e workflow.

| Vídeo | Título |
|-------|--------|
| 4.1 | O que são workflows e quando usar? |
| 4.2 | Construindo o workflow completo |
| 4.3 | Evoluindo workflows: controle, decisões e qualidade |

---

### Aula 5 — Gerenciando agentes com AgentOS

**Objetivos:** Entender o papel do AgentOS na gestão de agentes em produção, configurar persistência com SQLite, monitorar execuções, ativar memória de longo prazo, versionar prompts e aplicar boas práticas de governança.

| Vídeo | Título |
|-------|--------|
| 5.1 | Do protótipo à produção: por que AgentOS? |
| 5.2 | Monitorando e gerenciando agentes |
| 5.3 | Governança, escala e boas práticas |

---

## Estrutura do repositório

```
agno-criando-agentes-e-sistemas-multiagente/
├── Aula 1 - Criando seu primeiro agente com Agno/
│   └── Aula_1_3.ipynb
├── Aula 2 - Turbinando agentes com Tools/
│   ├── Aula_2_2.ipynb
│   └── Aula_2_3.ipynb
├── Aula 3 - Times de IA/
│   ├── Aula_3_1.ipynb
│   ├── Aula_3_2.ipynb
│   └── Aula_3_3.ipynb
├── Aula 4 - Orquestrando agentes com workflows/
│   ├── Aula_4_1.ipynb
│   ├── Aula_4_2.ipynb
│   └── Aula_4_3.ipynb
└── Aula 5 - Gerenciando agentes com AgentOS/
    ├── Aula_5_1.ipynb
    ├── Aula_5_2.ipynb
    └── Aula_5_3.ipynb
    
```

---

## Pré-requisitos

- Python 3.10+
- Conta e chave de API na [OpenAI](https://platform.openai.com)
- Conta e chave de API no [Tavily](https://tavily.com) 
- Conta no [Google Colab](https://colab.research.google.com) (recomendado)

---

## Configuração das chaves de API no Colab

Os notebooks utilizam os **Secrets do Colab** para carregar as chaves com segurança. Antes de rodar qualquer célula:

1. No Colab, clique no ícone de chave 🔑 no menu lateral
2. Adicione dois secrets:
   - `OPENAI_API_KEY` → sua chave da OpenAI
   - `TAVILY_API_KEY` → sua chave do Tavily
3. Marque ambos como acessíveis pelo notebook

---

## Instalação

Para rodar localmente (fora do Colab):

```bash
pip install -U agno openai tavily-python wikipedia pydantic
```

Para a Aula 5 com AgentOS:

```bash
pip install -U "agno[os]" openai tavily-python wikipedia python-dotenv
```

---

## Rodando a UI do AgentOS localmente

A Aula 5.1 inclui o script `scoutai_5_1.py` para demonstrar a UI do AgentOS fora do Colab.

```bash
# Instalar dependências
pip install -U "agno[os]" openai tavily-python python-dotenv

# Configurar chaves
cp .env.example .env   # edite o .env com suas chaves

# Rodar
python scoutai_5_1.py
```

Acesse [os.agno.com](https://os.agno.com), clique em **Connect to Local** e informe `http://localhost:7777`.

---

## Tecnologias utilizadas

| Tecnologia | Uso |
|---|---|
| [Agno](https://docs.agno.com) | Framework principal de agentes |
| [OpenAI](https://platform.openai.com) | Modelos de linguagem |
| [Tavily](https://tavily.com) | Busca web otimizada para agentes |
| [LanceDB](https://lancedb.com) | Vector store para RAG (Aula 3.3) |
| [Plotly](https://plotly.com/python) | Visualizações do Analista (Aulas 3.2, 3.3) |
| [Pydantic](https://docs.pydantic.dev) | Contratos de tipos entre etapas de workflow (Aula 4) |
| [SQLite](https://sqlite.org) | Persistência local via AgentOS (Aula 5) |

---
