# WayPoint

**TCC - WayPoint** (Sistema Inteligente de Monitoramento de Transporte Público)

---

## 📌 Funcionalidades do Sistema

### 🔐 1. Autenticação e Controle de Acesso
- Cadastro de usuário
- Login no sistema
- Diferenciação de perfis:
  - **ADMIN** (empresa)
  - **USER** (passageiro)
- Controle de permissões por tipo de usuário

### 👤 2. Gerenciamento de Usuário
- Cadastro de usuário
- Atualização de dados
- Sistema de confiabilidade do usuário (peso para consenso)
- Definição de preferências:
  - Linhas favoritas
  - Regiões/bairros de interesse
  - Tipo de notificação desejada

### 🚌 3. Gerenciamento de Linhas e Paradas
- Cadastro de linhas (ADMIN)
- Cadastro de paradas (ADMIN)
- Associação de paradas a linhas
- Consulta de linhas disponíveis
- Consulta de paradas de uma linha

### 📢 4. Registro de Ocorrências Oficiais (ADMIN)
- **Criar ocorrência oficial:**
  - Ônibus quebrado
  - Atraso
  - Desvio de rota
  - Interdição
- **Definir:**
  - Linha afetada
  - Região (opcional)
  - Prioridade (normal ou crítica)
- Atualizar ocorrência
- Encerrar ocorrência

### 🔔 5. Sistema de Notificações
- Envio de notificações baseadas em:
  - Linhas favoritas
  - Região do usuário
  - Notificação de ocorrências oficiais
- Filtragem por tipo:
  - Apenas críticas
  - Todas
- Visualização de notificações no sistema

### 📍 6. Envio de Reportes pelos Usuários
- Usuários podem registrar eventos como:
  - Ônibus passou no ponto
  - Ônibus atrasado
  - Ônibus lotado
  - Ônibus ainda não passou
- **Cada reporte contém:**
  - Linha
  - Parada (opcional)
  - Tipo de evento
  - Horário

### 🧠 7. Sistema de Validação por Consenso
- Agrupar reportes semelhantes
- Somar "peso" dos usuários
- Validar informação quando atingir um limite
- Descartar reportes inconsistentes
- Considerar confiabilidade do usuário

### ⏳ 8. Sistema de Expiração de Dados
- Definir tempo de validade dos reportes (ex: 10 minutos)
- Remover automaticamente dados antigos
- Garantir que apenas dados recentes influenciem o sistema

### 📊 9. Status Dinâmico das Linhas
- O sistema calcula automaticamente o status:
  - Normal
  - Atrasada
  - Lotada
  - Interrompida
- **Baseado em:**
  - Reportes validados
  - Ocorrências oficiais

### 🔎 10. Consulta de Informações
- Usuário pode:
  - Ver status da linha
  - Ver ocorrências ativas
  - Ver histórico recente
  - Ver informações das paradas

### ⚙️ 11. Processamento Interno do Sistema
- Processar reportes recebidos
- Atualizar status das linhas
- Validar informações automaticamente
- Integrar dados de usuário + empresa

### 🔄 12. Tarefas Automáticas (Scheduler)
- Remover reportes expirados
- Atualizar status das linhas periodicamente
- Manter consistência dos dados

### 🛡️ 13. Segurança do Sistema
- Autenticação (login)
- Autorização (ADMIN vs USER)
- Proteção de rotas da API
- Validação de dados recebidos

---

## 🧩 Visão Macro do Sistema

O sistema tem basicamente **5 grandes blocos**:

1. **Usuários**
2. **Linhas e paradas**
3. **Reportes colaborativos**
4. **Ocorrências oficiais**
5. **Sistema inteligente** (consenso + status)

---

## 📋 Requisitos do Sistema

### ✅ Requisitos Funcionais (RF)

*Tudo aquilo que o usuário pode usar ou que o sistema executa.*

#### 🔐 Autenticação e Usuários
- **RF01** – O sistema deve permitir o cadastro de usuários.
- **RF02** – O sistema deve permitir que usuários realizem login.
- **RF03** – O sistema deve diferenciar usuários por tipo (ADMIN e USER).
- **RF04** – O sistema deve permitir que o usuário atualize seus dados.

#### 👤 Preferências do Usuário
- **RF05** – O sistema deve permitir que o usuário selecione linhas favoritas.
- **RF06** – O sistema deve permitir que o usuário selecione regiões de interesse.
- **RF07** – O sistema deve permitir configurar preferências de notificação.

#### 🚌 Linhas e Paradas
- **RF08** – O sistema deve permitir que o ADMIN cadastre linhas.
- **RF09** – O sistema deve permitir que o ADMIN cadastre paradas.
- **RF10** – O sistema deve associar paradas às linhas.
- **RF11** – O sistema deve permitir a consulta de linhas disponíveis.
- **RF12** – O sistema deve permitir visualizar as paradas de uma linha.

#### 📢 Ocorrências Oficiais
- **RF13** – O sistema deve permitir que o ADMIN registre ocorrências oficiais.
- **RF14** – O sistema deve permitir definir a linha afetada pela ocorrência.
- **RF15** – O sistema deve permitir definir prioridade da ocorrência.
- **RF16** – O sistema deve permitir atualizar ocorrências.
- **RF17** – O sistema deve permitir encerrar ocorrências.

#### 🔔 Notificações
- **RF18** – O sistema deve enviar notificações de ocorrências oficiais aos usuários.
- **RF19** – O sistema deve filtrar notificações com base nas preferências do usuário.
- **RF20** – O sistema deve permitir visualizar notificações no sistema.

#### 📍 Reportes de Usuários
- **RF21** – O sistema deve permitir que usuários enviem reportes.
- **RF22** – O sistema deve registrar o tipo de evento do reporte.
- **RF23** – O sistema deve associar o reporte a uma linha.
- **RF24** – O sistema deve registrar o horário do reporte.

#### 🧠 Validação por Consenso
- **RF25** – O sistema deve agrupar reportes semelhantes.
- **RF26** – O sistema deve calcular o peso dos reportes com base na confiabilidade do usuário.
- **RF27** – O sistema deve validar informações ao atingir um limite mínimo.
- **RF28** – O sistema deve descartar reportes inconsistentes.

#### 📊 Status das Linhas
- **RF29** – O sistema deve calcular automaticamente o status das linhas.
- **RF30** – O sistema deve definir status como: normal, atrasado, lotado ou interrompido.
- **RF31** – O sistema deve atualizar o status com base em reportes e ocorrências.

#### 🔎 Consulta de Informações
- **RF32** – O sistema deve permitir consultar o status de uma linha.
- **RF33** – O sistema deve exibir ocorrências ativas.
- **RF34** – O sistema deve permitir visualizar informações das paradas.

#### 🔄 Processos Automáticos
- **RF35** – O sistema deve remover reportes expirados automaticamente.
- **RF36** – O sistema deve atualizar periodicamente o status das linhas.

---

### ⚙️ Requisitos Não Funcionais (RNF)

*Como o sistema deve funcionar.*

#### 🖥️ Plataforma e Acesso
- **RNF01** – O sistema deve ser acessível via navegador web.
- **RNF02** – O sistema deve ser compatível com dispositivos móveis e desktops.

#### ⚡ Desempenho
- **RNF03** – O sistema deve responder às requisições em até 2 segundos.
- **RNF04** – O sistema deve processar reportes em tempo quase real.

#### 🔐 Segurança
- **RNF05** – O sistema deve exigir autenticação para acesso às funcionalidades.
- **RNF06** – O sistema deve restringir ações administrativas ao perfil ADMIN.
- **RNF07** – O sistema deve validar os dados recebidos nas requisições.

#### 🔄 Atualização e Consistência
- **RNF08** – Os reportes devem expirar após um tempo definido (ex: 10 minutos).
- **RNF09** – O sistema deve manter apenas dados relevantes e atualizados.

#### 📊 Confiabilidade
- **RNF10** – O sistema deve validar informações utilizando consenso entre usuários.
- **RNF11** – O sistema deve minimizar a influência de dados inconsistentes.

#### 🔔 Notificações
- **RNF12** – As notificações devem ser entregues em tempo adequado.

#### 🧩 Escalabilidade
- **RNF13** – O sistema deve suportar múltiplos usuários simultâneos.

---
