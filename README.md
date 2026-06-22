# Photopea Share Plugin

Plugin per Photopea che esporta il documento attivo in PNG / JPG / WEBP e prova a condividerlo con la finestra di condivisione nativa del sistema, senza salvare prima il file sul dispositivo.

## File inclusi

- `index.html`: pannello plugin dentro Photopea.
- `share.html`: finestra top-level di fallback per browser che bloccano `navigator.share()` dentro iframe.
- `icon.svg`: icona plugin.
- `plugin.json`: file da caricare in Photopea dopo aver sostituito gli URL.

## Installazione

1. Carica questi file su un hosting HTTPS, ad esempio:
   `https://tuodominio.it/photopea-share-plugin/`
2. Modifica `plugin.json` sostituendo `https://TUO-DOMINIO.IT/photopea-share-plugin/` con il tuo URL reale.
3. Apri Photopea.
4. Vai su `Window > Plugins > Add Plugin` e carica il file `plugin.json`.

## Uso

1. Apri o crea un documento in Photopea.
2. Apri il plugin `Share Image`.
3. Scegli il formato.
4. Premi `CONDIVIDI`: il plugin esporta il documento e apre automaticamente la condivisione.
5. Se il browser blocca la condivisione dentro il pannello, il file viene scaricato automaticamente come fallback.

## Limiti tecnici

- Il browser può mostrare AirDrop solo se il sistema operativo e il browser lo includono tra le destinazioni disponibili.
- La Web Share API richiede HTTPS e un click diretto dell’utente.
- Alcuni browser bloccano la condivisione dei file dentro iframe: per questo è inclusa `share.html`.
- Se la condivisione non è supportata, il plugin offre il download fallback.
