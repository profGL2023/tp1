# Single Responsability Principle

Nous avons hérité du code d'un logiciel de gestion d'Employés. Dans ce code, nous trouvons la classe *Employe* avec les trois méthodes suivantes :
- *afficheDetails()* affiche le nom d’un employé et 
son matricule.
- *genererMatricule()* génère le matricule d’un employé. 
- *calculerSalaire()* calcule le salaire de l'employé pour le mois en cours
- *promouvoirGrade()* vérifie si un employé est admissible au grade suivant puis met à jour le grade et l'année du dernier grade.

```java
public class Employe {
    String prenom;
    String nom;
    int lieuDeNaissance;        // code wilaya
    boolean masculin ;          // masculin: true, feminin: false 
    int anneeRecrutement;        
    String grade ;
    int anneeDernierGrade ; 
    String matricule ; 

    // TODO - constructeur
    // ...

    // TODO - setters and getters
    // ...

    public String afficherDetails () {
        StringBuilder sb = new StringBuilder ("") ; 
        sb.append("Employé:\n")
            .append(grade).append(" ")
            .append(nom.toUpperCase()).append(" ").append(prenom) ;
        if (matricule != null){
            sb.append("\n").append("mat: ").append(matricule) ;
        }
        sb.append("\nsalaire: ").append(calculerSalaire ());
        System.out.println(sb.toString());
    }
    
    public String genererMatricule () {
        StringBuilder sb =  = new StringBuilder ("") ; 
        sb.append(anneeRecrutement)
            .append(".")
            .append(lieuDeNaissance)
            .append(masculin?0:1)
            .append(".")
            .append(new Randon().randInt(99999));        
        retrun sb.toString () ;
    }
    
    // salaire en centimes de dinars
    public long calculerSalaire () {
        // TODO
        return 0 ;
    }

    public void promouvoirGrade () {
        // TODO
    }
    
}
```

*Client* (la classe qui utilise les instances de *Employe*) dispose d'une méthode *main*, crée deux instances de *Employe*, puis affiche leurs détails.

1. générez un projet avec la classe *Employe*.
2. utilisez le code fourni et complétez le comme suit:
    - d'après le responsable de la RH, un employé est admissible au grade suivant, si il présente au moins cinq (05) années dans le grade actuel. 
    - d'après le respensable des finances, les employés sont payés en fonction de leurs grade selon la grille suivante:

| grade  |  salaire | 
|--|--|
|Grade-1|1000|
|Grade-2|2000|
|Grade-3|2500|
|Grade-4|3000|
|Grade-5|4500|

3. Analysez le code fourni, et identifiez les possiblités (au moins 3) selon lesquelle ce code pourait évoluer. En voici quelques examples: 
- l'affichage ne se produit pas sur la console mais sur une GUI.
- on décide de supprimer le code de la wilaya du matricule. 
- ...

4. Quel principe n'a pas été respecté dans ce code?
5. Rééditez le code afin de respecter le principe en question. 
