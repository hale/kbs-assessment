# Philip Hale
## CS3019 Assessment - 25% - due 07/12/2012

### Your report should include:

* Description of how you extended the provided ontology in different steps.
* Description of how you extended the provided rule set.
* Functionalities of your rule sets. Please provide step by step instructions and detailed examples to illustrate the functionalities of your rule sets.
* Your findings during the assessment.

---------------

## Between CAS 9 and CAS 11

###  Classify the ontology using an ontology reasoner

The Pellet reasoner's CLI is sufficient for this:

```
$ java -jar pellet-2.3.0/lib/pellet-cli.jar classify bookstore.owl
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

This can be achieved by explicitly specifying that Customer and Author are subclasses of Person:

`<rdfs:subClassOf rdf:resource="#Person"/>`

We can use the HermiT reasoner to check:

```
$ git checkout cas11
$ java -jar HermiT/HermiT.jar -ds :Person bookstore.owl
Direct sub-classes of ':Person':
    :Author
    :Customer
```

### Add some more books, authors and customers to allow for testing later

I extended the ontology by editing `bookstore.owl` in a text editor. I checked the consistency of the ontology with the pellet reasoner CLI. For the data, I used the first 10 books listed in the *World Library*. The names of the customers are taken from the children's TV show *My Little Pony: Friendship is Magic*. Their purchases are imagined.

To see the resulting ontology at this stage, `git checkout cas11`

<!-- TODO: put the contents of that git checkout in a zip and name it appropriately -->

## Between CAS 12 and CAS 14

### Manually add recommendations into the ontology based on the newly created instances.

The following recommendations were added, based on the *Moby Dick* example:

```
  <Recommendation rdf:ID="recommendation_1_1">
    <hasBook rdf:resource="#pride_and_prejudice"/>
    <hasBuyer rdf:resource="#fluttershy"/>
  </Recommendation>
  <Recommendation rdf:ID="recommendation_1_2">
    <hasBook rdf:resource="#molloy_malone_unnamable"/>
    <hasBuyer rdf:resource="#spike"/>
  </Recommendation>
  <Recommendation rdf:ID="recommendation_1_3">
    <hasBook rdf:resource="#the_divine_comedy"/>
    <hasBuyer rdf:resource="#twilight_sparkle"/>
  </Recommendation>
```

### Extend the ontology by adding a BookSubject class, and build up a small subject hierarchy beneath it. 

```
$ java -jar pellet-2.3.0/lib/pellet-cli.jar classify bookstore.owl
Classifying 31 elements
Classifying:  100% complete in 00:00
Classifying finished in 00:00

 owl:Thing
    bookstore:BookSubject
       bookstore:English
       bookstore:Fiction
          bookstore:Novel
             bookstore:NovelC19
             bookstore:NovelC20
             bookstore:NovelC21
          bookstore:Play
          bookstore:Poetry
       bookstore:NonEnglish
          bookstore:LanguageArabic
          bookstore:LanguageFrench
          bookstore:LanguageGerman
          bookstore:LanguageGreek
          bookstore:LanguageHebrew
          bookstore:LanguageLatin
          bookstore:LanguageRussian
       bookstore:NonFiction
          bookstore:CategoryBusiness
          bookstore:CategoryCalendars
          bookstore:CategoryComputing
          bookstore:CategoryLanguages
          bookstore:CategoryTravel
    bookstore:Book
    bookstore:Person
       bookstore:Author
       bookstore:Customer
    bookstore:Purchase
    bookstore:Recommendation
```

### Create a hasSubject property and use it to link the books with the subject individuals.

You can see in protege that books have been linked with subjects by way of the mirror hierarchy of subject instances.

git tag cas14.  `git checkout cas14`

<!-- TODO: put the contents of that git checkout in a zip and name it appropriately -->

## Between CAS 15 and CAS 17



