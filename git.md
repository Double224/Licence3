		Ci-dessous j'explique les commande de git
Git est un DVCS libre		
git init: initialise un depôt
git config --list affiche la configuration courante
git add : ajoute le fichier à l'index. c-à-d indexé le fichier
git diff affiche le détail des changements sur les fichiers
git status: permet de voir les modifications apportées aux fichiers du repertoire git
git log: permet de voir les series de commit éffectués (l'historique des modifs)
git commit valide le contenu de l’index
git commit -a -m: permet rajouté tous les fichiers se trouvant déjà dans l'index s'ils ont des modifications
git checkout id_commit(sha): permet de se positionner sur un commit 
	specifié(pour revenir au commit le plus recent on utilise git checkout "master")
git commit --amend -m "Votre nouveau message": 
	permet de modifier le message du dernier commit s'il n'est pas pushé 
git reset --hard‌:permet d'annuler une modification non commité
git pull: permet de récupérer une modification faite depuis un autre ordinateur ou un remote
git branch "nom de la branche" : permet de créer une branchhe
git merge "nom de la branche" : 
	permet de fusionner la branche courante à celle indiqué sur la ligne de commande;
git blame : permet de voir plus rapidement qui a fait un commit et à quel niveau et pourquoi
git show "SHA(id_commit)": permet de voir exactement le contenu d'un commit
.gitignore : permet d'ignorer des fichiers 
git stash : permet de mettre un travail en attente pour y revenir après
git stash pop: permet de récuperer un travail mis en attente
git fetch récupère les révisions des dépôts référencés
git pull récupère les révisions et les fusionne
Pour participer à un projet open source, il faut forker et le cloner sur son machine local

				PARTIE MAVEN:
Dans ce chapitre, j'ai survolé rapidement la gestion de projet Java avec Apache Maven.

Voici les choses importantes à retenir :

Maven utilise une approche « convention over configuration »
 (ou convention plutôt que configuration en français).
L'arborescence d'un projet Maven est fixée par convention. 
Elle comporte :
un fichier pom.xml à la racine qui sert à décrire et configurer le projet Maven ;
un répertoire src/main/java contenant les sources de l'application ;
un répertoire src/test/java contenant les sources des tests JUnit de l'application.
Pour créer un nouveau projet Maven, vous pouvez générer l'arborescence en utilisant 
un archétype grâce à la commande mvn archetype:generate.
Compilez votre projet, exécutez les tests et construisez un JAR de 
votre application en une seule commande : mvn package. Si la 
compilation et tous les tests passent sans encombre, un fichier
 target/<artifactId>-<version>.<packaging> est généré 
 (soit target/mon-appli-1.0-SNAPSHOT.jar dans mon exemple).
Dans les chapitres suivants, je vais entrer plus dans le détail 
du fonctionnement et de la configuration de Maven.

					JUNIT:
Création d’une classe de test
Ne nécessite aucun traitement particulier
— Il faut juste importer les packages de JUnit
— En général, les assertions sont importées en static
import org . j u n i t . ∗ ;
import s t a t i c org . j u n i t . A s s e r t . ∗ ;
public class
// . . .
}
UneClasseDeTest {

Écrire un cas de test
— La méthode représentant le cas de test doit être annotée avec org.junit.Test
— Elle contient en général
— une initialisation,
— l’appel de la méthode à tester
— des assertions pour vérifier les résultats
@Test
public void t e s t E m p t y C o l l e c t i o n () {
C o l l e c t i o n <O b j e c t > c o l l e c t i o n = new A r r a y L i s t <O b j e c t >() ;
a s s e r t T r u e ( c o l l e c t i o n . isEmpty ( ) ) ;
}

Qu’est-ce qu’une assertion ?
— Une assertion est une expression booléenne exprimant une propriété sémantique (prédicat)

Intérêt des assertions
— Une assertion permet de vérifier que ce que l’on croit « trivialement vrai » reste actuellement
vrai

assertArrayEquals égalité de deux tableaux
assertEquals égalité de deux éléments
assertFalse condition fausse
assertNotNull référence non null
assertNotSame identité de deux références
assertNull référence null
assertSame identité de deux références
assertThat vérifie une condition précisée par une instance de Matcher
assertTrue condition vraie
fail échec du test

Initialisation des tests :Les initialisations communes à des cas de tests se font dans le test fixture
@Before
public void setUp ( ) {
c o l l e c t i o n = new A r r a y L i s t <O b j e c t >() ;
}

Tests et exception
— Une exception attendue peut être spécifiée avec l’attribut expected de l’annotation Test (dans
ce cas, le test passe)
@Test ( e x p e c t e d=I n d e x O u t O f B o u n d s E x c e p t i o n . c l a s s )
public void testIndexOutOfBoundsException () {
A r r a y L i s t <O b j e c t > e m p t y L i s t = new A r r a y L i s t <O b j e c t >() ;
Object o = emptyList . get (0) ;
}

