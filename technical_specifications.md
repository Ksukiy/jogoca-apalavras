# Documento de Especificação Técnica — Jogo de Palavras Casual

## 1. Arquitetura do Sistema
- **Tipo de Aplicação**: Single-Page Application (SPA) Client-Side.
- **Tecnologias**: HTML5, Tailwind CSS, JavaScript (Vanilla ES6+).
- **Armazenamento Local**: LocalStorage para contagem de streak, histórico de partidas e estado do jogo atual do dia.

## 2. Estrutura de Dados (LocalStorage)
```json
{
  "lastPlayedDate": "YYYY-MM-DD",
  "currentStreak": 5,
  "bestStreak": 12,
  "totalPlayed": 20,
  "totalWins": 18,
  "gameState": {
    "wordOfDay": "PIXEL",
    "attempts": ["PASTA", "PIXEL"],
    "isCompleted": true,
    "hasWon": true
  }
}
```

## 3. Algoritmo de Validação de Tentativas
Para cada palavra submetida:
1. Normalizar caracteres (remover acentos e converter para maiúsculas).
2. Comparar tamanho com a palavra secreta (ex: 5 letras).
3. Atribuir estados às letras:
   - `correct` (Verde / Emerald): letra idêntica no mesmo índice.
   - `present` (Amarelo / Amber): letra existe na palavra, mas em outro índice.
   - `absent` (Cinza / Slate): letra não está presente na palavra.

## 4. Estrutura de Componentes da Interface
1. **Header Component**: exibe categoria temática atual e contador de streak.
2. **Board Component**: matriz 6x5 de caixas de letras com animações e acessibilidade (suporte a leitores de tela com `aria-label`).
3. **Virtual Keyboard**: teclado integrado com atualizações de cor refletindo os status descobertos das letras.
4. **Modal Component**: tela final de vitória/derrota com estatísticas e botão de compartilhamento rápido via Clipboard.