---
title: ".NET Framework 应用程序中的 COM 互操作性 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d9347f7771e0e86f9a19cbec94ef59dcf1bdb250
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a>.NET Framework 应用程序中的 COM 互操作性 (Visual Basic)
如果你想要在同一个应用程序中使用 COM 对象和.NET Framework 对象，你需要处理中的对象在内存中的存在的差异。 .NET Framework 对象位于托管内存-由公共语言运行时控制的内存 — 和根据需要可由运行时移动。 COM 对象位于非托管内存中，不应将移至另一个内存位置。 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]与[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]提供工具以控制这些交互托管和非托管组件。 有关托管代码的详细信息，请参阅[公共语言运行时](../../../standard/clr.md)。  
  
 除了使用.NET 应用程序中的 COM 对象，可能还想要使用[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]开发可从 com。 通过非托管代码访问的对象  
  
 此页上的链接提供有关 COM 和.NET Framework 对象之间的交互的详细信息。  
  
## <a name="related-sections"></a>相关章节  
 [COM 互操作](../../../visual-basic/programming-guide/com-interop/index.md)  
 提供到包含在 Visual Basic 中，包括 COM 对象、 ActiveX 控件，Win32 Dll，托管的对象和 COM 对象的继承的 COM 互操作性的主题的链接。  
  
 [COM 互操作包装错误](/cpp/misc/com-interop-wrapper-error)  
 如果项目系统无法创建特定组件的 COM 互操作性包装，描述的结果和选项。  
  
 [与非托管代码交互操作](https://msdn.microsoft.com/library/sd10k43k)  
 简要介绍了一些托管和非托管代码之间的交互问题并提供进一步学习的链接。  
  
 [COM 包装](../../../framework/interop/com-wrappers.md)  
 讨论运行时可调用包装器，它允许托管的代码调用 COM 方法调用，以及 COM 可调用包装器，它允许 COM 客户端调用.NET 对象的方法。  
  
 [高级 COM 互操作性](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 提供到包含 COM 互操作性方面包装、 异常、 继承、 线程、 事件、 转换和封送处理的主题的链接。  
  
 [Tlbimp.exe（类型库导入程序）](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)  
 讨论的工具，可用于将转换到公共语言运行时程序集中的等效定义 COM 类型库中找到的类型定义。
