---
tags:
    - teaching 
    - c
hide:
    - navigation
---

# TD3


## Variables impératives, structure de contrôle <i>if</i> et l'itération `for`

<h3>Expressions</h3>
<p>Il s'agir ici de regarder la <code>priorité</code> des opérations à effectuer. De manière générale, s'il n'y a pas d'ambiguïté, les parenthèses peuvent être enlevées.</p>
<ul class="tips">
  <li>Les opérations arithmétiques priment par rapport à l'affectation : l'expression à droite du <code>=</code> est d'abord évaluée avant de l'assigner à la variable <code>a</code>.</li>
  <li>La multiplication <code>*</code> prime par rapport à l'addition <code>+</code>.</li>
  <li>La division <code>/</code> prime par rapport à l'addition <code>+</code>.</li>
  <li>L'incrémentation <code>++</code> prime par rapport à la multiplication <code>*</code> qui lui par la suite par rapport à l'addition <code>+</code>.</li>
</ul>
<p>On fait la remarque suivante par rapport à la division <code>/</code> qui est ici une division entière : si <code>x</code> et <code>y</code> sont tous les deux des entiers, alors la division <code>x/y</code> est une <strong>division entière ou division euclidienne</strong> (plus de détails <a href="https://fr.wikipedia.org/wiki/Division_euclidienne">ici</a>). Le résultat admis est le <code>quotient euclidien</code>. Du coup ici, si <code>x = 3</code> et <code>y = 5</code>, le résultat de la division <code>x/y</code> vaut <code>0</code>.</p>

<p>À vous de jouer.</p>

<h3>Execution conditionnelle d'instructions : <i>if</i></h3>
<p>En programmation impérative, les instructions sont executées ligne par ligne et les unes à la suite des autres. On peut cependant <code>conditionner</code> l'execution d'une certaine instruction ou d'un certain <code>bloc d'instructions</code> (en C, les blocs d'instructions sont tout simplement une suite d'instructions délimitée par des accolades <code>{ }</code>). C'est-à-dire que si une certaine condition est vérifiée, on choisira d'executer un bloc plutôt qu'un autre. La <code>structure de contrôle if</code> permet de faire cela.</p>
<p>Voyons cela de plus près avec notre exercice.</p>

```
Algorithme                               En C
----------                               ----
debut:                                   int main() {
  age = 19                                  int age = 19;
  si (age >= 18) alors:                     if (age >= 18) {
    afficher "vous êtes majeur"               printf("vous êtes majeur\n");
  sinon:                                    } else {
    afficher "vous êtes mineur"               printf("vous êtes mineur\n");
  fin si                                    }
:fin                                        return EXIT_SUCCESS;
                                          }
```

!!! tip
    - Ici, si la <code>age >= 18</code> est vérifiée, on affichera <code>"vous êtes majeur"</code> et dans le cas contraire, on affichera <code>"vous êtes mineur"</code>.
    - La condition du <code>if</code> a une valeur <code>booléenne</code>, c'ets-à-dire vrai ou faux.
    - Dans la condition d'un <code>if</code> pour vérifier l'égalité de deux valeur on utilise l'opérateur <code>==</code>.
    - On peut combiner plusieurs conditions en utilisant les opérateurs logiques <code>ET : &&</code>, <code>OU : ||</code> et la <code>NEGATION : !</code>
    - Il est possible d'<code>imbriquer des if</code> : mettre un <code>if</code> dans le bloc d'un autre <code>if</code>.

<h3>Itération : l'instrucion <i>for</i></h3>
<p>On voudrait maintenant pouvoir répéter un bloc d'instructions, ou en d'autres termes répéter un certain nombre de fois les mêmes instruction. Pour cela, on utilise des <code>boucles</code>. Par exemple pour afficher 5 fois le mot "Bonjour", on mettra l'instruction <code>printf("Bonjour\n");</code> à l'intérieur d'une boucle <code>for</code>.</p>
<p><code>Une itération</code> correspond à <code>une execution</code>, d'un bloc d'instruction dans une boucle : si l'on veut répéter 5 fois, on aura 5 itérations.</p>

!!! tip
    - On utilise une variable de boucle pour compter le nombre d'itération à effectuer. On nomme souvent cette variable <code>i</code>, mais n'importe quel identificateur marche bien évidement.
    - Très souvent la première itération est l'<code>itération 0</code>, càd <code>i = 0</code>.
    - À la fin de chaque itération, on va donc <code>incrémenter</code> notre variable de boucle : <code>i++</code> ou <code>i = i + 1</code>.
    - Pour ne pas boucler indéfiniment, il nous faut spécifier une condition d'arret. Dans notre exemple si l'on veut 5 itérations, on arrêtera de boucler (on sortira de la boucle) dès que <code>i >= 5</code>. On peut également dire que l'on restera dans la boucle tant que <code>i < 5</code>.


<p>Voyons alors comment utiliser la boucle <code>for</code> avec tout ce que l'on a appris. Le principe du l'exercice du TD est exactement le même ;).</p>

```c
// debut du programme...
int i; // On déclare notre variable de boucle
for (i = 0; i < 5; i++) {
  printf("Bonjour\n");
}
printf("A la fin de la boucle i vaut %d\n", i);
// suite du programme...
```

<p>Ainsi, on est maintenant capable d'expliquer chaque argument de la boucle <code>for</code>.</p>

!!! note
    - Le premier argument <code>i = 0</code> permet d'initialiser notre variable de boucle.
    - Le deuxième argument <code>i < 5</code> est une expression booléenne qui indique que si cette condition est vraie, on reste dans la boucle et on continue avec une nouvelle itération. Sinon on sort de la boucle et on continue l'execution du programme directement après notre boucle (ici à la ligne <code>17</code>)
    - Le dernier argument <code>i++</code> sert à incrémenter notre variable de boucle : on passe à l'itération numéro <code>i+1</code>. On va considérer que cette instrucion est executée en dernier dans le bloc de notre boucle càd à la ligne <code>16</code>.

<h5>Trace du programme</h5>

```
lignes | i | Affichage (sortie écran)
-------------------------------------
13     | ? |
14     | 0 |
15     |   | Bonjour
16     | 1 |
15     |   | Bonjour
16     | 2 |
15     |   | Bonjour
16     | 3 |
15     |   | Bonjour
16     | 4 |
15     |   | Bonjour
16     | 5 |
17     |   | A la fin de la boucle i vaut 5
```

<p>Quand <code>i</code> vaudra <code>5</code>, la condition d'arret <code>i < 5</code> n'est plus vérifiée du coup on sort alors de notre boucle, et la valeur de <code>i</code> à la sortie est donc <code>5</code>.</p>

<ul class="tips">
  <li>On peut évidement initialiser la variable de boucle à <code>1</code>.</li>
  <li>On peut également avoir un <code>pas d'incrémentation</code> quelconque. Càd on peut incrémenter la variable de boucle de <code>2, 3, ...</code> selon notre convenance : dans ce cas on écrira dans le troisième argument du <code>for</code> soit <code>i = i + 2</code> ou <code>i = i + 3</code> etc.</li>
  <li>On peut aussi imbriquer des boucles <code>for</code>. Cependant il faudra bien faire attention à bien initialiser et incrémenter chaque variable de boucle.</li>
</ul>

<p>Pour le reste ce sera à vous de jouer :).</p>
