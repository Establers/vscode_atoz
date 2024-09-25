# vscode_atoz
VSCode C언어 개발 환경을 세팅해보자😊 따라하면 됩니다.

## 1. MinGW64 설치
https://sourceforge.net/projects/mingw/files/

![alt text](image.png)

![alt text]({E6BE91F7-F01E-40D1-B2D4-E2D2008D18D3}.png)

![alt text]({2D52153B-FEEF-43A9-9928-08169A97791E}.png)

### 환경 변수 설정
시스템 변수의 `Path` 에 `C:\MinGW\bin` 을 넣는다.
하실 수 있을거라고 믿습니다.
![alt text]({EA23B7D8-D6BB-40A3-A23F-9772FF27D531}.png)

![alt text]({FC137359-F8B3-45E2-B838-F4A7CAF58219}.png)

### 확인
`g++ --version` 을 CMD에 입력해서 Path 및 MinGW가 정상적으로 설정, 설치가 되었는지 확인한다.
![alt text]({FF3994ED-C00A-4291-8CD2-7339880A8B43}.png)

## 2. VSCode 설치
공식 홈페이지에서 설치한다.
VSCode로 열기 메뉴를 추가하기 위해서 체크를 꼭 하고 넘어간다.
안해도 괜찮지만 귀찮음.

![alt text]({40E31240-0D35-435A-97DD-3C74C34CAD9C}.png)

VSCode를 실행하면 이런 모양이 나온다.
폴더를 열어서 Source 폴더를 선택한다.
> 작업영역을 신뢰하냐고 하면 신뢰한다고 한다.

### C언어 Intellisense 세팅
C언어 문법검사 및 함수 링크 등등 그런 것들을 설정해줘야 한다.
![alt text]({1CCAF41E-3039-4ADF-8DD3-1EB75F501A14}.png)   
`c/c++` 을 ![alt text]({8C68EC84-E55B-4BC1-9D02-21343F9E74C6}.png)
여기서 검색해서 다운로드를 받는다.

#### C/C++ 세팅
너무 내용이 기므로   
기존에 메일로 송부드린 C/C++ Intellisense 를 참고 부탁드립니다.

### Source 열기
![alt text]({64AA0220-F13F-4C27-9BAB-8F927BA9BE44}.png)

탭에서 맨위에서 폴더열기를 클릭한다. 또는 아래 메뉴에서 들어갈 수 있다.
![alt text]({463428D2-FFDA-4C99-B5CE-9684B735575E}.png)

>SourceInsight는 프로젝트 처럼 관리되지만 VSCode는 그냥 폴더를 여는 개념이다. 프로젝트 그런 것이 따로 없다.

![alt text]({0EC1F031-32DB-424E-906E-01B4E55BA165}.png)

#### VSCode 갑분팁
`alt + shift + h` 를 누르면 호출 관계를 찾을 수 있다!
![alt text]({1DC921A3-C18E-4B1F-BF8D-9E39B80B1ABB}.png)
> 마우스 오른쪽 클릭후 메뉴를 클릭해도 된다.

![alt text]({9F886707-C588-4C03-B2AA-97A1CB6CE3C8}.png)   
`모든 참조 찾기`, `호출 계증 구조 표시`  '

##### 검색할 때... 특정 파일 제외 및 포함 시키는 방법
![1]({7EFDE917-A6C5-4ACD-86F9-59E3E2AE36F6}.png)

저기에 원하는 파일 형식 또는 이름을 넣으면 된다. 
> 예로들어, *.c, *.h 를 넣으면 c와 h 파일만 검색되고 제외할 파일에 *.json, *.ts 를 넣으면 저런 파일은 검색에서 제외된다.

특정 단어 위주로 포함되는 함수를 찾을 경우, 정규식을 활용해야한다.   
EncodePacket_MSG_TYPE_Function 을 찾고싶을 경우
![12]({541E8053-2826-41CC-8DF1-A7F567883CFD}.png)
`.*`

![34]({94C067C9-A8ED-41A1-BAE5-EDFBBFDC967D}.png)
![3]({666D426A-C412-4D91-AF45-A78AC3E76F32}.png)
> 이런게 있네욥?

아니면 상단 검색창에 `#EEPROM` 이런식으로 검색하셔도 됩니다.

### 세팅의 개념
- user 세팅(님 세팅)   
    모든 프로젝트에 공통으로 적용되는 설정
    VSCode를 설치한 후 모든 프로젝트에서 동일하게 적용되는 환경을 설정할 때 사용
    예: 테마, 글꼴 크기, 기본 키 바인딩 등.
- 이 폴더에 들어간 세팅 (작업공간 Workspace Settings)    
    특정 프로젝트(폴더)에만 적용되는 설정
    프로젝트별로 다른 설정이 필요할 때 사용
    예: 빌드 명령어, 디버그 설정, 특정 확장 기능의 설정 등.

이 두가지로 나뉩니다.

#### user Settings
![alt text]({29CC475C-96CD-4808-9DAB-13529B113BAE}.png)

![3]({75C4F666-1BAC-4D1E-B6D2-096070E5F839}.png)

이렇게 폰트 등을 수정할 수 있습니다.

프로젝트 컴파일러 설정등은 작업 영역에서 하는 것이 적절합니다.

##### 자동 저장
![313]({9C81348C-A56E-42E1-8E5C-C7165CA23EFE}.png)   
자동저장 같은거는 개인적인 것이니, user settings에 하는 것이 적절합니다.
![441]({93CB46FA-32B9-455A-9BBE-B0F2A1475509}.png)   
600ms 뒤에 저장되는 세팅입니다.

#### 작업영역(Workspace) Settings
![3](image-1.png)    
c/c++ 구성편집을 하면 

![3]({82C4D487-5DC3-49CF-B493-523D2C70CEF5}.png)

`.vscode` 폴더에서 c_cpp_properties.json 이 생성 됩니다. 이 세팅은 작업영역에만 종속적이므로 다른 곳을 열면 적용되지 않습니다.
그래서, 다른 프로젝트를 열 때 이 VSCode를 복사해서 넣고 새로 설정해주는게 마음 편합니다. (e.g. Include Directory 등) 아니면, 그냥 누가 git에 올려두고 아무도 건드리지 않으면 됩니다.

만약에 자동저장 Delay를 누가 작업영역에서
![alt text]({F3F213D0-D3A9-45FB-BD25-2C08BECA5309}.png)   
10003 으로 저장했다면
![1312]({3F96F540-6722-4E2D-B039-F89A3C7A8B87}.png)   
`.vscode` 안에 10003으로 Json 값 세팅이 됩니다.

그렇다면, user와 workspace 중 똑같은 설정에 대해 다른 값이 있다면 어떻게 될까요?   
workspace 세팅이 더 우선순위가 높습니다.
