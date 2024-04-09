HW 2, CS 625, Spring 2023
================
Sai Soujanya Ivaturi
Feb 2, 2023

    Initially, there were 59 pets in the raw data. 

    Step 1: In the column, “what kind of pet is this”, I have followed the below steps

    Edit Cells -> Cluster and edit 
    Key Collision -> Fingerprint
    Nearest Neighbor -> Levenshtein
    Nearest Neighbor -> PPM
    I have selected the options and clicked on Merge selected & re-cluster

![](Screen2.png)

    Step 2: In the same column, “what kind of pet is this”, I have followed the below steps

    Facet -> Text facet. I have changed the following names manually.

    Ca, Car, Cats -> Cat
    Dig, dlg, Mona, Phoebe, Sog, puppy, Pitbull, Doggo, god -> Dog
    Other(fish), Bettafish, Goldfish, Indoor Goldfish, Elephant -> Fish
    Other Guinea pig -> Guinea Pig
    Kitten, Katze, Kitty Meow -> Cat
    Bees, Prairie dog, Other: Snake -> Snake (I have checked the breed names of Bees and Prairie dogs and found out they are snakes)
    Other: bees -> Dog (I have checked the breed names and found out they are dogs)
    Leopard Gecko, Gecko -> Lizard
    Turtle -> Tortoise

How many types (kinds) of pets are there?

    After cleaning the data by following the above steps, I am left with 26 pets

![](Screen1.png)

How many dogs?

    There are 1128 dogs on the whole. 

![](Screen3.png)

    In the column 'what kind of pet is this' -> facet -> text facet -> dog and check the count


    Step 3: In the column “Pet’s age”, I have followed the below steps
    Edit cells -> Transform
    value.replace("years","").replace("year","").replace("ish","").replace("yesrs","")
    SS3
    value.replace("two","2").replace("six","6").replace("seven","7").replace("½",".5").replace("1/2",".5").replace(" ","").replace("~","").replace("&","").replace("≈","").replace("()","").replace("yo","").replace("old","")

![](Screen4.png)

    value.replace(" years","")

![](Screen5.png)

    Edit Cells -> Cluster and edit 

    Key collision -> Fingerprint (I have selected only which are applicable) -> Merge selected & re-cluster

![](Screen6.png)

    Step 4: In the column “Pet’s breed”, I have followed the below steps

    Edit Cells -> Cluster and edit 
    Key Collision -> Fingerprint
    Key Collision -> n-Gram fingerprint
    Key Collision-> Metaphone3 (Only the ones which are applicable)
    Nearest Neighbor -> Levenshtein (Only the ones which are applicable)
    Nearest Neighbor -> PPM (Only the ones which are applicable)

![](Screen7.png) ![](Screen8.png) ![](Screen9.png)

    Next, I have edited it manually, by following the below steps

    Pet’s breed -> Facet -> Text facet

![](Screen10.png)

    I have 490 breeds after cleaning the Pet’s name column.

How many breeds of dogs?

    There are 357 breeds of dogs

![](Screen11.png)

    In the column 'what kind of pet is this' -> facet -> text facet -> dog 
    In the column 'pet's breed' -> facet -> text facet and check the count there.

What’s the most popular dog breed?

       The most popular dog breed is Golden Retriever with the count 170
       

![](Screen12.png)

    In the column 'what kind of pet is this' -> facet -> text facet -> dog 
    In the column 'pet's breed' -> facet -> text facet and click on 'count'

    Step 5: In the column “Pet’s age”, to clean the data further, I have followed the below steps

    Edit Cells -> Cluster and edit 
    Key Collision -> n-Gram fingerprint (Only the ones which are applicable)

![](Screen13.png)

    Pet's age -> facet -> Numeric facet -> Non-numeric

    Then I started cleaning the non-numeric data manually I have selected each cell from the column and edited accordingly.

![](Screen14.png)

    Step 6: 

    Pet's age -> facet -> Custom text facet
    value.contains("mo") and selected the true value.

![](Screen15.png)

    I have used the below expression 
    import re
    return float(re.findall(r'\d+', value)[0])/12

![](Screen16.png)

    Similarly, I have done the same process to 'weeks' as well using the below expression
    import re
    return float(re.findall(r'\d+', value)[0])/52.143

What’s the age range of the dogs?

    The age range of the dogs is in between of 0.04 to 22 years

![](Screen17.png)

    Pet's age -> Sort -> numbers -> largest first and Pet's age -> Sort -> numbers -> smallest first and checked the values.

What’s the age range of the guinea pigs?

    The age range of the guinea pigs is in between of 1 to 5 years

![](Screen18.png)

    I have followed the same process as of the above question for this question as well.

What is the oldest pet?

    The oldest pet is a cat of 24 years (Bruce)

![](Screen19.png)

    Pet's age -> Sort -> largest first.
    The first result is of number 24 with a cat breed.

Which are more popular, betta fish or goldfish? How many of each?

    Betta fish is the most popular among betta fish and goldfish. The number of goldfish present are 5 and Betta fish are 11

![](Screen20.png)

    I have counted both goldfish and betta fish maually and figured that betta fish are more
    In the column 'what kind of pet is this' -> facet -> text facet -> fish

What’s the most popular everyday name for a cat?

    The most popular everyday name for a cat is Kitty

![](Screen21.png)

    In the column 'what kind of pet is this' -> facet -> text facet -> cat 
    In the column 'pet's everyday name' -> facet -> text facet and click on 'count'
    After checking, I have figured that the most popular everyday name is Kitty

What’s the most popular full name for a dog?

    The most popular full names for a dog are Bella and Sadie

![](Screen22.png)

    In the column 'what kind of pet is this' -> facet -> text facet -> dog 
    In the column 'pet's full name' -> facet -> text facet and click on 'count'
    After checking, I have figured that the most popular full names are Bella and Sadie

References :

<https://openrefine.org/docs/manual/expressions#grel-general-refine-expression-language>
<https://www.youtube.com/watch?v=wfS1qTKFQoI>
<https://openrefine.org/docs/manual/jythonclojure>
