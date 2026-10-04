# Omnia Digital Assistenza

Fork di [RustDesk](https://github.com/rustdesk/rustdesk) 1.5.0 (commit `fada664`), licenza **AGPL-3.0**
come l'originale (file `LICENCE`). È il programma che i clienti di Omnia Digital installano per
ricevere assistenza remota dal server `remote.omniadigital.it`.

## Modifiche rispetto a RustDesk 1.5.0

| File | Modifica |
|---|---|
| `res/omnia/profile.json`, `src/common.rs` | Profilo compilato nel programma: nome `OmniaAssistenza`, server/chiave/API fissi, solo ricezione, impostazioni nascoste, aggiornamenti verso RustDesk disattivati. `custom.txt` viene ignorato. |
| `src/platform/windows.rs` | Il nome del file eseguibile non può cambiare server, chiave o API. |
| `src/client.rs`, `src/server/connection.rs` | Solo ricezione senza eccezioni: niente sessioni in uscita, richiesta di inversione dei ruoli rifiutata. |
| `res/*.ico`, `res/*.png`, `flutter/assets/logo*.png`, `flutter/assets/icon.png`, `flutter/windows/runner/resources/app_icon.ico` | Icone e logo. |
| `flutter/windows/runner/Runner.rc` | Metadati dell'eseguibile. |
| `.github/workflows/omnia-windows.yml` | Build Windows x64 (senza firma, senza MSI). |

Le funzioni, il protocollo e la crittografia sono quelli di RustDesk; il server è descritto su
`https://remote.omniadigital.it/sorgenti/`.

## Build

Actions › "Omnia Windows x64" (manuale) oppure tag `omnia-*`, che pubblica anche una release con
l'eseguibile e il suo SHA-256.
