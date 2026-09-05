[English](README.md) | Português

# Diff Viewer

[![CI](https://github.com/obrenoalvim/diff-viewer/actions/workflows/ci.yml/badge.svg)](https://github.com/obrenoalvim/diff-viewer/actions/workflows/ci.yml) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

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
