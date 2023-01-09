- 프로젝트 만들기
  File - new - project
 
- 프로그램 환경파일
  1. Environment 			
	(1). variables 		* 데이터를 사용 후 삭제 / 암호화 필수
	(2). Cookies 
	(3). HTTP Header 	: 기본 헤더에 정보를 추가하고 싶을 때 사용
	(4). Script
	(5). TypeDefinition 
		- Objects : 현재 프로젝트에서 사용하고 있는 컴포넌트
		- Services : Resource Service ( 디자이너 ) 
				  User Service ( 개발자 )
				  *	 form / js / file 
					 통신 url 
		- ProtocolAdaptors 
		- DeviceAdaptors : 음성인식 / 제스처 기능을 등록하여 사용 가능 
				  * 웹환경에서는 사용 불가능 
	(6). Application information 
		- Datasets : 2차원 형태의 데이터를 관리할 수 있는 오브젝트 
		- Variables 
		- Applications 

- Button 이벤트 걸기 
  버튼 클릭 후 4번째 event 창에서 메소드 이름을 입력 
  
- log는 trace() 를 활용하여 확인이 가능함. ex) nexacro.getApplication().trace("안녕하세요");
- 속성의 값을 바꿀 때는 set_text() 를 사용 
 
	* 값을 세팅해줄 때에는 id를 기술하기보다 obj를 사용하는 것이 소스수정에 효과적임
           즉, 메소드안에서 자기 자신의 상태를 변화하고자 할 때는 obj로 접근함 


- 변수 선언의 차이 
	var str1 = "str"; : 스크립트 영역에서만 참조 가능 
	this.str2 = "123"; : 스크립트 영역뿐 아니라 디자인탭, form과 form 사이 활용 가능 
	str3 = "abc"; : 글로벌 변수로 작용하기 때문에 어플리케이션이 실행되는동안 남아있음
			    * 메모리 문제가 발생할 수 있음 

- 저장를 하게되면 Generate가 자동으로 됨. 한번 Generate 된 소스는 원본으로 돌릴 수 없음
	실행하기 위해서는 Generate를 진행해야함. ( 수동 Generate - Application )


/ * 		Tool 사용 		* /

1. code snippet 기능을 이용하여 주로 사용하는 코드를 불러올 수 있다

* 단축키
	- 블럭이동 : ctrl + ] 
	- 블럭선택 : ctrl + shift + ]
	- 블럭주석 : ctrl + / 
	- 주석해제 : alt + / 

2. 버튼 한 개를 가지고 복사할 경우, ctrl + shift + c 를 이용하여 복사 옵션을 선택할 수 있음

3. visiable 속성을 통해 보이지 않게도 가능 

4. 소스를 카피하여 작업하기 마우스오른쪽 - view source



/ * 		Components & Dataset 		* /
1. 종류
	- static : 한 줄에 텍스트
	- button : 클릭 이벤트
	- Edit : 한줄에 텍스트를 입력/출력 ex ) 비밀번호
	- MaskEdit : 정형화된 포멧을 출력할 때 출력. ex) 주민번호(string), 카드번호, 핸드폰 번호 등 
		* 두 가지 속성을 꼭 추가해야함 : type / format {****}  *로 표현하기 
	- Menu : 정렬과 level 설정 필수
	- Div / tab 

2. 동일한 컴포넌트 셋을 불러올 경우 url 에서 원하는 화면의 combo를 선택하여 불러올 수 있음 
3. cssClass 를 통해 동일 디자인을 입힐 수 있음 

4. Dataset 설정과 바인딩 (1) Dataset을 통째로 드래그 하여 input 창안에 넣어 설정 가능 
				    (2) Objects에서 해당하는 데이터 셋을 조회한 후 해당 컬럼을 끌어오기

5. 목록형 컴포넌트의 경우 바인딩 전에 아이템(inner dataset)을 설정하여야 한다 
	inner dataset 설정시 기존의 데이터 셋이 없는 경우, 직접 데이터를 밀어넣을 수 있음 
	property 창에서 innerdataset 설정하기 
6. 그리드내 바인딩 다르게 하기 
	ex ) displaytype : 사용자가 보는 시점 / edittype : 편집시점으로 바꼈을 때의 type 
	       CellMaskEdit 에서 format과 type 설정가능 
	       CellCombo 에서 combodataset (innerdataset) / combocodecol / combodatacol 설정
