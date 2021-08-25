# StyleCopAnalyzersDemo

This is a demo project to demonstrate how does the StyleCopAnalyzers NuGet package works.

## Set-up:

In order to use it for your project, following steps are need to be done:
1. Install StyleCopAnalyzers NuGet package for your project.
2. Create a .ruleset file and place it inside your project.
3. Add this property to a .csproj file, inside the first PropertyGroup: 
   ```<CodeAnalysisRuleSet>YourRulesetName.ruleset</CodeAnalysisRuleSet>```.
5. Configure individual rules by clicking on .ruleset file two times.
6. When done, rebuild a solution.
7. You should be able to see changes.

## Extra:
- You can configure additonal properties in stylecop.json.
- I picked a .ruleset file from GitExtensions GitHub repository.
- You can configure different rules for tests.
- You can also configure different rules via .editorconfig (using yellow lightbulb when hovering above code and configuring a severity for a specific rule). This file overrules other rules. More info: https://stackoverflow.com/questions/63245342/confused-over-ruleset-files-vs-editorconfig-files

## Sources:
- https://docs.microsoft.com/en-us/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules?view=vs-2019
- https://stackoverflow.com/questions/63245342/confused-over-ruleset-files-vs-editorconfig-files
- https://github.com/DotNetAnalyzers/StyleCopAnalyzers
- https://github.com/DotNetAnalyzers/StyleCopAnalyzers/blob/master/documentation/EnableConfiguration.md

Test change