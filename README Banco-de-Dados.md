💾 Projeto Integrador – Banco de Dados
📚 Descrição do Projeto
Este repositório contém o Schema e todos os Scripts SQL necessários para criar e gerenciar o Banco de Dados Relacional (PostgreSQL) que dará suporte ao sistema Back-End da nossa Escola Simulado.

Nosso objetivo é fornecer uma estrutura de dados robusta e íntegra para armazenar informações críticas como:

Alunos e Professores

Notas e Frequência

Perfil e Matrícula

Turmas e Disciplinas

O projeto completo é dividido entre vários grupos:

💾 Banco de Dados (nosso grupo): modelagem, criação e gestão do schema.
--
⚙️ Responsabilidades do Grupo Banco de Dados
Nosso grupo será responsável por:

Modelar o Banco de Dados: Criar o Diagrama Entidade-Relacionamento (ERD) e o Schema final.

Implementar a Estrutura (DDL): Criar todas as tabelas, colunas, chaves e relacionamentos.

Gerar Scripts SQL: Desenvolver os comandos DDL e DML (seeders) para criação e população inicial do banco.

Garantir a Integridade: Definir e aplicar restrições de Chaves Primárias e Estrangeiras.

Hospedar: Provisionar a instância do banco de dados na nuvem para uso dos demais grupos.

Documentação: Manter o dicionário de dados atualizado.
--
🧰 Tecnologias que serão utilizadas
PostgreSQL (SGBD Relacional)

pgAdmin 4 (Ferramenta de Gerenciamento Visual)

Draw.io / Lucidchart (Modelagem do Diagrama ERD)

SQL (Linguagem para DDL e DML)

Render / ElephantSQL (Sugestões para Hospedagem)
--
🚀 Etapas do Desenvolvimento
Modelagem de Dados    - Definir entidades e relacionamentos    - Desenhar o Diagrama ERD

Configuração do ambiente    - Instalar o PostgreSQL e o pgAdmin    - Criar o banco de dados local

Implementação do Schema    - Escrever e executar scripts DDL (criação de tabelas)    - Escrever e executar scripts DML (dados iniciais/seeders)

Testes e integração    - Testar a integridade das relações e a performance das consultas.    - Garantir a conexão para o grupo Back-End.
--
🔗 Comunicação com os Outros Grupos
O Back-End vai consumir o Schema e a String de Conexão que forneceremos.

Usaremos o Formato SQL para entregar a estrutura e os dados iniciais.

Vamos combinar a estrutura final das tabelas (nomes de colunas e tipos de dados) com o Back-End para facilitar o mapeamento no Sequelize.
--
🧩 ETAPAS INICIAIS DO GRUPO BANCO DE DADOS
🥇 1. Modelar Antes de escrever qualquer código SQL, o grupo precisa definir a estrutura. O sistema é tipo Net Escola, então precisamos de entidades para: Alunos, Professores, Turmas, Disciplinas, Notas e Frequência. Anotem quais atributos (colunas) cada entidade (tabela) precisa ter e como elas se relacionam (1:N, N:M).

📝 Dica: Façam um Diagrama Entidade-Relacionamento (ERD) usando Draw.io ou Lucidchart. Isso é o nosso "mapa".
--
Entidade,Atributos Críticos,Relacionamento Principal
Aluno,"ID, nome, matrícula, senha",1 Aluno -> N Matrículas
Professor,"ID, nome, registro, senha",1 Professor -> N Disciplinas
Notas,"ID, valor, aluno_id, disciplina_id",N:M entre Aluno e Disciplina
--
🥈 2. Criar o Repositório Um integrante cria um repositório no GitHub chamado por exemplo database-net-escola. Compartilha o link com os outros (adiciona como colaboradores).
--
🥉 3. Configurar Ambiente Local Na sua máquina (ou máquina definida como primária):

Ação:

Instalar o PostgreSQL (SGBD).

Instalar o pgAdmin 4 (Ferramenta de Gerenciamento).

Isso prepara o ambiente para trabalhar com o banco localmente.
--
🧱 4. Criar o Banco de Dados Local Abra o pgAdmin 4 e crie o banco de dados do projeto.

Ação:

Clique em "Servers" > "Create" > "Server".

Conecte-se ao seu PostgreSQL local.

Clique com o botão direito em "Databases" > "Create" > "Database..."

Nomeie-o, por exemplo, como escola_db.
--
⚙️ 5. Desenhar e Revisar o ERD O grupo finaliza o diagrama ERD (Entidade-Relacionamento) para garantir que todas as regras de negócio foram atendidas (por exemplo, como ligar Notas a Aluno e Disciplina).
--
🗄️ 6. Implementar DDL (Data Definition Language) Traduzam o ERD para código SQL, criando todas as tabelas e restrições.

Ação:

Crie um arquivo schema.sql (ou similar) no seu repositório.

Usem comandos CREATE TABLE para todas as entidades.

Adicionem PRIMARY KEY, FOREIGN KEY e NOT NULL.
--
🔐 7. Implementar DML (Data Manipulation Language) Criem os scripts para popular o banco com dados iniciais de teste (seeders).

Ação:

Crie um arquivo seeders.sql.

Usem comandos INSERT INTO para adicionar: 1 Professor Admin, 1 Aluno de Teste, 1 Turma e 1 Disciplina.

Isso é crucial para o Back-End testar o login.
--
🧪 8. Testar Consultas e Integridade Usem o pgAdmin ou o DBeaver para testar as tabelas.

Ação:

Execute consultas simples (SELECT * FROM alunos).

Tente inserir dados inválidos para garantir que as Chaves Estrangeiras estão bloqueando (Teste de Integridade).

Confiram se todas as tabelas estão prontas para o Sequelize (Back-End).
--
📘 9. Hospedar e Fornecer Conexão Escolham a plataforma de hospedagem (ex: Render, ElephantSQL) e provisionem a instância online.

Ação:

Execute os scripts schema.sql e seeders.sql na instância remota.

Forneça a String de Conexão (URL completa, user, password) para o grupo Back-End.
--
🧩 10. Documentar e Revisar Atualizem o README e o repositório no GitHub.

Ação:

Adicionem a imagem do ERD final no README.

Deixem claro o nome das tabelas e as chaves.

Confirmem com o Back-End que eles conseguem se conectar e enxergar os dados iniciais
