# Philip Hale
## CS3019 Assessment - 25% - due 07/12/2012

### Your report should include:

* Description of how you extended the provided ontology in different steps.
* Description of how you extended the provided rule set.
* Functionalities of your rule sets. Please provide step by step instructions and detailed examples to illustrate the functionalities of your rule sets.
* Your findings during the assessment.

---------------

### Classify the ontology using an ontology reasoner

```
$ java -jar HermiT/HermiT.jar -cPN bookstore.owl
Prefix(:=<http://www.cs4021/bookstore.owl#>)

Ontology(<http://www.cs4021/bookstore.owl#>

  SubClassOf( :Book owl:Thing ) Declaration( Class( :Book ) )
  SubClassOf( :Person owl:Thing ) Declaration( Class( :Person ) )
    SubClassOf( :Author :Person ) Declaration( Class( :Author ) )
    SubClassOf( :Customer :Person ) Declaration( Class( :Customer ) )
  SubClassOf( :Purchase owl:Thing ) Declaration( Class( :Purchase ) )
  SubClassOf( :Recommendation owl:Thing ) Declaration( Class( :Recommendation ) )

)
```
