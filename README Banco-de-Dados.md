🗄️ Status do Projeto

🔧 Em desenvolvimento
📍 Etapa atual: Modelagem e criação do banco de dados

💡 Observações

Este README será atualizado conforme o desenvolvimento do projeto avança.
O objetivo deste guia é orientar o grupo responsável pelo Banco de Dados sobre as etapas iniciais: modelagem, criação, configuração e integração com o back-end.

🚀 ETAPAS INICIAIS DO GRUPO BANCO DE DADOS
🥇 1. Planejar e Modelar o Banco

Antes de criar as tabelas, o grupo precisa entender quais dados o sistema irá armazenar e como se relacionam.
Exemplo do sistema (Net Escola):

Alunos

Professores

Disciplinas

Turmas

Notas

Frequências

📘 Dica: Usem papel, Figma, Lucidchart, Draw.io ou dbdiagram.io para criar o DER (Diagrama Entidade-Relacionamento).
Definam as chaves primárias, estrangeiras e relacionamentos (1:N, N:N, 1:1).

🧩 2. Definir as Tabelas e Colunas

Crie uma tabela com as definições básicas, por exemplo:

Tabela	Campos	Tipo de Dado	Chave
Aluno	id, nome, email, senha, turma_id	SERIAL, VARCHAR, VARCHAR, VARCHAR, INT	PK, FK
Professor	id, nome, email, senha	SERIAL, VARCHAR, VARCHAR, VARCHAR	PK
Turma	id, nome, disciplina_id	SERIAL, VARCHAR, INT	PK, FK
Disciplina	id, nome	SERIAL, VARCHAR	PK
Nota	id, aluno_id, professor_id, valor, data	SERIAL, INT, INT, DECIMAL, DATE	PK, FK
🖥️ 3. Escolher e Instalar a Plataforma do Banco de Dados

O grupo pode usar uma das seguintes opções:

🐘 PostgreSQL (recomendado, compatível com o back-end Node.js e Sequelize)

💾 MySQL (alternativa popular)

☁️ ElephantSQL (PostgreSQL online e gratuito para testes)

☁️ Railway ou Render (para hospedar o banco na nuvem)

📦 Instalação local (PostgreSQL):

# Windows
Baixe e instale o PostgreSQL: https://www.postgresql.org/download/

# Verifique se o psql funciona
psql --version

⚙️ 4. Criar o Banco e as Tabelas

Após instalar, abra o pgAdmin ou use o terminal:

CREATE DATABASE net_escola;

\c net_escola;

CREATE TABLE aluno (
  id SERIAL PRIMARY KEY,
  nome VARCHAR(100),
  email VARCHAR(100) UNIQUE NOT NULL,
  senha VARCHAR(255) NOT NULL
);


Repita o processo para as outras tabelas (professor, turma, disciplina, nota, frequência, etc.).

🔄 5. Testar Consultas

Testem comandos básicos no SQL:

-- Inserir
INSERT INTO aluno (nome, email, senha) VALUES ('Maria Silva', 'maria@teste.com', '12345');

-- Consultar
SELECT * FROM aluno;

-- Atualizar
UPDATE aluno SET nome = 'Maria S.' WHERE id = 1;

-- Excluir
DELETE FROM aluno WHERE id = 1;

🔗 6. Integrar com o Back-End

Quando o grupo do back-end estiver pronto, combinem para usar o Sequelize:

📁 Criação do arquivo .env com as credenciais:

DB_HOST=localhost
DB_USER=postgres
DB_PASS=sua_senha
DB_NAME=net_escola
DB_DIALECT=postgres


📘 Depois, testem a conexão:

npx sequelize db:authenticate

🧪 7. Testar Conexão

Verifiquem no log do terminal se aparece:

Conexão com o banco de dados estabelecida com sucesso!


Caso contrário, revisem as configurações no .env e no config/config.js.

🧭 8. Escrever o README do Banco

Quando o banco estiver pronto, completem o README com:

O modelo ER final (imagem ou link do diagrama)

As tabelas criadas e suas colunas

O SGBD utilizado (ex: PostgreSQL)

Como conectar (com Sequelize, pgAdmin, etc.)

Quem participou da modelagem

🌐 9. Hospedar o Banco (Opcional)

Caso o grupo queira deixar o banco online para testes do Front-End:

ElephantSQL → fácil e gratuito

Railway.app ou Render.com → permitem deploy rápido

✅ 10. Entregar ao Back-End

Quando o modelo e as tabelas estiverem criadas, avisem o grupo do Back-End.
Eles usarão as tabelas para montar as rotas e modelos do Sequelize.
