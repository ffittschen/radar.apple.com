# FB9178663 - Swift Compiler throws errors for Apple frameworks used by SPM packages during archive builds

Using Xcode 13.0 beta (13A5154h), the Swift compiler throws an error “Enum cases with associated values cannot be marked potentially unavailable with '@available’” and points to Apple’s own Frameworks in a swiftinterface file that is associated with an integrated Swift Package, when archiving the project.

In the attached screenshot and sample project, we integrated Tealium via SPM in Xcode and then archived the project. The Swift compiler is complaining that Apple’s `NWEndpoint` is using `@available` for enum cases that have associated values.

1. Open the attached sample project
2. Set a Development Team in the ‘Signing & Capabilities’ tab of the ‘Enum At Available’ target
3. Select ‘Any iOS Device’ as destination
4. Archive the project

I’d expect that archiving the project succeeds without the Swift compiler throwing errors originating in Apple’s own frameworks.

The Swift compiler throws errors originating in Apple’s own frameworks.