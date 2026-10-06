<div align="center">

<img src="app/icon.png" alt="Logo do Diff Viewer" width="120" height="120">

# Diff Viewer

**Compare dois textos e veja exatamente o que mudou, direto no navegador.**<br>
Unificado ou lado a lado, por linha, palavra ou caractere, com exportação em HTML. 100% client-side: nada é enviado.

[![Demo ao vivo](https://img.shields.io/badge/Demo_ao_vivo-abrir-3B82F6?style=for-the-badge&logo=vercel&logoColor=white)](https://diff-viewer-olive.vercel.app)

[![CI](https://github.com/obrenoalvim/diff-viewer/actions/workflows/ci.yml/badge.svg)](https://github.com/obrenoalvim/diff-viewer/actions/workflows/ci.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/obrenoalvim/diff-viewer?style=flat&logo=github&color=3b82f6)](https://github.com/obrenoalvim/diff-viewer/stargazers)
[![PWA](https://img.shields.io/badge/PWA-offline-5A0FC8?logo=pwa&logoColor=white)](#funcionalidades)

[English](README.md) · **Português**

[Funcionalidades](#funcionalidades) · [Como começar](#como-começar) · [Uso](#uso) · [Suporte a navegadores](#suporte-a-navegadores) · [Perguntas frequentes](#perguntas-frequentes)

</div>

---

Uma aplicação web moderna, 100% client-side, para comparar diferenças de texto em tempo real. Construída com Next.js 13 (App Router), TypeScript e Tailwind CSS, com visões unificada e lado a lado, além de várias opções de personalização.

## Funcionalidades

### Funcionalidade principal
- **Cálculo de diff em tempo real**: veja as diferenças instantaneamente enquanto digita ou cola texto
- **Dois modos de visualização**:
  - Visão unificada (coluna única, estilo Git)
  - Visão lado a lado (comparação em duas colunas)
- **Múltiplas granularidades**: compare por linhas, palavras ou caracteres
- **Normalização inteligente**: opções de comparação ignorando maiúsculas/minúsculas e espaços em branco
- **Números de linha**: alterne a exibição de números de linha para facilitar a navegação
- **Colapsar trechos inalterados**: colapsa automaticamente grandes blocos de conteúdo sem mudanças

### Experiência do usuário
- **Atualizações com debounce**: 200ms de debounce evita lag durante a digitação
- **Estado persistente**: todos os inputs e configurações são salvos no localStorage
- **Integração com clipboard**: botões de colar rápido para os dois campos de texto
- **Função de troca**: troque instantaneamente o conteúdo da esquerda com o da direita
- **Notificações toast**: feedback amigável para todas as ações

### Exportar e compartilhar
- **Copiar como texto**: exporta o diff em formato de texto unificado
- **Exportar HTML**: baixe um arquivo HTML totalmente estilizado com o diff embutido
- **Suporte offline**: funcionalidade de Progressive Web App (PWA)

### Internacionalização
- **Suporte multi-idioma**: inglês e português (Brasil)
- **Seleção de idioma persistente**: sua escolha de idioma é lembrada

## Tecnologias

- **Framework**: Next.js 13+ com App Router
- **Linguagem**: TypeScript
- **Estilo**: Tailwind CSS com tema escuro
- **Motor de diff**: biblioteca `diff` para comparação precisa
- **Componentes de UI**: componentes próprios com primitivos do Radix UI
- **Ícones**: Lucide React

## Como começar

### Pré-requisitos
- Node.js 18+
- npm ou yarn

### Instalação

1. Clone o repositório:
```bash
git clone https://github.com/obrenoalvim/diff-viewer.git
cd diff-viewer
```

2. Instale as dependências:
```bash
npm install
```

3. Rode o servidor de desenvolvimento:
```bash
npm run dev
```

4. Abra [http://localhost:3000](http://localhost:3000) no navegador

### Build de produção

```bash
npm run build
npm run start
```

A aplicação ficará otimizada e pronta para deploy.

## Uso

1. **Digite o texto**: digite ou cole o texto nas áreas de entrada da esquerda e da direita
2. **Configure as opções**:
   - Escolha entre visão Unificada ou Lado a Lado
   - Selecione a granularidade (Linhas, Palavras ou Caracteres)
   - Ative opções de normalização (ignorar maiúsculas/minúsculas, ignorar espaços)
   - Alterne números de linha e seções colapsadas
3. **Veja o diff**: a comparação atualiza automaticamente enquanto você digita
4. **Exportar**: use os botões da toolbar para copiar o diff como texto ou exportar como HTML

### Atalhos de teclado
- Use Tab para navegar entre os campos
- Cole diretamente nos campos com Ctrl+V (Cmd+V no Mac)

### Cálculo do diff
A aplicação usa a biblioteca `diff`, padrão da indústria, para calcular as diferenças entre textos. Suporta:
- Comparação linha a linha (padrão)
- Comparação palavra a palavra
- Comparação caractere a caractere

### Opções de normalização
- **Ignorar maiúsculas/minúsculas**: trata letras maiúsculas e minúsculas como idênticas
- **Ignorar espaços em branco**: normaliza múltiplos espaços e remove espaços nas bordas das linhas antes de comparar

### Indicadores visuais
- **Fundo verde**: conteúdo adicionado
- **Fundo vermelho**: conteúdo removido
- **Cinza/neutro**: conteúdo inalterado
- **Borda colorida**: borda esquerda com cor para leitura rápida

### Formatos de exportação
- **Texto**: formato de diff unificado com prefixos +/-
- **HTML**: arquivo HTML autocontido com estilos inline, ideal para compartilhar ou arquivar

## Considerações de performance

- **Debounce**: 200ms de atraso evita recálculos excessivos durante a digitação
- **Memoização**: hooks do React otimizam os re-renders
- **Cálculo preguiçoso**: o diff só é calculado quando os inputs ou opções mudam
- **Renderização eficiente**: o DOM virtual minimiza as atualizações reais do DOM

### Limitações conhecidas
- Textos muito grandes (>100.000 linhas) podem impactar a performance
- A visão Lado a Lado muda automaticamente para Unificada em dispositivos móveis
- A Clipboard API do navegador exige HTTPS em produção (ou localhost em desenvolvimento)

## Suporte a navegadores

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Navegadores móveis (iOS Safari, Chrome Android)

Os recursos de PWA exigem suporte moderno a Service Workers.

## Contribuindo

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou pull requests.

## Créditos

- Construído com [Next.js](https://nextjs.org/)
- Cálculo de diff por [jsdiff](https://github.com/kpdecker/jsdiff)
- Ícones do [Lucide](https://lucide.dev/)
- Componentes de UI inspirados em [shadcn/ui](https://ui.shadcn.com/)

---

## Perguntas frequentes

**Meu texto é enviado para algum lugar?**
Não. A comparação roda 100% no seu navegador, e não existe back-end.

**Dá pra comparar por palavra ou por caractere?**
Dá. Escolha Linhas, Palavras ou Caracteres, e opcionalmente ignore maiúsculas/minúsculas e espaços em branco.

**Funciona offline?**
Funciona. É um Progressive Web App, e precisa de um navegador com suporte a Service Worker.

**Como compartilho um diff?**
Copie como texto unificado, ou exporte um arquivo HTML autocontido com estilos inline.

**Por que a visão lado a lado muda para unificada no celular?**
Ela muda sozinha em dispositivos móveis, pra manter as colunas legíveis.

## Mais ferramentas web do mesmo autor

- [**pdf-metadata-editor**](https://github.com/obrenoalvim/pdf-metadata-editor): edite título, autor e outros detalhes de um PDF no navegador.
- [**custom-cpf**](https://github.com/obrenoalvim/custom-cpf): gere e valide CPFs brasileiros no navegador.
- [**status-hub**](https://github.com/obrenoalvim/status-hub): um grid só para toda página de status que você confere.

## Licença

[MIT](LICENSE)

---

<div align="center">

Se o Diff Viewer te poupou uma ida a uma ferramenta de diff, uma ⭐ ajuda outras pessoas a encontrá-lo.

<sub>**Tópicos:** diff · text-diff · diff-viewer · text-comparison · jsdiff · client-side · pwa · nextjs · react · typescript · developer-tools</sub>

</div>
