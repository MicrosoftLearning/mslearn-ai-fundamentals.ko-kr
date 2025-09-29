---
lab:
  title: Azure AI 파운드리 포털에서 Content Understanding을 사용하여 데이터 추출
---

# Azure AI 파운드리 포털에서 Content Understanding을 사용하여 데이터 추출

Azure AI 콘텐츠 이해는 정보 추출을 위해 문서, 오디오 파일, 비디오 및 이미지의 다중 모달 분석을 제공합니다.

이 연습에서는 지능형 애플리케이션을 만들기 위한 Microsoft 플랫폼인 Azure AI Foundry 포털에서 Azure AI 콘텐츠 이해를 사용하여 청구서에서 정보를 추출합니다. 

이 연습은 약 **25**분 정도 소요됩니다.

## 콘텐츠 이해를 위한 Azure AI Foundry 프로젝트 만들기

1. 웹 브라우저에서 [Azure AI 파운드리 포털](https://ai.azure.com)(`https://ai.azure.com`)을 열고 Azure 자격 증명을 사용하여 로그인합니다. 처음 로그인할 때 열리는 팁이나 빠른 시작 창을 닫고, 필요한 경우 왼쪽 위에 있는 **Azure AI 파운드리** 로고를 사용하여 다음 이미지와 유사한 홈페이지로 이동합니다(**도움말** 창이 열려 있는 경우 닫습니다).

    ![Azure AI Foundry 포털 홈페이지 스크린샷](./media/ai-foundry-portal.png)

1. 페이지 아래쪽으로 스크롤하고 **Azure AI 서비스 살펴보기** 타일을 선택합니다.

    ![Azure AI 서비스 살펴보기 타일 스크린샷](./media/ai-services.png)

1. Azure AI 서비스 페이지에서 **콘텐츠 이해 사용해 보기**를 선택합니다.

    ![콘텐츠 이해 사용해 보기 단추 스크린샷](./media/try-content-understanding.png)

1. 콘텐츠 이해 페이지에서 **시작할 프로젝트 만들기**를 선택합니다. 그런 다음, **프로젝트 만들기** 대화 상자에서 권장 리소스 종류(**Azure AI Foundry 리소스**)를 선택합니다.

    ![분석 결과 스크린샷](./media/resource-type.png)

1. **다음** 페이지에서 프로젝트의 올바른 이름을 입력합니다. 그런 다음, **고급 옵션**을 선택하고 다음 설정을 지정합니다.
    - **Azure AI 파운드리 리소스**: *Azure AI 파운드리 리소스의 유효한 이름*
    - **구독**: ‘Azure 구독’
    - **리소스 그룹**: ‘리소스 그룹 만들기 또는 선택’
    - **지역**: 다음 위치 중 하나를 선택하세요\*.
        * 미국 서부
        * 스웨덴 중부
        * 오스트레일리아 동부

    \**이 콘텐츠를 작성할 때는 이러한 지역에서 콘텐츠 이해가 지원되었습니다.*

    ![프로젝트 설정의 스크린샷](./media/content-project-settings.png)

1. **만들기**를 실행합니다. 설정 프로세스가 완료될 때까지 기다립니다. 몇 분이 걸릴 수 있습니다.

## 청구서에서 정보 추출

1. `https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-1.pdf`에서 [contoso-invoice-1.pdf](https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-1.pdf)를 다운로드합니다. 

1. 콘텐츠 이해 페이지에서 **사용해 보기** 탭을 선택한 다음, **청구서 데이터 추출** 타일을 선택합니다.

    ![콘텐츠 이해 "사용해 보기" 페이지의 스크린샷](./media/content-understanding-invoice.png)

    샘플 청구서가 제공됩니다.

1. 샘플 청구서를 선택하고 **분석 실행** 단추를 사용하여 정보를 추출합니다. 분석이 완료되면 결과를 확인합니다.

    ![샘플 청구서를 분석한 결과 스크린샷](./media/sample-invoice-analysis.png)

1. **파일 찾아보기** 링크를 사용하여 이전에 다운로드한 **contoso-invoice-1.pdf** 문서를 업로드하고 해당 파일에 대한 분석을 실행합니다.

    ![Contoso 청구서를 분석한 결과 스크린샷](./media/contoso-invoice-analysis.png)

    콘텐츠 이해 분석기는 이 청구서가 샘플과는 다르게 형식이 지정되어 있더라도 정보를 추출할 수 있습니다.

1. 추출된 필드가 표시되는 위치 오른쪽의 창에서 **결과** 탭을 보고 클라이언트 애플리케이션에 전송될 JSON 응답을 확인합니다. 개발자는 이 응답을 처리하고 추출된 필드를 사용하여 작업을 수행하는 코드를 작성합니다.

    ![Contoso 청구서를 분석한 결과 스크린샷](./media/invoice-analysis-json.png)

## 정리

콘텐츠 이해 서비스에서 작업을 완료한 경우 불필요한 Azure 비용이 발생하지 않도록 이 연습에서 만든 리소스를 삭제해야 합니다.

- Azure Portal에서 이 연습용으로 만든 리소스 그룹을 삭제합니다.
