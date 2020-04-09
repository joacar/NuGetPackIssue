# NuGet hell

1. Create NuGet package A with version 1.0.0-alpha by tagging with a-1.0.0-alpha
1. Add PackageOutputPath to RestoreSources project B
1. Add dependency `dotnet add b/B.csproj package A --version 1.0.0-alpha`

## Error
Works when adding source to VS Package Manager and adds from there
```
$dotnet add b/B.csproj package A --version 1.0.0-alpha
info : Adding PackageReference for package 'A' into project 'b/B.csproj'.
info : Restoring packages for C:\Temp\NuGetHell\b\B.csproj...
info : Package 'A' is compatible with all the specified frameworks in project 'b/B.csproj'.
error: Value cannot be null. (Parameter 'path1')
```
Haven't seem this, maybe regression for `dotnet --version 3.1.300-preview-015048`