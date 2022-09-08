<h1 id="seamine-4">Seamine 4:</h1>
<h2 id="notion">Notion :</h2>
<blockquote>
<p>L heritage représente la relation <strong> est un </strong> , il permet de créer
des classes plus spécialisées appelée <storng> sous classes </strong> ,à partir
de  classes plus générales appelée <strog> super classes </strong><br>
L'orsqu'une sous-classe  <strong>c1</strong> est créée a partir d'une super
class <strong>c</strong> , un c1 est aussi un c<br>
<strong> 😉 <em>L'enrichissement</em> : </strong> des attributs (ou/et) des méthodes
suplémentaires peuvent etre définis par la sous class c1<br>
<strong> 😉 <em>spécialisation</em>  : </strong>  des méthoes héritées de c peuvent
etre redéfinies en c1<br>
l'accés <strong>protégé</strong> assure la visibilité des membres d'une classe dans les classes
de sa desendance <br>
<strong>L'heritage </strong> permet donc: <br>
1. d'expléciter les relations structurelles et sémantique entre classes<br>
2. de reduire les redondances de description et de stockage des propriétés<br>
⚠️ <em>il ne doit jamais décrire une relation <strong>a-un </strong></em> <br></p>
</blockquote>
<h2 id="syntaxe">Syntaxe :</h2>
<pre><code class="language-cpp">class NomSousClass : public NomSuperClass{
    // class body
};
</code></pre>
<h2 id="notion-1">Notion :</h2>
<blockquote>
<p><strong>Masquage</strong> : un identificateur qui en cache un autre<br></p>
<ol>
<li>Meme nom d'attribut ou du méthode utilisé sur plusieurs niveaux<br></li>
<li>Peu courant pour les attributs</li>
<li>Trés courant et pratique pour les méthodes <br></li>
</ol>
</blockquote>
<h2 id="notion-2">Notion :</h2>
<blockquote>
<p>lors de l'instanciation d'une sous classe il faut initialiser :<br>
1. les attributs <em>propres à la sous classe</em><br>
2. les attrinuts <em>hérités des super-classes</em> <br>
⚠️ Mais  il ne doit pas etre à la charge du concepteur des sous-classes
de réaliser lui meme <em>l'initialisation des attributs hérités</em> <br>
🙌  l'initialisation des attributs hérités doit donc se faire en
invoquant <strong><em>les constructeurs</em></strong> des super-classes 😉<br>
l'invocation du constructeur de la super classe se fait au début de la section
d'appel aux constructeurs des attributs.<br></p>
</blockquote>
<h2 id="syntaxe-1">Syntaxe :</h2>
<pre><code class="language-cpp">SousClass(liste_parametres)
: SuperClass(argument),
attribut1(valeur),
.....
attributN(valeur)
{
    // instructions 
}
</code></pre>
<blockquote>
<p>Lorsque la super-classe admet un constructeur par defaut , l'invocation explicite
de se constructeur dans la sous-classe n'est pas obligatoire<br>
👉 le compilateur se charge de réaliser l'invocation du constructeur
par defaut<br>
💁 si l'on oublie l'appel à un constructeur du super classe<br>
1. Appel automatique au constructeur par défaut de la super classe<br><br />
2. Pratique parfois mais erreur si le constructeur par defaut n'existe pas <br><br>
👉 pour éviter des problémes avec les hiarchies de classes , dans un
premier temps:<br>
1. <em>Toujours déclarer au mois un constructeur</em> <br>
2. <em>Toujours faire l'appel à un constructeur de super-classe</em><br></p>
</blockquote>
