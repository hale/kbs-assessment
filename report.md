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
>> java -jar pellet-2.3.0/lib/pellet-cli.jar classify bookstore.owl
Classifying 8 elements
Classifying:  100% complete in 00:00
Classifying finished in 00:00

 owl:Thing
    bookstore:Book
    bookstore:Person
       bookstore:Author
       bookstore:Customer
    bookstore:Purchase
    bookstore:Recommendation
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
