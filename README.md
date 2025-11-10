# Gym Management System

## 📋 Descrição
Sistema de gerenciamento de academia completo com suporte para administradores, recepcionistas, instrutores e membros. Desenvolvido com Flask e MySQL.

**Editor/Responsável:** CSAleixo12

---

## 🚀 Requisitos do Sistema

- Python 3.8 ou superior
- MySQL Server 5.7 ou superior
- pip (gerenciador de pacotes Python)

---

## 📦 Dependências do Projeto

### Versões Atuais (2025)

```
Flask==3.0.0                    # Framework web Python
Flask-MySQLdb==2.0.0            # Integração com MySQL
WTForms==3.1.1                  # Validação de formulários
passlib==1.7.4                  # Hash de senhas
Werkzeug==3.0.1                 # WSGI utilities
```

---

## 🔧 Instalação e Configuração

### 1. Clonar o Repositório
```bash
git clone https://github.com/CSAleixo12/GymManagementSystem.git
cd GymManagementSystem
```

### 2. Criar Ambiente Virtual (Recomendado)
```bash
python3 -m venv venv
source venv/bin/activate  # No Windows: venv\Scripts\activate
```

### 3. Instalar Dependências
```bash
pip install -r requirements.txt
```

### 4. Configurar Banco de Dados

#### 4.1 Criar o Banco de Dados
```bash
mysql -u root -p < gym.sql
```

#### 4.2 Atualizar Credenciais no `app.py`
Edite o arquivo `app.py` e ajuste as credenciais MySQL:
```python
app.config['MYSQL_HOST'] = 'localhost'
app.config['MYSQL_USER'] = 'seu_usuario'
app.config['MYSQL_PASSWORD'] = 'sua_senha'
app.config['MYSQL_DB'] = 'Gym'
```

---

## ▶️ Executar o Projeto

```bash
python3 app.py
```

O servidor estará disponível em: **http://localhost:5000**

### Acessar a Aplicação
- URL: `http://localhost:5000`
- Página de Login: `http://localhost:5000/login`

---

## 👥 Tipos de Usuário

1. **Admin (prof=1)** - Acesso total ao sistema
2. **Recepcionista (prof=2)** - Gerenciamento de membros e equipamentos
3. **Instrutor (prof=3)** - Acompanhamento de membros e planos
4. **Membro (prof=4)** - Visualização de progresso e planos

---

## 📁 Estrutura do Projeto

```
GymManagementSystem/
├── app.py                    # Arquivo principal da aplicação
├── gym.sql                   # Script do banco de dados
├── requirements.txt          # Dependências Python
├── README.md                 # Este arquivo
├── static/                   # Arquivos estáticos
│   └── assets/
│       └── bootstrap/        # Bootstrap CSS/JS
└── templates/                # Templates HTML
    ├── layout.html
    ├── login.html
    ├── home.html
    ├── adminDash.html
    ├── recepDash.html
    ├── trainorDash.html
    ├── memberDash.html
    └── includes/             # Componentes reutilizáveis
```

---

## 🔐 Segurança

- Senhas criptografadas com SHA256
- Sessões de usuário gerenciadas com segurança
- Validação de formulários com WTForms
- Proteção contra acesso não autorizado via decoradores

---

## 🛠️ Melhorias Realizadas (v2025)

- ✅ Atualizado para Flask 3.0.0 (compatível com Python 3.12+)
- ✅ WTForms 3.1.1 - Import de DateField corrigido
- ✅ Removido flask_script (deprecated) - app.run() nativa
- ✅ Todas as dependências com versões atualizadas
- ✅ Documentação completa de instalação

---

## 📝 Notas de Desenvolvimento

### Debug Mode
O servidor inicia em modo debug (desenvolvimento). Para produção, ajuste em `app.py`:
```python
app.debug = False
```

### Porta Padrão
A aplicação roda na porta 5000. Para alterar, modifique em `app.py`:
```python
app.run(host='0.0.0.0', port=8000)  # Alterar 8000 para a porta desejada
```

---

## 🐛 Resolução de Problemas

### Erro: "ModuleNotFoundError: No module named 'flask'"
**Solução:** Execute `pip install -r requirements.txt`

### Erro: "Can't connect to MySQL server"
**Solução:** 
1. Verifique se MySQL está rodando
2. Corrija as credenciais em `app.py`
3. Verifique se o banco "Gym" foi criado

### Erro: "No module named 'wtforms.fields.html5'"
**Solução:** Este erro foi corrigido. Use a versão atualizada do código e reinstale com `pip install -r requirements.txt`

---

## 📚 Referências

- [Flask Documentation](https://flask.palletsprojects.com/)
- [Flask-MySQLdb](https://flask-mysqldb.readthedocs.io/)
- [WTForms 3.1](https://wtforms.readthedocs.io/)
- [Passlib](https://passlib.readthedocs.io/)

---

## 📄 Licença
Consulte o repositório para informações sobre licença.

---

**Última atualização:** November 10, 2025
The GYM MANAGEMENT SYSTEM is to automate everything that happens in the gym. It is to aid and simplify the job all those who work for the gym, who train in the gym and who owns the gym. The database consists of daily goals and stats of achievements/progress of a member who trains in the gym, contact details and personal info of everyone, training programs that the gym offers, equipment etc.

## Who is it for
- Gym members
- Admin
- Receptionist
- Trainers

## Functionality
* **Admin** - Admin/Owner of the gym can add a receptionist, delete a receptionist, add a trainer, and delete a trainer, view details of everyone (Receptionist, Trainers, and gym members), add a new member to the gym, delete a member when one is leaving, add equipment, remove equipment.
* **Gym members** - Gym members can login into the system to view their daily goals like their workouts, goals, diet plan, etc. They enter their daily training details. They can edit their personal information like contact details, personal info etc. They can also view their trainers contact info. They can track their progress.
* **Trainers** - Trainer can design and add a workout plan, view all the details, progress of all those who train under him/her, evaluate their workouts every day; edit their own contact details and personal info; can view all the equipment details available in the gym.
 * **Receptionist** - Receptionist can view contact details of everyone, add a member, delete a member.
