---
title: Central Package Management in .NET 📊
date: 2025-02-19 23:00:00+0100
categories: [tools]
tags: [programming, .net]
---

## Problem
If you have a solution that contains many libraries, then at some point in time there will be a problem with mismatched versions of NuGet libraries.  
Something like:
```ps
Solution.sln
src/
-- Project1.csproj
-- Project2.csproj
-- ProjectN.csproj
```

## Solution
Use [Central Package Management](https://learn.microsoft.com/en-us/nuget/consume-packages/central-package-management)
1. Place `Directory.Packages.props` file in the root of your solution
    ```ps
    Directory.packages.props
    Solution.sln
    src/
    -- Project1.csproj
    -- Project2.csproj
    -- ProjectN.csproj
    ```
2. With content
    ```xml
    <Project>
        <PropertyGroup>
            <ManagePackageVersionsCentrally>true</ManagePackageVersionsCentrally>
        </PropertyGroup>
        <ItemGroup>
            <PackageVersion Include="Newtonsoft.Json" Version="13.0.1" />
            ...rest of your packages
        </ItemGroup>
    </Project>
    ```
3. In related `.csproj` leave only PackageReference without version specified like
    ```xml
    <Project Sdk="Microsoft.NET.Sdk">
        <PropertyGroup>
            <TargetFramework>net9.0</TargetFramework>
        </PropertyGroup>
        <ItemGroup>
            <PackageReference Include="Newtonsoft.Json" />
        </ItemGroup>
    </Project>
    ```
4. Now you have a central place to manage your NuGet versions (also this is supported via Rider/Visual Studio)

## Tips & Tricks
- To migrate packages in existing solutions you can use https://github.com/Vannevelj/directory-packages-props-converter
