# string-format-benchmark
benchmark new string-format in jdk17

## Code

**Concat using (+)**

```java
"<h1>" + question + "</h1><ol><li>" + answer1 +
    "</li><li>" + answer2 + "</li><li>" + answer3 + "</li></ol>"
```

**StringBuilder**

```java
new StringBuilder().append("<h1>").append(question)
    .append("</h1><ol><li>").append(answer1)
    .append("</li><li>").append(answer2)
    .append("</li><li>").append(answer3)
    .append("</li></ol>").toString()
```

**String.format**

```java
String.format("<h1>%s</h1><ol><li>%s</li><li>%s</li><li>%s</li></ol>", question, answer1, answer2, answer3)
```

## Sample String

```html
<h1>Life is unfair</h1>
<ol>
  <li>Yes</li>
  <li>no</li>
  <li>maybe</li>
</ol>
```

## Result
```
jdk8
Benchmark                      (answer1)  (answer2)  (answer3)      (question)  Mode  Cnt     Score    Error  Units
BenchMark.appendPlain                Yes         no      maybe  Life is unfair  avgt   10    48.200 ±  0.186  ns/op
BenchMark.appendStringBuilder        Yes         no      maybe  Life is unfair  avgt   10    54.233 ± 10.659  ns/op
BenchMark.appendStringFormat         Yes         no      maybe  Life is unfair  avgt   10  1468.017 ± 22.966  ns/op
```
```
jdk9
Benchmark                      (answer1)  (answer2)  (answer3)      (question)  Mode  Cnt     Score    Error  Units
BenchMark.appendPlain                Yes         no      maybe  Life is unfair  avgt   10    57.782 ±  0.998  ns/op
BenchMark.appendStringBuilder        Yes         no      maybe  Life is unfair  avgt   10    60.588 ±  0.818  ns/op
BenchMark.appendStringFormat         Yes         no      maybe  Life is unfair  avgt   10  1721.897 ± 18.800  ns/op
```
```
jdk11
Benchmark                      (answer1)  (answer2)  (answer3)      (question)  Mode  Cnt     Score     Error  Units
BenchMark.appendPlain                Yes         no      maybe  Life is unfair  avgt   10    58.852 ±   0.352  ns/op
BenchMark.appendStringBuilder        Yes         no      maybe  Life is unfair  avgt   10    61.966 ±   2.671  ns/op
BenchMark.appendStringFormat         Yes         no      maybe  Life is unfair  avgt   10  1576.061 ± 213.517  ns/op
```
```
jdk17
Benchmark                      (answer1)  (answer2)  (answer3)      (question)  Mode  Cnt    Score    Error  Units
BenchMark.appendPlain                Yes         no      maybe  Life is unfair  avgt   10   65.608 ±  2.867  ns/op
BenchMark.appendStringBuilder        Yes         no      maybe  Life is unfair  avgt   10   64.280 ± 15.409  ns/op
BenchMark.appendStringFormat         Yes         no      maybe  Life is unfair  avgt   10  395.392 ±  1.626  ns/op
```
