---
lab:
  title: Speech Studio 탐색
---

# Speech Studio 탐색

**Azure AI 음성** 서비스는 음성을 텍스트로 변환하고 텍스트를 음성으로 변환합니다. AI Speech를 사용하여 회의록을 기록하거나 인터뷰 녹음에서 텍스트를 만들 수 있는 애플리케이션을 만들 수 있습니다.

이 연습에서는 Azure AI Speech Studio를 사용하여 Azure AI 음성의 기능을 시험해 봅니다. 

## *Azure AI 음성* 리소스 만들기

**Speech** 리소스 또는 **Cognitive Services** 리소스를 생성하여 Speech 서비스를 사용할 수 있습니다.

이 연습에서는 사용할 수 있는 리소스가 아직 없는 경우 AI Speech 리소스를 만듭니다.

1. 다른 브라우저 탭에서 [Azure AI Speech Studio](https://speech.microsoft.com/)를 열고 Microsoft 계정으로 로그인합니다.

1. **설정**을 선택한 다음 **리소스 만들기**를 선택합니다. 다음 설정을 사용하여 PuTTY를 구성합니다.
    - **새 리소스의 이름** *고유한 이름을 입력합니다*.
    - **구독**: *자신의 Azure 구독*.
    - **지역**: *[지원되는 지역](https://learn.microsoft.com/azure/ai-services/speech-service/regions)을 선택합니다*.
    - **가격 책정 계층**: *무료 FO(사용 가능한 경우, 표준 S0 선택).*
    - **리소스 그룹**: *고유한 이름이 있는 리소스 그룹을 선택하거나 생성*합니다.
1. **리소스 만들기**를 선택합니다. 리소스가 만들어질 때까지 기다린 다음 **리소스 사용**을 선택합니다. 음성 시작 페이지가 표시됩니다.

## Speech Studio에서 음성 텍스트 변환 살펴보기

1. **speech.zip**을 다운로드하려면 [**https://aka.ms/mslearn-speech-files**](https://aka.ms/mslearn-speech-files)을 선택합니다.  폴더를 엽니다. 

1. 음성 시작 페이지의 *음성 텍스트 변환*에서 *실시간 음성 텍스트 변환*을 찾습니다. **실시간 음성 텍스트 변환 사용해 보기**를 선택합니다.

    ![음성 시작](media/recognize-synthesize-speech/try-out-speech-to-text.png)

1. *오디오 파일 선택*에서 **파일 찾아보기**를 선택하고 파일을 저장한 폴더로 이동합니다. **WhatAICanDo.m4a**를 선택한 다음 **열기**를 선택합니다.

    ![파일 찾아보기](media/recognize-synthesize-speech/browse-files-speech.png)

1. 음성 서비스는 텍스트를 실시간으로 기록하고 표시합니다. 컴퓨터에 오디오가 있으면 텍스트가 기록되는 동안 녹음 내용을 들을 수 있습니다.
1. 오디오를 성공적으로 인식하고 텍스트로 변환한 출력을 검토합니다.

    > **참고** 오류 메시지가 표시되면 몇 분 정도 기다린 후 다시 시도합니다. 음성 리소스를 처음 사용할 수 있을 때까지 약간의 시간이 걸립니다.

이 연습에서는 Speech Studio에서 AI Speech 리소스를 만들었습니다. 그런 다음 실시간 음성 텍스트 변환 서비스를 사용하여 오디오 녹음을 텍스트로 변환했습니다. 오디오 파일이 재생되면서 텍스트 대화 기록이 생성되는 것을 볼 수 있었습니다.

## 정리

더 이상 연습할 생각이 없다면 더 이상 필요하지 않은 리소스를 삭제합니다. 이렇게 하면 불필요한 비용이 발생하는 것을 방지할 수 있습니다.

1. [Azure Portal]( https://portal.azure.com)을 열고 만든 리소스가 포함된 리소스 그룹을 선택합니다.
1. 리소스를 선택하고 **삭제**를 선택한 다음 **예**를 선택하여 확인합니다. 그러면 리소스가 삭제됩니다.

## 자세한 정보

이 연습에서는 음성 서비스 기능 중 일부만 보여 주었습니다. 이 서비스를 사용하여 수행할 수 있는 작업을 자세히 알아보려면 [Speech 페이지](https://azure.microsoft.com/services/cognitive-services/speech-services)를 참조하세요.
