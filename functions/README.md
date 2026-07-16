# Odesilani protokolu e-mailem

Tlacitko `Poslat na mail` ve strance vola Firebase Function `sendProtocolMail`.
Funkce odesle Word protokol na:

- `iva.glozova@astip.cz`
- kopie `jan.soldan@astip.cz`

## Nastaveni SMTP pristupu

V projektu Firebase je potreba jednorazove nastavit secrets:

```sh
firebase functions:secrets:set SMTP_HOST
firebase functions:secrets:set SMTP_PORT
firebase functions:secrets:set SMTP_USER
firebase functions:secrets:set SMTP_PASS
```

Typicke hodnoty:

- `SMTP_HOST`: adresa SMTP serveru
- `SMTP_PORT`: `587` nebo `465`
- `SMTP_USER`: e-mail/adresa odesilatele
- `SMTP_PASS`: heslo nebo app password pro SMTP

## Nasazeni

```sh
firebase deploy --only functions:sendProtocolMail
```

Po nasazeni uz tlacitko nic nestahuje a neotevira mailove okno. Protokol se vygeneruje v prohlizeci, posle se do Firebase Function a ta ho odesle jako prilohu.
