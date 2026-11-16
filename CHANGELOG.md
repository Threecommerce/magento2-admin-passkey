# Changelog

Il formato è basato su [Keep a Changelog](https://keepachangelog.com/it/1.1.0/)
e questo progetto aderisce al [Semantic Versioning](https://semver.org/lang/it/).

## [1.1.2] - 2026-11-16

### Fixed
- Il prompt del nome dava errore (validatore jQuery non caricato) e la passkey non veniva registrata; se il nome resta vuoto si usa quello suggerito.
- L'azione **Rimuovi** non compariva nelle righe della griglia.

## [1.1.1] - 2026-11-16

### Fixed
- Il pulsante **Aggiungi una passkey** della griglia rimandava a una pagina inesistente (404) invece di aprire il prompt.

## [1.1.0] - 2026-11-16

### Changed
- La pagina **Sistema → Permessi → My Passkeys** è ora una griglia standard dell'admin (UI component):
  pulsante **Aggiungi una passkey** nell'intestazione, toolbar con filtri, colonne e paginazione,
  azione **Rimuovi** per riga con conferma. Il nome della passkey si inserisce nel prompt che si apre col pulsante.
  Prima l'elenco e il modulo erano HTML libero sotto la tabella, poco leggibili con i temi admin scuri.

### Added
- Rimozione massiva delle passkey selezionate dalla griglia.

## [1.0.0] - 2026-11-09

### Added
- Pulsante **Accedi con passkey** nel login dell'admin: nessuna password, nemmeno lo username (credenziale rilevabile).
- Pagina **Sistema → Permessi → My Passkeys** per registrare, elencare e rimuovere le proprie passkey (fino a N per utente).
- Opzione per far valere la passkey come secondo fattore (verifica utente sempre obbligatoria); funziona anche con
  `Magento_TwoFactorAuth` disattivato.
- Comando `bin/magento threecommerce:adminpasskey:reset --user=NOME | --all` per il recupero.
- Opzione **Blocca la password per chi ha una passkey**: chi ha almeno una passkey non entra più con la password,
  né dal login né dal token API admin (recupero con il comando di reset).
- Antiabuso: limite ai tentativi falliti e alle richieste, challenge monouso a scadenza, contatore delle firme.
