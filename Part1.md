<h1 id="semaine-1">Semaine 1 😃</h1>
<h2 id="notion">Notion :</h2>
<blockquote>
<p><strong> La programmation orionté objet </strong> utilise le concept <strong>portée de la
classe &lt; : &gt;</strong> ce qui signifie que les attribute de la Class sont
Connut on touts la classe</p>
</blockquote>
<h2 id="exemple">Exemple :</h2>
<pre><code class="language-cpp">class Exemple{
    int attribute1;
    int attribute2;
    void display(){
        printf(&quot;%d&quot;,attribute1);
        /*attribute 1 est connut on touts les methods du class 
        Exemple*/
        return;
    };
};
</code></pre>
<h2 id="notion-1">Notion:</h2>
<blockquote>
<p>Pour une meilleure <strong>lisibilité</strong> et <strong>modularité</strong> du code il est possible d'écrire
les définitions des méthodes a l'extérieur de la déclaration de la classe, pour
relier la définition d'une méthode à la Class pour le quelle elle est définie
il suffit d'utiliser l'opérateur de <strong> la résolution de portée </strong> (opérateur ::)</p>
</blockquote>
<h2 id="exemple-1">Exemple :</h2>
<pre><code class="language-cpp">class Exemple{
    int attribute1;
    int attribute2;
    void display();
};
void Exemple::display(){
    printf(&quot;%d&quot;,attribute1);
    return;
}
</code></pre>
<h2 id="notion-2">Notion :</h2>
<blockquote>
<p>les méthodes d'une classe peuvent distinguer aux 2 types :</p>
<ol>
<li>Méthodes qui peuvent modifier l'état  de l'objet : <strong>action</strong></li>
<li>Méthodes qui ne changent rien à l'objet : <strong>prédicats</strong>
<br> <strong>Pour une méthode prédicat il faut ajouter le mot-clé &ldquo;const&rdquo;
après la liste des paramètres de la fonction </strong></li>
</ol>
</blockquote>
<h2 id="exemple-2">Exemple :</h2>
<pre><code class="language-cpp">class Exemple{
    int attribute1;
    int attribute2;
    void display() const;
    void setattr1(int replace);
};
// display est une predicat 
void Exemple::display() const{
    printf(&quot;%d&quot;,attribute1);
    return;
}
// setattr1 est une action
void Exemple::setattr1(int replace){
    attribute1 = replace;
    return;
}
</code></pre>
<h2 id="notion-3">Notion :</h2>
<blockquote>
<p><strong>Le masquage</strong> : un identificateur cache un autre identificateur par exemple
dans le cas suivant :<br></p>
</blockquote>
<pre><code class="language-cpp">void Exemple::setattr2(int attribute2)
{ 
    attribute2 = attribute2;
    return;
}
</code></pre>
<blockquote>
<p>Dans ce cas en a un <strong>masquage</strong> car la variable attribute2 signifiée à la fois
l'attribut de la Class et la variable passer en  paramètres<br />
L'utilisation du pointeur <strong>this</strong>(un pointeur sur l'instance courant) est obligatoire en cas de masquage.</p>
</blockquote>
<h2 id="exemple-3">Exemple :</h2>
<pre><code class="language-cpp">class Exemple{
    int attribute1;
    int attribute2;
    void display() const;
    void setattr1(int replace);
    void setattr2(int attribute2);
};
void Exemple::display() const{
    printf(&quot;%d&quot;,attribute1);
    return;
}
void Exemple::setattr1(int replace){
    attribute1 = replace;
    return;
}
void Exemple::setattr2(int attribute2){
    this-&gt;attribute2 = attribute2;
    return;
}
</code></pre>
<hr />
