API JWT com Spring Boot
API de autenticação e autorização usando JWT (JSON Web Token) implementada com Spring Boot. Permite cadastro de usuários, login e controle de acesso com base em roles (ADMIN, USER). 
github.com
github.com
+1
github.com
+1

🛠 Tecnologias
Java (17+)

Spring Boot

Spring Security

JWT (JSON Web Token)

Maven

PostgreSQL

📦 Pré‑requisitos
Java 17 (ou superior)

Maven instalado

Banco de dados PostgreSQL configurado

⚙️ Configuração do Banco de Dados
Crie um banco chamado jwt_auth_db no PostgreSQL.

Edite src/main/resources/application.properties e configure:

spring.datasource.url

spring.datasource.username

spring.datasource.password

🚀 Instalando
bash
Copiar
Editar
git clone https://github.com/LorenaNobre/API-JWT-Java.git
cd API-JWT-Java
mvn clean install
▶️ Executando
bash
Copiar
Editar
mvn spring-boot:run
A API estará disponível em: http://localhost:8080

🔌 Endpoints da API
🔐 Autenticação
POST /api/auth/register – registra um novo usuário
Body (JSON):

json
Copiar
Editar
{
  "name": "Nome do Usuário",
  "email": "usuario@email.com",
  "password": "senha123"
}
POST /api/auth/login – autentica usuário
Body (JSON):

json
Copiar
Editar
{
  "email": "usuario@email.com",
  "password": "senha123"
}
👥 Usuários (necessita token JWT em Authorization: Bearer <token>)
GET /api/users/me – dados do usuário autenticado

PUT /api/users/me – atualiza dados do próprio usuário

GET /api/users – lista todos (somente ADMIN)

GET /api/users/{id} – usuário específico (somente ADMIN)

PUT /api/users/{id} – editar outro usuário (somente ADMIN)

DELETE /api/users/{id} – remover usuário (somente ADMIN)

🛡️ Segurança
Todos os endpoints (exceto /api/auth/**) exigem JWT válido.

O token deve ser enviado no header Authorization: Bearer <token>.

Roles:

USER: acesso limitado aos próprios dados

ADMIN: pode acessar e gerenciar usuários de forma ampla
