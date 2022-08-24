<h1 id="semaine-2">Semaine 2 😃</h1>
<h2 id="notion">Notion :</h2>
<blockquote>
<p><strong> Les constructeurs </strong>  est une methode :</br></p>
<ol>
<li>invoqué automatiquement lors de la declaration d un objet</li>
<li>chargé d'effectuer toutes les opérations requises en <strong>debut de vie
de l'objet </strong> (dont l'initialisation des attributs)</li>
<li>pas de type de retour</li>
<li>meme nom que la class</li>
<li>comme les autre methodes <strong>les constructeurs</strong> peuvent
etre <strong>surchargés</strong></li>
</ol>
</blockquote>
<h2 id="exemple">Exemple :</h2>
<pre><code class="language-cpp">class Exemple{
    int attribute1;
    int attribute2;
    Exemple(int attr1,int attr2){
        attribute1 = attr1;
        attribute2 = attr2;
    }
};
</code></pre>
<h2 id="notion-1">Notion:</h2>
<blockquote>
<p><strong>Un constructeur</strong> devrait normalement contenir une section d'appel
aux constructeurs des attributs de type objet , ainsi que l'initialisation des
attributs de type de base. <br>
C est ce qu'on appelle <strong>la liste d'initialisation du constructeur</strong>
<br></p>
</blockquote>
<pre><code class="language-cpp">NomClass::NomClass(liste_parametre):
attr1(),//appel au constructeur de attribut1
.
.
attrN()//appel au constructeur de attributN
{
// autres Operations
}
</code></pre>
<h2 id="exemple-1">Exemple :</h2>
<pre><code class="language-cpp">class Color{
    int id;
    char* name;
    Color(int id,char* name);
    // ........
};
class Point{
    int x;
    int y;
    int z;
    int id;
    Point(int x,int y,int z,int id);
    //...................
};
class ExempleComplex{
    int id;
    Point Exemeple_point;
    Color Exemple_color;
    ExempleComplex(
        int id,
        int x,
        int y,
        int z,
        int id_point,
        int id_color,
        char* color
    );
};
ExempleComplex::ExempleComplex(
        int id,
        int x,
        int y,
        int z,
        int id_point,
        int id_color,
        char* color
):Point(id_point,x,y,z),Color(id_color,color){
    this-&gt;id = id;
}
</code></pre>
<blockquote>
<p>😉 Cette section introduit par <strong>:</strong>  est optionnelle mais <strong>
recommandé </strong>.</p>
</blockquote>
<h2 id="notion-2">Notion :</h2>
<blockquote>
<p><strong>Un constructeur par defaut </strong> est un constructeur qui <strong>
n'a pas du parametre </strong> ou dont tous les parametres ont des valeurs par
defaut <br>
Si aucun constructeur n'est spécifié,le compilateur génére automatiquement
une <strong>version minimale</strong> du constructeur par defaut
qui s'appelle le constructeur par defaut par defaut qui : <br>
1. appelle le constructeur par defaut des attributs objet<br>
2. laisser <strong>non-initialisés</strong> les attributs de type de base<br></p>
</blockquote>
<hr />
<blockquote>
<p>😭  Dés qu' au moins un constructeur a ete spécifié , ce constructeur par defaut
par defaut n'est plus fourni.<br>
😉 Mais si l'on veut quand meme avoir un constructeur par défaut par défaut
,on peut <strong>re-demander</strong> en écrivant dans la definition de la
class <strong> NomClass() = default </strong><br></p>
</blockquote>
<h2 id="exemple-2">Exemple :</h2>
<pre><code class="language-cpp">class Exemple{
    // attributs 
    Exemple() = default;
    Exemple(// args );
};
</code></pre>
<hr />
