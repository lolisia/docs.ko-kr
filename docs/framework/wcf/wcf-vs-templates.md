---
title: WCF Visual Studio 템플릿
ms.date: 03/30/2017
ms.assetid: 6a608575-3535-4190-89da-911e24c8374f
ms.openlocfilehash: 13183ad5f05350c34eebd025eca3faa7d97644f8
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2020
ms.locfileid: "81608025"
---
# <a name="wcf-visual-studio-templates"></a>WCF Visual Studio 템플릿
WCF(Windows 통신 재단) Visual Studio 템플릿은 Visual Studio에서 WCF 서비스 및 주변 응용 프로그램을 신속하게 빌드하는 데 사용할 수 있는 미리 정의된 프로젝트 및 항목 템플릿입니다.  
  
## <a name="using-the-wcf-templates"></a>WCF 템플릿 사용  
 WCF Visual Studio 템플릿은 서비스 개발을 위한 기본 클래스 구조를 제공합니다. 특히 이러한 템플릿은 서비스 계약, 데이터 계약, 서비스 구현 및 구성에 대한 기본 정의를 제공합니다. 이러한 템플릿을 사용하여 최소의 코드 상호 작용만으로 간단한 서비스를 만들 수 있을 뿐만 아니라 고급 서비스에 대한 빌딩 블록을 만들 수 있습니다.  
  
### <a name="wcf-service-library-project-template"></a>WCF 서비스 라이브러리 프로젝트 템플릿  
 WCF 서비스 라이브러리 프로젝트 템플릿은 **시각적 C#\WCF** 및 시각적 **기본\WCF**에서 새 프로젝트 대화 상자에서 사용할 수 있습니다.  
  
 **WCF Service** 템플릿을 사용하여 새 프로젝트를 만들면 새 프로젝트에 다음 세 파일이 자동으로 포함됩니다.  
  
- 서비스 계약 파일(IService1.cs 또는 IService1.vb). 서비스 계약 파일은 WCF 서비스 특성이 적용된 인터페이스입니다. 이 파일은 서비스를 정의하는 방법을 보여 주는 간단한 서비스 정의를 제공하고 매개 변수 기반 작업과 간단한 데이터 계약 샘플을 포함합니다. WCF 서비스 프로젝트를 만든 후 코드 편집기에 표시되는 기본 파일입니다.  
  
- 서비스 구현 파일(Service1.cs 또는 Service1.vb). 서비스 구현 파일은 서비스 계약 파일에 정의된 계약을 구현합니다.  
  
- 애플리케이션 구성 파일(App.config). 구성 파일은 보안 HTTP 바인딩을 통해 WCF 서비스 모델의 기본 요소를 제공합니다. 또한 서비스에 대한 엔드포인트를 포함하고 메타데이터 교환을 활성화합니다.  
  
> [!NOTE]
> Visual Studio는 기본 구성인 [WcfSvcHost.exe(WcfSvcHost.exe)를](wcf-service-host-wcfsvchost-exe.md)사용하여 실행할 때 App.config 파일을 프로젝트의 구성 파일로 인식하도록 구성됩니다. 실행 파일에서 서비스 라이브러리를 호스팅할 경우 DLL의 구성 파일이 유효하지 않게 되므로 구성 코드를 실행 파일의 구성 파일로 이동해야 합니다.  
  
### <a name="wcf-service-application-template"></a>WCF 서비스 애플리케이션 템플릿  
 WCF 서비스 응용 프로그램 템플릿은 **시각적 C#\WCF** 및 **시각적 기본\WCF**에서 새 프로젝트 대화 상자에서 사용할 수 있습니다.  
  
 **WCF 웹 응용 프로그램 서비스** 템플릿을 사용하여 새 프로젝트를 만들 때 프로젝트에는 다음 네 개의 파일이 포함됩니다.  
  
- 서비스 호스트 파일(service1.svc)  
  
- 서비스 계약 파일(IService1.cs 또는 IService1.vb).  
  
- 서비스 구현 파일(Service1.svc.cs 또는 Service1.svc.vb)  
  
- 웹 구성 파일(Web.config)  
  
 템플릿은 가상 디렉터리에 배포할 웹 사이트를 자동으로 만들고 해당 디렉터리에 서비스를 호스트합니다.  
  
### <a name="wcf-web-site-template"></a>WCF 웹 사이트 템플릿  
 WCF 웹 사이트 템플릿은 **시각적 C#\웹 사이트\WCF 서비스** 및 **시각적 기본\웹 사이트\WCF 서비스**아래의 새 프로젝트 대화 상자에서 사용할 수 있습니다. 이 템플릿은 WCF 서비스 애플리케이션 템플릿과 같은 파일을 만들지만 ASP.NET 웹 사이트인 것처럼 정리합니다. App_Code 및 App_Data 폴더가 생성됩니다.  
  
### <a name="wcf-service-item-template"></a>WCF 서비스 항목 템플릿  
 WCF 서비스 항목 템플릿은 기존 Visual Studio 프로젝트에 WCF 서비스를 빠르게 추가할 수 있는 사용자 지정 템플릿입니다.  
  
 이 템플릿을 사용하려면 **솔루션 탐색기** 창으로 이동하여 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 **, 추가를**가리키고 새 항목 **추가** 대화 상자를 실행하려면 **새 항목을** 클릭합니다.  
  
 서비스 인터페이스와 구현 파일은 루트 프로젝트 폴더에 있습니다.  
  
 템플릿은 새 서비스의 구성 섹션과 기존 구성 파일이 호환 가능한 형식인 경우 서로 병합하려고 합니다.  
  
 기존 프로젝트가 웹 프로젝트인 경우 서비스 호스트 파일(service1.svc)도 만들어집니다.  
  
### <a name="wcf-wf-service-project-and-item-template"></a>WCF WF 서비스 프로젝트 및 항목 템플릿.  
 이러한 템플릿은 웹 서비스처럼 액세스할 수 있는 워크플로서비스인 워크플로 서비스를 호스팅하는 WCF 서비스를 만듭니다. XAML 또는 필수 프로그래밍 모델에 대한 별도의 템플릿이 존재합니다. 이 템플릿을 사용하여 순차 또는 상태 시스템 워크플로를 만들 수 있습니다. 이러한 유형의 워크플로에 대한 자세한 내용은 [워크플로 만들기 방법을](../windows-workflow-foundation/how-to-create-a-workflow.md)참조하십시오. 워크플로 프로젝트 만들기에 대한 자세한 내용은 [레거시 워크플로 프로젝트 만들기](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)를 참조하십시오.  
  
 Visual Studio 디자이너는 XOML 형식 워크플로가 코드 기반 워크플로 대신 사용될 때 더 반응성이 높습니다. 만들어지는 기본 워크플로 형식은 XOML 워크플로입니다.  
  
### <a name="wcf-syndication-service-library-template"></a>WCF 배포 서비스 라이브러리 템플릿  
 이 템플릿을 사용하면 RSS 또는 ATOM 형식으로 피드를 WCF 서비스로 노출할 수 있습니다. 자세한 내용은 [WCF 신디케이션](./feature-details/wcf-syndication.md)을 참조하십시오.  
  
#### <a name="changing-the-address-of-the-feed"></a>피드의 주소 변경  
 배포 템플릿은 실행 중에 Internet Explorer를 사용합니다. Visual Studio의 **솔루션 탐색기에서** 프로젝트를 마우스 오른쪽 단추로 클릭하면 **속성을**선택한 다음 **디버그** 탭을 선택하면 템플릿의 기본 주소를 볼 수 있습니다. Internet Explorer는 이 주소에서 피드를 열려고 합니다.  
  
 피드의 주소를 변경하는 경우 **디버그** 탭의 주소도 변경해야 합니다. 이렇게 하지 않으면 Internet Explorer가 기본 주소에서 피드를 열려고 시도하고 실패합니다.  
  
### <a name="ajax-enabled-wcf-service-item-template"></a>AJAX 사용 WCF 서비스 항목 템플릿  
 이 템플릿은 AJAX 컨트롤을 WCF 서비스로 노출합니다. AJAX 컨트롤에 대한 자세한 내용은 [AJAX 제어 설명서를](/aspnet/ajax/)참조하십시오.  
  
### <a name="silverlight-enabled-wcf-service-item-template"></a>Silverlight 사용 WCF 서비스 항목 템플릿  
 이 템플릿은 Silverlight 클라이언트 또는 프런트 엔드에 데이터를 제공하는 웹 서비스를 만듭니다. 템플릿을 웹 사이트 또는 웹 응용 프로그램 프로젝트에 추가하여 Silverlight 클라이언트와의 통신을 지원하는 서비스 코드 및 구성을 포함하는 WCF 서비스를 만들 수 있습니다. 그런 다음 **서비스 참조 추가를** 사용하여 클라이언트에 서비스의 클라이언트 프록시를 추가하고 Silverlight 클라이언트와 Silverlight 지원 WCF 서비스 간에 데이터를 교환할 수 있습니다.  
  
 이 템플릿에 액세스하려면 **솔루션 탐색기에서**웹 사이트 또는 웹 응용 프로그램 프로젝트를 마우스 오른쪽 단추로 클릭하고 **새 항목 추가를**클릭하고 **Silverlight 지원 WCF 서비스를**클릭합니다.  
  
> [!NOTE]
> Silverlight 사용 WCF 서비스는 보안 설정을 사용하지 않고 `basicHttpBinding` 엔드포인트를 노출합니다. 따라서 이 서비스에 연결하는 모든 클라이언트가 서비스에 대한 정보를 얻을 수 있습니다. 서비스와 클라이언트 간에 교환되는 메시지도 서명되거나 암호화되지 않습니다. 엔드포인트를 올바르게 보안하려면 ASP.NET 인증, HTTPS 또는 기타 메커니즘을 사용해야 합니다.  
  
## <a name="see-also"></a>참고 항목

- [WCF 서비스 호스트(WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
- [WCF 테스트 클라이언트(WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)
