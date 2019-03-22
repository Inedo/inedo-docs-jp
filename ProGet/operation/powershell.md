---
title: PowerShell
keywords: ProGet
sequence: 30
show-related-content: false
---

PowerShellフィードは、PowerShellモジュールを保存することを目的とした特殊なタイプのNuGetフィードです。[PowerShellGet](https://docs.microsoft.com/en-us/powershell/module/powershellget/?view=powershell-6)から直接アクセスできます。

### PowerShellフィードへの公開
PowerShell 5.0以降およびPowerShellGetを使用して、ProGetにPowerShellフィードを簡単に登録して公開できます。

```
インポートモジュールPowerShellGet

Register-PSRepository -Name MyProGetFeed -SourceLocation <ProGetUrl>/nuget/<FeedName>/ -PublishLocation <ProGetUrl>/nuget/<FeedName>/
Publish-Module -Path <ModuleFile> -NuGetApiKey <UserName>:<Password> -Repository MyProGetFeed
```
