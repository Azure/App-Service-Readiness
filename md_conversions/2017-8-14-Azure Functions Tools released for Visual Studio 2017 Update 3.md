---
title: "Azure Functions Tools released for Visual Studio 2017 Update 3"
author_name: Donna Malayeri
layout: post
hide_excerpt: true
---
      [Donna Malayeri](https://social.msdn.microsoft.com/profile/Donna Malayeri)  8/14/2017 11:00:16 AM  We're excited to announce that Azure Functions tools for Visual Studio are out of preview! The tools are now included in the Azure workload of [Visual Studio 2017 Update 3](https://blogs.msdn.microsoft.com/visualstudio/2017/08/14/visual-studio-2017-version-15-3-released/). Just update your existing VS 2017 installation to Update 3--there's no need to use the preview channel or manually install the Functions tooling extension. The tools support building and publishing a class library as the implementation of your functions. Configure bindings and triggers using attributes in your code, rather than a separate metadata file. To get started with the tools, check out these articles:  - [Create your first function using Visual Studio](https://docs.microsoft.com/en-us/azure/azure-functions/functions-create-your-first-function-visual-studio)
 - [Azure Functions Tools for Visual Studio](https://docs.microsoft.com/en-us/azure/azure-functions/functions-develop-vs)
 - [Using .NET class libraries with Azure Functions](https://docs.microsoft.com/en-us/azure/azure-functions/functions-dotnet-class-library)
  Azure Functions Core Tools
--------------------------

 Along with this release is the 1.0 version of the [Azure Functions Core Tools](https://www.npmjs.com/package/azure-functions-core-tools). These are used by the Visual Studio tools when you run or debug a Function App locally. You can also use the Core Tools directly to retrieve app settings from Azure or publish your Function App. To learn more, see [Run locally using the Azure Functions Core Tools](https://docs.microsoft.com/en-us/azure/azure-functions/functions-run-local). [![]({{ site.baseurl }}/media/2017/08/cli-screenshot-300x209.png)]({{ site.baseurl }}/media/2017/08/cli-screenshot.png) What's new in this release
--------------------------

 If you've used the preview tooling, you've probably seen the package [Microsoft.NET.Sdk.Functions](https://www.nuget.org/packages/Microsoft.NET.Sdk.Functions). This package is automatically added by the New Function project template and ensures that generated files are always in sync with your code. In this release, only triggers are generated in function.json. There is a new property in function.json that tells the runtime to use .NET attributes for input and output bindings, rather than function.json configuration: [sourcecode language="plain"] "configurationSource": "attributes" // possible values are "attributes" or "config" [/sourcecode] If the value of **configurationSource** is **attributes**, then the contents of function.json cannot be changed after it is generated. That is because the Functions runtime uses attributes in the assembly to configure bindings and triggers. (If you’re wondering why some properties are still in function.json, it’s because the [Scale Controller uses it to make scaling decisions on the Consumption plan](https://docs.microsoft.com/en-us/azure/azure-functions/functions-scale#how-the-consumption-plan-works).) Functions project type
----------------------

 The Functions project type is a .NET Standard class library though it currently targets **net461**. This is because the Azure Functions runtime does not yet take a dependency on the .NET Standard 2.0 facades that enable full framework support. Now that .NET Standard 2.0 is RTM, we will make this update in a future release. See [Support .NET Standard 2.0 class libraries #1792](https://github.com/Azure/azure-webjobs-sdk-script/issues/1792). Once we have completed the [Azure Functions port to .NET Core 2.0](https://github.com/Azure/Azure-Functions/issues/98), the .NET Standard 2.0 target will become much more important. At that time, we will change the default in the Visual Studio New Project dialog. Learn more
----------

 We’ve seen a great response to our preview tooling and we’re excited to release this version.  - For more product news, follow [@AzureFunctions](https://twitter.com/AzureFunctions).
 - To report bugs or file feature requests, please open an issue on the [Azure-Functions](https://github.com/Azure/Azure-Functions) GitHub repo. Please include “Visual Studio” in the issue title.
 - For technical questions, please post on the [MSDN forums](https://social.msdn.microsoft.com/Forums/azure/en-US/home?forum=azurefunctions) or [StackOverflow](https://stackoverflow.com/questions/tagged/azure-functions). The entire Functions engineering team monitors these questions, so you’re sure to get an expert answer.
       