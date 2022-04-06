# conventions
Conventions for contributions to this organization

# Repositories

## Naming

Repositories are named in kebab-case. https://kulturbanause.de/faq/was-ist-kebab-case/

## Access

By default, repositories are private. Public repositories are only created if an organization administrator allows to do so.
For individual access control, there are teams for each year of apprenticeship, aswell es for the individual projects. 

# Code

## Committing

Each coding session only has one push. You should actively commit your changes and push them at the end of your session. Do not write hundrets of lines of code and commit them only once with the message "added feature X"

> Commit messages have to be descriptive and are written only in lower case, also starting with an lower case character.

## Format

### Indentation style

Use the 1TBS (https://en.wikipedia.org/wiki/Indentation_style#Variant:_1TBS_(OTBS)) style.

**Bad Example:**

```java
void doSomething(args) 
{
  if (expression) 
  {
    //execute code
  }
  else 
  {
    //throw exception
  }
}
```

**Good Example:**

```java
void doSomething(args) {
  if (expression) {
    //execute code;
  } else {
    //throw exception;
  }
}
```

### Blank Lines
Do not overuse blank lines to reduce the code's vertical size.

**Bad Example:**

```java
public final class User {

  private final String name;

  public String getName() {
    
    return name;
  }
  
}
```

**Good Example:**

```java
public final class User {
  private final String name;

  public String getName() {
    return name;
  }
}
```

### Whitespaces

Please use whitespaces after structure keywords (`if`, `else`, `while`, `for`, `do`, `try`, etc...) or before curly braces, but *never* use two ore more whitespaces behind each other.

**Bad Example:**

```java
void doSomething ( args ){
  if( expression )  {
    //do something;
  }
}
```

**Good Example:**

```java
void doSomething(args) {
  if (expression) {
    //do something;
  }
}
```

### Maximum line length
Keep the amount of characters per line below `80`.

## Naming

### For Java:

Follow oracle's java naming conventions, use *UpperCamelCase* for class names, use *lowercase* for package names, *camelCase* for variables & methods and *UPPERCASE* for constants.

### For C#:

Follow Microsoft's conventions: https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions

### For C++:

...

### Do not use public fields

Do not use public fields, instead use getters and setters. Many of our plugins depend on other plugins, when you decide that you dont want to check something when getting a field, you need to add getters and setters, then every plugin using yours needs to be changed.

**Bad Example:**

```java
class AdventurePlayer {
  public UUID playerUuid;
}
```

**Good Example:**

```java
class AdventurePlayer {
  private UUID playerUuid;
  
  public UUID getPlayerUuid() {
    //check something;
    return playerUuid;
  }
}
```

### Do not use booleans

Please do not use booleans, instead, use enums.

**Bad Example:**

```java
class Guild {
  boolean needsInvitation;
}
```

**Good Example:**

```java
class Guild {
  
  enum State {
    OPEN_FOR_ALL,
    INVITATION_ONLY
  }
  
  private State state;
  
}
```

### Do not use magic numbers

Please do not use magic numbers, instead, create constants. Allowed numbers in code are `-1`, `0` and `1`.

**Bad example:**

```java
adventurePlayer.addMoney((todayOnlineTime / 60) * 20);
```

**Good example:**

```java
adventurePlayer.addMoney((todayOnlineTime / TIME_DIVISOR) * COINS_PER_HOUR);
```

### Do not use acronyms

Instead of using acronyms, use (a) descriptive word(s).

**Bad example:**

```java
if (sp < MAP) {
  p.sendMessage(PTL);
}
```

**Good example:**

```java
if (selectedPrice < MIN_AUCTION_PRICE) {
  player.sendMessage(PRICE_TOO_LOW);
}
```

### Do not use plaintext in your logical code

Instead of using plaintext, for example use enums or constants.

**Bad example:**

```java
if (expression) {
  player.sendMessage("You've won something in the case opening!");
}
```

**Good example:**

```java
if (expression) {
  player.sendMessage(CASE_OPENING_WON);
}
```
