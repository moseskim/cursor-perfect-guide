# 📕 3장 Cursor 기능 설명

원고를 완성한 이후 변경점에 관해 보충 설명합니다.

## 📘 3.1 Chat（AI 챗 기능）

## 📘 ▼ 챗 모드 전환 🌟New🌟

Interpreter Mode는 버전 0.40, Long Context Chat은 0.43에서 폐기되었습니다. 챗 모드 전환 기능도 폐지되어 있습니다(풀다운이 표시되지 않음).

- Interpreter Mode의 모다 강화된 기능으로 컴포저의 agent 모드가 릴리스되었습니다. 이후 Interpreter Mode를 사용하는 화면에서 컴포저의 agent 모드를 사용합니다. 
- Long Context Chat 폐지 후, 각 모델의 컨텍스트 윈도우까지 챗이나 컴포저가 데이터를 송수신할 수 있는지에 관한 공식적인 언급은 현재까지 없습니다.

## 📘 모델 선택

모델 선택 드롭다운 위에 「Search...」 필드가 추가되었습니다. 모델명의 일부를 입력해 검색할 수 있습니다. 여러 모델 목록에서 원하는 모델로 전환할 때 편리합니다. 이 조작은 Chat, Compose, Cmd K에서 모두 사용할 수 있습니다.

![](../images/models_search.png)


## 📘 파일 피커<sup>file picker</sup> 추가

Cursor 0.40에서 챗 화면이나 조작성이 한층 개선되었고 파일 피커가 추가되었습니다.

![](../images/filepicker.png)

파일 피커는 새로운 기능인 컴포저에 구현되어 있는 기능으로, 업데이트 대상을 지정하는 기능입니다.

이후 설명하는 `@`을 사용한 심볼 참조는 문자 그대로 「참조용」 정보임에 비해 파일 피커를 사용해 선택된 파일은 「업데이트 대상」의 의미를 갑습니다.

![](../images/filepicker_edit.png)

현재, 컴포저와 달리 여러 파일을 대상으로 일괄 변경을 확정할 수는 없습니다. 각 파일별로 「Apply」 조작을 실행해야 합니다.

## 📘 apply above 버튼 추가

수정 코드가 제시되고 「Apply」 버튼이 표시되었을 때 프롬프트 입력 필드 오른쪽 아래 버튼이 「apply above」 버튼으로 표시됩니다. 프롬프트 입력 필드에 커서가 잇는 상태라면 `Cmd(⌘)+Enter`키(macOS) 또는 `ctrl+Enter`키(Windows)를 눌러 적용할 수 있습니다.

![](../images/Chat_Apply.png)

## 📘 Copy Message 버튼 추가

챗 대답 필드에 표시되는 「Copy Message」 버튼을 클릭하면 챗의 대답 내용을 복사할 수 있습니다.

![](../images/CopyMessage.png)


「WILL USE」, 「USED」 필드에 표시되었던 참조 정보는 업데이트 대상 파일과 병렬로 표시됩니다. 

![](../images/chat_ref.png)

![alt text](../images/Chat_Apply.png)

각 참조 정보를 클릭해 내용을 확대해서 표시하거나, 숨길 수 있습니다.

그리고 기존에는 수동으로 지정한 참조 이외에는 삭제할 수 없었지만, 각 참조에 붙어 있는 x 기호를 클릭하면 자유롭게 삭제할 수 있습니다.

![](../images/chat_ref2.png)

## 📘 챗에서 파일 작성 가능

챗에서 파일을 작성할 수 있게 되었습니다.

코드 블록에 파일명이 출력되는 경우, 해당 파일이 존재하지 않으면 「Apply」 버튼을 클릭했을 때 새로 해당 파일을 만듭니다. 파일명은 프롬프트에서 지정사거나 AI 어시스턴트의 제안에 맡길 수 있습니다.

![](../images/chat_file_create.png)

## 📘 Docs 참조

커스텀 Docs 목록 안에 인덱싱된 날짜, 시각이 표시됩니다.

기어 아이콘을 클릭하면 설정 화면의 「Features」 탭 안에서 커스턴 Docs 설정이 표시됩니다(설명 화면에서 인덱싱을 업데이트할 수 있습니다).

![](../images/docs_on_chtat.png)

## 📘 Lint Errors 참조

0.34.2 이후 `@Lint Errors`는 표시되지 않습니다. 이 현상에 관해 공식 포럼, 공식 저장소에 따르면 오류 수정을 수행한 것으로 설명하고 있지만 현재까지 복구되지 않았습니다.

- https://forum.cursor.com/t/is-lint-errors-gone-in-0-34-2/5427
- https://github.com/getcursor/cursor/issues/1470

0.42에서 Lint Errors 참조를 다시 사용할 수 있게 되었습니다. 🌟New🌟

> We have made slight improvements to Debug with AI and added back @Lint Errors in Chat.
- https://changelog.cursor.com/?nightly=true#042---composer-history-lint-errors-vs-code-1931-

## 📘 @Recommended 참조

프롬프트와 의미적 연관성을 탐색하고 연관성이 높은 파일 목록을 제시합니다. 챗, 컴포저에서 사용할 수 있습니다.

1. `@Recommended`를 지정합니다(인덱싱이 완료되어야 합니다).
   
   ![](../images/Recommended1.png)

2. 표시된 파일에서 참조할 파일을 지정합니다.
   
   ![](../images/Recommended2.png) 

## 📘 「Apply」, 「Copy」, 「Reply」 버튼

- 0.40에서 버튼 배열 순서가 변경되었습니다.
- 「Reply」 버튼은 「Ask」 버튼으로 라벨이 변경되었습니다. 기능은 같습니다.
- 「Apply」 버튼은 GPT, Claude, Gemini 등 주요 모델에서 동작합니다(공식 발표는 없지만 로컬에서 동작을 확인했습니다).
  - 「Apply」는 Cursor의 커스텀 모델을 사용하기 때문에 API 키를 사용해 Cursor에 요금을 지불하지 않는 상태에서는 실행할 수 없습니다.

![](../images/ask_button.png)

제안된 코드 블록 아래 흐리게 표시되었던 「Apply」, 「Reply」, 「Copy」 버튼은 표시되지 않습니다.

![](../images/apply_button_lost.png)

## 📘 /edit 명령어

`/edit` 명령어는 Cursor 버전 0.40에서 폐지되었습니다.

현재 새로운 명령어가 추가되어 챗, 컴포저의 프롬프트 입력 필드에서 `/` 기호를 입력하면 「Reset」, 「Reference Open Editors」 등의 명령어가 표시됩니다.

![](../images/edit_command.png)

- 「Reset」 명령어: 해당 챗, 컴포저 섹션 정보를 초기화합니다(빈 챗, 컴포저가 됩니다).
- 「Reference Open Editors」: 에디터에 열려 있는 파일을 포아 파일 피커로 선택한 조작을 합니다.
