# Guia de Deploy - Mintlify

## Passos para fazer o deploy da documentação

### 1. Conectar ao GitHub

1. Acesse [Mintlify Dashboard](https://dashboard.mintlify.com)
2. Faça login na sua conta
3. Vá em **Settings** → **GitHub App**
4. Clique em **Install GitHub App**
5. Autorize o acesso ao repositório onde está a pasta `mintlify-docs`

### 2. Criar/Configurar Projeto

1. No dashboard, clique em **Create Project** ou selecione projeto existente
2. Se criar novo projeto:
   - Nome: "Reach Documentation"
   - Selecione o repositório GitHub correto
   - **Importante**: Defina o **Root Directory** como `mintlify-docs` (ou o caminho onde está o `docs.json`)
   - Se o `docs.json` está em `reach-docs/mintlify-docs/`, o root directory deve ser `mintlify-docs`

### 3. Verificar Configuração

Certifique-se de que:
- ✅ O arquivo `docs.json` está no diretório raiz configurado
- ✅ Todos os arquivos `.mdx` referenciados no `docs.json` existem
- ✅ O repositório foi commitado e pushed para o GitHub

### 4. Deploy Automático

Após conectar o GitHub:
- O Mintlify faz deploy automático quando você faz push para a branch padrão (geralmente `main` ou `master`)
- Você pode ver o status do deploy no dashboard
- A documentação ficará disponível na URL fornecida pelo Mintlify

### 5. Testar Localmente (Opcional)

Antes de fazer deploy, você pode testar localmente:

```bash
# Instalar CLI do Mintlify
npm i -g mint

# Navegar para a pasta da documentação
cd reach-docs/mintlify-docs

# Iniciar servidor local
mint dev
```

Acesse `http://localhost:3000` para ver a documentação localmente.

## Verificações Importantes

### ✅ Arquivos Necessários

Certifique-se de que todos estes arquivos existem:
- `docs.json` (configuração principal)
- `index.mdx` (página inicial)
- Todos os arquivos `.mdx` referenciados no `docs.json`

### ✅ Estrutura de Pastas

A estrutura deve estar assim:
```
reach-docs/
  └── mintlify-docs/
      ├── docs.json
      ├── index.mdx
      ├── getting-started/
      ├── dashboard/
      ├── campaigns/
      ├── leads/
      ├── segments/
      ├── deals/
      ├── sequences/
      ├── accounts/
      ├── security/
      ├── analytics/
      └── organizations/
```

### ✅ Root Directory no Mintlify

No dashboard do Mintlify, o **Root Directory** deve ser:
- `mintlify-docs` (se o repositório é `reach-docs`)
- Ou o caminho relativo correto até a pasta onde está o `docs.json`

## Troubleshooting

### Ainda vendo "Starter Kit"

Se ainda está vendo o starter kit:

1. **Verifique a URL**: Certifique-se de estar acessando a URL correta do seu projeto (não a demo)
2. **Verifique o Root Directory**: No dashboard, confirme que o root directory está correto
3. **Verifique o Repositório**: Confirme que conectou o repositório correto
4. **Aguarde o Deploy**: Pode levar alguns minutos após o push para o deploy completar
5. **Verifique o Branch**: O deploy automático geralmente acontece na branch padrão (`main` ou `master`)

### Erros de Deploy

Se o deploy falhar:

1. Verifique os logs no dashboard do Mintlify
2. Confirme que todos os arquivos referenciados no `docs.json` existem
3. Verifique a sintaxe do `docs.json` (use um validador JSON)
4. Certifique-se de que o `docs.json` está no diretório raiz configurado

### Arquivos Não Aparecem

Se páginas não aparecem:

1. Verifique que os caminhos no `docs.json` estão corretos
2. Confirme que os arquivos `.mdx` existem nos caminhos especificados
3. Verifique a sintaxe dos arquivos `.mdx` (especialmente o frontmatter)

## Próximos Passos

Após o deploy bem-sucedido:

1. ✅ Adicione screenshots/GIFs/vídeos nos placeholders indicados
2. ✅ Personalize logos e favicon
3. ✅ Atualize links sociais no `docs.json`
4. ✅ Configure domínio customizado (se necessário)

## Links Úteis

- [Mintlify Dashboard](https://dashboard.mintlify.com)
- [Mintlify Documentation](https://mintlify.com/docs)
- [GitHub App Installation](https://dashboard.mintlify.com/settings/organization/github-app)

