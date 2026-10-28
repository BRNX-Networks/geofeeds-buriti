# geofeeds-buriti

Geofeeds de autopublicação de geolocalização IP no formato **RFC 8805**, servidos
via GitHub Pages com `Content-Type: text/csv` (aceito pelo registro.br).

## Feeds publicados

| Prefixo | URL do geofeed |
| --- | --- |
| `45.232.245.0/24` | https://brnx-networks.github.io/geofeeds-buriti/geofeeds_45.232.245.0_24.csv |

Cada URL deve ser informada no atributo `geofeed:` do respectivo objeto *inetnum*
no registro.br. Um link por bloco.

## Formato

```
prefixo,país,região,cidade,código-postal
45.232.245.0/24,BR,BR-MA,Buriti,65515-000
```

- `país`: ISO 3166-1 alpha-2
- `região`: ISO 3166-2 (`BR-MA` = Maranhão)
- Sem cabeçalho, sem aspas, uma linha por prefixo, terminada em LF

## Verificação

```bash
curl -sI https://brnx-networks.github.io/geofeeds-buriti/geofeeds_45.232.245.0_24.csv
# esperado: HTTP/2 200 e content-type: text/csv; charset=utf-8
```

## Referências

- RFC 8805 — formato do arquivo de geofeed
- RFC 9877 — registro do media type `application/geofeed+csv`
