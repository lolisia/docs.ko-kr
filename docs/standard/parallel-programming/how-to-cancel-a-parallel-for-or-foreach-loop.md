---
title: '방법: Parallel.For 또는 ForEach 루프 취소'
description: ParallelOptions 매개 변수의 메서드에 취소 토큰 개체를 제공하여 .NET에서 Parallel.For 또는 Parallel.ForEach 루프를 취소합니다.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel foreach loop, how to cancel
- parallel for loops, how to cancel
ms.assetid: 9d19b591-ea95-4418-8ea7-b6266af9905b
ms.openlocfilehash: 0a22794f3c45e685a80d36a42ecd849461936c7b
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769004"
---
# <a name="how-to-cancel-a-parallelfor-or-foreach-loop"></a>방법: Parallel.For 또는 ForEach 루프 취소
<xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> 메서드는 취소 토큰을 사용하는 방법으로 취소 기능을 지원합니다. 일반적으로 취소에 대한 자세한 내용은 [취소](../threading/cancellation-in-managed-threads.md)를 참조하세요. 병렬 루프에서는 <xref:System.Threading.CancellationToken>을 <xref:System.Threading.Tasks.ParallelOptions> 매개 변수의 메서드에 제공하고 try-catch 블록으로 병렬 호출을 묶습니다.  
  
## <a name="example"></a>예제  
 다음 예제는 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>에 대한 호출을 취소하는 방법을 보여줍니다. <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> 호출에 동일한 접근 방식을 적용할 수 있습니다.  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 취소 신호를 보내는 토큰이 <xref:System.Threading.Tasks.ParallelOptions> 인스턴스에 지정된 것과 동일한 토큰이면 병렬 루프에서 취소에 대한 단일 <xref:System.OperationCanceledException>를 throw합니다. 다른 토큰이 취소를 발생시키는 경우 루프에서 <xref:System.OperationCanceledException>이 InnerException으로 설정된 <xref:System.AggregateException>을 throw합니다.  
  
## <a name="see-also"></a>참조

- [데이터 병렬 처리](data-parallelism-task-parallel-library.md)
- [PLINQ 및 TPL의 람다 식](lambda-expressions-in-plinq-and-tpl.md)
