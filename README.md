# Object Oriented Design Patterns

## Creational Patterns

### The Builder Pattern


Let's create a class `Person`
```
public class Person() {
    int age;
    String firstName;
    String lastName;
    int id;
}
```

Given our class's [`member variables`](https://docs.oracle.com/javase/tutorial/java/javaOO/variables.html)
when we [`instantiate`](https://docs.oracle.com/javase/tutorial/java/javaOO/objectcreation.html)  our object 
we may want to also set those associated `fields` (aka `member variables`).

##### How have we previously `instantiated` objects?

via [`constructors`](https://docs.oracle.com/javase/tutorial/java/javaOO/objectcreation.html)!

---
##### Let's say that I want to set the person's `age` and `firstName`, but not `lastName` and `id` during "`instantiation`?"
```
    public Person (int _age, String _firstName) {
        this.age = _age;
        this.firstName = _firstName;
    }

```
##### Now let's say that I want to set the person's `age` and nothing else, during "`instantiation`?"

```
    public Person (int _age) {
        this.age = _age;
    }

```

We can see that accounting for all possible combinations of `member variables` using
multiple `constructors` can become a bit tedious to deal with.
---
##### You may ask, why don't we simply use [`setter methods`]((https://docs.oracle.com/javaee/7/tutorial/cdi-basic010.htm)) after we have already created the object?

To answer this, I would like to introduce the concept of [immutable objects](https://docs.oracle.com/javase/tutorial/essential/concurrency/immutable.html) or 
objects that "do not change" after they have been created. 

If we think back to the `Singleton` design
pattern, this is a good example of a pattern that would greatly benefit from `immutability`, being that
if it is a "single" source of truth, you don't want other pieces of the application to be able to 
change its metadata (mutate it).

---

##### For the simple scenario where you may want to enforce object immutability, have multiple `member variables` that may or may not need to be set, I bring you the `Builder` pattern!

#### References

- [AWS Java SDK - GitHub Source Code](https://github.com/aws/aws-sdk-java/blob/master/aws-java-sdk-core/src/main/java/com/amazonaws/client/builder/AwsClientBuilder.java#L121)
- [Builder Design Pattern - Medium Article](https://github.com/aws/aws-sdk-java/blob/master/aws-java-sdk-core/src/main/java/com/amazonaws/client/builder/AwsClientBuilder.java#L121)
- [What are member variables? - Oracle](https://docs.oracle.com/javase/tutorial/java/javaOO/variables.html)
- [Creating Objects - Oracle](https://docs.oracle.com/javase/tutorial/java/javaOO/objectcreation.html)
- [Java Object Getters/Setters - Oracle](https://docs.oracle.com/javaee/7/tutorial/cdi-basic010.htm)
- [Java Immutable Objects - Oracle](https://docs.oracle.com/javase/tutorial/essential/concurrency/immutable.html)









fdgh