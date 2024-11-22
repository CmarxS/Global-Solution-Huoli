# Projeto: HUOLI
## Descrição
O *HUOLI* é um protótipo de site desenvolvido em Next.js para simular uma solução de gerenciamento de consumo de energia em eletrodomésticos. O projeto visa auxiliar usuários a monitorar o consumo de seus eletrodomésticos, gerenciar suas configurações e reduzir o consumo de energia em casa. A plataforma conta com funcionalidades que permitem cadastrar, atualizar, visualizar, e deletar eletrodomésticos, além de realizar ajustes nas configurações de consumo.
## Funcionalidades do Site
O site contém informações sobre os eletrodomésticos cadastrados e suas respectivas configurações de consumo. Para acessar essas funcionalidades, o usuário precisa se cadastrar e realizar login. Após o login, ele é redirecionado para a página inicial, onde pode:
## Funcionalidades do Site
O site contém informações sobre os eletrodomésticos cadastrados e suas respectivas configurações de consumo. Para acessar essas funcionalidades, o usuário precisa se cadastrar e realizar login. Após o login, ele é redirecionado para a página inicial, onde pode:

- Consultar as informações dos eletrodomésticos cadastrados:

    - O usuário pode acessar a lista de todos os eletrodomésticos cadastrados, bem como visualizar detalhes como nome, marca, modelo e o custo estimado de consumo.
- Adicionar, alterar ou deletar um eletrodoméstico:

    - Os eletrodomésticos podem ser gerenciados diretamente pelo usuário utilizando uma API em Java. É possível realizar operações de criação, atualização e exclusão de eletrodomésticos.

- Configurar o consumo de um eletrodoméstico:
 - O usuário pode acessar a página de configurações de um eletrodoméstico específico para definir limites de consumo e ações automáticas, como alertas ou desligamento, de forma a otimizar o uso de energia.
## APIs Utilizadas
### API em Java
- Eletrodomésticos: Endpoints para criar, atualizar, visualizar e deletar eletrodomésticos.
- Clientes: Endpoints para criar, atualizar, visualizar e deletar clientes.
- Github - Repositório CRUD API
### API em Python (Flask)
- Autenticação: Endpoint para autenticar o usuário.
- Configurações de Consumo: Endpoints para criar, atualizar, visualizar e deletar configurações de consumo associadas aos eletrodomésticos.
- Github - Repositório Autenticação API
## Como rodar o projeto
1. Necessário ter a versão 20.15.1 do NodeJS
2. Necessário ter a versão 10.7.0 do Node Package Manager (NPM)
3. Rodar o comando npm install
4. Rodar o comando npm run dev



