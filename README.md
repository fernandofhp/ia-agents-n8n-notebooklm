# Engenharia de Automação: Agentes de IA Autônomos e Orquestração com n8n

## 🎯 Escopo da Pesquisa & Objetivos de Aprendizado

Este repositório consolida o desenvolvimento de um **Caderno Temático Avançado** criado no **NotebookLM**, como parte do desafio prático de Aprendizagem Ativa da DIO. 

O foco desta pesquisa é investigar a transição dos fluxos de trabalho lineares (IaaS/iPaaS tradicionais) para **Sistemas Multi-Agentes de IA (AI Agents)** orquestrados via **n8n**, explorando como LLMs integradas a ferramentas (*tools*) e memória podem tomar decisões dinâmicas em ambientes corporativos.

### Objetivos Estratégicos:
* **Mapear a Arquitetura de Agentes:** Compreender a fundo os conceitos de *Reasoning Engine* (Mecanismos de Raciocínio), memória de curto/longo prazo (vetoriais) e o paradigma *Human-in-the-loop*.
* **Analisar a Orquestração Avançada no n8n:** Dominar os nós de IA avançados do n8n (*AI Agent Node*, *Tools Node*, *Vector Store*) e entender como expor APIs e sistemas legados como ferramentas para os agentes.
* **Mitigar Alucinações em Produção:** Avaliar técnicas de RAG (Geração Aumentada de Recuperação) dentro da esteira de automação para garantir respostas corporativas determinísticas e seguras.

---

## 📚 Curadoria de Fontes e Base de Conhecimento

Para mitigar alucinações e fundamentar o aprendizado em dados técnicos reais, o NotebookLM foi alimentado com a seguinte base de conhecimento especializada (3 a 5 fontes):

1. **Documentação Oficial do n8n (Advanced AI Nodes):** Guias técnicos sobre a implementação do nó *AI Agent* e a fiação de ferramentas e memórias.
2. **"The Rise of Autonomous AI Agents in Workflow Automation"** (Artigo Técnico/Whitepaper selecionado de repositórios abertos sobre a evolução das ferramentas de iPaaS).
3. **Manual de Integração de Ferramentas (LangChain/n8n Concepts):** Documento detalhando como transformar requisições HTTP REST em *tools* interpretáveis por LLMs.

---

## 🔬 Engenharia de Prompts & Registro de "Cicatrizes" (Troubleshooting)

O grande diferencial deste projeto foi o processo iterativo de engenharia de prompts dentro do NotebookLM para extrair o melhor nível de detalhamento técnico, documentado abaixo:

### 🛑 Rodada 1: Abordagem Exploratória (Resultado Superficial)
* **Prompt Utilizado:** `"Explique como o nó de AI Agent do n8n funciona."`
* **Comportamento da IA:** A IA retornou uma resposta comercial/documental rasa, explicando que o nó usa modelos de linguagem para executar tarefas, sem detalhar a mecânica de loops de pensamento.
* **Cicatriz de Troubleshooting:** Prompts amplos em bases de dados técnicas geram resumos enciclopédicos. Para arquitetura de software, é preciso forçar a IA a agir como um engenheiro de sistemas.

### 🔄 Rodada 2: Contextualização por Papel (Efeito Alucinação Parcial)
* **Prompt Utilizado:** `"Como um Arquiteto de Soluções, me diga quais os tipos de memória eu posso plugar no AI Agent do n8n usando apenas os arquivos fornecidos."`
* **Comportamento da IA:** O NotebookLM estruturou melhor a resposta, mas tentou sugerir bancos de dados genéricos (como Redis puro) que não estavam explícitos nos nós nativos das fontes enviadas.
* **Cicatriz de Troubleshooting:** A IA tendeu a usar o conhecimento geral dela quando o prompt ficou muito aberto. Foi necessário aplicar travas de escopo restritivas.

### 🎯 Rodada 3: Refinamento de Escopo e Restrição Máxima (Nota 10)
* **Prompt Utilizado:** `"Baseando-se estritamente na Fonte 1 (Documentação n8n), diferencie o comportamento do agente ao utilizar o nó 'Window Buffer Memory' versus 'Buffer Memory'. Monte uma tabela comparando os impactos de consumo de tokens de contexto."`
* **Comportamento da IA:** Resposta cirúrgica. A IA extraiu exatamente os trechos técnicos, ignorou o conhecimento externo e montou uma tabela de arquitetura precisa indicando como o histórico de conversas afeta o payload da API.

---

## 📖 Miniguia de Estudo: O Ecossistema de Agentes no n8n

*Este miniguia foi gerado e refinado de forma ativa através das interações documentadas acima.*

### 📄 1. Resumos Estruturados do Assunto
* - Cards didáticos: https://notebooklm.google.com/notebook/3c2ae6ee-93a4-4e11-a1cb-498b5966acf9 *

### 🧠 2. Glossário de Conceitos-Chave
* **AI Agent (Agente de IA):** Entidade de software que utiliza um modelo de linguagem para planejar e executar ações baseadas em objetivos, em vez de seguir um código linear rígido.
* **Tools (Ferramentas):** Interfaces de código (como sub-workflows do n8n ou requisições HTTP) que o Agente decide invocar quando precisa interagir com o mundo externo (ex: buscar dados no CRM, enviar um e-mail).
* **Vector Store / Embeddings:** Bancos de dados de vetores usados no n8n para dar memória semântica de longo prazo aos agentes, permitindo consultas RAG eficientes.
* **Loop de Reação (Reasoning Loop):** O ciclo de "Pensamento -> Ação -> Observação" que a LLM executa internamente até julgar que a tarefa do fluxo foi concluída.

### 🛠️ 3. Biblioteca de Prompts Reutilizáveis para Revisão
Guarde estes prompts no seu NotebookLM para revisitar este tema no futuro:
```text
PROMPT PARA MAPEAR NOVOS NÓS:
"Atuei como analista de integrações. Analise a nova fonte fornecida sobre o nó [NOME_DO_NO] do n8n e me diga: 1) Qual o input esperado, 2) Quais as ferramentas padrão ele aceita e 3) Forneça um exemplo de JSON de saída."
