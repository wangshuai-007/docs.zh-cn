---
title: "如何： 确定文件是否为程序集 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9b69a40bd11425b7e481dc28fddc560c41df3962
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a>如何： 确定文件是否为程序集 (Visual Basic)
当且仅当程序集处于托管状态，并在其元数据中包含程序集条目时，该文件才为程序集。 有关程序集和元数据的详细信息，请参阅主题[程序集清单](https://msdn.microsoft.com/library/1w45z383)。  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a>如何手动确定文件是否为程序集  
  
1.  启动 [Ildasm.exe（IL 反汇编程序）](https://msdn.microsoft.com/library/f7dy01k1)。  
  
2.  加载要测试的文件。  
  
3.  如果 **ILDASM** 报告文件不是可移植的可执行 (PE) 文件，则不是程序集。 有关详细信息，请参阅主题 [How to: View Assembly Contents](../../../../framework/app-domains/how-to-view-assembly-contents.md)（如何：查看程序集内容）。  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a>如何以编程方式确定文件是否为程序集  
  
1.  调用 <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> 方法，传递要测试的文件的完整文件路径和名称。  
  
2.  如果引发 <xref:System.BadImageFormatException> 异常，则该文件不是程序集。  
  
## <a name="example"></a>示例  
 此示例测试 DLL 以查看其是否为程序集。  
  
```vb  
Module Module1  
    Sub Main()  
        Try  
            Dim testAssembly As Reflection.AssemblyName =  
                                Reflection.AssemblyName.GetAssemblyName("C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll")  
            Console.WriteLine("Yes, the file is an Assembly.")  
        Catch ex As System.IO.FileNotFoundException  
            Console.WriteLine("The file cannot be found.")  
        Catch ex As System.BadImageFormatException  
            Console.WriteLine("The file is not an Assembly.")  
        Catch ex As System.IO.FileLoadException  
            Console.WriteLine("The Assembly has already been loaded.")  
        End Try  
        Console.ReadLine()  
    End Sub  
End Module  
' Output (with .NET Framework 3.5 installed):  
'        Yes, the file is an Assembly.  
```
  
 <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> 方法加载测试文件，然后在读取信息之后释放它。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Reflection.AssemblyName>  
 [编程概念](../../../../visual-basic/programming-guide/concepts/index.md)  
 [程序集和全局程序集缓存 (Visual Basic)](index.md)
