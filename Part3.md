<h1 id="semaine-3">Semaine 3: 😃</h1>
<h2 id="notion">Notion :</h2>
<blockquote>
<ol>
<li>Un attribut de class est <strong> partagé par tous les instance </strong>
de la meme  class on parle aussi d'attribut statique <br></li>
<li>La declaration d'un attribut de class est précédée  du mot clé <strong> static
</strong><br></li>
<li>Il existe meme lorsqu'aucune instance de la class est déclarée<br></li>
<li>Un attribut de class peut etre <strong>privé </strong> ou <strong>public</strong><br></li>
<li>Un attribut de la cass doit etre  explicitement initialisé a l'exterieur de la class
a l'aide du operateur de resolustion du porté</li>
<li>Les attributs de class sont trés pratique différents objet d'une class doivent
accéder à une meme information<br></li>
<li>Ils permet notament d'éviter que cette information soit dupliqué au niveau de
chaque oebjet<br></li>
</ol>
</blockquote>
<h2 id="syntaxe">Syntaxe :</h2>
<pre><code class="language-cpp">class NomClass{
    private / public:
        static type NomAttribut;
};
NomClass::NomAttribut(valeur_initiale);
</code></pre>
<h2 id="exemple">Exemple :</h2>
<pre><code class="language-cpp">class Exemple{
    private:
        static int counter;
        char* texte;
    public:
        Exemple();
};
// initialisation du variable 'counter' a 0:
Exemple::counter(0);
</code></pre>
<h2 id="notion-1">Notion :</h2>
<blockquote>
<p>Similairement , si on ajoute le mot clé static à une method :</p>
<ol>
<li>On peut accéder aussi à la method sans objet , à partir du nom de class
et de l'opetrateur de resolution de portée <strong> &lt;&lt; :: &gt;&gt; </strong><br></li>
<li>Puisqu'une methode de class peut etre appelée sans objet :<br>
2.1.  elles n'ont pas le droit d'utiliser de methode ni d'attribut d'instance
(y compris <strong> this </strong>)<br>
2.2. elle ne peuvent accédé seulement qu'à d'autre   methodes ou attributs de
classe<br>
2.3. Ce sont simplement des fonctions usuelles mise dans une class.</li>
</ol>
</blockquote>
<h2 id="syntaxe-1">Syntaxe  :</h2>
<pre><code class="language-cpp">class NomClass{
    public:
        static type_retoure Nommethode();
};
NomClass::Nommethode();
</code></pre>
<h2 id="notion-2">Notion :</h2>
<blockquote>
<ol>
<li>Un operateur est une operation sur un ou entre deux operande(s) <br></li>
<li>Un appel à un operateur est un appel à une fonction ou une methode spécifique<br></li>
<li><strong>Surcharge</strong> du fonction  : deux fonction ayant le meme nom mais
pas les meme parametres , De la meme facon on va pouvoir écrire plusieur
fonctions pour les opérateurs<br></li>
</ol>
</blockquote>
<h2 id="exemple-1">Exemple :</h2>
<pre><code class="language-cpp">// surcharge du fonction :
int max(int ,int);
double max(double ,double);
// surcharge d'operateur :
Exemple operator+(Exemple , Exemple);
ComplexExemple operator+(ComplexExemple, ComplexExemple);
</code></pre>
<blockquote>
<ol start="4">
<li>Presque tous les operateurs sont surchargables (sauf &lt; :: &gt;, &lt; . &gt;)<br></li>
<li>La surcharge des opérateurs peut etre réalisée : <br>
5.1. soit a <strong>l'exterieur </strong>
de la classe à laquelle il s'appliquent ( fonction ),
<br>
5.2. soit a <strong>l'interieur  </strong>
de la classe à laquelle il s'appliquent ( methode ) <br></li>
</ol>
</blockquote>
<h3 id="surcharge-externe">Surcharge externe :</h3>
<blockquote>
<p>🎉 La surcharge externe est nécessaire pour des opérateurs concernés par une
class , mais pour lesquels la class en question n'est pas l'operande de guache.</p>
</blockquote>
<h2 id="exemple-2">Exemple :</h2>
<pre><code class="language-cpp">// Surcharge externe :
class Exemple{
    private:
        double x;
        double y;
    public:
        Exemple(double x,double y)
        {
            this-&gt;x = x;
            this-&gt;y = y;
        };
        double get_x() const {
            return x;
        };
        double get_y() const {
            return y;
        };
};
const Exemple operator+(Exemple e1, Exemple const&amp; e2)
{
    return Exemple (
        e1.get_x()+e2.get_x(),
        e1.get_y()+e2.get_y()
    );
}
</code></pre>
<blockquote>
<p>Parfois ,il peut etre nécessaire d'autoriser les opérateurs externe d'accéder à
certains éléments  <strong>private</strong> ,dans ce cas ajoutez dans la definition
de la classe, leur prototype précédé du mot clé <strong> firend </strong><br></p>
</blockquote>
<h2 id="syntaxe-2">Syntaxe :</h2>
<pre><code class="language-cpp">friend const Exemple operator+(double , Exemple const&amp;);  
</code></pre>
<blockquote>
<p>Le mot clé <strong> friend </strong> signifié que ces fonctions , bien que ne
faisant pas partie de la classe , peuvent avoir accés aux attributs et méthodes
<strong> private </strong> de la classe .<br>
😉 <strong>les definitions restent hor de la classe (et sans le mot clé friend)
</strong><br>
<br></p>
</blockquote>
<h3 id="surcharge-interne">Surcharge interne :</h3>
<blockquote>
<p>🎉Pour surcharger un opérateur dans une class (surcharge interne ) il faut ajouté
la méthode dans la class <br></p>
</blockquote>
<h2 id="syntaxe-3">Syntaxe :</h2>
<pre><code class="language-cpp">class NomClass{
    type_retour operatorOp(type arg);
};
// implementation operateur de resolution du porté:
NomClass::operatorOp(args){
    //........
}
</code></pre>
