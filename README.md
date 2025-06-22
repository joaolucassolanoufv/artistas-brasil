# Dataset de Artistas Musicais Brasileiros (JSON)

Este repositório contém um **dataset** em formato JSON com metadados de mais de 4.000 artistas musicais brasileiros, consolidado a partir de Wikipedia, Wikidata e informações do Spotify. O objetivo é fornecer uma base rica para sistemas de _information retrieval_ e projetos de **Retrieval-Augmented Generation (RAG)**.

---

## Estrutura do arquivo JSON

O arquivo principal (`artists.json`) é um objeto cujo **_key_** é o **ID Wikidata** do artista (ex.: `Q221479`) e cujo valor é outro objeto com os campos:

| Campo               | Tipo                | Descrição                                                                                   |
|---------------------|---------------------|---------------------------------------------------------------------------------------------|
| `Abstract`          | `string`            | Texto completo da biografia resumida (Português).                                           |
| `Name`              | `string`            | Nome oficial do artista.                                                                    |
| `Origin`            | `string`            | Cidade – Estado – País de origem.                                                           |
| `Type`              | `string`            | Tipo de entidade (ex.: `"Pessoa"`, `"Grupo"`).                                             |
| `Activity`          | `object`            | Período de atividade musical:<br>  – `start`: ano de início<br>  – `end`: ano de término ou `"Presente"`. |
| `Genres`            | `array[string]`     | Gêneros extraídos da biografia.                                                             |
| `ShortDescription`  | `string`            | Resumo curto para interfaces rápidas.                                                       |
| `Group`             | `string`            | Nome do grupo ou mesmo valor de `Name` para artistas solo.                                  |
| `spotify_info`      | `object`            | Informações do Spotify (followers, popularidade, gêneros, URL e top tracks).                |

---

## Exemplo de item

```jsonc
"Q221479": {
  "Abstract": "Gilberto Gil é um cantor, compositor e multi-instrumentista brasileiro, nascido em Salvador, Bahia, em 1942, cuja carreira musical começou oficialmente em 1962 e segue ativa até hoje. Ele é um dos principais nomes da Tropicália, movimento musical e cultural que revolucionou a música brasileira nos anos 1960, incorporando influências do rock, samba, baião e música africana. Além de sua carreira artística, Gil também teve atuação política como ministro da Cultura do Brasil entre 2003 e 2008, e é reconhecido internacionalmente por sua contribuição à música popular brasileira.",
  "Name": "Gilberto Gil",
  "Origin": "Salvador - Bahia - Brasil",
  "Type": "Pessoa",
  "Activity": {
    "start": 1962,
    "end": "Presente"
  },
  "Genres": [
    "MPB (Música Popular Brasileira)",
    "Tropicália",
    "Samba",
    "Baião",
    "Reggae",
    "Rock",
    "Funk",
    "Disco",
    "Jazz",
    "Música Africana",
    "Samba de Breque",
    "Forró",
    "Maxixe",
    "Xote"
  ],
  "ShortDescription": "Gilberto Gil, de Salvador, Bahia, região Nordeste, é um ícone da MPB e Tropicália, com carreira ativa desde 1962 até hoje.",
  "Group": "Gilberto Gil",
  "spotify_info": {
    "spotify_followers": "1M+",
    "spotify_genres": [
      "mpb",
      "bossa nova",
      "forró tradicional",
      "samba",
      "brazilian jazz"
    ],
    "spotify_popularity": "B",
    "spotify_url": "https://open.spotify.com/artist/7oEkUINVIj1Nr3Wnj8tzqr",
    "top_tracks": [
      {
        "name": "Esperando na janela",
        "release_date": "2000-01-01",
        "artists": [
          { "name": "Gilberto Gil", "spotify_url": "https://open.spotify.com/artist/7oEkUINVIj1Nr3Wnj8tzqr" }
        ]
      },
      {
        "name": "Andar com fé",
        "release_date": "1982",
        "artists": [
          { "name": "Gilberto Gil", "spotify_url": "https://open.spotify.com/artist/7oEkUINVIj1Nr3Wnj8tzqr" }
        ]
      }
      // ... mais faixas ...
    ]
  }
}
