# HotMoney

💰 Empréstimos Pessoais — PWA
App de controle de empréstimos pessoais com salvamento no Google Drive.
Funciona como app no Android via PWA (sem precisar de Play Store).
---
🚀 Como instalar no GitHub Pages
1. Criar repositório no GitHub
Acesse https://github.com e faça login
Clique em "New repository"
Nome: `emprestimos` (ou qualquer nome)
Marque Public
Clique em "Create repository"
2. Fazer upload dos arquivos
Na página do repositório, clique em "uploading an existing file"
Arraste os 3 arquivos: `index.html`, `manifest.json`, `sw.js`
Clique em "Commit changes"
3. Ativar GitHub Pages
Vá em Settings → Pages
Em "Source", selecione main branch
Clique em Save
Aguarde ~1 minuto e acesse a URL gerada:
`https://SEU_USUARIO.github.io/emprestimos/`
---
🔑 Configurar Google Drive (opcional mas recomendado)
1. Criar projeto no Google Cloud
Acesse https://console.cloud.google.com
Clique em "Novo Projeto" → dê um nome → Criar
2. Ativar Google Drive API
No menu lateral: APIs e Serviços → Biblioteca
Busque "Google Drive API" → clique → Ativar
3. Criar credenciais OAuth
APIs e Serviços → Credenciais → Criar credenciais → ID do cliente OAuth 2.0
Tipo: Aplicativo da Web
Nome: `Emprestimos PWA`
Em "Origens JavaScript autorizadas", adicione:
`https://SEU_USUARIO.github.io`
Clique em Criar
Copie o Client ID gerado (formato: `xxx.apps.googleusercontent.com`)
4. Configurar a tela de consentimento OAuth
APIs e Serviços → Tela de consentimento OAuth
Tipo de usuário: Externo → Criar
Preencha nome do app e e-mail
Em Escopos, adicione: `../auth/drive.appdata`
Em Usuários de teste, adicione seu e-mail do Google
Salve
5. Inserir o Client ID no app
Abra o arquivo `index.html`
Localize a linha:
```javascript
   const CLIENT_ID = 'SEU_GOOGLE_CLIENT_ID_AQUI';
   ```
Substitua pelo seu Client ID:
```javascript
   const CLIENT_ID = '123456789-abc.apps.googleusercontent.com';
   ```
Salve e faça upload novamente para o GitHub
---
📱 Instalar no Android como app
Abra o Chrome no celular
Acesse `https://SEU_USUARIO.github.io/emprestimos/`
Toque nos 3 pontinhos (menu) → "Adicionar à tela inicial"
Toque em "Adicionar"
O app aparecerá na sua tela inicial como qualquer outro app! ✅
---
✨ Funcionalidades
✅ Registrar empréstimos que você fez ou recebeu
✅ Cálculo automático de juros compostos mensais
✅ Registrar pagamentos parciais
✅ Histórico completo por empréstimo
✅ Barra de progresso de quitação
✅ Funciona offline (dados locais)
✅ Sincroniza com Google Drive (dados na nuvem)
✅ Instala como app no Android
---
📂 Estrutura dos arquivos
```
emprestimos/
├── index.html    → App principal
├── manifest.json → Configuração PWA
├── sw.js         → Service Worker (offline)
└── README.md     → Este arquivo
```
Os dados são salvos no App Data do Google Drive — uma pasta privada
que só este app consegue acessar, não visível na interface normal do Drive.
