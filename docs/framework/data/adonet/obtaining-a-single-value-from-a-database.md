---
title: 데이터베이스에서 단일 값 가져오기
description: ADO.NET에서 단일 값을 반환 하는 방법에 대해 알아봅니다. 이 예제 코드는 삽입 된 레코드에 대 한 id 열 값을 반환 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: 9ce29bc1321814bd60cfaacd222fc55a3fbf12ed
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150728"
---
# <a name="obtaining-a-single-value-from-a-database"></a>데이터베이스에서 단일 값 가져오기

테이블이나 데이터 스트림 형식보다는 단순히 단일 값인 데이터베이스 정보를 반환해야 하는 경우가 있습니다. 예를 들어 COUNT ( \* ), SUM (Price) 또는 AVG (Quantity)와 같은 집계 함수의 결과를 반환할 수 있습니다. **Command** 개체는 **ExecuteScalar** 메서드를 사용 하 여 단일 값을 반환 하는 기능을 제공 합니다. **ExecuteScalar** 메서드는 결과 집합에서 첫 번째 행의 첫 번째 열 값을 스칼라 값으로 반환 합니다.  
  
 다음 코드 예제에서는 <xref:System.Data.SqlClient.SqlCommand>를 사용하여 데이터베이스에 새 값을 삽입합니다. 여기서 <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> 메서드는 삽입된 레코드의 ID 열 값을 반환하는 데 사용됩니다.  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a>참고 항목

- [명령 및 매개 변수](commands-and-parameters.md)
- [명령 실행](executing-a-command.md)
- [DbConnection, DbCommand 및 DbException](dbconnection-dbcommand-and-dbexception.md)
- [ADO.NET 개요](ado-net-overview.md)
