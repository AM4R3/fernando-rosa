# Site oficial de Fernando Rosa

Arquivo único (`index.html`), sem framework e sem build. Para publicar, é só subir a pasta.
Produção: https://fernando-rosa.vercel.app

---

## Publicar uma data nova

Abra o `index.html`, procure por `var SHOWS` e acrescente um objeto **no topo** do array:

```js
{
  nome:   'BLACKOUT',
  data:   '2026-11-14',                 // AAAA-MM-DD, sempre
  casa:   'Red Star',
  cidade: 'São Paulo, SP',
  link:   'https://...'                 // url de ingressos; vazio se a venda não abriu
}
```

O resto do site se ajusta sozinho a partir daí:

- o pôster vira **destaque** com o selo "Próximo show" e a contagem `faltam X dias`
  (calculada no fuso de São Paulo, então bate igual para quem abrir de Tóquio);
- os botões do topo, do rodapé e da barra do celular viram **Ingressos** e apontam para o link;
- o show que já passou desce sozinho para a faixa "Já aconteceu";
- o `Event` do Schema.org é gerado com data, local e link.

**Sem link de ingresso** os botões dizem "Venda em breve" e vão para o Instagram: eles nunca
prometem ingresso sem ter onde vender.

**Data escrita errado** (mês 13, 31/02, formato trocado) é ignorada e avisada no console, em vez de
quebrar a página.

Para um show sem data marcada, use `tba: true` no lugar de `data`.

---

## Trocar as fotos

As imagens ficam em `img/`. Cada `<figure>` já tem `width`, `height` e `loading` corretos: mantenha.

**Foto de show** (falta), na seção da agenda, logo depois do texto do BLACKOUT:

```html
<figure class="ph ph--palco" data-reveal style="margin-top:24px">
  <img src="img/palco-01.jpg" alt="Fernando Rosa tocando baixo no BLACKOUT"
       loading="lazy" width="1200" height="800">
</figure>
```

Para trocar uma foto que já existe, gere também a versão menor e mantenha o `srcset`
(o site serve a de 900px no celular e a de 1600px no desktop).

---

## Colocar os contatos de booking

Na seção `#booking`, troque o parágrafo `A confirmar: e-mail e WhatsApp de booking` por:

```html
<a class="btn btn--linha btn--full" href="mailto:booking@dominio.com">E-mail de booking</a>
<a class="btn btn--linha btn--full" href="https://wa.me/5511999999999"
   target="_blank" rel="noopener">WhatsApp</a>
```

Atualize também a coluna Booking do rodapé.

---

## O que ainda falta confirmar

| Item | Onde está no site |
|---|---|
| Data da próxima edição do BLACKOUT | array `SHOWS` |
| E-mail e WhatsApp de booking | seção `#booking` e rodapé |
| Foto de show | seção da agenda |
| Links de vídeo (BLACKOUT ao vivo, Funk Ship) | seção `#musica` |
| Autorização das fotos e crédito do retrato de estúdio | rodapé |
| Se as marcas W Bass Cabinets, Soul Ears, Vakenelli e Mais Cabello são parceria oficial | faixa de marcas |
| Origem e autorização da frase do Lenny Kravitz | bloco da citação |

---

## De onde veio cada informação da bio

Nada foi escrito por suposição. Só entrou o que foi aberto e conferido na fonte:

| Afirmação no site | Fonte |
|---|---|
| Já dividiu a estrada com Lenny Kravitz | [Bass Magazine](https://bassmagazine.com/lenny-kravitz-straight-cold-player/) |
| iHeartRadio Music Festival, set/2023, em *It Ain't Over 'Til It's Over* | [No Treble](https://www.notreble.com/buzz/2023/10/10/lenny-kravitz-with-fernando-rosa-it-aint-over-til-its-over-live/) |
| Artista oficial Ernie Ball Music Man, toca StingRay | [music-man.com/artists](https://www.music-man.com/artists) |
| Bailes de garagem em Itaquera, autodidata, as lives da pandemia | [Terra](https://www.terra.com.br/diversao/musica/baixista-fernando-rosa-ganha-o-mundo-apos-lives-na-pandemia,f975cb03f446929fa41516a5205a7abbhb311890.html) |
| Funk Ship no Blue Note SP, 17/06/2025, com Derrick McKenzie | [Rolling Stone Brasil](https://rollingstone.com.br/musica/fernando-rosa-conta-a-rs-sobre-seu-novo-show-funk-ship-que-chega-a-sao-paulo/) |
| Frase do Lenny Kravitz | [Folha de Londrina](https://www.folhadelondrina.com.br/ultimas-noticias/conheca-fernando-rosa-baixista-que-chamou-a-atencao-de-lenny-kravitz-slash-e-spike-lee-3182444e.html) |

**Ficou de fora de propósito**, por não ter confirmação do artista: gravações no disco
*Blue Electric Light* do Lenny Kravitz (ele mesmo disse em entrevista que não sabia se entraram),
Chemical Brothers, Ed Motta, Kell Smith, o instrumento feito pela Fender, a idade em que começou a
tocar e o número de edições do BLACKOUT.

Sobre a data no cartaz: o cartaz oficial diz "27/ago, quinta, às 21h" e **não imprime o ano**.
27 de agosto cai numa quinta-feira em 2015, 2020 e 2026, então o ano não foi publicado em lugar
nenhum do site. O que dá para afirmar, em qualquer um dos casos, é que aquela edição já aconteceu.
