# TestJDBC2014
Test de JDBC donné en 2014 aux étudiants de l'IUT d'Aix-Marseille


## Partie 2 (Sébastien NEDJAR)
### Document autorisé : Le polycopié du cours de JDBC uniquement.


**Remarque :** Les événements et les situations de ce sujet étant purement fictifs, toute ressemblance avec des événement et des situations existantes ou ayant existé ne saurait être que fortuite.

Museomix, c’est le premier makeathon culturel international qui croise les regards et les talents. Museomix, c’est une rencontre des médiateurs, bricoleurs, designers, développeurs, graphistes, communiquants, artistes, écrivains, scientifiques… qui se retrouvent au cœur d’un musée pour expérimenter et vibrer ensemble.

Museomix, c’est 3 jours pour inventer, concevoir, fabriquer et tester un dispositif de médiation muséale innovant et emprunt de numérique.

Plusieurs de vos collègues courageux (eux au moins), participent à cet événement pour imaginer le musée de demain. Pour garder la liste de toutes les idées proposées par les muséomixeurs, ils ont besoin que vous écriviez la couche de persistance de la base de données qu’ils ont conçu. Les idées sont proposées autour des thèmes identifiés par le musée Départementale de l’Arles Antique. Pour faciliter la compréhension des participants, chaque thème possède une description textuelle.


IDEE(*ID_IDEE*, LIBELLE, ID_THEME#, ID_MUSEOMIXEUR#)

THEME (*ID_THEME*, NOM_THEME, DESCRIPTION)

MUSEOMIXEUR (*ID_MUSEOMIXEUR*, NOM, PRENOM, ADRESSE, CATEGORIE)


Par convention, les clefs primaires sont en italique et les clefs étrangères sont postfixées
par le symbole #.


1. Écrire la déclaration de la classe MuseoMixeur en respectant la convention Java Bean (Constructeur par défaut, setter/getter, equals/hashcode). Il ne vous est demandé que la déclaration, en aucun cas le corps des méthodes.
2. Écrire la déclaration de la classe Idée avec la même convention que la question précédente. Attention de bien penser à  implémenter les liens unidirectionnels qui lient cette classe aux deux autres.
3. Écrire la déclaration de la classe DAOIdée qui implémente l’interface DAO<Idée> (La définition de l’interface vous est donnée page suivante). Dans un premier temps, vous n’implémenterez aucune méthode de cette classe.
4. Implémenter la méthode delete(Idée obj)de la classe DAOIdée.
5. Implémenter la méthode getById(int id) de la classe DAOIdée. Vous supposerez que les classes DAOTheme et DAOMuseoMixeur vous sont fournies.


________________

```java
public interface DAO<T> {
    // Permet la suppression d'un tuple de la base
    public boolean delete(T obj);
    // Permet de récupérer tous les objets d'une table
    public List<T> FindAll();
    // Permet de récupérer un objet via son ID
    public T getById(int id);
    // Permet de créer une entrée dans la base de données par rapport
    // à un objet
    public T insert(T obj);
    // Permet de mettre à jour un tuple dans la base à partir d'un
    // objet passé en paramètre
    public boolean update(T obj);
}
```
