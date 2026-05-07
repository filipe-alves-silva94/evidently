# Evidently.

> Um quadro visual de investigação para tarefas, ideias e conexões — sem servidor, sem login, sem colunas.

---

## O que é?

**Evidently** é um quadro kanban offline, contido em um único arquivo, inspirado em murais de investigação de detetive. Em vez de colunas fixas, você posiciona cards livremente sobre um quadro de cortiça, conecta-os com fios coloridos, agrupa-os em zonas coloridas e navega por tudo com zoom e arrastar.

Tudo roda em um único arquivo `.html`. Sem etapa de build, sem dependências, sem servidor. Abra no navegador e comece a fixar.

---

## Funcionalidades

### Cards
- **Cards de nota** — título, descrição, checklist com barra de progresso, prazo com alerta de atraso e tag
- **Cards de foto** — anexe imagens via URL ou upload local, com legenda
- **Badge de status** — clique para alternar entre `A FAZER → FAZENDO → FEITO →`
- **5 tags** — `work`, `pessoal`, `urgente`, `ideia`, `meeting`
- **4 cores de alfinete** — vermelho, azul, amarelo, verde
- **8 cores de card** — Padrão, Mel, Rosa, Azul, Verde, Lilás, Âmbar, Branco
- **4 variantes de card** — padrão, envelhecido, nota (amarelo), vermelho
- **Cards redimensionáveis** — arraste o canto inferior direito para redimensionar largura e altura
- **Links clicáveis** — URLs nas descrições são renderizados como links clicáveis
- **Arraste livremente** para qualquer lugar do quadro
- **Duplo clique** para editar, **clique simples** no badge para alternar status

### Conexões (Fios)
- Clique no alfinete de um card para entrar no modo de conexão
- Clique em um segundo card para desenhar um fio curvo entre eles
- **8 cores de fio** — Vermelho, Laranja, Amarelo, Verde, Azul, Roxo, Branco, Preto
- **Relações tipadas** — rotule fios como: `bloqueia`, `depende de`, `relacionado`, `referência`
- Rótulos aparecem sobre o ponto médio do fio
- **Cortar/editar conexões** — gerencie conexões individuais por card

### Zonas
- Crie áreas coloridas de fundo para agrupar cards visualmente
- **Arraste** pelo cabeçalho, **redimensione** pelo canto inferior direito
- **Duplo clique** no nome da zona para renomear
- 6 temas de cores predefinidos

### Temas
- **3 temas de quadro** — Cork (quadro de cortiça, padrão), Night (modo escuro), Paper (claro/limpo)
- Seletor de tema disponível nas propriedades do quadro (⚙)
- Temas afetam toda a interface: quadro, cards, cabeçalho, barra de ferramentas e modais

### Fontes dos Cards
- **8 opções de fonte** — Caveat, Kalam, Indie Flower, Patrick Hand, DM Sans, Courier Prime, Playfair, Special Elite
- Seletor de fonte disponível nas propriedades do quadro (⚙)
- A escolha de fonte persiste entre sessões

### Navegação
- **Scroll** para zoom in/out, centralizado no cursor
- **Botão do meio do mouse** para arrastar o quadro
- **Pinça para zoom** e **arrastar com 1 dedo** em dispositivos touch
- **Minimapa** — aparece no canto superior direito durante o arraste, mostrando todos os cards
- **Indicador de zoom** — clique no badge `%` para resetar a visualização

### Seleção múltipla
- **Arraste em área vazia** do quadro para desenhar um laço de seleção
- **Shift+clique** para adicionar/remover cards da seleção
- **Arraste qualquer card selecionado** para mover o grupo todo

### Modo Foco
- Clique em **"focar"** em qualquer card para destacá-lo junto com suas conexões diretas
- Todos os cards e fios não relacionados ficam quase invisíveis
- Clique em um card esmaecido ou no fundo do quadro para sair, ou pressione `Esc`

### Busca
- Barra de busca no cabeçalho filtra cards por título, descrição, tag, legenda e itens de checklist
- Suporta múltiplos termos separados por espaços
- Cards não correspondentes ficam esmaecidos; cards encontrados ficam destacados com contagem de resultados
- Pressione `Esc` ou clique fora para limpar

### Templates
- Selecione um card e clique em **📋 Templates** na barra de ferramentas
- Salve seu layout (título, descrição, estrutura do checklist, tag, estilo) como template reutilizável
- Templates persistem entre sessões no `localStorage`
- Instancie um card a partir do template diretamente no centro da visualização atual

### Múltiplos Quadros
- Crie quantos quadros precisar usando o botão `+` nas abas
- Cada quadro tem seus próprios cards, zonas e conexões
- O quadro ativo é refletido no hash da URL (`#boardId`) para favoritar
- Navegação por histórico do navegador (voltar/avançar) entre quadros

### Propriedades do Quadro (⚙)
- Renomear o quadro ativo
- **Seletor de tema** — alterne entre Cork, Night e Paper
- **Seletor de fonte** — escolha a família de fonte dos cards
- **Estatísticas do quadro** — visão geral de cards, conexões e zonas
- **Exportar** — salva todos os quadros em um único arquivo `.invboard` (JSON)
- **Importar** — carregue um arquivo `.invboard`; escolha adicionar como novos quadros, substituir o quadro atual ou mesclar conteúdo
- **Salvar como PNG** — captura o quadro como imagem de alta resolução
- Resetar sessão (limpa todos os dados)

### Log de Atividades
- Log de atividades por card rastreando edições e mudanças de status
- Até 50 entradas por card com data e hora
- Acessível pela aba Histórico no modal de edição do card

### Histórico
- **Ctrl+Z** — desfazer (até 60 níveis por quadro)
- **Ctrl+Shift+Z** ou **Ctrl+Y** — refazer
- Histórico é independente por quadro e limpa ao trocar de quadro
- Arrastar cards não polui a pilha de desfazer

### Mobile e Touch
- Suporte completo a toque: arrastar cards, duplo toque para editar, pinça para zoom, arrastar com 1 dedo
- Botão flutuante **+** (FAB) expande em opções de adição
- Todos os modais abrem como bottom sheets em telas pequenas
- Margens seguras do iOS respeitadas

---

## Começando

Nenhuma instalação necessária.

1. Baixe o `evidently.html`
2. Abra em qualquer navegador moderno
3. Comece a adicionar cards

```
open evidently.html
```

Pronto.

---

## Atalhos de Teclado

| Atalho | Ação |
|---|---|
| `Scroll` | Zoom in / out |
| `Botão do meio` | Arrastar o quadro |
| `Duplo clique no card` | Editar card |
| `Clique no alfinete` | Iniciar / finalizar conexão |
| `Ctrl+Z` | Desfazer |
| `Ctrl+Shift+Z` | Refazer |
| `Ctrl+Y` | Refazer |
| `Esc` | Cancelar conexão / fechar modal / sair do foco |
| `Shift+clique` | Adicionar card à seleção |

---

## Formato de Arquivo

Quadros são exportados como arquivos `.invboard` — JSON puro com campo de versão. Você pode inspecioná-los ou editá-los manualmente.

```json
{
  "version": 1,
  "exported": "2025-01-01T00:00:00.000Z",
  "boards": [{ "id": "abc123", "name": "Meu Quadro" }],
  "cards":  { "abc123": [ "..." ] },
  "conns":  { "abc123": [ "..." ] },
  "zones":  { "abc123": [ "..." ] }
}
```

Imagens carregadas localmente são armazenadas como base64 dentro do objeto do card. Isso torna o arquivo autocontido, mas pode crescer bastante — exporte regularmente para evitar atingir os limites do `localStorage`.

---

## Dados e Privacidade

- **Tudo fica no seu dispositivo.** Nenhum dado é enviado a um servidor.
- Cards, zonas e conexões são salvos automaticamente no `localStorage`.
- Exporte arquivos `.invboard` para backups ou para compartilhar quadros.
- Limpar o armazenamento do navegador apagará seus dados — sempre mantenha um backup exportado.

---

## Suporte a Navegadores

Funciona em qualquer navegador moderno com suporte a ES2020+:

| Navegador | Status |
|---|---|
| Chrome / Edge 90+ | Suporte completo |
| Firefox 90+ | Suporte completo |
| Safari 15+ | Suporte completo |
| Mobile Chrome / Safari | Suporte completo a toque |

A exportação como PNG requer acesso ao `esm.sh` (CDN) para carregar o `html2canvas`. Se sua rede bloqueia CDNs externos, a exportação sugere uma captura de tela do sistema.

---

## Ideias para o Roadmap

- [ ] Edição colaborativa em tempo real (WebSockets / CRDT)
- [ ] Filtragem por tipo de relação (mostrar apenas cards que "bloqueia" outros)
- [ ] Criação de cards via teclado

---

## Licença

MIT — faça o que quiser com isso.

---

<p align="center">
  <strong>Evidently.</strong> — conecte os pontos.
</p>
