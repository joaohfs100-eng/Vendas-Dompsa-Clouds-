# Vendas Dompsa - PWA Edition

Uma aplicação Progressive Web App (PWA) 100% funcional para gerenciamento de vendas com suporte offline-first.

## 🚀 Características

- ✅ **100% Offline-First**: Funciona completamente sem conexão com a internet
- ✅ **Sincronização Automática**: Dados sincronizam quando a conexão retorna
- ✅ **CRUD Completo**: Gerenciar clientes, produtos e vendas
- ✅ **Persistência Local**: Dados salvos em localStorage
- ✅ **Tema Escuro**: Interface moderna e confortável
- ✅ **Responsivo**: Funciona em qualquer dispositivo
- ✅ **Instalável**: Pode ser instalado como app nativo

## 📁 Arquivos

```
pwa/
├── index.html          # Aplicação completa em um único arquivo
├── service-worker.js   # Service Worker para cache offline
├── manifest.json       # Configuração PWA
└── README.md          # Este arquivo
```

## 🔧 Como Usar

### 1. Localmente (Desenvolvimento)

```bash
# Servir com Python 3
python3 -m http.server 8000

# Ou com Node.js
npx http-server

# Ou com Live Server (VS Code)
# Instale a extensão Live Server e clique em "Go Live"
```

Acesse: `http://localhost:8000`

### 2. Deploy no GitHub Pages

```bash
# 1. Crie um repositório no GitHub
# 2. Clone o repositório
git clone https://github.com/seu-usuario/vendas-dompsa-pwa.git
cd vendas-dompsa-pwa

# 3. Copie os arquivos PWA
cp -r pwa/* .

# 4. Faça commit e push
git add .
git commit -m "Initial PWA release"
git push origin main

# 5. Ative GitHub Pages nas configurações do repositório
# Settings → Pages → Source: main branch
```

Acesse: `https://seu-usuario.github.io/vendas-dompsa-pwa`

### 3. Instalar como App

#### No Desktop (Chrome, Edge, Firefox)
1. Abra a aplicação no navegador
2. Clique no ícone de instalação na barra de endereço
3. Clique em "Instalar"
4. O app será adicionado ao seu menu de aplicações

#### No Mobile (Android)
1. Abra a aplicação no Chrome
2. Toque no menu (⋮)
3. Selecione "Instalar app"
4. O app será adicionado à sua tela inicial

#### No iOS
1. Abra a aplicação no Safari
2. Toque no ícone de compartilhamento
3. Selecione "Adicionar à Tela Inicial"
4. O app será adicionado à sua tela inicial

## 🔄 Sincronização de Dados

### Como Funciona

1. **Online**: Todos os dados são salvos localmente em tempo real
2. **Offline**: A aplicação continua funcionando normalmente
3. **Reconexão**: Quando voltar online, os dados são sincronizados automaticamente

### Dados Armazenados

- **localStorage**: Clientes, Produtos, Vendas, Contas
- **Sem limite**: Funciona com qualquer quantidade de dados

## 📱 Conversão para APK

### Método 1: Usando Apache Cordova

```bash
# 1. Instale Cordova
npm install -g cordova

# 2. Crie um novo projeto
cordova create vendas-dompsa-app

# 3. Adicione plataforma Android
cd vendas-dompsa-app
cordova platform add android

# 4. Copie os arquivos PWA
cp ../pwa/* www/

# 5. Construa o APK
cordova build android

# 6. O APK estará em: platforms/android/app/build/outputs/apk/
```

### Método 2: Usando Capacitor

```bash
# 1. Instale Capacitor
npm install -g @capacitor/cli

# 2. Crie um novo projeto
npx @capacitor/cli create

# 3. Copie os arquivos PWA
cp ../pwa/* www/

# 4. Adicione plataforma Android
npx cap add android

# 5. Abra no Android Studio
npx cap open android

# 6. Construa e execute o APK
# (Use o Android Studio para compilar)
```

### Método 3: Usando PWA Builder

1. Acesse [PWA Builder](https://www.pwabuilder.com)
2. Insira a URL da sua PWA
3. Clique em "Build"
4. Selecione "Android"
5. Baixe o APK gerado

### Método 4: Usando Electron (Desktop)

```bash
# 1. Instale Electron
npm install -g electron

# 2. Crie um arquivo main.js
cat > main.js << 'EOF'
const { app, BrowserWindow } = require('electron');

app.on('ready', () => {
  const win = new BrowserWindow();
  win.loadFile('index.html');
});
EOF

# 3. Execute
electron .
```

## 🛠️ Desenvolvimento

### Adicionar Nova Funcionalidade

1. Edite `index.html`
2. Adicione a lógica no objeto `state`
3. Crie funções para manipular dados
4. Atualize `render()` para mostrar a UI

### Exemplo: Adicionar Novo Campo

```javascript
// 1. Adicione ao estado
state.newField = [];

// 2. Crie função para manipular
function addNewField(value) {
  state.newField.push(value);
  storage.set('newField', state.newField);
  render();
}

// 3. Atualize render() para mostrar
```

## 📊 Estrutura de Dados

### Cliente
```javascript
{
  id: 1,
  accountId: 1,
  name: "Cliente X",
  cia: "Dompsa",
  whatsapp: "5511999999999",
  createdAt: Date
}
```

### Produto
```javascript
{
  id: 1,
  accountId: 1,
  name: "Produto X",
  price: "100.00",
  stockDaily: 10,
  createdAt: Date
}
```

### Venda
```javascript
{
  id: 1,
  accountId: 1,
  clientId: 1,
  productId: 1,
  quantity: 5,
  price: "500.00",
  status: "pendente" | "pago",
  notes: "Observações",
  saleDate: Date,
  createdAt: Date
}
```

## 🔒 Segurança

- ✅ Dados salvos localmente (não enviados para servidores)
- ✅ Sem autenticação necessária (local-first)
- ✅ HTTPS recomendado para produção
- ✅ Sem rastreamento ou analytics

## 🐛 Troubleshooting

### App não funciona offline
- Verifique se o Service Worker foi registrado (DevTools → Application → Service Workers)
- Limpe o cache do navegador
- Recarregue a página

### Dados não sincronizam
- Verifique se localStorage está habilitado
- Abra o DevTools → Application → Local Storage
- Verifique se há espaço disponível

### Instalação não funciona
- Verifique se está usando HTTPS (necessário para PWA)
- Verifique se manifest.json está acessível
- Verifique se o Service Worker está registrado

## 📝 Licença

Proprietary - Vendas Dompsa

## 🤝 Suporte

Para suporte, abra uma issue no repositório GitHub.

## 🚀 Roadmap

- [ ] Sincronização em nuvem (backend)
- [ ] Autenticação com OAuth
- [ ] Relatórios e gráficos
- [ ] Integração WhatsApp
- [ ] Backup automático
- [ ] Compartilhamento de dados
- [ ] Modo escuro/claro
- [ ] Múltiplos idiomas

---

**Desenvolvido com ❤️ usando HTML, CSS e JavaScript puro**
