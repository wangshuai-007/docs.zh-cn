---
title: "如何：使用 LINQ 查询数据库 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9949b5f6f670c66463c42a71434c0cdd941c995b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a>如何：使用 LINQ 查询数据库 (Visual Basic)
语言集成查询 (LINQ)，可以轻松地访问数据库信息和执行查询。  
  
 下面的示例演示如何创建新的应用程序对 SQL Server 数据库执行查询。  
  
 本主题中的示例使用 Northwind 示例数据库。 如果你的开发计算机上没有 Northwind 示例数据库，您可以下载它从[Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web 站点。 有关说明，请参阅[下载示例数据库](https://msdn.microsoft.com/library/bb399411)。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a>若要创建与数据库的连接  
  
1.  在 Visual Studio 中，打开**服务器资源管理器**/**数据库资源管理器**通过单击**服务器资源管理器**/**数据库资源管理器**上**视图**菜单。  
  
2.  右键单击**数据连接**中**服务器资源管理器**/**数据库资源管理器**，然后单击**添加连接**。  
  
3.  指定到 Northwind 示例数据库的有效连接。  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>若要添加包含 LINQ to SQL 文件的项目  
  
1.  在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。 选择 Visual Basic **Windows 窗体应用程序**作为项目类型。  
  
2.  在 **“项目”** 菜单上，单击 **“添加新项”**。 选择**LINQ to SQL 类**项模板。  
  
3.  为 `northwind.dbml` 文件命名。 单击 **“添加”**。 此时，northwind.dbml 文件打开的对象关系设计器 （O/R 设计器）。  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a>若要添加到 O/R 设计器查询的表  
  
1.  在**服务器资源管理器**/**数据库资源管理器**，展开包含到 Northwind 数据库的连接。 展开**表**文件夹。  
  
     如果你已经关闭 O/R 设计器，你可以通过双击前面添加的 northwind.dbml 文件重新打开它。  
  
2.  单击客户表并将其拖到设计器的左窗格中。 单击订单表并将其拖到设计器的左窗格中。  
  
     设计器创建新`Customer`和`Order`为你的项目的对象。 请注意，设计器会自动检测表之间的关系并创建子相关对象的属性。 例如，IntelliSense 将显示`Customer`对象具有`Orders`与该客户相关的所有订单的属性。  
  
3.  保存所做的更改并关闭设计器。  
  
4.  保存你的项目。  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a>若要添加代码以查询数据库并显示结果  
  
1.  从**工具箱**，拖动<xref:System.Windows.Forms.DataGridView>控件拖到你的项目，form1 的默认设置 Windows 窗体。  
  
2.  双击 Form1 以将代码添加到`Load`窗体的事件。  
  
3.  当表添加到 O/R 设计器时，设计器添加<xref:System.Data.Linq.DataContext>为你的项目的对象。 此对象包含必须具有访问这些表，除了单个对象和集合的每个表的代码。 <xref:System.Data.Linq.DataContext>对象命名为你的项目基于.dbml 文件的名称。 对于此项目，<xref:System.Data.Linq.DataContext>对象命名为`northwindDataContext`。  
  
     你可以创建的实例<xref:System.Data.Linq.DataContext>在你的代码和查询表指定由 O/R 设计器。  
  
     以下代码添加到`Load`事件以查询公开为属性的数据上下文的表。  
  
     [!code-vb[VbLINQToSQLHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_1.vb)]  
  
4.  按 F5 运行项目，并查看结果。  
  
5.  以下是你可以尝试一些其他查询：  
  
     [!code-vb[VbLINQToSQLHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_2.vb)]  
    [!code-vb[VbLINQToSQLHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_3.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [查询](../../../../visual-basic/language-reference/queries/queries.md)  
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)  
 [DataContext 方法 （O/R 设计器）](/visualstudio/data-tools/datacontext-methods-o-r-designer)
