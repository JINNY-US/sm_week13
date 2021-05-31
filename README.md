# sm_week13
스마트모바일프로그램설계 13주차

12주차 팀 프로젝트 활동 : https://github.com/Kim-KyungJin/sm_week12   

>앱 실행 링크
>>  


### 팀 구성   
스마트정보통신공학과 201621216 이준석   
스마트정보통신공학과 201921036 김경진   
스마트정보통신공학과 201921054 박유리   
스마트정보통신공학과 201921083 이혜정   
스마트정보통신공학과 201921104 홍수빈    
스마트정보통신공학과 201990009 미르자크메더브 사르더르    

   ***   
### 모든 항목은 변경되거나 삭제될 여지가 있습니다   
   ***   

### 이중필터링(수빈,혜정) 검색 기능 다듬기 (혜정)
>
>> 1. 이중필터링
>>
>> 사용자에게 식당, 카페, 쇼핑 등등 카테고리 별로 원하는 최대소비가격을 입력받고 그 가격에 해당하는 가게들을 카테고리별로 추천해주는 기능에 필요한 이중필터링 부분을 구현했습니다. 
>> 아직 기능 구현만 성공한 상태이며 앱 내에 적용시키는 것은 이번주 안에 해결하려고 합니다.
>>
>> 다음은 그 이중필터링 코드입니다.
>>![카테고리 필터링](https://user-images.githubusercontent.com/79883808/120185149-cac2d000-c24c-11eb-8889-0dcce3031892.PNG)
>> 식당인지 카페인지 등의 카테고리별로 가게를 필터링 하는 부분으로 동작확인, 실행을 위해 type 값을 카페로 넣어, 카테고리 값을 카페로 임의 지정한 상태입니다. 
>> 이 부분은 수정하여 카테고리 별로 type 값에 들어가게 끔 구현할 것입니다. <br>
>> 위처럼 필터링 된 가게 리스트들은 datasnapshot 형태로 ArrayList에 넣어 저장되어 1차 필터링 됩니다. <br><br>
>> 가격 리스트도 위와 똑같이 진행되며, 카테고리와 상관없이 EditText에 입력된 가격 값으로만 필터링됩니다.
>> 즉, 카테고리 상관없이 가게들의 상품 가격과 비교하여 입력된 값보다 작은 상품이 하나라도 있을 시 필터링 됩니다.
>> 이때 필터링된 가게들도 datasnapshot 형태로 카테고리로 필터링된 가게들과 다른 ArrayList에 저장됩니다.
>> 다음은 그 코드입니다. 
>> ![가격 필터링](https://user-images.githubusercontent.com/79883808/120187316-98ff3880-c24f-11eb-8a16-55c4916135bb.PNG)
>> 
>> 다음은 카테고리와 가격, 두 필터링 모두에 해당하는 가게리스트를 뽑아주기 위해 두 ArrayList를 비교하는 부분입니다.
>> ![uid비교](https://user-images.githubusercontent.com/79883808/120187845-512ce100-c250-11eb-84c9-43a0647368eb.PNG) 
>> 각 ArrayList에 있는 가게들의 uid를 비교하여 똑같을 경우, 두 필터링에 해당한다는 뜻이므로 이 가게들은 따로 ArrayLsit에 넣어주었습니다.
>> 이렇게 ArrayList에 모인 가게들은 상품으로 필터링되어서 중복으로 저장되었을 수 있으므로 for문으로 검사를 돌려주었습니다.
>> 필터링까지 되고 검사까지 한 가게리스트들은 ListView에 출력하여 사용자에게 보여줍니다.
>> 다음은 실행영상입니다.

>>[이중필터링](https://user-images.githubusercontent.com/79883808/120190377-7c64ff80-c253-11eb-96f2-f983246d39b5.mp4)

>> 2. 검색 기능 다듬기
>>
>> 상위지역구 spinner 값에 맞는 하위지역구spinner 값들로 변경되지 않아 이부분 수정하였습니다. 
>> 또 검색된 가게 리스트들을 RecycleView에 출력하도록 구현하였는데 클릭이벤트 구현이 비효율적인 것 같아 ListView로 바꾸어주었습니다.
>> 수정한 뒤 리스트 클릭까지 되는 것을 확인할 수 있으며 이번주안에 클릭이벤트까지 구현해서 가게 페이지로 넘어가는 것을 구현할 계획입니다.

>> [검색 기능 다듬기](https://user-images.githubusercontent.com/79883808/120192145-ca7b0280-c255-11eb-9aec-309dffb5c395.mp4)


### 사업자 최초 로그인 시 필수 1회 가게 정보 셋팅(홍수빈)
>> !!깃허브의 업로드 용량 제한으로 인해 외부 프로그램을 이용해 동영상 용량을 강제로 줄인 관계로 화질저하, 워터마크가 포함되었습니다. 양해 부탁드립니다.!!
>> 아래 영상은 사업자로 설정되어있고, 기존에 로그인한적 없는 아이디입니다.(이 메일 인증은 편의상 미리 해둔 상태.) 
>> https://user-images.githubusercontent.com/76034369/120196121-76bee800-c25a-11eb-9a35-59b9f7193395.mp4
>> 유저가 사업자 아이디이고, 최초 로그인일 경우 firebase의 설정값을 확인한 후 로그인 직후 메인페이지의 접속이 아니라 셋팅페이지로 이동합니다. 
>> !화질 문제가 생각보다 심각하여 재녹화, 혹은 다른 프로그램 이용을 통해 문제를 해결 후 재 업로드 하겠습니다. 설명 역시 화질 문제 개선 후 다시 이어서 작성하겠습니다.!


### 태그 선택 유지 기능 추가(수빈, 혜정)
>> https://user-images.githubusercontent.com/76034369/120194378-7de4f680-c258-11eb-8d07-5c1e65176212.mp4 \
>> 기존에는 태그 설정 페이지 접속 시 기존에 설정되어있던 태그들이 초기화된 화면이 보이던 문제를 개선하였습니다. listview로 이루어진 태그를 getCheckedItemPositions()를 이용하여 SparseBooleanArray타입 변수에 담은 후 선택된 값들의 position 값들을 for 문을 이용하여 하나의 string으로 만든 후 그 string을 intent.putExtra를 이용하여 seller setting 페이지로 넘겨주고, 다시 태그 설정 페이지로 이동하는 cardview를 누를 경우 넘겨줬던 string을 다시 받아와 int형 array에 넣은 후 array와 setItemChecked를 이용하여 기존에 체크했던 값들을 다시 true로 변경하여, 체크된 상태를 유지한것처럼 보여줍니다.
>> ![20210531_214830](https://user-images.githubusercontent.com/76034369/120195703-0a43e900-c25a-11eb-8458-e73c65e8d2f5.png)
>>위의 코드가 선택된 position 값들을 string으로 만들고 넘겨주는 부분입니다.
>>![20210531_214852](https://user-images.githubusercontent.com/76034369/120195860-2d6e9880-c25a-11eb-9d9e-e1b69ad7b862.png)
>>string을 받아와서 setItemChecked 해주는 부분입니다.

### 광고 설정 바꾸기 (이준석)

![메인 엑티비티 2](https://user-images.githubusercontent.com/79889548/120197278-c2be5c80-c25b-11eb-80b8-f0ee628050c7.PNG)

![메인 엑티비티3](https://user-images.githubusercontent.com/79889548/120197287-c3ef8980-c25b-11eb-8515-f0c93e37bde0.PNG)

![메인 엑티비티 4](https://user-images.githubusercontent.com/79889548/120197291-c4882000-c25b-11eb-8198-c960b8b7db10.PNG)


지난번에는 회원가입 화면에 버튼이 잇어서 광고화면이 잘 안보였는데 .. 전면광고로 만들었습니다.
그리고 Join Activity 에는 광고 화면 설정 , 광고 초기화 함수 , 광고 에러 설정을 했습니다. 

실행 화면입니다 .

![interstitialAd](https://user-images.githubusercontent.com/79889548/120197294-c4882000-c25b-11eb-9514-64c6a77f2afb.PNG)

### 구글 인앱 결제(샤르더르)

![KakaoTalk_1](https://user-images.githubusercontent.com/79889548/120198824-85f36500-c25d-11eb-9e60-432d503e978c.png)

![KakaoTalk_2](https://user-images.githubusercontent.com/79889548/120198830-87bd2880-c25d-11eb-969e-39abfad1eace.png)

![KakaoTalk3](https://user-images.githubusercontent.com/79889548/120198832-87bd2880-c25d-11eb-9937-f992152934d7.png)

실행화면 입니다. 

![KakaoTalk4](https://user-images.githubusercontent.com/79889548/120198834-8855bf00-c25d-11eb-8043-86db43ef1906.png)




