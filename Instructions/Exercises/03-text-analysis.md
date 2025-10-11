---
lab:
  title: Azure AI 파운드리 포털에서 텍스트 분석
---

# Azure AI 파운드리 포털에서 텍스트 분석

Azure AI 언어에는 엔터티 인식, 핵심 구 추출, 요약 및 감정 분석과 같은 기능을 갖춘 텍스트 분석이 포함되어 있습니다. 예를 들어, 가상의 여행사 Margie's Travel이 고객에게 호텔 숙박에 대한 검토를 제출하도록 권장한다고 가정해 보겠습니다. 언어 서비스를 사용하여 명명된 엔터티를 추출하고, 핵심 구를 식별하고, 텍스트를 요약하는 등의 작업을 할 수 있습니다.

이 연습에서는 지능형 애플리케이션을 만들기 위한 Microsoft 플랫폼인 Azure AI 파운드리 포털의 Azure AI 언어를 사용하여 호텔 리뷰를 분석합니다. 

이 연습에는 약 **20**분이 소요됩니다.

## Azure AI 파운드리 포털에서 프로젝트 만들기

1. 웹 브라우저에서 [Azure AI 파운드리 포털](https://ai.azure.com)(`https://ai.azure.com`)을 열고 Azure 자격 증명을 사용하여 로그인합니다. 처음 로그인할 때 열리는 팁이나 빠른 시작 창을 닫고, 필요한 경우 왼쪽 위에 있는 **Azure AI 파운드리** 로고를 사용하여 다음 이미지와 유사한 홈페이지로 이동합니다(**도움말** 창이 열려 있는 경우 닫습니다).

    ![Azure AI Foundry 포털 홈페이지 스크린샷](./media/ai-foundry-portal.png)

1. 페이지 아래쪽으로 스크롤하고 **Azure AI 서비스 살펴보기** 타일을 선택합니다.

    ![Azure AI 서비스 살펴보기 타일 스크린샷](./media/ai-services.png)

1. Azure AI 서비스 페이지에서 **언어 + 번역기** 타일을 선택합니다.

    ![언어 + 번역기 타일 스크린샷](./media/language-tile.png)

1. **언어 + 번역기** 페이지에서 **언어 플레이그라운드 사용해 보기**를 선택합니다. 그런 다음, 메시지가 표시되면 다음 설정을 사용하여 새 프로젝트를 만듭니다.
    - **프로젝트 이름**: *프로젝트의 올바른 이름을 입력합니다.*
    - **고급 설정**:
        - **구독**: ‘Azure 구독’
        - **리소스 그룹**: ‘리소스 그룹 만들기 또는 선택’
        - **지역**: ***AI Foundry 권장** 지역 선택*
        - **AI Foundry 또는 Azure OpenAI** *유효한 이름으로 새 Azure AI Foundry 리소스 만들기*

1. **만들기**를 실행합니다. 프로젝트가 만들어질 때까지 기다립니다. 몇 분이 걸릴 수 있습니다.

1. 프로젝트가 만들어지면 **언어** 플레이그라운드로 이동됩니다(그렇지 않은 경우 왼쪽의 작업창에서 **플레이그라운드**를 선택하고 거기에서 언어 플레이그라운드 열기).

    언어 플레이그라운드는 일부 Azure AI 언어 기능을 사용해 볼 수 있는 사용자 인터페이스입니다.  

## Azure AI 언어를 사용하여 텍스트 분석

Azure AI 언어는 광범위한 텍스트 분석 기능을 제공합니다.

### Azure AI 파운드리 포털에서 Azure AI 언어를 사용하여 명명된 엔터티 추출

*명명된 엔터티*는 사람, 장소 및 사물을 고유한 이름으로 설명하는 단어입니다. Azure AI 언어의 명명된 엔터티 추출 기능을 사용하여 리뷰에서 정보 유형을 식별해 보겠습니다.

1. 언어 플레이그라운드에서 **정보 추출**을 선택합니다. 그런 다음 **명명된 엔터티 추출** 타일을 선택합니다. 

1. *샘플*에서 다음 리뷰를 입력합니다.

    ```
    Tired hotel with poor service
    The Royal Hotel, London, United Kingdom
    5/6/2018
    This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
    ```

1. **실행**을 선택합니다. 출력을 검토합니다.

    ![언어 플레이그라운드에서 명명된 엔터티 추출 인터페이스의 스크린샷](./media/entity-extraction.png)

    *세부 정보* 섹션에서 추출된 엔터티에 유형 및 신뢰도 점수와 같은 추가 정보가 어떻게 제공되는지 확인합니다. 신뢰도 점수는 식별된 형식이 실제로 해당 범주에 속할 가능성을 나타냅니다.

### Azure AI 파운드리 포털에서 Azure AI 언어를 사용하여 핵심 구 추출

*핵심 구*는 텍스트에서 가장 중요한 정보입니다. Azure AI 언어의 핵심 구 추출 기능을 사용하여 리뷰에서 중요한 정보를 추출해 보겠습니다.

1. 언어 플레이그라운드에서 **정보 추출**을 선택합니다. 그런 다음 **핵심 구 추출** 타일을 선택합니다. 

1. *샘플*에서 다음 리뷰를 입력합니다.

    ```
    Good Hotel and staff
    The Royal Hotel, London, UK
    3/2/2018
    Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
    ```

1. **실행**을 선택합니다. 출력을 검토합니다.

    ![언어 플레이그라운드의 핵심 구 추출 인터페이스 스크린샷](./media/key-phrases.png)

    *세부 정보* 섹션에서 추출된 다양한 구를 확인합니다. 이러한 문구는 텍스트의 의미에 가장 크게 기여합니다.

### Azure AI 파운드리 포털에서 Azure AI 언어를 사용한 텍스트 요약
 
Azure AI 언어의 요약 기능을 살펴보겠습니다.

1. 언어 플레이그라운드에서 **정보 요약**을 선택한 다음 **텍스트 요약** 타일을 선택합니다.

1. *샘플*에서 다음 리뷰를 입력합니다.
    
    ```
    Very noisy and rooms are tiny
    The Lombard Hotel, San Francisco, USA
    9/5/2018
    Hotel is located on Lombard street which is a very busy SIX lane street directly off the Golden Gate Bridge. Traffic from early morning until late at night especially on weekends. Noise would not be so bad if rooms were better insulated but they are not. Had to put cotton balls in my ears to be able to sleep--was too tired to enjoy the city the next day. Rooms are TINY. I picked the room because it had two queen size beds--but the room barely had space to fit them. With family of four in the room it was tight. With all that said, rooms are clean and they've made an effort to update them. The hotel is in Marina district with lots of good places to eat, within walking distance to Presidio. May be good hotel for young stay-up-late adults on a budget
    ```

1. **실행**을 선택합니다. 출력을 검토합니다.

    ![언어 플레이그라운드의 텍스트 요약 인터페이스 스크린샷](./media/summarize-text.png)

    *세부 사항*의 *요약 추출*에서 가장 두드러진 문장에 대한 순위 점수를 확인할 수 있습니다.

### 텍스트의 감정 분석

감정 분석은 호텔 리뷰와 같은 텍스트를 분석할 때 일반적인 작업입니다.

1. 언어 플레이그라운드에서 **텍스트 분류**를 선택합니다. 그런 다음, **감정 분석** 타일을 선택합니다.

1. *샘플*에서 다음 리뷰를 입력합니다.
    
    ```
    Disappointing Stay at The City Hotel
    The City Hotel, London
    9/5/2018
    My experience at The City Hotel in London was far from pleasant. The constant noise from nearby train tracks made it nearly impossible to sleep, with vibrations felt throughout the building. The rooms were outdated, dusty, and poorly maintained—dripping faucets, squeaky beds, and broken fixtures were just the beginning. Sound insulation was nonexistent, so every conversation from neighboring rooms was clearly audible. While the location near public transport was convenient and the staff were friendly, these positives couldn't make up for the overall discomfort and lack of value. I wouldn’t recommend this hotel to anyone seeking a restful or enjoyable stay.
    ```

1. **실행**을 선택합니다. 출력을 검토합니다.

    ![언어 플레이그라운드의 감정 분석 인터페이스 스크린샷](./media/sentiment-analysis.png)

    분석은 각 문장에 대한 전체 감정 점수와 개별 점수를 생성합니다.

## 언어 감지 및 텍스트 번역

Azure AI 언어를 사용하면 텍스트가 기록된 언어를 감지할 수 있습니다. 또한 Azure AI 번역기를 사용하면 텍스트를 한 언어에서 다른 언어로 쉽게 번역할 수 있습니다.

### 언어 검색

먼저 리뷰가 작성된 언어를 감지해 보겠습니다.

1. **텍스트 분류** 창에서 **언어 감지** 타일을 선택합니다.

1. *샘플*에서 다음 리뷰를 입력합니다.
    
    ```
    Un séjour mémorable à l’Hôtel d’Ville
    l’Hôtel d’Ville, Paris
    9/5/2018
    J’ai passé un excellent séjour à l’Hôtel d’Ville à Paris. L’emplacement est idéal, en plein cœur de la ville, ce qui permet de découvrir facilement les principaux sites touristiques. Le personnel était chaleureux, professionnel et toujours prêt à aider. La chambre était propre, confortable et bien équipée, avec une vue charmante sur les rues parisiennes. Le petit-déjeuner était varié et délicieux, parfait pour commencer la journée. Je recommande vivement cet hôtel à tous ceux qui recherchent une expérience parisienne authentique et agréable.
    ```

1. **실행**을 선택합니다. 출력을 검토합니다.

    ![언어 플레이그라운드의 언어 감지 인터페이스 스크린샷](./media/detect-language.png)

    언어가 프랑스어로 감지됩니다. 

### 텍스트 번역

이제 프랑스어 리뷰를 영어로 번역해 보겠습니다.

1. 페이지 맨 위에서 **언어 플레이그라운드** 페이지 제목 옆에 있는 **&larr;**(뒤로) 링크를 사용하여 사용 가능한 모든 플레이그라운드를 확인합니다.
1. 플레이그라운드 목록에서 **번역기 플레이그라운드**를 엽니다.
1. 번역기 플레이그라운드에서 **텍스트 번역**을 선택합니다.
1. **구성** 창에서 다음 언어 옵션을 선택합니다.
    - **번역 전 언어**: 프랑스어
    - **번역 후 언어**: 영어
1. *샘플*에서 프랑스어 리뷰를 입력합니다.
    
    ```
    Un séjour mémorable à l’Hôtel d’Ville
    l’Hôtel d’Ville, Paris
    9/5/2018
    J’ai passé un excellent séjour à l’Hôtel d’Ville à Paris. L’emplacement est idéal, en plein cœur de la ville, ce qui permet de découvrir facilement les principaux sites touristiques. Le personnel était chaleureux, professionnel et toujours prêt à aider. La chambre était propre, confortable et bien équipée, avec une vue charmante sur les rues parisiennes. Le petit-déjeuner était varié et délicieux, parfait pour commencer la journée. Je recommande vivement cet hôtel à tous ceux qui recherchent une expérience parisienne authentique et agréable.
    ```

1. **번역**을 선택합니다. 출력을 검토합니다.

    ![번역기 플레이그라운드의 텍스트 번역 인터페이스 스크린샷](./media/text-translation.png)

    프랑스어 리뷰는 영어로 번역됩니다.

## 정리

더 이상 연습할 생각이 없다면 더 이상 필요하지 않은 리소스를 삭제합니다. 이렇게 하면 불필요한 비용이 발생하는 것을 방지할 수 있습니다.

1. [https://portal.azure.com](https://portal.azure.com)에서 **Azure Portal**을 열고 생성한 리소스가 포함된 리소스 그룹을 선택합니다.
1. **리소스 그룹 삭제**를 선택하고 **리소스 그룹 이름을 입력**하여 확인합니다. 그러면 해당 리소스 그룹이 삭제됩니다.

## 자세한 정보

이 서비스를 사용하여 수행할 수 있는 작업을 자세히 알아보려면 [언어 서비스 페이지](https://learn.microsoft.com/azure/ai-services/language-service/overview)를 참조하세요.
