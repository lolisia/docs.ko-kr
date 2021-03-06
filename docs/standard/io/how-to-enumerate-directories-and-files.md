---
title: '방법: 디렉터리 및 파일 열거'
description: .NET에서 배열보다 더 나은 성능을 제공할 수 있는 열거 가능한 컬렉션을 사용하여 디렉터리와 파일을 열거하는 방법을 알아봅니다.
ms.date: 12/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
ms.openlocfilehash: 276668f4a3eee89610a81b1256820770d1f72dc3
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662578"
---
# <a name="how-to-enumerate-directories-and-files"></a>방법: 디렉터리 및 파일 열거
열거 가능한 컬렉션은 대규모의 디렉터리 및 파일 컬렉션으로 작업할 때 배열보다 나은 성능을 제공합니다. 디렉터리 및 파일을 열거하려면 디렉터리, 파일 이름이나 해당 <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo> 또는 <xref:System.IO.FileSystemInfo> 개체의 열거할 수 있는 컬렉션을 반환하는 메서드를 사용합니다.  
  
디렉터리 또는 파일의 이름만 검색하고 반환하려면 <xref:System.IO.Directory> 클래스의 열거 메서드를 사용합니다. 디렉터리 또는 파일의 다른 속성을 검색하고 반환하려면 <xref:System.IO.DirectoryInfo> 및 <xref:System.IO.FileSystemInfo> 클래스를 사용합니다.  
  
이러한 메서드의 열거 가능한 컬렉션은 <xref:System.Collections.Generic.List%601>과 같은 컬렉션 클래스의 생성자에 대한 <xref:System.Collections.Generic.IEnumerable%601> 매개 변수로 사용할 수 있습니다.  
  
다음 표에는 열거 가능한 파일 및 디렉터리 컬렉션을 반환하는 메서드가 요약되어 있습니다.  
  
|검색 및 반환하려면|메서드 사용|  
|------------------|-------------------------------------|-------------------|  
|디렉터리 이름|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|디렉터리 정보(<xref:System.IO.DirectoryInfo>)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|파일 이름|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
|파일 정보(<xref:System.IO.FileInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|파일 시스템 항목 이름|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
|파일 시스템 항목 정보(<xref:System.IO.FileSystemInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
|디렉터리 및 파일 이름 |<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  

> [!NOTE]
> 선택적 <xref:System.IO.SearchOption> 열거형의 <xref:System.IO.SearchOption.AllDirectories> 옵션을 사용하면 부모 디렉터리의 하위 디렉터리에 있는 모든 파일을 즉시 열거할 수 있지만, <xref:System.UnauthorizedAccessException> 오류로 인해 열거가 불완전할 수 있습니다. 먼저 디렉터리를 열거한 다음, 파일을 열거하면 이러한 예외를 catch할 수 있습니다.  
  
## <a name="examples-use-the-directory-class"></a>예: 디렉터리 클래스 사용  
  
다음 예제에서는 <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> 메서드를 사용하여 지정된 경로의 최상위 디렉터리 이름 목록을 가져옵니다.  

[!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
[!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  

다음 예제에서는 <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> 메서드를 사용하여 특정 패턴과 일치하는 디렉터리 및 하위 디렉터리의 모든 파일 이름을 재귀적으로 열거합니다. 그런 다음, 각 파일의 각 줄을 읽고 해당 파일 이름 및 경로가 있는 지정된 문자열이 포함된 줄을 표시합니다.

[!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
[!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
## <a name="examples-use-the-directoryinfo-class"></a>예: DirectoryInfo 클래스 사용  
  
다음 예제에서는 <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> 메서드를 사용하여 <xref:System.IO.FileSystemInfo.CreationTimeUtc>가 특정 <xref:System.DateTime> 값보다 이전인 최상위 디렉터리의 컬렉션을 나열합니다.  

[!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs)]
[!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb)]  
  
다음 예제에서는 <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> 메서드를 사용하여 <xref:System.IO.FileInfo.Length>가 10MB를 초과하는 모든 파일을 나열합니다. 이 예제는 먼저 최상위 디렉터리를 열거하여 가능한 권한 없는 액세스 예외를 catch하고 파일을 열거합니다.  

[!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
[!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a>참조

- [파일 및 스트림 I/O](index.md)
