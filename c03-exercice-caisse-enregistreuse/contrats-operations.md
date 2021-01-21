# Contrat CU03-MiseEnPlateau
## **Opération:** saisirIdentifiant(identifiant: String, mdp: String)
#### Présconditions:
- Un caissier existe
- Le caissier a un identifiant actif
#### Postconditions
- Aucune

### **Opération:** poserPlateau(identifiantPlateau: String)
#### Présconditions:
- Le caissier est authentifié
- Une instance ca:Caisse existe dans le système
- ca.isOuvert est vrai
#### Postconditions
- Une instance p:Plateau a été créée
- p.identifiant est devenu identifiant
- Une instance mp:MiseEnPlateau a été créée
- mp.dateDebut est maintenant
- Une association est créée entre caissier et mp:MiseEnPlateau
- Une association est créée entre Plateau et mp:MiseEnPlateau sur la base de correspondance avec identifiantPlateau
- Une association est créée entre ca:Caisse et mp:MiseEnPlateau

### **Opération:** entrerMontantPlateau(montant: double)
#### Présconditions:
- Une instance mp:MiseEnPlateau existe dans le système
#### Postconditions
- mp.montant est devenu montant

### **Opération:** fermerTirroirCaisse()
#### Présconditions:
- Le caissier est authentifié sur la caisse ca:Caisse
- ca.isOuvert est vrai
#### Postconditions
- ca.isOuvert est devenu faux
