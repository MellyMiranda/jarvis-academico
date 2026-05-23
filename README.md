# 🤖 JARVIS ACADÊMICO - Assistente pessoal acadêmico desenvolvido para a disciplina de Inteligência Artificial.

O sistema integra:

* LLM (Gemma 12B)
* RAG (Retrieval-Augmented Generation)
* Tool Calling
* Agenda acadêmica
* Lista de tarefas

---

# ▶️ Execução

Opção 1: Abrir diretamente pelo Google Colab
1. Abrir o notebook no Google Colab (https://colab.research.google.com/drive/1ntC-Y_NBj7c9B9EV27LVQyNuighO4NwE?usp=sharing)
2. Executar todas as células do notebook
3. Abrir interface Gradio gerado ao final da execução

Opção 2: Executar localmente pelo GitHub
1. Abrir repositório no GitHub
2. Clicar em: Code -> Download ZIP
3. Extrair o arquivo .zip
4. Abrir Google Colab
5. Fazer upload do notebook: Trabalho_jarvis_academico.ipynb
6. Executar todas as células
7. Abrir interface Gradio gerado ao final da execução

---

# 🤖 Ferramentas de IA Utilizadas

* Gemini
* ChatGPT

---

# ✅ Funcionalidades Implementadas (Trabalho 1)

## 1. Consulta a materiais acadêmicos (RAG)

O sistema permite fazer perguntas sobre materiais de estudo presentes no dataset.

Exemplos:

* "Explique regressão logística"
* "O que são embeddings?"
* "Resuma o conteúdo sobre redes neurais"

Fluxo implementado:

1. carregamento de documentos
2. divisão em chunks
3. geração de embeddings
4. recuperação de contexto relevante
5. geração de resposta utilizando LLM

---

## 2. Agenda acadêmica

O sistema permite:

* adicionar eventos
* listar eventos
* consultar eventos do dia
* consultar eventos da semana
* excluir eventos

Exemplos:

* "O que tenho hoje?"
* "Eventos da semana"

A agenda é armazenada localmente em JSON.

---

## 3. Lista de tarefas

O sistema permite:

* adicionar tarefas
* listar tarefas
* concluir tarefas
* excluir tarefas

Exemplos:

* "Adicionar tarefa estudar embeddings, domingo"
* "Concluir tarefa 0"

As tarefas são armazenadas localmente em JSON.

---

# 🛠️ Tool Calling

O sistema implementa Tool Calling utilizando a LLM Gemma 12B.
A decisão sobre qual ferramenta utilizar é feita pela própria LLM, não por lógica fixa.

Ferramentas implementadas:
* buscar_material_rag
* listar_agenda
* adicionar_evento
* excluir_evento
* listar_tarefas
* adicionar_tarefa
* concluir_tarefa
* excluir_tarefa

---

# 📊 Logs do Sistema

O sistema registra logs contendo:

* ferramenta utilizada
* entrada recebida
* saída gerada
* horário
* status de execução (se deu erro ou não)

Os logs são armazenados em arquivo JSON.

---

# 📂 Dataset

O dataset foi construído usando materiais acadêmicos relacionados a Inteligência Artificial.

Quantidade: 10 documentos

Temas/Arquivos usados:
1.Fundamentos de Machine Learning
2.Introdução à Inteligência Artificial.pdf
3.Regressão Logística.pdf
4.Redes Neurais Artificiais.pdf
5.RAG.pdf
6.Embeddings.pdf
7.Deep Learning (DL).pdf
8.LLM.pdf
9.Gradiente na Inteligência Artificial.pdf
10.Inteligência Artificial Generativa.pdf

---

# ✂️ Estratégia de Chunking

* divisão por tamanho de caracteres
* overlap entre chunks para preservar contexto

Impacto no sistema:

* melhora da recuperação semântica
* respostas mais relevantes
* menor perda de contexto

---

# ⚠️ Limitações do Dataset

Limitações identificadas:

* alguns PDFs possuem imagens e diagramas importantes que não são interpretados pelo sistema de extração de texto
* parte do contexto pode ser perdida devido ao processo de chunking
* chunks podem separar explicações relacionadas em blocos diferentes
* alguns caracteres especiais extraídos dos PDFs apresentam pequenas inconsistências de formatação
* a qualidade das respostas depende diretamente da qualidade do texto recuperado pelo RAG

---

# 🧠 Tecnologias Utilizadas

* Python (linguagem principal)
* Gradio (para criar a interface gráfica)
* LangChain (auxilio na construção do sistema RAG e integração com LLMs)
* FAISS (biblioteca usada para armazenar e buscar embeddings de forma eficiente no RAG)
* Sentence Transformers (biblioteca utilizada para gerar embeddings dos textos/documentos)
* OpenRouter API (utilizado para acessar o modelo Gemma 12B via API)
* Gemma 12B (LLM utilizado pelo sistema para interpretar perguntas, decidir tools e gerar respostas)

---

# 🏗️ Arquivos JSON utilizados:

* tarefas.json
* agenda.json
* logs.json
  
---

# 💻 Interface

O sistema possui interface gráfica desenvolvida em Gradio contendo:

* chat principal
* visualização de tarefas
* visualização de agenda
* visualização de logs

---

# 👨‍💻 Desenvolvido por  

* Melly Sabrina Araújo Miranda
