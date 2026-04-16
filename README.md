# Next Gear — Facebook Vehicle Catalog

Feed oficial do inventario da **Next Gear Remarketing** formatado para o Facebook Vehicle Catalog.

## Arquivos

- **`vehicles.csv`** — feed no formato FB Vehicle Catalog (15 veiculos, Kia Soul excluido)
- **`images/`** — fotos dos veiculos (nome: `{stock_id}_{idx:02d}.jpg`)

## URL publica do feed

```
https://raw.githubusercontent.com/Oliveiramv/Nextgear-marketing-/main/fb_catalog/vehicles.csv
```

Essa URL fica como **feed URL** no Commerce Manager. FB busca periodicamente e sincroniza.

## Como atualizar

1. Editar `inventory.csv` em `/home/nextgear/Documents/Next gear Remarketing/`
2. Rodar: `python3 /home/nextgear/Nextgear-marketing/generate_fb_catalog.py`
3. `git add fb_catalog/ && git commit -m "update catalog" && git push`
4. Commerce Manager sincroniza na proxima rodada (ate 4h, ou disparar manual)

## Como adicionar fotos para carros sem imagem

Carros atualmente SEM fotos:
- Ford F-250 Super Duty 2017 (stock E17587)
- Mercedes SL 550 2014 (stock 027651)
- Tesla Model S 2015 (stock 100394)
- Mitsubishi Outlander 2017 (stock 013118)

Para adicionar:
1. Criar pasta em `/home/nextgear/Pictures/` com nome descritivo
2. Adicionar fotos jpg/png
3. Editar `PHOTO_FOLDERS` dict em `generate_fb_catalog.py`
4. Rodar generate + commit + push

## Setup do Commerce Manager (1 vez)

Ver `SETUP-COMMERCE-MANAGER.md` na raiz do repo.
