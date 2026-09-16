# Astroquímica da Nebulosa de Órion — Região OMC-1

Rotinas computacionais em Python para **identificação de moléculas** na região OMC-1
do Complexo de Órion, a partir de um cubo de dados do observatório **ALMA**.

Material de apoio ao artigo submetido à revista *Physicæ Organum* (Universidade de
Brasília), com finalidade **didática**: cada etapa do notebook é comentada para que
estudantes de licenciatura (Química, Física, Ciências) possam reproduzir e adaptar a
análise.

**Autores:** Thayllan Anthony de Oliveira · Rafael Ramon Ferreira
**Instituição:** Instituto Federal do Triângulo Mineiro (IFTM)

---

## O que o notebook faz

Partindo do cubo FITS do ALMA, o notebook `Espectro_OMC-1.ipynb`:

1. Baixa e carrega o cubo de dados tridimensional (2 eixos espaciais + 1 de frequência).
2. Mapeia a nuvem e localiza o pixel de emissão máxima (a "Região 5").
3. Extrai o espectro de rádio nesse pixel.
4. Identifica as moléculas (*Line ID*) consultando os catálogos JPL e CDMS via Splatalogue.
5. Aplica um filtro físico (energia do nível superior, `Eu/k < 500 K`).
6. Converte a posição do pixel em coordenadas celestes (RA/Dec).

Ao final, discute o **potencial didático** da proposta e sugere atividades para sala de
aula e iniciação científica.

## Estrutura do repositório

```
.
├── Espectro_OMC-1.ipynb   # notebook principal, comentado
├── README.md              # este arquivo
├── requirements.txt       # dependências
└── figuras/               # figuras geradas pelo notebook (.png e .pdf)
```

> A pasta `dados/` (com o cubo FITS e a tabela CSV) é criada automaticamente na primeira
> execução. O cubo do ALMA é grande e **não** é versionado — ele é baixado pelo notebook.

## Como executar

### Google Colab (recomendado — não exige instalação)

1. Abra o notebook no Colab (badge no topo do arquivo `.ipynb`).
2. Execute as células na ordem. A biblioteca `astroquery` é instalada automaticamente.
3. As figuras são salvas na pasta `figuras/`.

### Localmente

```bash
pip install -r requirements.txt
jupyter notebook Espectro_OMC-1.ipynb
```

## Dados

Cubo público do ALMA:
`OMC-1_Region5_sci.spw18.cube.I.pbcor.fits`, baixado do
[ALMA Science Archive](https://almascience.eso.org/).

## Licença

Uso educacional e acadêmico. Ao reutilizar, cite o artigo correspondente.
