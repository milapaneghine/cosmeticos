# ✨ Beauty Tracker

App pessoal para controle de produtos de skincare, cabelos e maquiagem com:

- 📦 **Controle de produtos abertos** com previsão automática de término
- 🏠 **Estoque em casa** que ajusta a prioridade de compra
- 📋 **Histórico** de cada produto finalizado (data, marca, preço)
- 📊 **Estatísticas** de duração média, gasto total, custo por dia
- 🎯 **Cálculo por gramatura/ml** — duração se adapta ao tamanho
- ☁️ **Sincronização via GitHub Gist** — dados acessíveis em qualquer dispositivo

## 🚀 Publicar no GitHub Pages

1. Acesse [github.com](https://github.com) e faça login
2. **+** no canto superior direito → **New repository**
3. Nome: `beauty-tracker` (ou outro)
4. Marque **Public** e **Add a README file**
5. **Create repository**
6. Na página do repo: **Add file → Upload files**
7. Arraste o `index.html`
8. **Commit changes**
9. **Settings → Pages → Source: Deploy from a branch → Branch: main → Save**
10. Aguarde 1-2 min. URL: `https://SEU-USUARIO.github.io/beauty-tracker/`

## ☁️ Sincronização entre dispositivos

Os dados ficam salvos num **gist secreto** no seu GitHub e sincronizam automaticamente.

### Primeiro dispositivo (criar o gist)

1. No app, clique em **configurar sync** (canto superior direito)
2. Crie um token: vá em [github.com/settings/tokens/new](https://github.com/settings/tokens/new?description=Beauty+Tracker&scopes=gist)
   - **Note:** Beauty Tracker
   - **Expiration:** No expiration (ou um período longo)
   - **Scopes:** marque **`gist`** apenas
   - Clique em **Generate token** e **copie o token** (só aparece uma vez!)
3. No app, cole o token e deixe o campo "ID do gist" em branco
4. Clique em **conectar** — o app cria o gist automaticamente
5. **Anote o ID do gist** que aparece (você vai precisar nos outros dispositivos)

### Outros dispositivos

1. Abra a mesma URL do app no celular/outro navegador
2. Clique em **configurar sync**
3. Cole o **mesmo token** e o **ID do gist** que você anotou
4. Clique em **conectar** — os dados serão baixados automaticamente

### Como funciona

- Toda alteração local é enviada ao gist em 2 segundos (debounce)
- Ao abrir o app, ele baixa a versão mais recente do gist
- O indicador verde mostra a última sincronização
- Os dados são privados — só você (com o token) tem acesso
- Você pode ver o gist em `https://gist.github.com/SEU-ID`

### Segurança

- O gist é **secreto** (não aparece no seu perfil público)
- O token fica **só no seu navegador**, nunca é enviado para terceiros
- Você pode revogar o token a qualquer momento em [github.com/settings/tokens](https://github.com/settings/tokens)
- O token tem permissão **só para gists**, não para o resto da sua conta

## 📱 Acesso pelo celular

Depois de publicado, abra a URL no navegador do celular:

**iOS (Safari):** botão de compartilhar (□↑) → "Adicionar à Tela de Início"

**Android (Chrome):** menu (⋮) → "Adicionar à tela inicial"

## 💾 Backup local (alternativa ao sync)

Se preferir não usar GitHub, ainda dá pra exportar/importar manualmente:

- **Exportar:** copia um JSON com todos os dados
- **Importar:** cola o JSON em outro dispositivo

## 🧪 Como funciona o cálculo

As **taxas de consumo** (dias por grama/ml) foram calculadas a partir de histórico real de 18 meses de uso. Por exemplo:

- **Desodorante 45g**: 0.42 d/g → ~19 dias
- **Sabonete facial**: 0.35 d/g → 105g = ~37 dias, 525g = ~184 dias
- **Protetor solar 50ml**: 1.58 d/ml → ~79 dias

Quando você abre um produto e informa o tamanho, o app calcula a previsão de término. Cada vez que você finaliza, a duração real fica registrada no histórico — gerando estatísticas pessoais que vão refinando a previsão ao longo do tempo.

## 🔒 Privacidade

- Dados ficam **só no seu navegador** (localStorage) e, se você ativar, no **seu gist privado** no GitHub
- Nenhuma informação é enviada para servidores de terceiros
- Limpou os dados do navegador? Reabra o app e configure o sync com o mesmo token+gistID para recuperar tudo
