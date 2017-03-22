## Succinc\<T\> ##
#### Discriminated unions, pattern matching and partial applications for C#  ####

### Current project status ###
| | Status |
| ---: | :-: |
|Master branch|[![Build Status (master)](https://ci.appveyor.com/api/projects/status/i294j7cukasq88ry/branch/master?svg=true)](https://ci.appveyor.com/project/DavidArno/succinct)
|C# 7 branch|[![Build Status (C#7)](https://ci.appveyor.com/api/projects/status/i294j7cukasq88ry/branch/csharp7migration?svg=true)](https://ci.appveyor.com/project/DavidArno/succinct)|
|Current release|[![NuGet](https://img.shields.io/nuget/v/SuccincT.svg)](http://www.nuget.org/packages/SuccincT)|

----------
### Overview ###
Succinc\<T\> is a .NET library that adds a number of functional features to C#:

* Discriminated unions,
* Pattern matching,
* Partial applications,
* "Implicitly" typed lambdas,
* The ability to treat `void` methods as `Unit` functions,
* Replacements for `TryParse` methods that return an `Option<T>` (or `Maybe<T>`, if you prefer), rather than using the `out` parameter anti-pattern.
* "cons" support for `IEnumerable<T>` (add elements to the head of an enumeration, or split an enumeration into its head element and an enumeration containing the remaining items, all without repeatedly enumerating that enumerable).
* `Cycle()` methods that endlessly repeat an enumeration or array, again without repeatedly enumerating that enumerable).
* Replacements for `IEnumerable<T>`'s `XXXOrDefault` methods that return an `Option<T>` (or `Maybe<T>`, if you prefer), avoiding `null` and the "did it return a value, or the default?" problem,
* And finally, as an experimental feature at this stage, forward pipe support.

For more details of each of these feature, [please refer to the wiki](https://github.com/DavidArno/SuccincT/wiki).

### Serialization ###
V2.2.0 saw the introduction of of JSON.Net serialization support for Succinc\<T\>. Using the Succinc\<T\> serializers, all types can now be correctly serialized/deserialized to JSON.

For details, see the [Serializing to JSON](https://github.com/DavidArno/SuccincT/wiki/JsonSerialization) wiki page.

### Current Release ###
The current release of Succinc\<T\> is 2.3.0, which is available as a [nuget package that supports .NET 4+ and Windows 8+ appstore apps](https://www.nuget.org/packages/SuccincT/). 

This release also includes SuccincT.Json v2.3.0, which is available as a separate [nuget package that supports .NET 4+ and Windows 8+ appstore apps](https://www.nuget.org/packages/SuccincT.Json/). SuccincT.Json is dependent on Succinc\<T\>, so will pull that package in as part of the install. Also, please note that this nuget package is also dependent on the Newtonsoft.JSON v4.0.30319 nuget package.

**WARNING**: Support for .NET Core has been temporarily dropped. Previously, the Succinc\<T\> nuget package was incorrectly using the .NET Core version of the dll for framework projects, which could cause runtime failures as it tried to link to v4.1 of `System.Runtime`. Experiments with .NET Core suggest it didn't work reliably with that technology either. So with v2.2, support for .NET Core was temporarily dropped. Hopefully with the v1 tooling released alongside VS2017, this feature will return in the next release.

### What's planned? ###
The next release (barring bugs in v2.3.0, resulting in a bug-fix release) will be v3.0.0. This will include new features that take advantage of C#7 (hopefully in a backward compatible fashion).
 
### Forking and Contributing ###
If you wish to fork this repo and build it on your own machine, please refer to the [Branches page](docs/Branches.md) for details of the currently active branches.

If you wish to contribute in any way (from saying "hi" to submitting a PR), please refer to the [Contributing page](docs/Contributing.md). 