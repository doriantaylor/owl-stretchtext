## An Agent Certification Ontology

<div about="#" typeof="owl:Ontology bibo:Webpage">

  - Author  
    [<span property="foaf:name">Dorian
    Taylor</span>](http://doriantaylor.com/person/dorian-taylor#me)
  - Created  
    January 23, 2014
  - Namespace URI  
    <https://vocab.methodandstructure.com/certification#>
  - Preferred Namespace Prefix  
    acrt

This document specifies a vocabulary for asserting the existence of
official endorsements or certifications of *agents*, such as people and
organizations.

While there are plenty of linked data vocabularies for [expressing
licensing rights](http://creativecommons.org/ns) on intellectual
property, as well as those for [cryptographic
certificates](http://www.w3.org/ns/auth/cert), as *well* as [methods of
referencing catalogues](http://www.w3.org/TR/vocab-adms/) *of* private
and government certifications, *as **well*** as ways of [expressing the
*privileges*](http://www.w3.org/community/odrl/two/model/) of
certifications, there appears to be no other concise way to say
something like the following:

> I have been granted a passport, by the government of Canada, with the
> number XY123456, issued on October 16, 2010, which expires on October
> 16, 2015.

Here is the same assertion expressed in
[Turtle](http://www.w3.org/TR/turtle/) using the proposed vocabulary:

> 
> 
>     <http://doriantaylor.com/data/passport> a acrt:Certification;
>         acrt:qualification <http://dbpedia.org/page/Category:Passports>;
>         acrt:authority <http://www.ppt.gc.ca/>;
>         acrt:principal <http://doriantaylor.com/person/dorian-taylor#me>;
>         # (never do this for real, at least for public consumption)
>         acrt:proof <http://doriantaylor.com/file/my-passport.jpeg>;
>         dct:coverage <http://dbpedia.org/page/Canada>;
>         dct:identifier "XY123456"^^xsd:string;
>         dct:issued "2010-10-16"^^xsd:date;
>         dct:valid "2015-10-16"^^xsd:date .

Note that this assertion says only in *informal* terms what the
certification is, and what it allows me to do. This vocabulary is
intended neither to describe the privileges granted by the
certification, nor to describe the artifact that embodies the
certification. It simply connects the subject of the certification to
the issuing authority and their official serial number of the account.

I chose a passport for the example because it is about as banal as a
certification gets: it merely certifies that I am who I say I am and
that I am a Canadian citizen. This vocabulary could be used equally for
drivers' licenses, business licenses, fishing licenses, dog licenses,
etc., as it is intended only to encode and store a hint that such
certification exists. It is also intended to be used for encoding
achievements, awards, academic degrees, and public and private training
certificates. It even could be used to convey information about
reputation points on social networks or services like [Mozilla Open
Badges](http://openbadges.org/).

The purpose of this vocabulary is record-keeping and exchange, and
likewise is its application context. The actual vetting mechanisms of
the certifications in question are out of scope.

</div>

<div>

## Classes

At this time, there is only the single class,
[Certification](https://vocab.methodandstructure.com/certification#Certification).

<div id="Certification" about="[acrt:Certification]" typeof="owl:Class">

#### Certification

This class represents the abstract notion of certification, of an agent,
by another agent, that the first agent possesses some property or set of
properties implied by the certification, potentially within some
spatiotemporal scope, and which may or may not be designated by some
identifier.

  - Examples:
    
      - The issuance of a government-regulated privilege, e.g. driver's
        license
      - The issuance of an academic degree to a particular person
      - An officially-recognized trade qualification, e.g. a welding
        ticket
      - A mandatory professional status, e.g. bar association membership
      - A private certification of achievement, e.g. CISSP
      - An errors and omissions insurance policy
      - A pet license, where the principal is an animal
      - The notarization of an affadavit
      - An award (e.g. 2014 Nobel Prize in physics)
      - Anything that resembles some entity underwriting some attribute,
        privilege, skill, achievement, or claim of some other entity.

[Back to Top](https://vocab.methodandstructure.com/certification#)

</div>

</div>

<div>

## Properties

Many of the requirements of this vocabulary can be achieved with [Dublin
Core terms](http://dublincore.org/documents/dcmi-terms/).

  - For the jurisdiction, use
    [dct:coverage](http://purl.org/dc/terms/coverage)
  - For the license number, use
    [dct:identifier](http://purl.org/dc/terms/identifier)
  - For the issue date, use
    [dct:issued](http://purl.org/dc/terms/issued)
  - For the expiry date, use [dct:valid](http://purl.org/dc/terms/valid)

What follows are terms peculiar to certification itself.

<div id="qualification" about="[acrt:qualification]" typeof="owl:ObjectProperty">

#### qualification

This property specifies what achievement, skill, or fact is being
certified.

> The range of this term is left open, but should probably reference
> something abstract like a skos:Concept, an org:Role (itself a subclass
> of skos:Concept), or a skill, such as modeled by the Cognitive
> Characteristics Ontology.

  - Domain:  
    [acrt:Certification](https://vocab.methodandstructure.com/certification#Certification)
  - See also:  
    [skos:Concept](http://www.w3.org/2004/02/skos/core#Concept)
    [org:Role](http://www.w3.org/TR/vocab-org/#org:Role)
    [The Cognitive Characteristics
    Ontology](http://smiy.sourceforge.net/cco/spec/cognitivecharacteristics.html)

[Back to Top](https://vocab.methodandstructure.com/certification#)

</div>

<div id="principal" about="[acrt:principal]" typeof="owl:ObjectProperty">

#### principal

This property specifies who or what agent is being certified.

> The principal of the certification can be any agent, like a person,
> company, animal, AI, whatever.

  - Domain:  
    [acrt:Certification](https://vocab.methodandstructure.com/certification#Certification)
  - Range:  
    [foaf:Agent](http://xmlns.com/foaf/0.1/Agent)
  - Inverse of:  
    [acrt:has-certification](https://vocab.methodandstructure.com/certification#has-certification)

[Back to Top](https://vocab.methodandstructure.com/certification#)

</div>

<div id="has-certification" about="[acrt:has-certification]" typeof="owl:ObjectProperty">

#### has-certification

This property specifies that an agent possesses a given certification.

  - Domain:  
    [foaf:Agent](http://xmlns.com/foaf/0.1/Agent)
  - Range:  
    [acrt:Certification](https://vocab.methodandstructure.com/certification#Certification)
  - Inverse of:  
    [acrt:principal](https://vocab.methodandstructure.com/certification#principal)

[Back to Top](https://vocab.methodandstructure.com/certification#)

</div>

<div id="authority" about="[acrt:authority]" typeof="owl:ObjectProperty owl:FunctionalProperty">

#### authority

This property specifies who (or what) is doing the certifying.

> The issuing authority can, once again, be a person, business,
> institution, or any other kind of agent.

  - Domain:  
    [acrt:Certification](https://vocab.methodandstructure.com/certification#Certification)
  - Range:  
    [foaf:Agent](http://xmlns.com/foaf/0.1/Agent)
  - Inverse of:  
    [acrt:certifies](https://vocab.methodandstructure.com/certification#certifies)

[Back to Top](https://vocab.methodandstructure.com/certification#)

</div>

<div id="certifies" about="[acrt:certifies]" typeof="owl:ObjectProperty owl:InverseFunctionalProperty">

#### certifies

This property specifies that its subject, an agent, has issued a
certification.

  - Domain:  
    [foaf:Agent](http://xmlns.com/foaf/0.1/Agent)
  - Range:  
    [acrt:Certification](https://vocab.methodandstructure.com/certification#Certification)
  - Inverse of:  
    [acrt:authority](https://vocab.methodandstructure.com/certification#authority)

[Back to Top](https://vocab.methodandstructure.com/certification#)

</div>

<div id="proof" about="[acrt:proof]" typeof="owl:ObjectProperty">

#### proof

This property points to some proof of the certification, like a scan of
an official document or a page on the issuing authority's website that
corroborates the certification.

> The range of this term is left open, but should probably reference a
> document. It could even point to an actual cryptographic certificate.

  - Domain:  
    [acrt:Certification](https://vocab.methodandstructure.com/certification#Certification)
  - Inverse of:  
    [acrt:proves](https://vocab.methodandstructure.com/certification#proves)
  - See also:  
    [The Cert Ontology](http://www.w3.org/ns/auth/cert)

[Back to Top](https://vocab.methodandstructure.com/certification#)

</div>

<div id="proves" about="[acrt:proves]" typeof="owl:ObjectProperty">

#### proves

This property asserts that its subject is somehow proof of a given
certification.

  - Range:  
    [acrt:Certification](https://vocab.methodandstructure.com/certification#Certification)
  - Inverse of:  
    [acrt:proof](https://vocab.methodandstructure.com/certification#proof)

[Back to Top](https://vocab.methodandstructure.com/certification#)

</div>

</div>
