# 🚀 Como Publicar no GitHub

## Passo 1: Criar Repositório no GitHub

1. Acesse [github.com](https://github.com)
2. Clique em "New repository"
3. Nome: `vendas-dompsa-pwa`
4. Descrição: "Progressive Web App para gerenciamento de vendas"
5. Selecione "Public"
6. Clique em "Create repository"

## Passo 2: Clonar o Repositório

```bash
git clone https://github.com/seu-usuario/vendas-dompsa-pwa.git
cd vendas-dompsa-pwa
```

## Passo 3: Copiar Arquivos PWA

```bash
# Copie todos os arquivos da pasta pwa
cp -r ../pwa/* .

# Ou copie manualmente:
# - index.html
# - service-worker.js
# - manifest.json
# - README.md
# - .gitignore
```

## Passo 4: Fazer Commit e Push

```bash
# Adicionar todos os arquivos
git add .

# Fazer commit
git commit -m "Initial PWA release - Vendas Dompsa"

# Fazer push
git push origin main
```

## Passo 5: Ativar GitHub Pages

1. Acesse seu repositório no GitHub
2. Vá para "Settings" (Configurações)
3. Clique em "Pages" (no menu lateral esquerdo)
4. Em "Source", selecione "Deploy from a branch"
5. Selecione "main" como branch
6. Clique em "Save"
7. Aguarde alguns minutos
8. Sua PWA estará disponível em: `https://seu-usuario.github.io/vendas-dompsa-pwa`

## Passo 6: Testar a PWA

### No Desktop
1. Abra a URL em Chrome, Edge ou Firefox
2. Clique no ícone de instalação na barra de endereço
3. Clique em "Instalar"

### No Mobile (Android)
1. Abra a URL em Chrome
2. Toque no menu (⋮)
3. Selecione "Instalar app"

### No iOS
1. Abra a URL em Safari
2. Toque no ícone de compartilhamento
3. Selecione "Adicionar à Tela Inicial"

## 🔄 Atualizar a PWA

Sempre que fizer mudanças:

```bash
# Editar arquivos
# ...

# Fazer commit
git add .
git commit -m "Descrição das mudanças"

# Fazer push
git push origin main

# Aguarde alguns minutos para que o GitHub Pages atualize
```

## 📊 Verificar Status

### Verificar Service Worker
1. Abra a PWA no navegador
2. Pressione F12 (DevTools)
3. Vá para "Application" (ou "Aplicação")
4. Clique em "Service Workers"
5. Você deve ver o Service Worker registrado

### Verificar Manifest
1. DevTools → Application → Manifest
2. Você deve ver os dados do manifest.json

### Verificar Cache
1. DevTools → Application → Cache Storage
2. Você deve ver "vendas-dompsa-v1"

## 🛠️ Troubleshooting

### PWA não aparece para instalar
- Verifique se está usando HTTPS (GitHub Pages usa HTTPS automaticamente)
- Verifique se manifest.json está acessível
- Limpe o cache do navegador
- Recarregue a página

### Service Worker não registra
- Verifique se service-worker.js está no diretório raiz
- Verifique se não há erros no console (DevTools → Console)
- Tente limpar o cache e recarregar

### Dados não sincronizam
- Verifique se localStorage está habilitado
- Verifique se há espaço disponível no navegador
- Tente abrir em modo privado/incógnito

## 📱 Converter para APK

Veja o arquivo `README.md` para instruções de conversão para APK.

## 🔐 Segurança

- A PWA é servida via HTTPS (GitHub Pages)
- Dados são armazenados localmente (não enviados para servidores)
- Sem autenticação necessária
- Sem rastreamento ou analytics

## 📈 Próximos Passos

1. Adicione um backend para sincronização em nuvem
2. Implemente autenticação com OAuth
3. Adicione relatórios e gráficos
4. Integre com WhatsApp API
5. Crie um aplicativo nativo para iOS/Android

## 📞 Suporte

Para suporte, abra uma issue no repositório GitHub.

---

**Pronto! Sua PWA está no ar! 🎉**
