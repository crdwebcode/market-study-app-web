# SEMI - Sistema de Estudo de Mercado Imobiliário

Este repositório contém o código fonte do **SEMI** (Sistema de Estudo de Mercado Imobiliário), uma aplicação web desenvolvida para facilitar o estudo e a análise de mercado imobiliário.

## Funcionalidades

- **Login e Registro de Usuário**
  - Sistema seguro com hash de senha.
  - Feedback visual imediato para ações do usuário.

- **Avaliação de Imóveis**
  - Preenchimento manual e automático (via integração com APIs).
  - Cálculo da média de valor por m², valor estimado e competitivo.
  - Geração de conclusão e relatório em PDF.

- **Interface Responsiva e Tema Dark Mode**
  - Design responsivo utilizando Bootstrap.
  - Modo escuro para melhor experiência do usuário.

- **Integração com APIs**
  - Conexão com APIs de imóveis para busca e preenchimento automático de dados.

## Tecnologias Utilizadas

- **Frontend**
  - HTML5, CSS3, JavaScript (com Bootstrap).

- **Backend**
  - PHP 7.4+ com PDO para interação com banco de dados.

- **Banco de Dados**
  - MySQL 8.0.

- **Bibliotecas**
  - [FPDF](http://www.fpdf.org/) para geração de relatórios em PDF.

---

## Estrutura do Projeto

```
market-study-app-web/
├── assets/
│   ├── css/
│   │   └── styles.css
│   ├── img/
│   │   └── logo-semi.png
│   └── js/
│       └── app.js
├── auth.php
├── calcular.php
├── conclusao.php
├── conexao.php
├── dashboard.php
├── gerar_pdf.php
├── index.php
├── login.php
├── logout.php
├── register.php
├── register_process.php
└── README.md
```

---

## Requisitos de Instalação

1. **Requisitos do Servidor:**
   - Servidor Apache.
   - PHP 7.4 ou superior.
   - MySQL 8.0 ou superior.

2. **Dependências:**
   - Extensão PDO habilitada no PHP.
   - Biblioteca FPDF incluída no diretório `fpdf`.

---

## Passos para Instalação

1. **Clone o Repositório:**
   ```bash
   git clone https://github.com/seu-usuario/market-study-app-web.git
   cd market-study-app-web
   ```

2. **Configuração do Banco de Dados:**
   - Crie um banco de dados MySQL chamado `market_study`.
   - Execute o script SQL disponível abaixo para criar as tabelas:

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

3. **Configuração do Arquivo de Conexão:**
   - Atualize as credenciais no arquivo `conexao.php`:

```php
<?php
$host = 'localhost';
$dbname = 'market_study';
$username = 'root';
$password = '';

try {
    $pdo = new PDO("mysql:host=$host;dbname=$dbname", $username, $password);
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
} catch (PDOException $e) {
    die("Erro na conexão com o banco de dados: " . $e->getMessage());
}
```

4. **Configuração Inicial:**
   - Acesse `http://localhost/market-study-app-web` no navegador.
   - Crie um novo usuário ou use o seguinte usuário inicial:
     - **E-mail:** admin@gmail.com
     - **Senha:** admin123 (senha em MD5 no banco de dados).

---

## Instruções de Uso

1. **Login e Registro:**
   - Acesse `login.php` para entrar no sistema.
   - Registre-se em `register.php` caso não tenha uma conta.

2. **Avaliação de Imóveis:**
   - Preencha os campos do formulário ou integre com uma API de imóveis.
   - Clique em **Calcular** para visualizar os resultados.
   - Gere a **Conclusão** e o **Relatório PDF** conforme necessário.

3. **Logout:**
   - Clique no botão de logout no dashboard para encerrar a sessão.

---

## Contribuição

Contribuições são bem-vindas! Por favor, siga os passos abaixo:

1. Fork este repositório.
2. Crie uma branch para sua feature (`git checkout -b minha-feature`).
3. Commit suas mudanças (`git commit -m 'Adiciona nova feature'`).
4. Envie para a branch (`git push origin minha-feature`).
5. Abra um Pull Request.

---

## Licença

Este projeto está licenciado sob a Licença MIT. Consulte o arquivo LICENSE para mais detalhes.

---

## Contato

Para dúvidas ou sugestões, entre em contato:
- **Email:** suporte@semi.com.br
- **GitHub:** [Seu Usuário GitHub](https://github.com/seu-usuario)
