# Development best practices

This is a collection of best practices for Gradle implementation.
Should and should not do's.

## Error messages and suggestions

Traditionally if an error occurred the error message and the possible solution were provided to the console via a single String in the corresponding exception.
That meant possible solutions for Problems could be scattered all over the console output.
To improve the user experience we introduced a new way to provide suggestions.
The idea is to provide a list of suggestions for a problem in the console output.
The suggestions are displayed in the separate "Try"- section of the console output.
The suggestions are collected in the `BuildExceptionReporter` and printed to the console.

In some cases you still want to keep the old behavior and display the suggestions in the error message.

### Add custom suggestions

1. To add a custom suggestion in the "Try" section of the console output your exception needs to implement `ResolutionProvider` interface.
2. That should be it. The suggestion will be displayed in the "Try" section.

