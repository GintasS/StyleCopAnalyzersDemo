# StyleCopAnalyzersDemo

This is a demo project to demonstrate how does the StyleCopAnalyzers NuGet package works.

## Set-up:

In order to use it for your project, following steps are need to be done:

1. Install following **NuGet** packages for every project where you want to enforce the rules:
   -  ```StyleCop.Analyzers``` - **(must)**, so that StyleCop rules would work.
   -  ```SonarAnalyzer.CSharp``` - **(optional)**, only if you want to include SonarQube rules.
2. Create a ```.ruleset``` file and place it inside your project/solution folder.
3. Add these properties to a ```.csproj``` file (for every project where you want to enforce the rules), inside the first ```PropertyGroup```: 
   - ```<CodeAnalysisRuleSet>YourRulesetName.ruleset</CodeAnalysisRuleSet>``` - to include your ruleset.
   - ```<EnforceCodeStyleInBuild>true</EnforceCodeStyleInBuild>``` - to enforce some rules that are being ignored by Visual Studio.
4. Alternatively, if you want to use a single ```.ruleset``` file in your Solution, you can use<br>
   ```<CodeAnalysisRuleSet>..\Solution items\YourRulesetName.ruleset</CodeAnalysisRuleSet>```. <br>
   Create a ```Solution items``` root folder first and place the .ruleset file there.<br>
   Also place the ruleset inside Visual Studio's solution folder named ```Solution items```.
5. Configure individual rules by clicking on ```.ruleset``` file two times.
6. When done, rebuild the solution.
7. You should be able to see **Errors/Warnings/Information messages in Error List Window**.

## Extra:
- You can configure additonal properties in stylecop.json.
- I picked a .ruleset file from [GitExtensions](https://github.com/gitextensions/gitextensions) repository.
- You can configure different rules for tests.
- You can also configure different rules via .editorconfig (using yellow lightbulb when hovering above code, to configure a severity for a specific rule). This file overrules other rules. More info: https://stackoverflow.com/questions/63245342/confused-over-ruleset-files-vs-editorconfig-files

## Difference between Sonar and StyleCop

https://medium.com/@michaelparkerdev/linting-c-in-2019-stylecop-sonar-resharper-and-roslyn-73e88af57ebd

Quote from Michael Parker:
> Sonar is, IMO, not a competitor to Stylecop, it is designed for a different purpose and can be used alongside Stylecop. It does deeper analysis of your code than stylecop, so it is (warning: over-generalisation!) less concerned with where you put your braces and more concerned with cyclomatic complexity. 
> 
> You can use both.
Sonar does NOT have automatic fixes for its errors, which might annoy some people as it purely tells you what’s wrong, but doesn’t help you fix it.
>
> Sonar DOES have the ability to rate your code cleanliness, host a central server, track your code over time by integrating into CI. If you want a simple linter with automatic > fixes, StyleCop is what you want. If you want a higher level tracking system for how complex your codebase is over time, and maybe even comparing codebases between teams, and > tracking technical debt, Sonar is what you want. We intend to use both.


## Sources:
- https://docs.microsoft.com/en-us/visualstudio/code-quality/roslyn-analyzers-overview?view=vs-2019
- https://docs.microsoft.com/en-us/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules?view=vs-2019
- https://stackoverflow.com/questions/63245342/confused-over-ruleset-files-vs-editorconfig-files
- https://github.com/DotNetAnalyzers/StyleCopAnalyzers
- https://github.com/SonarSource/sonar-dotnet
- https://github.com/DotNetAnalyzers/StyleCopAnalyzers/blob/master/documentation/EnableConfiguration.md
- https://github.com/DotNetAnalyzers/StyleCopAnalyzers/blob/master/documentation/Configuration.md
- https://github.com/gitextensions/gitextensions/commit/8d2d71ba426dec75e3df2bd3438cbbdcc7581da6#diff-e7e1921c2348699ea66076964a404647435cd2c7550441c3c7a8a156d2826bd1
- https://github.com/dotnet/roslyn/issues/33558
