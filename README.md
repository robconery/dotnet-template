## The Starter Template Template
You can use this template to build your own. Be sure to replace the text here so people who want to help out can read more about the template project (as opposed to reading more about the template).

## The Template File
There is a `template.json` file in the `/.templates.config` directory which needs to be updated with your template settings. 

Here is a sample from the Vue starter template:

```json
{
  "$schema": "http://json.schemastore.org/template",
  "description": "An ASP.NET Minimal API with Vue 3",
  "defaultName" : "Vue.Starter",
  "repository": {
    "url": "https://github.com/robconery/Vue.Starter",
    "type": "GitHub"
  },
  "projectURL": "https://github.com/robconery/Vue.Starter",
  "releaseNotes": "Separated client and server projects, added Minimal API with a simple Markdown CMS",
  "author": "Rob Conery",
  "classifications": [ "Web Application" ], 
  "name": "ASP.NET Minimal API with Vue 3",
  "identity": "Microsoft.Web.Vue3",         
  "shortName": "vue",                    
  "tags": {
    "language": "Web",                         
    "type":"project"
  },
  "sourceName": "Vue.Starter",
  "preferNameDirectory":true
}
```


## The CSPROJ File
Be sure to update the contents in the `csproj` file with the name and description of your project, which should match that of your `template.json`.

Here is a sample from the Vue starter:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <PackageLicenseExpression>MIT</PackageLicenseExpression>
    <NoDefaultExcludes>true</NoDefaultExcludes>
    <PackageReadmeFile>content/templates/vue/README.md</PackageReadmeFile>
    <PackageIcon>content/templates/vue/icon.png</PackageIcon>
    <PackageType>Template</PackageType>
    <PackageVersion>1.1.6</PackageVersion>
    <PackageId>Vue.Web.Starter</PackageId>
    <Title>ASP.NET Core with Vue 3</Title>
    <Authors>Rob Conery</Authors>
    <Description>ASP.NET Core Web Application with Vue 3</Description>
    <PackageTags>dotnet-new;templates;mvc;web;vue</PackageTags>
    <TargetFramework>net7.0</TargetFramework>
    <IncludeContentInPack>true</IncludeContentInPack>
    <IncludeBuildOutput>false</IncludeBuildOutput>
    <ContentTargetFolders>content</ContentTargetFolders>
  </PropertyGroup>

  <ItemGroup>
    <Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**;templates\**\node_modules\**" />
    <Compile Remove="**\*" />
  </ItemGroup>

</Project>
```

Whenever you change your template, be sure to rev the version as needed, otherwise Nuget won't change anything.

## Deploying Your Template
When you're ready to push, make sure that you have:

 - Updated the `template.json` file with your template settings.
 - Updated the two README files, including this one, which should have instructions on how to use the template, getting help and so on.
 - Added your own icon file inside your project
 - Changed the `sample` directory name to whatever shortname you've chosen
 - Updated the `.csproj` file as needed

Now you need to create a publish package and you do that by running `dotnet publish` in the root directory. This will create a Nuget Package file in `/bin/Debug/net7.0` and you will then upload to Nuget once you've logged in.


