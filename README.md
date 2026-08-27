# Derroteiro do Cap de Creus

Roteiro de 6 dias em Llançà e no Parc Natural del Cap de Creus, para 5 pessoas.
**29 de agosto a 4 de setembro de 2026.**

Página estática, um arquivo só, sem dependências além das fontes do Google. Feita para abrir no celular durante a viagem: os telefones são links de discagem e o mapa leva direto ao dia.

## Publicar no GitHub Pages

1. Crie um repositório novo no GitHub (pode ser público ou privado — o Pages funciona nos dois em contas Pro).
2. Suba `index.html` e `README.md` na raiz.
3. Vá em **Settings → Pages**.
4. Em *Source*, escolha **Deploy from a branch**; em *Branch*, escolha `main` e a pasta `/ (root)`. Salve.
5. Em um ou dois minutos o site sai em `https://SEU-USUARIO.github.io/NOME-DO-REPO/`.

Pelo terminal:

```bash
cd roteiro-llanca
git init
git add .
git commit -m "Derroteiro do Cap de Creus"
git branch -M main
git remote add origin git@github.com:SEU-USUARIO/NOME-DO-REPO.git
git push -u origin main
```

Depois é só ativar o Pages pelo Settings, como acima.

## Estrutura

```
index.html   página inteira: estilos, SVG do mapa e conteúdo
README.md    este arquivo
```

## Como editar

Tudo está em `index.html`, em português, sem build. As partes que você provavelmente vai querer mexer:

- **Cores e fontes** — no bloco `:root`, no topo do `<style>`. A paleta vem de carta náutica: azul de tinta, tom de terra, água rasa, e o magenta que as cartas reservam para luzes, zonas restritas e avisos. Na página, magenta significa a mesma coisa: preço, alerta e farol.
- **Um dia** — cada dia é um `<article class="day" id="dN">`. Dentro, cada parada é um `<li class="stop">` com horário, título e texto.
- **Os pinos do mapa** — no `<svg>`, os `<a class="pin-hit">`. O `href` aponta para o `id` do dia.
- **Tabelas de custo e de restaurantes** — `<table class="tbl">`, marcação normal.

Se mudar o número de dias, ajuste também a lista da `.daynav` e os `animation-delay` dos `.pin-hit` no CSS.

## Fontes dos dados

Preços de ingressos, horários e telefones foram levantados dos sites oficiais e dos operadores em agosto de 2026: Patrimoni Cultural da Generalitat, Fundació Gala-Salvador Dalí, Parcs Naturals de Catalunya, Barca Tour Llançà, Pirates del Cap de Creus e SK Kayak. **Confirme na hora de reservar** — coisa de temporada muda.

O mapa é um esquema desenhado à mão para orientar o roteiro. Não serve para navegação.
