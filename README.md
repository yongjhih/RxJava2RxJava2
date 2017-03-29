### `Action0` to `Action`/`Runnable`

Before:

```java
new Action0() {
  @Override
  public void call() {
  }
}
```

After:

```java
new Action() {
  @Override
  public void run() throws Exception {
  }
}
```

After:

```java
new Runnable() {
  @Override
  public void run() {
  }
}
```

### `Action1<T>` to `Consumer<T>`

Before:

```java
new Action1<String>() {
  @Override
  public void call(String text) {
  }
}
```

After:

```java
new Consumer<String>() {
  @Override
  public void accept(String text) throws Exception {
  }
}
```

### `Action2<T>` to `BiConsumer<T>`

Before:

```java
new Action2<String, Integer>() {
  @Override
  public void call(String text, Integer i) {
  }
}
```

After:

```java
new BiConsumer<String, Integer>() {
  @Override
  public void accept(String text, Integer i) throws Exception {
  }
}
```

### `Func0<R>` to `Callable<R>`

Before:

```java
new Func0<Boolean>() {
  @Override
  public Boolean call() {
    return true;
  }
}
```

After:

```java
new Callable<Boolean>() {
  @Override
  public Boolean call() throws Exception {
    return true;
  }
}
```

### `Func1<T, Boolean>` to `Predicate<T>`

Before:

```java
new Func1<String, Boolean>() {
  @Override
  public Boolean call(String text) {
    return true;
  }
}
```

After:

```java
new Predicate<String>() {
  @Override
  public boolean test(String text) {
    return true;
  }
}
```

### `Func1<T, R>` to `Function<T, R>`

Before:

```java
new Func1<String, Integer>() {
  @Override
  public Integer call(String text) {
    return ret;
  }
}
```

After:

```java
new Function<String, Integer>() {
  @Override
  public Integer apply(String text) {
    return ret;
  }
}
```

### `Func2<T, T2, R>` to `BiFunction<T, T2, R>`

Before:

```java
new Func2<String, Integer, Boolean>() {
  @Override
  public Boolean call(String text, Integer i) {
    return true;
  }
}
```

After:

```java
new BiFunction<String, Integer, Boolean>() {
  @Override
  public Boolean apply(String text, Integer i) {
    return true;
  }
}
```

### `ActionN<T>` to `Action<Object[]>`

Before:

```java
new Action3<String, Integer, Boolean>() {
  @Override
  public void call(String text, Integer i, Boolean b) {
  }
}
```

After:

```java
new Action<Object[]>() {
  @Override
  public void accept(Object[] objects) throws Exception {
  }
}
```

### `FuncN<T>` to `Function<Object[], R>`

Before:

```java
new Func3<String, Integer, Boolean>() {
  @Override
  public Boolean call(String text, Integer i) {
    return true;
  }
}
```

After:

```java
new Function<Object[], R>() {
  @Override
  public R apply(Object[] objects) throws Exception {
      return ret;
  }
}
```
