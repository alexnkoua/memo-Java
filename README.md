# Memo-Java




Le Kit de développement Java (jdk) contient le compilateur ainsi que l'environnement d'exécution (JRE).
 La JRE contient uniquement la JVM (Java Virtual Machine) qui prend en charge l'exécution uniquement.
Le fichier .class est obtenu après la compilation du fichier source java. Il contient le bytecode qui est exécuté  par la machine virtuelle (JVM).




## Les différents types de variables
* nombre entiers  byte ( 1 octet / 8 bit  ), short ( 2 octet / 16 bit ), int (4 octet / 32 bit), long ( 8 octet /64 bit) ; long double (  128octet / 16 bit)
* nombres décimaux float (  4 octet / 32 bit )  et  double( 8octet /  64 bit) 
* chaînes de caractères char(1 octet /  8 bit ), String
* boolean ( 1 bit)

Une valeur entiere (int) est d’abord considerer par Java comme un Int jusqu’au cast ==> long force = 99999999999L;
Une valeur décimal (float)est d’abord considerer par Java comme un double jusqu’au cast ==> float prix = 1.45f;

Pour déclarer un variable avec var faut l’initialiser directement ==> var age = 30;



Nombres Décimaux
Pour une précision jusqu'à 7 décimales après la virgule, vous pouvez utiliser  float.  Au-delà, ce sera  double.
La plupart du temps, quand vous développez un programme, vous ne contrôlez pas forcément la précision des variables que vous aurez à traiter. C'est pourquoi, en pratique, vous constaterez que la plupart des programmeurs Java utilisent le type  double.



Mélangez des types numériques ( le  Cast)
Pour utiliser en même temps des nombres de types différents dans les opérations, utilisez  le cast pour qu'ils se comportent comme le type nécessaire ;

int a = 10;
int b = 4;
double c = a(double)/ b;   //-> c contient 2.5, car la valeur de b est transformée en double


## Les constantes
L'utilisation de constantes est utile pour deux raisons :
1. Elles permettent aux programmes d'être plus rapides. L'ordinateur sait combien d'espace une constante prend. 
2. Pour vérifiez que certaines valeurs ne changent pas, intentionnellement ou par accident. 
3.  Le nom d’une constante en Java est toujours en majuscules : cela permet de mieux les reconnaître
final int NUMBEROFWEEKDAYS = 7;
final String MYFAVOURITEFOOD = "Icecream";


## Porter des variables
Chaque variable n'est disponible (et accessible) que dans le contexte dans lequel elle a été déclarée.
La portée d'une variable peut être locale ou globale, en fonction de l'endroit où la variable est déclarée



## Écrivez un code plus court avec des opérateurs d'affectation raccourcis
// Version d'affectation normale
	savings = savings + 100;
// Version raccourcie d'affectation
	savings += 100;
Les autres variantes courtes sont :
* +=  addition ;
* -=  soustraction ;
* *=  multiplication ;
* /=  division.


## Concatenation et Formatage chaine de caractères
### Concatenation
L’opérateur ‘ + ‘ permet de concaténer des caractères  ou additionner  un nombre  mais c’est le premier élément devant le premier + qui conditionne son 
utilisation,  si c’est un nombre il additionne sinon il concatène tous les éléments.
‘ ’ ==> correspond à un caractère.
" " ==> correspond à string.

String debut = " Au commencement ";
String fin = "j'y étais. ";
System.out.println(debut + fin);   // Au commencement j'y étais.

 —> Il est recommender de concatener 2 éléments aux maximums pour des raisons de performances à chaque ‘+ ‘ java crée un chaine de caractères intermédiaires en mémoire qui est l’addition de deux ancienne chaine . (Vrai pour les anciennes version  java, aujourd’hui le compilateur optimise tout.)

—> L’autre problème est la lisibilité, plus il ya des ‘+’ moins il ya de lisibilité d’ou la préférence aux chaines formaté printF .

### Formater chaine de caractère 
Avec printF on à une seule chaine de caractères et on peut rajouter des variable à la volé ( %+type variable ) que l’on déclare à la fin de la chaine de caractère.
%s ==> type chaine de caractères
%d ==> variable de type entier
%b ==> type flottant
%b ==> booléen

int age = 18;
System.out.printf(" Mon age est %d ans",age);


## Opérateur d’incrémentation ou décrémentation
++ (double + pour incrémenter une variable de 1)
—   (double - pour décrémenter une variable de 1)
La position de cette opérateur à une importance dans les priorité d’éxécution de l’instruction.
Si ++ ou — est après le nom de variable, le égal (=) va prendre la priorité sur le signe. (l’addition ou la soustraction se fait après l’affectation)

Opérateur de comparaison ou Opérateur Relationel 
IL s’agit d’évaluer si les choses sont supérieures (>), inférieur (<), égal (==), différente ( !=) , supérieures ou égales  (>=), inférieur ou égales  (<=)
Ce sont des opérateurs qui donne un résultat booléen
Ils nous permettent de comparer uniquement les valeurs primitifs.


## Opérateur Logique
Ces opérateurs vous permettent de combiner des valeurs booléennes : soit des valeurs booléennes spécifiques, soit des résultats d'expressions. Ils sont au nombre de trois

( & ) ET logique ( Porte logique AND Le résultat n'est vrai que si toutes les parties participantes sont vraies Mais si une partie est false le résultat sera faux.  Pour des raisons  de performances il s’écrit deux fois. Sinon il évalue tout ce qui se trouve a gauche et droite de l’opérateur dans toute les situations)
(&&) ET logique(le résultat est vrai si au moins une des parties participantes est vrai et inversement )

( | )  OU inclusif  (Porte logique  OR  Le résultat est Vrai si l’un des booléen est Vrai…. Pour des raisons  de performances il s’écrit deux fois. Sinon il évalue tout ce qui se trouve a gauche et droite de l’opérateur dans toute les situations ) 
( || ) OU inclusif (…… Le résultat est vrai si au moins une des parties participantes est vraie mais plus besoin de tester le deuxième )
( ^ ) OU exclusif (Porte logique XOR la combinaison de 2 vrai est égal à false)

( ! )  NON ( Porte logique NOT Il inverse simplement l'expression donnée. Se met devant le nom de variables. Se combine avec les autres opérateurs…… !expression1  est vrai si   expression1  est fausse)


## Condition Ternaire
	System.out.println(ageDuCaptaine > 35 ? "l'age du captaine est "+ageDuCaptaine : "cas contraire");