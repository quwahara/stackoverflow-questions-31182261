# stackoverflow-questions-31182261

This project is a proof of [this question](http://stackoverflow.com/questions/31182261/thymeleaf-at-syntax-returns-empty-if-i-include-resourceurlencodingfilter/31331691).

## Build and running

```
$ gradle build
$ java -jar build/libs/stackoverflow-questions-31182261-1.0.jar
```

## The page of reproduce

http://localhost:9090/home

The html template is:

```
<body>
[<span th:text="@{/}"></span>]
</body>
```

So, if it can be reproduced, you will see:

```
[]
```

If it can't be reproduced, you will see:

```
[/]
```

## causation

webjar dependency in build.gradle causes the matters.
For instance:

```
compile('org.webjars:bootstrap:3.3.1')
```

## remarks

I challenged the reproduce in Eclipse and command line.
In Eclipse, including webjar causes the matters. Excluding doesn't causes it.
It's straight.
In command line, it causes the matters even if you exclude webjar once you have included.
I can't explain the case. 




