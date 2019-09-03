# Exception Handling

Exception handling is an important aspect of quality software development. When exception handling is not done well, it results in systems behaving unexpectedly or errors not being handled well. When exception handling is done well, it means that the system behave correctly even in abnormal situations.

## Bad practices in exception handling

Silent exception handling

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





