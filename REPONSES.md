## 1. La fonctionnalité ajoutée 
Ajout de **Withdraw** permettant le retrait d’un montant depuis un compte.
Cette opération :
- la validité du montant (montant > 0),
- l’existence du compte,
- la disponibilité du solde.
En cas d’erreur, un **SOAP Fault** est retourné.

## 2. les fichiers modifiés (XSD + classes/endpoint) 

### XSD
- `bank.xsd`
  - Ajout des éléments :
    - `WithdrawRequest` (accountId, amount)
    - `WithdrawResponse` (newBalance)

### Classes
- `WithdrawRequest.java`
- `WithdrawResponse.java`

### Côté serveur
- `BankService.java`
  - Ajout de la méthode `withdraw(accountId, amount)`
  - Gestion des erreurs : montant invalide, compte inexistant, solde insuffisant
- `BankEndpoint.java`
  - Ajout de l’opération SOAP `Withdraw`


## 3. Résultats des tests Postman

Les captures d’écran de Postman sont rendu dans la compte rendu dans l'espace du classroom et aussi dans le dossier images .
