# Apex Mocks Snippets

This is an extension to make it easier to develop with Apex mocks by providing useful code snippets.

<https://github.com/apex-enterprise-patterns/fflib-apex-mocks>

## Snippets

Where there are blanks - the snippet will default the cursor to populate
If there are multiple gaps, after populating the first empty, pressing tab will take the cursor to
the next slot.

![Apex Mocks Example](apex-mocks-example.gif)

### unit-test

```java
@IsTest(isParallel=true)
class  {
    @IsTest
    public static void methodUnderTest_changes_expectedResult() {
        Test.startTest();
        Test.stopTest();
    }
}
```

### test-case

```java
@isTest
public static void methodUnderTest_changes_expectedResult() {
    Test.startTest();
    Test.stopTest();
}
```

### answer

```java
private with sharing class Answer implements fflib_Answer {
    public Answer() {}
    public Object answer(fflib_InvocationOnMock invocation) {
          ArgumentType argumentOne = (ArgumentType) invocation.getArgument(0);

          return null;
    }
}
```

### asserte

```java
System.assertEquals(, , );
```

### assert

```java
System.assert(, );
```

### fflib-asserte

```java
fflib_System.assertEquals(fflib_Match.(), ,);
```

### startStubbing

```java
.startStubbing();

.stopStubbing();
```

### startTest

```java
Test.startTest();

Test.stopTest();
```

### create-mock-builder

```java
fflib_ApexMocks  = new fflib_ApexMocks();
```

### argumentCaptor

```java
fflib_ArgumentCaptor serviceParmsCaptor = fflib_ArgumentCaptor.forClass(
    .class
);
```

### capture-argument

```java
(Type) .capture()
```

### verify-calls

```java
((Service) .verify(serviceToMock, 1)).methodName((ArgumentType) fflib_Match.anyObject());
```

### create-mock

```java
mockService = () .mock(.class)
```

### doThrowWhen

```java
((ServiceType) .doThrowWhen(
    new TestException('Splat!'),
    mockService
))
.methodName((ArgumentType) fflib_Match.anyObject());
```

### thenReturn

```java
.when(
    mockService.methodName((ArgumentType) fflib_Match.anyObject())
)
.thenReturn(mockResult);
```

### thenAnswer

```java
.when(
    mockService.methodName((ArgumentType) fflib_Match.anyObject())
)
.thenAnswer(answerInstance);
```

### runAs

```java
System.runAs() {

}
```
