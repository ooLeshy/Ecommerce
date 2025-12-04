# 🎮 GameStore - E-commerce de Jogos

![GameStore Banner](https://images.unsplash.com/photo-1550745165-9bc0b252726f?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80)

Um sistema completo de e-commerce para venda de jogos, desenvolvido com **HTML, CSS, JavaScript, PHP e MySQL**. O projeto inclui catálogo de produtos, carrinho de compras, checkout, sistema de pagamento simulado, área do cliente e painel administrativo.

## ✨ Funcionalidades

### 🛒 Catálogo e Vitrine
- Página inicial com busca e produtos em destaque
- Listagem por categorias (Ação, RPG, Esportes, Estratégia)
- Ordenação por preço e nome
- Página de produto com imagem, preço, estoque e botão "Adicionar ao carrinho"

### 🛍️ Carrinho e Checkout
- Atualização de quantidades no carrinho
- Remoção de itens
- Cálculo automático de subtotal e frete
- Processo de checkout em 4 etapas:
  1. Login/Registro
  2. Endereço de entrega
  3. Pagamento
  4. Confirmação do pedido
- Geração de número do pedido com status inicial "Pendente"

### 💳 Pagamento Simulado
- Métodos de pagamento: cartão de crédito, PIX e boleto
- Códigos simulados para PIX e boleto
- Opção para marcar pagamento como realizado
- Atualização de status do pedido após pagamento

### 👤 Conta do Cliente
- Sistema de cadastro e login seguro
- Histórico de pedidos com status
- Endereços de entrega

### 🛠️ Painel Administrativo
- Acesso restrito a administradores
- CRUD completo de produtos e categorias
- Atualização do status dos pedidos
- Controle de estoque

## 🚀 Pré-requisitos

Antes de começar, você precisará ter instalado:

- [XAMPP](https://www.apachefriends.org/) (Apache + MySQL + PHP)
- Navegador web moderno (Chrome, Firefox, Edge)
- Editor de código (VS Code, Sublime, etc.)

## 📦 Instalação e Configuração

### Passo 1: Clonar o Repositório

```bash
# Clone este repositório
git clone https://github.com/seu-usuario/gamestore.git

# Acesse a pasta do projeto
cd gamestore
```

### Passo 2: Configurar o XAMPP

1. **Instale o XAMPP** seguindo as instruções do site oficial
2. **Inicie o XAMPP Control Panel**
3. **Inicie os serviços**:
   - Apache (clique em "Start")
   - MySQL (clique em "Start")

### Passo 3: Configurar o Projeto no XAMPP

1. **Copie a pasta do projeto** para o diretório do XAMPP:
   - Windows: `C:\xampp\htdocs\`
   - Linux: `/opt/lampp/htdocs/`
   - macOS: `/Applications/XAMPP/htdocs/`

2. **Renomeie a pasta** para `gamestore` (se necessário)

### Passo 4: Configurar o Banco de Dados

1. **Acesse o phpMyAdmin**:
   - Abra seu navegador
   - Acesse: `http://localhost/phpmyadmin`

2. **Crie um novo banco de dados**:
   ```sql
   CREATE DATABASE gamestore_db;
   ```

3. **Importe a estrutura do banco**:
   - Clique no banco `gamestore_db` criado
   - Vá para a aba "Importar"
   - Selecione o arquivo `gamestore_database.sql` da pasta do projeto
   - Clique em "Executar"

4. **Ou execute manualmente** o SQL do arquivo `database/schema.sql`

### Passo 5: Configurar as Credenciais do Banco

1. **Edite o arquivo** `config/database.php`:

```php
private $host = "localhost";
private $db_name = "gamestore_db";
private $username = "root";      // Usuário padrão do XAMPP
private $password = "";          // Senha padrão do XAMPP (vazia)
```

### Passo 6: Testar a Instalação

1. **Inicie o servidor Apache** e **MySQL** no XAMPP
2. **Acesse o projeto** no navegador:
   ```
   http://localhost/gamestore/
   ```

## 🗂️ Estrutura do Projeto

```
gamestore/
│
├── index.html                 # Página principal
├── assets/                    # Recursos estáticos
│   ├── css/
│   │   └── style.css         # Estilos principais
│   ├── js/
│   │   └── app.js            # JavaScript principal
│   └── images/               # Imagens do projeto
│
├── api/                       # Endpoints da API
│   ├── auth.php              # Autenticação (login/registro)
│   ├── products.php          # Gerenciamento de produtos
│   ├── cart.php              # Operações do carrinho
│   ├── orders.php            # Gerenciamento de pedidos
│   ├── categories.php        # Gerenciamento de categorias
│   └── admin.php             # Operações administrativas
│
├── config/                    # Configurações
│   └── database.php          # Configuração do banco de dados
│
├── includes/                  # Includes PHP
│   └── session.php           # Gerenciamento de sessões
│
├── database/                  # Scripts do banco
│   ├── schema.sql            # Estrutura do banco
│   └── seeds.sql             # Dados iniciais
│
└── README.md                  # Este arquivo
```

## 🔧 Configuração do Banco de Dados

### Usuários Padrão

Após importar o banco, você terá os seguintes usuários:

#### Administrador
- **Email**: admin@gamestore.com
- **Senha**: admin123

#### Cliente de Teste
- **Email**: joao@email.com
- **Senha**: cliente123

### Tabelas Principais

| Tabela | Descrição |
|--------|-----------|
| `users` | Usuários do sistema |
| `products` | Produtos/jogos |
| `categories` | Categorias dos produtos |
| `cart_items` | Itens do carrinho |
| `orders` | Pedidos realizados |
| `order_items` | Itens dos pedidos |
| `addresses` | Endereços dos clientes |

## 🌐 Endpoints da API

| Endpoint | Método | Descrição |
|----------|---------|-----------|
| `/api/auth.php` | POST | Login/Registro de usuários |
| `/api/products.php` | GET | Listar produtos |
| `/api/cart.php` | GET/POST/PUT/DELETE | Gerenciar carrinho |
| `/api/orders.php` | POST | Criar pedido |
| `/api/categories.php` | GET | Listar categorias |
| `/api/admin.php` | GET/POST/PUT/DELETE | Operações administrativas |

## 🧪 Testando o Sistema

### 1. Teste Básico
1. Acesse `http://localhost/gamestore/`
2. Navegue pelos produtos
3. Adicione itens ao carrinho
4. Clique no ícone do carrinho para visualizar

### 2. Teste de Checkout
1. Adicione produtos ao carrinho
2. Clique em "Finalizar Compra"
3. Siga as 4 etapas do checkout
4. Ao final, um número de pedido será gerado

### 3. Teste de Login
1. Clique no ícone de usuário no header
2. Use as credenciais:
   - Email: `joao@email.com`
   - Senha: `cliente123`
3. Verifique o histórico de pedidos

### 4. Painel Administrativo
1. Faça login como administrador:
   - Email: `admin@gamestore.com`
   - Senha: `admin123`
2. Clique no ícone de engrenagem no header
3. Teste o CRUD de produtos e categorias
4. Atualize o status dos pedidos

## 🔒 Segurança

### Recomendações para Produção

1. **Altere as senhas padrão** do banco de dados
2. **Configure .htaccess** para proteger diretórios sensíveis
3. **Use HTTPS** em produção
4. **Implemente CSRF tokens** em formulários críticos
5. **Valide todos os inputs** no backend
6. **Use prepared statements** para todas as queries

### Exemplo de .htaccess para proteção

```apache
# Na pasta /api/
Deny from all
Allow from 127.0.0.1

# Na pasta /config/
Order Deny,Allow
Deny from all
```

## 🐛 Solução de Problemas

### Problema: Página não carrega
**Solução**:
- Verifique se o Apache está rodando no XAMPP
- Confira se os arquivos estão em `htdocs/gamestore/`
- Acesse `http://localhost/gamestore/`

### Problema: Erro de conexão com o banco
**Solução**:
- Verifique se o MySQL está rodando
- Confira as credenciais em `config/database.php`
- Teste a conexão no phpMyAdmin

### Problema: API retorna erro 500
**Solução**:
- Verifique os logs de erro do Apache
- Confira permissões de arquivos
- Verifique sintaxe PHP nos arquivos da API

### Problema: Sessão não persiste
**Solução**:
- Verifique se o diretório de sessão tem permissão de escrita
- Confira configurações de `session.save_path` no php.ini

## 📝 Logs e Debug

### Habilitar Logs do PHP
1. Edite `php.ini` no XAMPP
2. Configure:
```ini
error_reporting = E_ALL
display_errors = On
log_errors = On
error_log = "C:\xampp\php\logs\php_error.log"
```

### Verificar Logs do Apache
- Windows: `C:\xampp\apache\logs\error.log`
- Linux: `/opt/lampp/logs/error_log`

## 🔄 Atualizando o Sistema

### Backup do Banco de Dados
```bash
# Via linha de comando
mysqldump -u root -p gamestore_db > backup_$(date +%Y%m%d).sql

# Via phpMyAdmin
# 1. Selecione o banco gamestore_db
# 2. Clique em "Exportar"
# 3. Selecione formato SQL
# 4. Clique em "Executar"
```

### Restaurar Backup
```bash
# Via linha de comando
mysql -u root -p gamestore_db < backup.sql

# Via phpMyAdmin
# 1. Selecione o banco gamestore_db
# 2. Clique em "Importar"
# 3. Selecione o arquivo backup.sql
# 4. Clique em "Executar"
```

## 🚀 Deploy para Produção

### Requisitos de Servidor
- PHP 7.4 ou superior
- MySQL 5.7 ou superior
- Apache 2.4 ou Nginx
- SSL Certificate (HTTPS)

### Passos para Deploy
1. **Configure o banco de dados** no servidor
2. **Atualize as credenciais** em `config/database.php`
3. **Configure as permissões** de arquivos:
   ```bash
   chmod 755 -R gamestore/
   chmod 644 config/database.php
   ```
4. **Configure o virtual host** no Apache/Nginx
5. **Instale um certificado SSL** (Let's Encrypt)
6. **Desative display_errors** no php.ini

## 🤝 Contribuindo

1. Faça um Fork do projeto
2. Crie uma Branch para sua Feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a Branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## 👥 Autores

- **Saulo Gomes** - *Desenvolvimento inicial* - https://github.com/ooLeshy
