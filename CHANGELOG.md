# Changelog

Il formato è basato su [Keep a Changelog](https://keepachangelog.com/it/1.1.0/)
e questo progetto aderisce al [Semantic Versioning](https://semver.org/lang/it/).

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
