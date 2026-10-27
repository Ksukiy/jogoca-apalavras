# Testes

## Executar

Na raiz do projeto:

```powershell
python -m http.server 8000
```

Abra [http://localhost:8000/tests/game_tests.html](http://localhost:8000/tests/game_tests.html) no navegador. Cada teste é independente e o resultado aparece na página.

## Cobertura curta

- criação do tabuleiro 6x5 e do teclado;
- entrada de letras, limite de tamanho e backspace;
- rejeição de tentativa curta;
- aplicação do feedback visual;
- atualização das estatísticas ao vencer;
- compartilhamento sem revelar a palavra.

O runner usa apenas HTML e JavaScript nativos, sem dependências ou build. Os testes usam a palavra calculada para a data corrente.
