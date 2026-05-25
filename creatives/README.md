# Creatives folder

Imagens dos anúncios. Cada arquivo deve estar listado em `manifest.json` mapeando o `Ad Name` (da planilha) para o nome do arquivo.

Estrutura de exemplo:
```
creatives/
  manifest.json
  AD01_100OFF_AMIL.jpg
  AD09_UNIMED_CURITIBA.png
  300x50.jpg
```

manifest.json:
```json
{
  "ads": {
    "AD01_100OFF_AMIL": "AD01_100OFF_AMIL.jpg",
    "AD09_UNIMED_CURITIBA": "AD09_UNIMED_CURITIBA.png",
    "300x50.jpg": "300x50.jpg"
  }
}
```
