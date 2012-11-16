# Philip Hale
## CS3019 Assessment - 25% - due 07/12/2012

### Your report should include:

* Description of how you extended the provided ontology in different steps.
* Description of how you extended the provided rule set.
* Functionalities of your rule sets. Please provide step by step instructions and detailed examples to illustrate the functionalities of your rule sets.
* Your findings during the assessment.

---------------
## 1

###  Classify the ontology using an ontology reasoner

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

### Edit these two classes, making them direct subclasses of Person, and also change the asserted type of the 4 existing instances of Person appropriately to be either Author or Customer, depending on whether he/she has written a book or made a purchase.

Using the tag 'v1', we can see that only Author and Customer are direct subclasses of Person 
```
$ java -jar HermiT/HermiT.jar -ds :Person bookstore.owl
Direct sub-classes of ':Person':
    :Author
    :Customer
```



MAKE A GIT TAG AT THIS POINT BEFORE GOING FURTHER!!
