# API de Charadas Backend

Uma API RESTful desenvolvida em Flask para gerenciamento de charadas, com autenticação JWT e integração com Firebase Firestore.

## 📋 Descrição

Esta API permite gerenciar uma coleção de charadas, incluindo operações CRUD (Criar, Ler, Atualizar, Deletar). Inclui autenticação para proteger rotas administrativas e documentação automática via Swagger.

## 🚀 Funcionalidades

- ✅ Listar todas as charadas
- ✅ Obter uma charada aleatória
- ✅ Buscar charada por ID
- ✅ Adicionar novas charadas (requer autenticação)
- ✅ Editar charadas existentes (requer autenticação)
- ✅ Excluir charadas (requer autenticação)
- ✅ Autenticação JWT para administradores
- ✅ Documentação interativa com Swagger UI
- ✅ Suporte a CORS para integração com frontends

## 🛠️ Tecnologias Utilizadas

- **Flask**: Framework web para Python
- **Firebase Firestore**: Banco de dados NoSQL
- **JWT (PyJWT)**: Autenticação baseada em tokens
- **Flasgger**: Geração automática de documentação Swagger
- **Flask-CORS**: Suporte a Cross-Origin Resource Sharing
- **Gunicorn**: Servidor WSGI para produção
- **Vercel**: Plataforma de deploy

## 📦 Instalação e Configuração

### Pré-requisitos

- Python 3.8 ou superior
- Conta no Firebase (para Firestore)
- Conta no Vercel (opcional, para deploy)

### Passos de Instalação

1. **Clone o repositório:**
   ```bash
   git clone <url-do-repositorio>
   cd api_charadas_backend
   ```

2. **Crie um ambiente virtual:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # No Windows: venv\Scripts\activate
   ```

3. **Instale as dependências:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure as variáveis de ambiente:**

   Crie um arquivo `.env` na raiz do projeto com as seguintes variáveis:
   ```
   SECRET_KEY=sua_chave_secreta_aqui
   ADM_USUARIO=admin
   ADM_SENHA=sua_senha_admin
   FIREBASE_CREDENTIALS={"type": "service_account", "project_id": "...", ...}
   ```

   Para obter as credenciais do Firebase:
   - Acesse o Console do Firebase
   - Vá para Configurações do Projeto > Contas de Serviço
   - Gere uma nova chave privada
   - Copie o conteúdo do arquivo JSON gerado

5. **Configure o Firebase:**

   - Certifique-se de que o arquivo `firebase.json` contém suas credenciais locais (opcional para desenvolvimento)
   - No Firestore, crie uma coleção chamada `charadas` e outra chamada `contador` com um documento `controle_id`

## 🚀 Como Usar

### Executando Localmente

```bash
python app.py
```

A API estará disponível em `http://127.0.0.1:5000`

### Documentação da API

Acesse `http://127.0.0.1:5000/apidocs` para visualizar a documentação interativa do Swagger.

## 📚 Endpoints da API

### Autenticação

- `POST /login` - Realizar login e obter token JWT

### Charadas

- `GET /` - Informações da API
- `GET /charadas` - Listar todas as charadas
- `GET /charadas/aleatoria` - Obter uma charada aleatória
- `GET /charadas/{id}` - Buscar charada por ID
- `POST /charadas` - Adicionar nova charada (requer token)
- `PUT /charadas/{id}` - Atualizar charada completamente (requer token)
- `PATCH /charadas/{id}` - Atualizar charada parcialmente (requer token)
- `DELETE /charadas/{id}` - Excluir charada (requer token)

### Exemplo de Uso

1. **Login:**
   ```bash
   curl -X POST http://127.0.0.1:5000/login \
     -H "Content-Type: application/json" \
     -d '{"usuario": "admin", "senha": "sua_senha"}'
   ```

2. **Adicionar charada:**
   ```bash
   curl -X POST http://127.0.0.1:5000/charadas \
     -H "Content-Type: application/json" \
     -H "Authorization: Bearer SEU_TOKEN_AQUI" \
     -d '{"pergunta": "O que é que tem olhos mas não vê?", "resposta": "Uma batata"}'
   ```

## 🚀 Deploy

### Vercel

1. Instale a CLI do Vercel:
   ```bash
   npm install -g vercel
   ```

2. Faça login no Vercel:
   ```bash
   vercel login
   ```

3. Configure as variáveis de ambiente no Vercel:
   ```bash
   vercel env add SECRET_KEY
   vercel env add ADM_USUARIO
   vercel env add ADM_SENHA
   vercel env add FIREBASE_CREDENTIALS
   ```

4. Faça o deploy:
   ```bash
   vercel --prod
   ```

## 📁 Estrutura do Projeto

```
api_charadas_backend/
├── app.py              # Arquivo principal da aplicação Flask
├── auth.py             # Módulo de autenticação JWT
├── openapi.yaml        # Especificação OpenAPI para documentação
├── requirements.txt    # Dependências Python
├── vercel.json         # Configuração de deploy no Vercel
├── firebase.json       # Credenciais Firebase (local)
├── notas.md            # Notas do desenvolvimento
└── README.md           # Este arquivo
```

## 🤝 Contribuição

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/nova-feature`)
3. Commit suas mudanças (`git commit -am 'Adiciona nova feature'`)
4. Push para a branch (`git push origin feature/nova-feature`)
5. Abra um Pull Request

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.

## 👨‍💻 Autor

Pedro V - Desenvolvedor Backend

---

**Nota:** Este projeto foi desenvolvido como parte de estudos em Programação Back-end.</content>
<parameter name="filePath">c:\Users\SENAI DS 2025\Desktop\3° Ano - 1° Semestre\Programação Back-end 2\Aula 11\api_charadas_backend\README.md