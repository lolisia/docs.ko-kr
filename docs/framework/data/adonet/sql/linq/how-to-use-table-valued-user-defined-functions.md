---
title: '방법: 테이블 반환 사용자 정의 함수 사용'
description: 다음 예를 사용 하 여 단일 행 집합을 반환 하는 테이블 반환 함수를 만드는 방법을 배울 수 있습니다. 이러한 테이블 반환 함수는 테이블과 동일 하 게 사용 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a4ae2b4-3290-4aa1-bc95-fc70c51b54cf
ms.openlocfilehash: 68a2b54c8fd541595d36bf9c864257b1be1f7856
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203581"
---
# <a name="how-to-use-table-valued-user-defined-functions"></a>방법: 테이블 반환 사용자 정의 함수 사용

테이블 반환 함수에서는 여러 결과 모양을 반환할 수 있는 저장 프로시저와 달리 단일 행 집합을 반환합니다. 테이블 반환 함수의 반환 형식은 `Table`이기 때문에 테이블을 사용할 수 있는 SQL의 위치인 어디에나 테이블 반환 함수를 사용할 수 있습니다. 또한 테이블 반환 함수를 테이블로 처리할 수 있습니다.  
  
## <a name="example"></a>예제  

 다음 SQL 함수는 `TABLE`을 반환한다는 것을 명시적으로 나타냅니다. 따라서 반환된 행 집합 구조는 암시적으로 정의됩니다.  
  
```sql
CREATE FUNCTION ProductsCostingMoreThan(@cost money)  
RETURNS TABLE  
AS  
RETURN  
    SELECT ProductID, UnitPrice  
    FROM Products  
    WHERE UnitPrice > @cost  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 함수를 다음과 같이 매핑합니다.  
  
 [!code-csharp[DLinqUDFS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#1)]
 [!code-vb[DLinqUDFS#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#1)]  
  
## <a name="example"></a>예제  

 다음 SQL 코드에서는 함수에서 반환하는 테이블에 조인하거나 테이블 반환 함수를 원하는 다른 테이블로 처리할 수 있음을 보여 줍니다.  
  
```sql
SELECT p2.ProductName, p1.UnitPrice  
FROM dbo.ProductsCostingMoreThan(80.50)  
AS p1 INNER JOIN Products AS p2 ON p1.ProductID = p2.ProductID  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 쿼리는 다음과 같이 렌더링됩니다.  
  
 [!code-csharp[DLinqUDFS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#2)]
 [!code-vb[DLinqUDFS#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>참고 항목

- [사용자 정의 함수](user-defined-functions.md)
