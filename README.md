# 💰 FinChat - App Conversacional de Finanças Pessoais

Um aplicativo de organização financeira pessoal simples e humano, movido a Inteligência Artificial. Sem planilhas genéricas, formulários cansativos ou excesso de entrada manual.

---

## 📌 1. Resumo do Projeto

O **FinChat** é um aplicativo de controle financeiro projetado para iniciantes e pessoas que desistem dos apps tradicionais por conta da alta complexidade e da digitação manual ostensiva.

Com o FinChat, a gestão financeira é feita através de uma **conversa natural**: o usuário envia mensagens de texto ou áudio (ex.: *"Gastei 45 reais no almoço"*), e o Agente Financeiro alimentado por IA registra, categoriza e consolida as transações automaticamente.

### 🌟 Principais Funcionalidades

- **Registro via Chat Natural:** Entrada de receitas e despesas por texto ou áudio sem necessidade de preencher formulários rígidos.
- **Categorização Automática:** Reconhecimento instantâneo do valor, data e categoria do gasto via IA.
- **Agente Financeiro Educativo:** Recomendações personalizadas e dicas sutis de economia enviadas no momento certo.
- **Dashboard Minimalista:** Visão clara de entradas, saídas, saldo e distribuição de gastos em gráficos simples.
- **Acompanhamento de Metas:** Definição de objetivos financeiros com barras de progresso visuais e projeções automáticas de aportes.

---

## 📑 2. Prompt Final (PRD - Product Requirement Document)

Abaixo está a especificação completa utilizada para orientar a geração da interface e regras de negócio no Lovable.dev:

```text
Crie o front-end de um aplicativo web e mobile-first de Organização de Finanças Pessoais Conversacional chamado "FinChat". O design deve ser moderno, limpo, acolhedor e minimalista, utilizando cores suaves (tons de verde para finanças/sucesso, cinza claro para fundos e acentos em azul ou roxo para a IA).

Sistemas de Navegação e Telas:
Inclua uma barra de navegação inferior (Bottom Navigation Bar) responsiva para alternar entre 3 telas principais:

1. TELA DE CHAT (Hub Principal):
- Cabeçalho com o nome do aplicativo e um avatar do "Agente Financeiro IA".
- Área de mensagens em estilo chat (balões do usuário à direita, balões da IA à esquerda).
- Exemplo de mensagem do usuário: "Gastei R$ 45,00 no almoço no restaurante".
- Exemplo de resposta da IA: Um balão com texto amigável acompanhado de um Card de Confirmação Interativo destacando:
  * Valor: R$ 45,00
  * Categoria: Alimentação
  * Data: Hoje
  * Botões de ação rápida: "Confirmar" (verde) e "Editar" (neutro).
- Card especial da IA com uma "Dica de Economia": destaque visual sutil com um ícone de lâmpada.
- Rodapé com um campo de entrada de texto flexível, botão de envio e um ícone de microfone (simulando gravação de áudio).

2. TELA DE DASHBOARD:
- Resumo Financeiro do Mês: Cards no topo mostrando "Entradas", "Saídas" e "Saldo Atual".
- Gráfico de Rosca (Donut Chart) simples exibindo a divisão de gastos por categorias (Ex: Alimentação, Moradia, Transporte, Lazer).
- Seção "Últimas Transações": Uma lista limpa de itens recentes com ícone de categoria, nome, data e valor (com cor vermelha para saídas e verde para entradas).

3. TELA DE METAS:
- Lista de cards com objetivos financeiros (ex: "Reserva de Emergência", "Viagem de Fim de Ano").
- Cada card deve ter: Título, Valor Atual / Valor Objetivo (ex: R$ 1.500 / R$ 5.000), Barra de Progresso elegante em porcentagem e uma sugestão sutil do agente (ex: "Faltam R$ 350/mês para atingir em Dezembro").
- Botão "Nova Meta" flutuante ou no topo.

Detalhes de UI/UX:
- Use Tailwind CSS, Lucide Icons e componentes do Shadcn UI.
- Adicione dados fictícios (mock data) para que o protótipo já venha preenchido e funcional para demonstração.
- Permita interatividade básica (ex: adicionar uma mensagem simulada no chat atualiza os estados do dashboard ou insere um novo item na lista).
```

Resultado Final no Loveable: https://pixel-perfect-dream-1931.lovable.app


---

## 🖼️ 3. prints

<img width="1906" height="954" alt="image" src="https://github.com/user-attachments/assets/49b9c928-d30a-4f4f-b8b8-95014974108e" />
<img width="1913" height="950" alt="image" src="https://github.com/user-attachments/assets/2bb8278b-5c4f-4880-b087-2b5efa81d609" />



---

## 🧠 4. Reflexão sobre o Processo de Desenvolvimento

### 🟢 O que funcionou bem?

- **Prototipagem Ultra Rápida:** Especificar os componentes de UI, fluxos e design system em um único prompt estruturado permitiu que o Lovable gerasse uma interface funcional e moderna em poucos segundos.
- **Arquitetura Conversacional:** A abordagem de "Chat em primeiro lugar" reduziu significativamente o atrito de usabilidade para registrar transações rápidas em comparação com menus tradicionais.
- **Divisão de Responsabilidades:** Separar a aplicação em Chat (entrada/interpretação), Dashboard (leitura/visão geral) e Metas (planejamento) manteve a experiência de usuário leve e organizada.

### 🔴 O que não funcionou como o esperado?

- **Ações Encadeadas sem Estado:** Em interações mais complexas (como editar um valor direto no chat e esperar atualização automática instantânea em gráficos do dashboard), foi necessário refinar as regras de estado do projeto manual ou via prompts de ajuste.
- **Ambiguidade em Entradas Múltiplas:** Frases que continham mais de um gasto em uma única mensagem (ex.: *"Gastei 20 no Uber e 50 no mercado"*) exigiram prompts mais específicos para garantir a criação de múltiplos cards de confirmação.

### 💡 O que aprendi sobre conversar e criar com IAs?

- **Clareza Contextual é Tudo:** IAs de geração de código respondem muito melhor a diretrizes que detalham o "estado desejado", o "comportamento visual" e a "estrutura de dados" de forma pragmática, em vez de comandos genéricos.
- **Desenvolvimento Iterativo:** O melhor fluxo não é tentar resolver 100% no primeiro prompt, mas sim estabelecer uma base sólida no prompt principal (PRD) e refiná-la incrementalmente com comandos focados.
- **Design Driven by Logic:** Projetar pensando primeiro no contrato de dados (ex.: o que a IA precisa extrair da mensagem do usuário) facilita enormemente a construção dos componentes visuais do aplicativo.
