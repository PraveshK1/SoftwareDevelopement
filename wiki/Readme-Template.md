Here’s the content from your image, Pravesh, transcribed exactly as it appears with line numbers preserved:


```
  <center>
  <h1><span style="color:red; font-weight: bold;">TODO: Add Repository Name</span></h1>
  </center>
  
  [Documentation](<span style="color:red; font-weight: bold;">TODO: Add Link to Confluence Docs</span>)
  [<span style="color:red; font-weight: bold;">TODO: Add Link to API/Swagger Docs</span>]
  
  [Engineering Insights](<span style="color:red; font-weight: bold;">TODO: Add Link to Engineering Insights Page for Repo</span>)
  
  [SonarQube Setup](<span style="color:red; font-weight: bold;">TODO: Add Link to SonarQube Report for Repo</span>)
  [Code Coverage](<span style="color:red; font-weight: bold;">TODO: Add Link to SonarQube Coverage Report for Repo</span>)
  [Build Status](<span style="color:red; font-weight: bold;">TODO: Add Link to Azure Build Pipeline for Repo</span>)
  
  </center>
  
  # Summary
  
  {TODO: Brief description of this repo}
  
  # Introduction
  
  {TODO: Introduction of this repo}
  
  # Documentation
  
  All documentation for this tool can be found in Confluence: [Documentation](<span style="color:red; font-weight: bold;">TODO: Add Link to Confluence Docs</span>)
  
  ## Visual Diagrams
  
  All visual diagrams for this tool can be found in Confluence: [Visual Diagrams](<span style="color:red; font-weight: bold;">TODO: Add Link to Diagrams</span>)
  
  ## API Documentation
  
  All API documentation for this tool can be found in Confluence: [API Documentation](<span style="color:red; font-weight: bold;">TODO: Add Link to API/Swagger Docs</span>)
  
  ## Engineering Insights
  
  All engineering insights for this tool can be found in Confluence: [Engineering Insights](<span style="color:red; font-weight: bold;">TODO: Add Link to Engineering Insights Page</span>)
  
  ## SonarQube Setup
  
  All SonarQube setup for this tool can be found in Confluence: [SonarQube Setup](<span style="color:red; font-weight: bold;">TODO: Add Link to SonarQube Docs</span>)
  
  ## Build Status
  
  All build status for this tool can be found in Confluence: [Build Status](<span style="color:red; font-weight: bold;">TODO: Add Link to Build Pipeline</span>)
  
  # Compliance Audits
  
  This API is an internal service tool that is not currently subject to compliance audits or certification.
  
  # Getting Started
  
  ## Clone the repository
  
  Clone the repo to check it out locally:
  
  <span style="color:red; font-weight: bold;">TODO: Update Bash snippet with {Link}</span>
  
  ## Install Dependencies
  After successfully cloning the solution install the following tools, if you don't already have them on your PC:
  ### Visual Studio
  Our solution is compatible with the latest version of [Visual Studio](https://visualstudio.microsoft.com/downloads/).
  ### .NET Core SDK
  Download the latest version of [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet).
  ### Docker Desktop (TODO: Remove if not relevant)
  Our solution uses [Docker Desktop](https://www.docker.com/products/docker-desktop) to (TODO: Add Purpose of Docker)

  ## Build, Test, and Run the Solution
  ### Restore NuGet packages
  We must run this command in the root folder to restore any missing NuGet packages in the solution.
      dotnet restore
  ### Build the Solution
  To build the code, run the following in the root folder.
  (TODO: Update Solution path in bash snippet)
      dotnet build {Solution Name}.sln
  ### Build the Solution with Buildkit (TODO: Remove if not relevant)
  /shared_jenkins/**this repository uses Derivo's smart build tool. See the [buildkit docs](https://dev.azure.com/DerivoSoftware/_git/Platform-Extensions-Pipelines?path=%2Fdocs%2Fconcepts%2Fbuildkit.md&version=GBmaster) for more details.
  We can restore the Buildkit tool by running the following command in the root of the repo. *This has to be repeated when the tool version has been updated by a team member (using `dotnet tool update`) and the change pulled via git.
      dotnet tool restore
  Now we can build targets:
      dotnet buildkit
  We can use `dotnet buildkit --help` for additional options.
  ### Add additional dependencies (e.g., Starting Docker Containers)
  (TODO: Update Docker Arguments in bash snippet)
      docker-compose up -d
  ### Run Unit Tests
  To run the unit tests, execute the following in the root folder.
  (TODO: Update 1st Path in bash snippet)
      dotnet test .\tests\{Add 1st Project Filename}.csproj
  ### Run E2E Tests
  To run the E2E tests, execute the following in the root folder.
  (TODO: Update 1st Path in bash snippet)
      dotnet test .\tests\{Add 1st Project Filename}.csproj
  ### Run Integration Tests
  To run the integration tests, execute the following in the root folder.
  (TODO: Update 1st Path in bash snippet)
      dotnet test .\tests\{Add 1st Project Filename}.csproj
  ### Run the Project
  To run the project, execute the following in the root folder.
  (TODO: Update Project path in bash snippet)
      dotnet run --project .\src\{Add Project File Path and Name}.csproj

  ## Environments and Dependencies
  ### Environment Details
  This system is deployed to 3 servers:
  (TODO: Add Dev Environment Details)
  (TODO: Add Test Environment Details)
```




*****

[[category.storage-team]] 
[[category.confluence]] 
