# CHAPTER 2 MEANINGFUL NAMES

## Use intention revealing names
Choosing good names takes time but it save more than it takes. Everyone who reads your code including you will be happier if you do.

The name of a variable, function or class should answer all the big questions. It should tell why it is exists.
```java
int d; // elapsed time in days
```

The name _d_ reveals nothing. It does not evoke a sense of elapsed time nor of days.

```java
int elapsedTimeInDays;
int daysSinceCreation;
int daysSinceModification;
int fileAgeInDays;
```

Choosing names that reveal intent can make it much easier to understand and change code.

---


```java
public List<int[]> getThem() {
    List<int[]> list1 = new ArrayList<int[]>();
    for (int[] x : theList)
        if (x[0] == 4)
            list1.add(x);
    return list1;
}
```

Why is it hard to tell what this code above is doing? There are no complex expression. Spacing and indentation are reasonable. There are not even fancy classes or polymorphic methods, just a list of arrays.

* What kinds of things are in _theList_?
* What is the significance of the zeroth subscript of an item in _theList_?
* What is the significance of the value _4_?
* How would I use the list being returned?

Let us assume that the code snippet belongs to a mine sweeper game and change the variable names. Create a constant named _FLAGGED_ as a value of 4.

```java
public List<int[]> getFlaggedCells() {
    List<int[]> flaggedCells = new ArrayList<int[]>();
    
    for (int[] cell : gameBoard)
        if (cell[STATUS_VALUE] == FLAGGED)
            flaggedCells.add(cell);
    
    return flaggedCells;
}
```

Notice that the simplicity of the code has not changed. It still has exactly the same number of operators. 

We can go further and write a simple class for cells which has a function named _isFlagged_.

```java
public List<Cell> getFlaggedCells() {
    List<Cell> flaggedCells = new ArrayList<Cell>();
    
        for (Cell cell : gameBoard)
            if (cell.isFlagged())
                flaggedCells.add(cell);
        
    return flaggedCells;
}
```


With these simple changes it is not difficult to understand what's going on.

### Use Pronounceable Names

```java
class DtaRcrd102 {
private Date genymdhms;
private Date modymdhms;
private final String pszqint = "102";
};
```
```java
class Customer {
private Date generationTimestamp;
private Date modificationTimestamp;;
private final String recordId = "102";
};
```
_"Hey Race have a look at this record. The generation timestamp is set to tomorrow's date."_

## Class Names
Classes and objects should be a noun or a noun phrase like _Customer_, _WikiPage_, _Account_. Avoid works like _Manager_, _Processors_, _Data_, _Info_ in the name of a class. A class name should not be a verb.

## Method Names

Methods should have verb or verb phrase names like _postPayment_, _deletePage_ or _save_.

```java
String getName();
void setName(String name);
boolean isPosted();
```


