---
highlighter: shiki
lineNumbers: false
aspectRatio: "16/10"
---

# twdo

---

## Integrantes

- André Silva de Oliveira

- Luana da Silva Chaves

- Pedro Lucas Barros Palma

- Vitor Barroso de Sousa

---

## Minimundo

O twdo é um organizador pessoal de tarefas minimalista, pensado em ser um ambiente simples e livre de distrações, de maneira que o usuário possa focar no que realmente precisa ser feito. Ele faz isso através de uma interface limpa, fácil de entender e agradável de utilizar.
<br>
<br>
Ele permite que o usuário crie uma conta (utilizando e-mail pessoal ou conta existente no GitHub) e já comece a criar suas tarefas. As tarefas podem ser agrupadas em projetos e arrastadas ao longo da tela para ordená-las. Dependendo da direção que o usuário arraste a tarefa, ela pode ser adicionada para um projeto ou iniciar um timer pomodoro para a realização da tarefa.
<br>
<br>
A aplicação também conta com uma área reservada para as tarefas do dia atual (que possui também informações relacionadas à temperatura), de maneira que o usuário possa configurar um envio automático de e-mail para avisá-lo das tarefas que ele organizou para aquele dia. As tarefas também ser agendadas para serem realizadas em um determinado dia, com uma área dedicada do aplicativo para listar essas tarefas.

---

## Glossário

| Termo            | Descrição                                                                                                                                                                                                                                                                                                                              |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| To-do list       | Lista (ordenada ou não) de tarefas geralmente utilizada para organização pessoal.                                                                                                                                                                                                                                                      |
| API              | Sigla para "Application Programming Interface", que consiste em um conjunto de métodos prontos para serem utilizados, cujas implementações são abstraídas do desenvolvedor que irá utilizá-los.                                                                                                                                        |
| Chaves de Acesso | Chave única utilizada para identificar quem está fazendo uma determinada ação. Amplamente utilizadas para uso de API's externas da aplicação em desenvolvimento.                                                                                                                                                                       |
| Github           | Sistema de gerenciamento de repositórios Git em nuvem.                                                                                                                                                                                                                                                                                 |
| Registro         | Criação de conta única para um usuário poder utilizar a aplicação.                                                                                                                                                                                                                                                                     |
| Login            | Acesso à uma conta previamente criada pelo usuário para poder utilizar a aplicação.                                                                                                                                                                                                                                                    |
| JWT              | Sigla para "JSON Web Token". Consiste em um código hash devolvido pelo servidor para o navedor após login bem sucedido. O hash conterá informações à respeito do usuário e será enviado em futuros pedidos para o servidor quando o usuário precisar acessar rotas protegidas, obrigando-o a realizar o login para utilizar o sistema. |
| Tarefa           | Tarefa ligada à um único usuário que conterá uma descrição, data e data limite.                                                                                                                                                                                                                                                        |
| Projeto          | Conjunto de Tarefas.                                                                                                                                                                                                                                                                                                                   |
| Pomodoro         | Timer utilizado para que o usuário possa focar em realizar uma tarefa dentro de um determinado período de tempo.                                                                                                                                                                                                                       |

---

## Requisitos Funcionais<span> ></span> <h3>Projetos e Tarefas</h3>

| RF  | Descrição                                                                             |
| --- | ------------------------------------------------------------------------------------- |
| RF1 | O sistema deve permitir que o usuário crie uma Tarefa                                 |
| RF2 | O sistema deve permitir que o usuário liste as Tarefas dele agendadas para aquele dia |
| RF3 | O sitema deve permitir que o usuário liste as Tarefas agendadas para dias futuros     |
| RF4 | O sitema deve permitir que o usuário marque uma Tarefa como feita                     |
| RF5 | O sitema deve permitir que o usuário edite a descrição e as datas de uma Tarefa       |
| RF6 | O sistema deve permitir que o usuário agrupe Tarefas em um Projeto                    |
| RF7 | O sistema deve permitir que o usuário veja seus Projetos atuais                       |
| RF8 | O sistema deve permitir que o usuário edite as Tarefas de seus Projetos               |
| RF9 | O sistema deve permitir que o usuário edite o nome de seus Projetos                   |

---

## Requisitos Funcionais<span> ></span> <h3>Conta e Autenticação</h3>

| RF   | Descrição                                                                                                                                                      |
| ---- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| RF10 | O sitema deve permitir autenticação com Github                                                                                                                 |
| RF11 | O sistema deve permitir que o usuário crie uma conta utilizando email ou através de oAuth com conta do Github                                                  |
| RF12 | O sistema deve exigir que o usuário esteja logado no sistema para acessar quaisquer funcionalidades relacionadas à Tarefas, Projetos ou Configurações de Conta |
| RF13 | O sistema deve permitir que o usuário se autentique fornecendo um endereço de email e senha ou utilizando uma conta do Github                                  |
| RF14 | O sistema deve permitir que o usuário delete sua própria conta                                                                                                 |
| RF15 | O sistema deve permitir que o usuário altere o email da sua própria conta                                                                                      |

---

## Requisitos Funcionais<span> ></span> <h3>Features e Armazenamento</h3>

| RF   | Descrição                                                                                                                               |
| ---- | --------------------------------------------------------------------------------------------------------------------------------------- |
| RF16 | O sistema deve permitir que o usuário configure um envio de email automático para lembrá-lo das suas Tarefas agendadas para o dia atual |
| RF17 | O sistema deve armazenar os registros de Usuários, Tarefas e Projetos em banco de dados próprio                                         |
| RF18 | O sistema deve permitir que o usuário escolha entre tema claro ou escuro                                                                |
| RF19 | O sistema deve permitir que o usuário utilize um timer pomodoro                                                                         |

---

## Requisitos Não Funcionais

| RNF  | Descrição                                                           |
| ---- | ------------------------------------------------------------------- |
| RNF1 | O sistema deve criptografar a senha do usuário antes de armazená-la |
| RNF2 | O sistema não deve expor as chaves de autenticação do usuário       |

---

## Regras de Negócio

| RN  | Descrição                                                                                                                             |
| --- | ------------------------------------------------------------------------------------------------------------------------------------- |
| RN1 | Um usuário não pode cadastrar uma conta com um email já pertencente à outra conta cadastrada.                                         |
| RN2 | Um usuário não pode alterar o email da sua conta para um email já pertencente à outra conta cadastrada.                               |
| RN3 | Um usuário não pode associar uma Tarefa à mais de um Projeto.                                                                         |
| RN4 | Um usuário só pode realizar qualquer operação de usuário (Manter tarefas, projetos, deletar conta, alterar email) após se autenticar. |

---

## Integrações

1. Github oAuth
2. Weather API
3. SendGrid

---

## Casos de Uso

<pre>
<span>1.</span> Manter Conta
  <span>1.1</span> Registrar Conta
  <span>1.2</span> Deletar Conta
  <span>1.3</span> Alterar Email
<span>2.</span> Manter Tarefa
<span>3.</span> Manter Projeto
<span>4.</span> Iniciar Sessão
<span>5.</span> Enviar Feedback
<span>6.</span> Arrastar Tarefa
<span>7.</span> Reordenar projeto
<span>8.</span> Ver previsão da temperatura
<span>9.</span> Configurar envio de email com resumo do dia
<span>10.</span> Usar Pomodoro
<span>11.</span> Iniciar Modo Foco
<span>12.</span> Mudar tema da aplicação
</pre>

---

## Diagrama de Casos de Uso

<img src="/use_cases.png">

---

## Casos de Uso<span> ></span> <h3>1.1 - Registrar Conta</h3>

| Propriedade       | Descrição                                                                 |
| ----------------- | ------------------------------------------------------------------------- |
| Nome              | Registrar conta                                                           |
| Objetivo          | Criar conta na aplicação                                                  |
| Atores            | Usuário                                                                   |
| Pré-condições     | Ator na tela de cadastro                                                  |
| Trigger           | Ator seleciona "Sign up"                                                  |
| Fluxo Principal   | 1. Ator digita um nome de usuário, email e senha nos campos do formulário |
|                   | 2. Ator seleciona "Sign up"                                               |
|                   | 3. Sistema redireciona para tela de login                                 |
| Fluxo Alternativo | 1. Ator seleciona "Sign up with Github"                                   |
|                   | 2. Sistema redireciona para telas de confirmação                          |
|                   | 3. Ator seleciona "I accept"                                              |
|                   | 4. Sistema redireciona para tela de login.                                |
| Extensões         | N/A                                                                       |
| Pós-condições     | Ator na tela de login                                                     |
| Regras de negócio | N/A                                                                       |

---

## Casos de Uso<span> ></span> <h3>1.2 - Deletar Conta</h3>

| Propriedade       | Descrição                                                    |
| ----------------- | ------------------------------------------------------------ |
| Nome              | Deletar conta                                                |
| Objetivo          | Deletar conta da aplicação                                   |
| Atores            | Usuário                                                      |
| Pré-condições     | Ator precisa estar logado e na página "Settings"             |
| Trigger           | Ator clica em "Delete your Account"                          |
| Fluxo Principal   | 1. Ator clica no botão "Delete your Account"                 |
|                   | 2. Sistema pede uma confirmação da ação                      |
|                   | 3. Ator confirma a ação                                      |
|                   | 4. Sistema deleta a conta e redireciona para tela de sign up |
| Extensões         | N/A                                                          |
| Pós-condições     | Ator na tela de sign up                                      |
| Regras de negócio | N/A                                                          |

---

## Casos de Uso<span> ></span> <h3>1.3 - Alterar Email</h3>

| Propriedade       | Descrição                                                                                                          |
| ----------------- | ------------------------------------------------------------------------------------------------------------------ |
| Nome              | Alterar email                                                                                                      |
| Objetivo          | Alterar endereço de email da conta                                                                                 |
| Atores            | Usuário                                                                                                            |
| Pré-condições     | Ator precisa estar logado e na página "Settings"                                                                   |
| Trigger           | Ator clica em "Change my email"                                                                                    |
| Fluxo Principal   | 1. Ator preenche formulário com novo email                                                                         |
|                   | 2. Ator clica em "Save Changes"                                                                                    |
|                   | 3. Sistema pede uma confirmação da ação                                                                            |
|                   | 4. Ator confirma a ação                                                                                            |
|                   | 5. Sistema altera email, mantém o ator na página "Settings" e mostra uma notificação caso a ação seja bem-sucedida |
| Extensões         | N/A                                                                                                                |
| Pós-condições     | Ator na tela "Settings"                                                                                            |
| Regras de negócio | RN2                                                                                                                |

---

## Casos de Uso<span> ></span> <h3>2 - Iniciar Sessão</h3>

| Propriedade       | Descrição                                                                   |
| ----------------- | --------------------------------------------------------------------------- |
| Nome              | Iniciar sessão                                                              |
| Objetivo          | Iniciar sessão na aplicação                                                 |
| Atores            | Usuário                                                                     |
| Pré-condições     | O usuário não pode estar logado na aplicação e possuir uma conta registrada |
| Trigger           | Ator seleciona "Sign in"                                                    |
| Fluxo Principal   | 1. Ator digita email e senha nos campos do formulário                       |
|                   | 2. Ator seleciona "Sign in"                                                 |
|                   | 3. Sistema redireciona para tela inicial de "Today"                         |
| Fluxo Alternativo | 1. Ator seleciona "Sign in with Github"                                     |
|                   | 2. Sistema redireciona para telas de confirmação                            |
|                   | 3. Ator seleciona "I accept"                                                |
|                   | 4. Sistema redireciona para inicial de "Today"                              |
| Extensões         | N/A                                                                         |
| Pós-condições     | Ator na tela "Today"                                                        |
| Regras de negócio | N/A                                                                         |

---

## Casos de Uso<span> ></span> <h3>3 - Enviar Feedback</h3>

| Propriedade       | Descrição                                                                         |
| ----------------- | --------------------------------------------------------------------------------- |
| Nome              | Enviar Feedback                                                                   |
| Objetivo          | Enviar feedback da aplicação para os desenvolvedores                              |
| Atores            | Usuário                                                                           |
| Pré-condições     | O Ator precisa estar logado na aplicação e na tela de "Settings"                  |
| Trigger           | Ator seleciona "Send Feedback"                                                    |
| Fluxo Principal   | 1. Sistema mostra uma caixa de texto para o usuário                               |
|                   | 2. Ator digita sua mensagem na caixa de texto                                     |
|                   | 3. Ator seleciona "Send Feedback"                                                 |
| Extensões         | N/A                                                                               |
| Pós-condições     | Sistema mostra uma notificação de agradecimento e retira a caixa de texto da tela |
| Regras de negócio | N/A                                                                               |

---

## Casos de Uso<span> ></span> <h3>4 - Configurar envio de email com resumo do dia</h3>

| Propriedade       | Descrição                                                                              |
| ----------------- | -------------------------------------------------------------------------------------- |
| Nome              | Configurar envio de email com resumo do dia                                            |
| Objetivo          | Configurar envio de email diário com informações das tarefas agendadas para aquele dia |
| Atores            | Usuário                                                                                |
| Pré-condições     | O Ator precisa estar logado na aplicação e na tela de "Settings"                       |
| Trigger           | N/A                                                                                    |
| Fluxo Principal   | 1. Ator marca a caixa "Send daily reminder of my Tasks"                                |
|                   | 2. Ator seleciona o botão "Save Changes"                                               |
| Extensões         | N/A                                                                                    |
| Pós-condições     | Sistema mostra uma notificação de que as configurações foram salvas com sucesso        |
| Regras de negócio | N/A                                                                                    |

---

## Links

- https://balsamiq.cloud/sxy21mi/pqwza
