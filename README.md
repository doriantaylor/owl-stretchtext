<div about="#" typeof="owl:Ontology">

Author  
<a href="http://doriantaylor.com/person/dorian-taylor#me"
rel="external dct:creator"><span property="foaf:name">Dorian
Taylor</span></a>

Created  
August 23, 2023

Namespace URI  
<https://vocab.methodandstructure.com/stretchtext#>

Preferred Namespace Prefix  
stv

<span property="rdfs:comment dct:description">This document is an
attempt to define a reasonably robust and portable description of
stretchtext.</span> <a href="https://en.wikipedia.org/wiki/StretchText"
property="dct:references">Stretchtext</a> is a relatively little-used
hypermedia technique for managing levels of *detail*. Successive levels
of detail in a text can be recursively hidden under lower-detail text,
subject to user activation.

</div>

<div class="section">

## Classes

At this time, there is only the single class,
[`StretchText`](https://vocab.methodandstructure.com/stretchtext#StretchText).

<div id="StretchText" class="section" about="[stv:StretchText]"
typeof="owl:Class">

### `StretchText`

This class represents an addressable unit of stretchtext.

Properties:  
<a href="https://vocab.methodandstructure.com/stretchtext#initial"
rev="rdfs:domain"><code>initial</code></a>

<a href="https://vocab.methodandstructure.com/stretchtext#replace-with"
rev="rdfs:domain"><code>replace-with</code></a>

<a href="https://vocab.methodandstructure.com/stretchtext#append"
rev="rdfs:domain"><code>append</code></a>

<a href="https://vocab.methodandstructure.com/stretchtext#prepend"
rev="rdfs:domain"><code>prepend</code></a>

<a href="https://vocab.methodandstructure.com/stretchtext#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div class="section">

## Properties

<div id="initial" class="section" about="[stv:initial]"
typeof="owl:ObjectProperty owl:FunctionalProperty">

### `initial`

This property denotes the initial value of a run of stretchtext.

Domain:  
<a href="https://vocab.methodandstructure.com/stretchtext#StretchText"
rel="rdfs:domain"><code>stv:StretchText</code></a>

Cardinality:  
1

<a href="https://vocab.methodandstructure.com/stretchtext#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="replace-with" class="section" about="[stv:replace-with]"
typeof="owl:ObjectProperty">

### `replace-with`

When the subject stretchtext is activated, replace the initial value
with the object.

Domain:  
<a href="https://vocab.methodandstructure.com/stretchtext#StretchText"
rel="rdfs:domain"><code>stv:StretchText</code></a>

<a href="https://vocab.methodandstructure.com/stretchtext#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="append" class="section" about="[stv:append]"
typeof="owl:ObjectProperty">

### `append`

When the subject stretchtext is activated, put the object *after* the
initial value (or its replacement).

Domain:  
<a href="https://vocab.methodandstructure.com/stretchtext#StretchText"
rel="rdfs:domain"><code>stv:StretchText</code></a>

<a href="https://vocab.methodandstructure.com/stretchtext#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="prepend" class="section" about="[stv:prepend]"
typeof="owl:ObjectProperty">

### `prepend`

When the subject stretchtext is activated, put the object *before* the
initial value (or its replacement).

Domain:  
<a href="https://vocab.methodandstructure.com/stretchtext#StretchText"
rel="rdfs:domain"><code>stv:StretchText</code></a>

<a href="https://vocab.methodandstructure.com/stretchtext#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>
