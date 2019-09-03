# Exception Handling

Exception handling is an important aspect of quality software development. When exception handling is not done well, it results in systems behaving unexpectedly or errors not being handled well. When exception handling is done well, it means that the system behave correctly even in abnormal situations.

## Rule 1. Do not silently ignore exceptions

### Bad practice: Silently ignoring exception

The most basic form of silent exception handling is when there is an empty catch block:

```csharp
try
{
    var lines = File.ReadAllLines(@"D:\file.txt");
}
catch(Exception ex)
{

}
```

The next form of silent exception handling is leaving comments for developers but again when this is activated in production it is same as silent exception handling:

```csharp
try
{
    var lines = File.ReadAllLines(@"D:\file.txt");
}
catch (Exception ex)
{
    // TODO: This should not happen
}
```

Above that, we also have the semi-silent exception handling whereby the developer writes to the console or trace, using this for debugging purposes during development, but again this isn't adequate for production:

```csharp
try
{
    var lines = File.ReadAllLines(@"D:\file.txt");
}
catch (Exception ex)
{
    Console.WriteLine("This should not happen");
    Trace.WriteLine("This should not happen");
}
```

### Rule 2. Correctly rethrow exceptions

### Bad practice: Incorrectly rethrowing exceptions

There are cases when we cannot handle an exception adequately, but we want to intercept it before letting it propagate further. An example is that when we want to log an exception before letting it propagate further.

Someone might accidentally do this - because then the stack trace of the original exception disappears!

```csharp
try
{
    var lines = File.ReadAllLines(@"D:\file.txt");
}
catch (Exception ex)
{
    // Do something, such as logging the exception
    throw ex;
}
```

### Good practice: Correctly rethrowing exceptions

The correct way to rethrow exceptions is as follows, which ensures that the stack trace of the original exception is preserved:

```csharp
try
{
    var lines = File.ReadAllLines(@"D:\file.txt");
}
catch (Exception ex)
{
    // Do something, such as logging the exception
    throw;
}
```









The next form of silent exception handling is printing out statements within the catch block:







Catching general exceptions instead of specific exceptions





Returning exception stack trace in REST API

Not disposing managed resources in cases when exceptions occur

Not logging exceptions 

Using exceptions for flow control 

Doing try-catch inside controllers for purposes of returning error response





## Good practices in exception handling









Creating global exception filters 

Logging exceptions 

Returning errors using RFC standard ProblemDetails class 

Ensuring managed resources are disposed





