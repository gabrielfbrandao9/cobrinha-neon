# Cobrinha Neon

Jogo da cobrinha com visual neon, feito em um único arquivo HTML — sem dependências, sem build.

**Jogar:** https://gabrielfbrandao9.github.io/cobrinha-neon/

## Como jogar

Abra o `index.html` em qualquer navegador moderno. Só isso.

### Controles

| Ação | Teclado | Celular |
| --- | --- | --- |
| Mover | Setas ou WASD | Deslizar o dedo ou usar o direcional na tela |
| Pausar / continuar | Espaço | Botão ❚❚ |
| Começar / jogar de novo | Espaço, Enter ou botão **Jogar** | Botão **Jogar** |

### Itens

| Item | Cor | Efeito |
| --- | --- | --- |
| Comida | Rosa | +10 pontos e a cobra cresce |
| Ouro | Amarelo | +50 pontos; some em 5 segundos |
| Gelo | Azul | Deixa o jogo mais lento por 6 segundos |
| Fantasma | Roxo | Atravessa paredes e o próprio corpo por 5 segundos |

Itens especiais piscam pouco antes de sumir. A cada 60 pontos você sobe de nível e a cobra fica mais rápida.

O recorde fica salvo no navegador (`localStorage`).

## Tema e app

- O botão ☀/☾ no canto troca entre tema claro e escuro (o padrão segue o aparelho).
- Dá para instalar como app: botão **Instalar** no canto (baixa o APK para Android; dentro do app, vira **Atualizar**) ou **Compartilhar → Adicionar à Tela de Início** no iPhone.
  Depois de aberto uma vez, funciona sem internet.
- `sw.js` e `manifest.webmanifest` cuidam do app; ao mudar a lista de arquivos, aumente `VERSAO` no `sw.js`.

## App Android (.apk)

**Baixar:** <https://github.com/gabrielfbrandao9/cobrinha-neon/releases/latest/download/CobrinhaNeon.apk>

`android/` tem um app mínimo em Java: um WebView que abre o site publicado e guarda uma cópia para usar
sem internet. O site não muda nada: `android/shim.js` entra em cada página dentro do app e faz funcionar
o que o WebView não tem (baixar, abrir e compartilhar arquivos, login com Google pelo navegador, botão voltar).

- **Telas e funções:** chegam sozinhas. Basta publicar o site (`git push`) e na próxima abertura do app está lá.
- **Parte Android:** precisa de APK novo. O app avisa quando há Release mais nova.

Gerar o APK (Git Bash, na pasta do projeto): `bash android/build-apk.sh`. Sai em `dist/CobrinhaNeon.apk`.
Para uma versão nova, aumente os dois números em `android/versao.txt`.

A chave de assinatura fica fora do Git, em `Documents\Claude Code\apk-chaves` (`com.gabrielfbrandao.cobrinha.*`).
**Guarde essa pasta:** sem ela, versões novas não instalam por cima da antiga.
