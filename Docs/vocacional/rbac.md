# Controle de Acesso - Teste Vocacional

## 1. Objetivo

Este documento apresenta os níveis de acesso relacionados ao teste vocacional e define o que cada tipo de usuário pode fazer dentro da funcionalidade.

A intenção é separar o uso normal do teste das ações relacionadas à manutenção das informações utilizadas pelo sistema.

## 2. Perfis de Acesso

### 2.1 Usuário

O usuário é a pessoa que utiliza o teste vocacional para conhecer melhor os cursos que podem ter relação com o seu perfil.

Ele pode iniciar o teste, responder às perguntas, informar suas preferências e visualizar o resultado apresentado ao final.

### 2.2 Administrador

O administrador é responsável por manter as informações utilizadas pelo teste atualizadas.

Entre suas funções estão revisar perguntas, alternativas, perfis, cursos e modalidades disponíveis, além de realizar ajustes quando for necessário.

## 3. Matriz de Permissões

| Ação | Usuário | Administrador |
|---|---|---|
| Iniciar o teste vocacional | Sim | Sim |
| Responder às perguntas | Sim | Sim |
| Informar modalidade de ensino | Sim | Sim |
| Visualizar o resultado | Sim | Sim |
| Alterar perguntas e alternativas | Não | Sim |
| Atualizar cursos e modalidades | Não | Sim |
| Alterar os perfis utilizados no teste | Não | Sim |

## 4. Considerações sobre o Acesso

O usuário comum terá acesso apenas às funções necessárias para realizar o teste e visualizar o resultado.

As alterações nas informações internas do teste devem ficar restritas ao administrador ou à equipe responsável pelo sistema, evitando mudanças indevidas nas perguntas, perfis, cursos e modalidades.

Caso novos tipos de usuários sejam adicionados futuramente, as permissões poderão ser atualizadas de acordo com a necessidade do projeto.