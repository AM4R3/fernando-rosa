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

Nada foi escrito por suposição. Cada linha abaixo foi aberta e conferida na fonte, e quase todas
aparecem em duas fontes independentes ou mais.

| Afirmação no site | Fontes |
|---|---|
| Nasceu em Itaquera, zona leste de SP | [Folha de Londrina, 2022](https://www.folhadelondrina.com.br/ultimas-noticias/conheca-fernando-rosa-baixista-que-chamou-a-atencao-de-lenny-kravitz-slash-e-spike-lee-3182444e.html) · [Terra](https://www.terra.com.br/diversao/musica/baixista-fernando-rosa-ganha-o-mundo-apos-lives-na-pandemia,f975cb03f446929fa41516a5205a7abbhb311890.html) |
| Bailes de garagem, autodidata | [Terra](https://www.terra.com.br/diversao/musica/baixista-fernando-rosa-ganha-o-mundo-apos-lives-na-pandemia,f975cb03f446929fa41516a5205a7abbhb311890.html) |
| Começou aos 8 anos, profissional aos 14 | Folha de Londrina · [Reggies Chicago](https://www.reggieslive.com/band/fernando-rosa/) · [listagem do Jazz Cafe](https://www.blackhistorymonth.org.uk/article/listings/region/camden/fernando-rosa/) |
| Tocou na banda de Ed Motta | [Música & Mercado, 27/07/2021](https://musicaemercado.org/contrabaixista-fernando-rosa-fecha-parceria-com-music-man-e-ernie-ball/) · Folha de Londrina |
| Apoio oficial Music Man e Ernie Ball desde 2021 | Música & Mercado · [music-man.com/artists](https://www.music-man.com/artists) |
| Baixo da Fender com o nome dele, cor "Fernando Rosa Green" | [Rolling Stone Brasil, 10/05/2024](https://rollingstone.com.br/musica/fernando-rosa-recorda-como-foi-tocar-com-lenny-kravitz-muito-facil/) · [Tenho Mais Discos Que Amigos, 2022](https://www.tenhomaisdiscosqueamigos.com/2022/07/11/fernando-rosa-entrevista-vibra-open-air-fender/) |
| Vídeos na pandemia chamaram a atenção de Slash, Adam Levine, Duff McKagan | Folha de Londrina · Rolling Stone Brasil 2024 |
| ... e de Spike Lee | Folha de Londrina · [PopLine, 2022](https://portalpopline.com.br/como-as-redes-sociais-fizeram-fernando-rosa-ser-reconhecido-como-um-dos-instrumentistas-mais-influentes-do-mundo/) |
| Projeto ALIVE com Derrick McKenzie; Teatro Prudential (Rio) | PopLine · Reggies Chicago |
| Jazz Cafe, Londres, março de 2022 | [No Treble, 06/04/2022](https://www.notreble.com/buzz/2022/04/06/fernando-rosa-in-the-stone-and-dont-stop-til-you-get-enough/) · [vídeo no canal oficial do Derrick McKenzie](https://www.youtube.com/watch?v=pQz9D-EAvMw) |
| Convite de Lenny Kravitz, Los Angeles, ensaios nas Bahamas, vários shows | Rolling Stone Brasil 2024 (relato dele) · [Bass Magazine](https://bassmagazine.com/lenny-kravitz-straight-cold-player/) |
| iHeartRadio Music Festival 2023, Las Vegas, *It Ain't Over 'Til It's Over* | [No Treble, 10/10/2023](https://www.notreble.com/buzz/2023/10/10/lenny-kravitz-with-fernando-rosa-it-aint-over-til-its-over-live/) · [vídeo no canal dele](https://www.youtube.com/watch?v=i_bLfbZu_fQ) |
| Funk Ship no Blue Note SP, 17/06/2025, com Derrick McKenzie | [Rolling Stone Brasil, 13/06/2025](https://rollingstone.com.br/musica/fernando-rosa-conta-a-rs-sobre-seu-novo-show-funk-ship-que-chega-a-sao-paulo/) |
| Frase do Lenny Kravitz (mensagem ao Fernando) | Folha de Londrina, 26/03/2022 |
| Vegano | bio do Instagram dele ("Vegan for the animals") |

**Ficou de fora de propósito**, por aparecer numa fonte só ou por ser incerto:
- gravações no disco *Blue Electric Light* do Kravitz (ele mesmo disse à Rolling Stone que não sabia se entrariam);
- Chemical Brothers e Kell Smith (só a Folha cita);
- "primeiro brasileiro da Ernie Ball Music Man" (só a Rolling Stone; a Música & Mercado, que noticiou a parceria, não diz isso);
- "três noites esgotadas no Jazz Cafe e duas no New Morning" (a página que dizia isso saiu do ar);
- "um dos baixistas mais influentes do mundo" pelo Scott's Bass Lessons (duas matérias repetem, mas nenhuma mostra a lista);
- número de edições do BLACKOUT e número de seguidores (muda toda semana).

Sobre a data no cartaz: o cartaz oficial diz "27/ago, quinta, às 21h" e **não imprime o ano**.
27 de agosto cai numa quinta-feira em 2015, 2020 e 2026, então o ano não foi publicado em lugar
nenhum do site. O que dá para afirmar, em qualquer um dos casos, é que aquela edição já aconteceu.
