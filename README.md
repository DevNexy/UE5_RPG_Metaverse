# UE5_RPG_Metaverse
# 메타버스 게임 클라이언트 개발
![image](https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/343eca48-195c-4470-b2a3-36307ceee0c3)

[시연 동영상](#시연-동영상)

## 요약
- 메타버스 게임 클라이언트 개발

## 역할
- Unreal Engine 5를 활용한 게임 클라이언트 개발
- 안드로이드 빌드 패키징 및 테스트
- UI/UX 구현 및 수정
- 주요 기능 및 시스템 구현
- 리팩토링

## 구현한 기능
- 인트로 씬
- 캐릭터 커스터마이징 UI
- 닉네임 설정 팝업
- 메인메뉴 고정 UI
- 텍스트 채팅 UI
- 인벤토리 기능 구현(장비, 카테고리 별 정렬 등)
- 팝업 시스템 구현
- 설정(옵션) 시스템 구현
- 사운드 (배경, 효과음, Voice) 및 조절 구현
- 사운드 조절 값 저장
- 옵션 값 저장
- 캐릭터 정보 창 구현
- 채널 UI 구현
- 미니맵 및 지도 구현(UV 좌표 사용)
- NPC 대화 시스템 구현(UI 및 데이터 테이블)
- NPC 퀘스트 상호작용

## 사용한 협업 툴
- GitLab
- 소스트리

## 시기
- 프로젝트 진행 기간 (23.04 ~ 23.09)

# 구현한 기능 소개

### <인트로 씬>
<details>
  <summary>순서</summary>
    <ul>
      <li>회사명 출력</li>
      <li>게임명 로고 출력</li>
      <li>인트로 씬 출력</li>
    </ul>
</details>

<details>
  <summary>특징</summary>
    <ul>
      <li>앱을 실행하면 가장 먼저 들어가는 씬</li>
      <li>로고 출력 후 인트로 씬으로 이동</li>
      <li>화면 중앙 하단에 "화면을 터치해주세요" 문구</li>
      <li>화면을 아무 곳이나 터치하면 다음 씬으로 이동</li>
      <li>아바타 정보가 없을 때(첫 접속 일때) : 로딩 후 캐릭터 씬으로 이동</li>
      <li>아바타 정보가 있을 때 : 로딩 후 월드 씬으로 이동</li>
    </ul>
</details>


### <로딩 씬>
<details>
  <summary>특징</summary>
  <ul>
    <li>씬이 변경될 때(로딩) 출력되는 씬</li>
  </ul>
</details>
<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/1cc73b60-a6f0-4d9a-b481-23cef973cd6a" width="50%" height="50%">

### <캐릭터 커스터마이징 UI>
<details>
  <summary>특징</summary>
  <ul>
    <li>아바타 정보가 없을 경우(계정 첫 접속) 이동하게 되는 씬</li>
    <li>기본 아바타와 닉네임을 설정</li>
    <li>성별 선택 가능</li>
    <li>아바타를 커스터마이징 할 수 있는 파츠는 헤어, 상의, 하의, 신발 순으로 구성</li>
    <li>아바타에는 기본적으로 커스터마이징 파츠 별 첫 번째 아이템 착용</li>
    <li>커스터마이징 첫 번째 탭(성별)일 경우, 이전 버튼이 비활성화 처리</li>
    <li>커스터마이징 첫 번째 탭이 아닌 경우, 이전 버튼이 활성화</li>
    <li>다음 버튼을 눌러 커스터마이징 탭을 이동</li>
    <li>마지막 커스터마이징 탭(신발)에서 다음 버튼을 누르면 닉네임 설정으로 이동</li>
  </ul>
</details>

<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/5b75a664-055e-4bce-bce1-9f0cd5a2676c" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/45a04508-ee32-4d6e-87d6-54bce2d561e8" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/40ec3cd2-2fc9-4bb3-b99f-68c023336668" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/5f51c4f0-c5e7-4fdc-94dc-374999995659" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/0e71dc90-643d-4aff-8c35-7411a0fcbef1" width="50%" height="50%">


### <닉네임 설정 기능 및 팝업 UI>
<details>
  <summary>특징</summary>
  <ul>
    <li>마지막 커스터마이징 탭(신발)에서 다음 버튼을 누르면 닉네임 설정창 출력</li>
    <li>닉네임은 중복 확인을 진행</li>
    <details>
      <summary>닉네임 중복 확인 시 알림 문구</summary>
      <ul>
        <li>이미 존재하는 닉네임일 경우 : 이미 존재하는 닉네임입니다.</li>
        <li>사용 가능한 닉네임일 경우 : 사용 가능한 닉네임입니다.</li>
      </ul>
    </details>
    <li>닉네임 중복 확인 후 띄워진 알림 문구들은 닉네임 입력창의 내용이 바뀌면 사라짐</li>
    <li>닉네임 중복 확인 후, 사용할 수 있는 닉네임이라도 닉네임을 재입력 가능 → 내용 변경 시 중복 여부를 다시 진행</li>
    <li>중복 확인을 완료하지 않고 확인 버튼을 누르면 “닉네임 중복 체크를 먼저 진행해주세요.”라는 문구 출력</li>
    <li>닉네임 설정창의 취소 버튼 클릭 시, 닉네임 설정창이 닫히고 아바타 커스터마이징으로 돌아간다.</li>
    <li>중복 체크 완료 후, 확인 버튼을 누르면 “닉네임”(으)로 결정하겠습니까?”라는 문구의 닉네임 결정창이 출력</li>
    <li>닉네임 결정창의 결정 버튼 클릭 시 아바타 및 닉네임 정보가 계정에 저장되고 월드 씬으로 이동</li>
    <li>닉네임 결정창의 취소 버튼 클릭 시, 닉네임 결정창이 닫히고 닉네임 설정창으로 돌아간다.</li>
  </ul>
</details>

<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/e0f2cf32-5985-4158-b718-eb6819deca83" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/5e650172-95df-4223-910a-01739dfcc16c" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/8384fcc4-ac9d-4ca4-b219-e32270e8e08c" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/b05e1cb1-f079-43d8-9d2a-8a4be23561a3" width="50%" height="50%">
 

### <메인메뉴 고정 UI>
<details>
  <summary>기능 버튼 묶음</summary>
  <ul>
    <li>화면 우측 상단에 배치</li>
    <li>구성: 미니맵, 출석 체크, 상점, 인벤토리, 옵션, 퀘스트 리스트</li>
    <li>출석 체크 아이콘과 인벤토리 아이콘의 경우, 해당 기능에 변경 사항이 존재하면 아이콘 좌측 상단에 알림 표시가 생김</li>
    <li>출석 체크 변경 사항 예시 : 출석 체크가 초기화되고, 아직 출석을 하지 않은 경우</li>
    <li>인벤토리 변경 사항 예시 : 새로운 아이템을 획득한 경우</li>
  </ul>
</details>
<details>
  <summary>채널 선택</summary>
  <ul>
    <li>화면 좌측 상단에 배치</li>
    <li>채널을 선택하여 해당 채널로 이동하는 기능</li>
  </ul>
</details>
<details>
  <summary>닉네임 및 보유 포인트</summary>
  <ul>
    <li>화면 좌측 상단에 배치</li>
    <li>닉네임 및 포인트 보유량 확인 가능</li>
  </ul>
</details>
<details>
  <summary>조이스틱</summary>
  <ul>
    <li>화면 좌측 하단에 배치</li>
    <li>플레이어 캐릭터 이동 기능</li>
  </ul>
</details>
<details>
  <summary>채팅 및 음성 채팅 버튼</summary>
  <ul>
    <li>텍스트 채팅 버튼 : 화면 중앙 하단 배치</li>
    <li>음성 채팅 버튼 : 화면 우측 하단 배치</li>
  </ul>
</details>
<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/d7019668-0490-4780-b02f-1d7228233099" width="50%" height="50%">


### <인벤토리>
인벤토리 탭 : 헤어, 상의, 하의, 신발
인벤토리 뒷 배경 : 블러처리된 인게임 배경
<details>
  <summary>인벤토리 주요 기능</summary>
  <ul>
    <li>정렬 기능 X</li>
    <li>첫 번째 슬롯에 장착 중인 아이템 출력</li>
    <li>가장 최근에 획득한 아이템 순으로 두 번째 슬롯부터 출력 (첫 번째는 장착 중인 아이템)</li>
    <li>플레이어가 보유하고 있는 모든 아이템을 확인 가능</li>
    <li>인벤토리가 열리면 첫 번째 탭이 기본으로 선택</li>
    <li>선택된 탭은 푸시 상태의 버튼으로 변경</li>
  </ul>
</details>
<details>
  <summary>장비 기능</summary>
  <ul>
    <li>탭 별로 장착 중인 아이템이 아이템 슬롯 첫 번째에 출력</li>
    <li>장착 중인 아이템의 경우, 장비 표시 이미지 추가</li>
    <li>인벤토리의 아이템을 클릭하면 팝업 출력</li>
    <li>팝업을 통해 아이템을 장착 가능</li>
    <li>아이템 장착 시 탭을 나간 다음 다시 들어왔을 때 새롭게 장착한 아이템이 첫 번째 슬롯에 출력</li>
  </ul>
</details>

<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/8fc9e463-c232-483a-b039-366c62d6420f" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/318fa2b4-820b-4fbe-bce4-2293dd3d50d8" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/a5ef2fce-8ca1-44ea-9329-9fe68597e97d" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/a7a24f91-1164-40d7-a7e7-0773f193ac89" width="50%" height="50%">


### <상점>
<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/0f661141-6aa5-4dc4-a88e-e8a8861577ef" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/a77bd486-a025-4d12-96bd-5062365342de" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/71923bc8-2797-4c7c-b924-8e11b0c8bfda" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/81536c7c-d64a-4af2-9c52-e0c5614caef4" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/7632ca63-e2a9-4a39-ae7e-3b21054e06cc" width="50%" height="50%">


### <텍스트 채팅>
<ul>
  <li>화면 중앙 하단의 버튼을 통해 채팅 UI를 띄울 수 있음</li>
  <li>채팅 버튼을 클릭하여 채팅 UI가 활성화되면, 채팅 버튼의 테두리가 초록색으로 변함</li>
  <li>채팅 UI는 투명도 존재 (채팅 창을 켜도 게임 화면이 보이도록)</li>
  <li>채팅 내용 오른쪽 말풍선은 나 자신, 왼쪽 말풍선은 다른 플레이어</li>
  <li>안드로이드일 경우 채팅 입력 칸을 누르면 가상 키보드가 열리고, 채팅 창이 위로 올라가게 됨</li>
  <li>안드로이드일 경우 가상 키보드 이외의 화면 클릭 시, 가상 키보드가 닫히고 채팅 창이 다시 내려옴</li>
  <li>채팅 UI 우측 상단의 닫기 버튼을 클릭하거나 화면 중앙 하단의 채팅 버튼 클릭 시 채팅 UI 닫힘 → 채팅 버튼의 초록색 테두리 사라짐</li>
</ul>
[window 채팅 화면]   

<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/5780c3be-8ba8-4fe8-b75b-5396b3334037" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/5b87c500-7ce5-45db-831e-330ae6170701" width="50%" height="50%">

[Android 채팅 화면]     
<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/4453e924-1cc9-4ad7-9675-26bf89bdcc14" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/2aad505f-8cea-423c-81bb-b1209fc61436" width="50%" height="50%">


### <팝업 시스템>
인벤토리-아이템 클릭 시  
<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/e2054f1f-957b-47dd-a206-9014585e02dd" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/6aa09c77-4c7f-4ee5-a519-c206b51ba5e8" width="50%" height="50%">
 

상점-아이템 구매 시   
<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/eb0d8fa8-b73b-4d62-9fc0-5f0777517d6b" width="50%" height="50%">


상점-아이템 구매 완료   

<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/52649b9c-5154-4670-a136-32938f95be07" width="50%" height="50%">


상점-아이템 구매 불가   
<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/047fbd94-4bd7-47b4-9bff-cfd27e26a544" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/b31e3351-85d2-4f7a-8554-8cc05327bed4" width="50%" height="50%">


옵션-로그 아웃   
<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/29ad1401-1a33-4717-8f42-7cece3d87089" width="50%" height="50%">

옵션-회원 탈퇴   
<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/7f4150e0-0ed0-4ff4-b652-1fec249b7a7e" width="50%" height="50%">

옵션-게임 종료   
<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/6729d1c4-1c15-4f4f-9b5b-d513016bd5a8" width="50%" height="50%">

채널 변경-채널 이동   
<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/2c672d6e-2f48-4d05-8973-5104faab45d7" width="50%" height="50%">

<details>
  <summary>UI 연출</summary>
  <ul>
    <li>메시지 박스 UI : 중앙에서 사방으로 점점 커지며 나타나는 연출</li>
  </ul>
</details>

### <채널>
<details>
  <summary>기능</summary>
    <ul>
      <li>채널 선택 창에서 다른 채널로 이동 가능</li>
      <li>채널 이름, 접속 중인 채널 인원 확인 가능</li>
      <li>채널을 선택하지 않은 상태라면 이동 버튼 비활성화</li>
    <details>
      <summary>채널 생성 기준</summary>
      <ul>
        <li>게임 내 유저가 아무도 없을 때, 처음으로 유저가 접속한 경우</li>
        <li>현재 존재하는 채널들 모두 수용 가능 인원이 가득 찼을 때</li>
      </ul>
    </details>
    <details>
      <summary>채널 삭제 기준</summary>
      <ul>
        <li>현재 채널에 입장한 유저가 0명일 때</li>
      </ul>
    </details>
    <details>
      <summary>채널 수용 인원이 가득 찬 채널에는 입장 불가</summary>
      <ul>
        <li>가득 찬 채널의 경우, 비활성화 처리(선택 불가) + 인원 수 표시 텍스트를 빨간색으로 강조</li>
      </ul>
    </details>
    <details>
      <summary>현재 내가 있는 채널 버튼의 경우, 푸시 상태로 되어 있음(선택 불가)</summary>
      <ul>
        <li>이동을 원하는 채널 버튼 클릭 시, 해당 채널 버튼의 색상 변경</li>
        <li>채널을 선택하면 이동 버튼 활성화</li>
      </ul>
    </details>
    <details>
      <summary>채널을 선택하고 이동 버튼을 클릭 시, 채널 이동 팝업 창을 띄움</summary>
      <ul>
        <li>확인 버튼 클릭 시 해당 채널로 이동</li>
        <li>취소 버튼 클릭 시 팝업 창 닫힘</li>
      </ul>
    </details>
    <details>
      <summary>채널 선택창 닫기</summary>
      <ul>
        <li>채널 선택 창 우측 상단의 닫기 버튼 클릭 시 채널 선택 창 닫힘</li>
      </ul>
    </details>
  </ul>
</details>
<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/f8e59c24-3ae4-4468-9438-246594292164" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/0276f509-2562-43c5-a2de-da138aebe978" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/59cd7cf7-2576-4a71-b93f-1de67c656a96" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/c3a7bb24-eb17-4d5e-95b8-466ae40e0e2d" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/7e23efea-1b39-4410-a10b-498d71d64e69" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/02fa17e4-25a8-4afc-b540-f3a4c4757a7a" width="50%" height="50%">

### <설정(옵션) 시스템>   
설정 탭 : 사운드 탭 / 알림 탭 / 계정 탭

<details>
  <summary>특징</summary>
  <ul>
    <li>설정 창 출력 시, 설정 창 외 다른 조작 불가</li>
    <li>닫기 버튼 클릭 시, 설정 창 닫힘</li>
  </ul>
</details>
<details>
  <summary>사운드 탭 구성</summary>
  <details>
    <summary>사운드 탭 사운드 게이지 바</summary>
    <ul>
      <li>설정창 출력 시, 사운드 탭이 기본으로 선택</li>
      <li>설정창 출력 시, 뒷 배경이 블러처리 됨</li>
      <li>사운드 게이지 바로 각 사운드 항목의 음량 조절</li>
      <li>게이지 바 설정 변경은 실시간으로 변경 값 저장 및 적용</li>
      <li>최초 진입 시 사운드 음량은 50%가 기본 값</li>
    </ul>
  </details>
  <details>
    <summary>음소거</summary>
    <ul>
      <li>음소거 버튼 체크 시 해당하는 사운드 항목이 음소거</li>
      <li>음소거 시 각 항목의 게이지 바가 비활성화되며 조절 불가</li>
      <li>음소거 된 사운드 항목의 음량 설정 값은 저장</li>
      <li>음소거 버튼 체크 해제 시 사운드 항목이 저장되어 있던 음량 설정 값으로 다시 활성화</li>
      <li>음소거 체크 항목도 텍스트 파일에 저장</li>
    </ul>
  </details>
</details>
<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/0e07ed41-2291-4484-9f68-38dec31877f6" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/926b56ab-079d-4c98-bc13-d964972bd90d" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/e187b8ba-9733-497d-bbec-6b3b3b8cf03f" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/1f590e51-050b-4887-bcca-26d220241d06" width="50%" height="50%">

<details>
  <summary>알림 탭 구성</summary>
  <ul>
    <li>알림 탭 클릭 시 알림 탭 색 변경 및 알림 탭 창으로 변경</li>
    <li>알림 동의는 거부 버튼이 기본으로 선택되어 있음</li>
    <details>
      <summary>동의 버튼 클릭 시</summary>
      <ul>
        <li>동의 확인 창 팝업</li>
        <li>동의 확인 창에서 동의 버튼 클릭 시 알림 창 닫히고 알림 동의 항목의 ‘동의’ 버튼 색 변경 + 체크 아이콘, 하위 설정 항목(공지/이벤트 알림, 피로도 알림)의 켜짐/꺼짐 버튼 활성화</li>
        <li>동의 확인 창에서 거부 버튼 클릭 시 알림 창 닫히고 알림 동의 항목의 ‘거부’ 버튼 유지</li>
        <li>켜짐/꺼짐 버튼은 플레이어가 알림 동의를 하기 전까지 비활성화 유지</li>
        <li>켜짐/꺼짐 버튼 클릭시 버튼 색이 초록색으로 변경되고 체크 박스에 체크 아이콘이 띄워짐</li>
        <li>기존에 체크되어 있던 버튼은 자동으로 체크 해제+회색으로 버튼 색 변경</li>
      </ul>
  </details>
  </ul>
</details>
<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/6e7324d5-8604-4ebc-96b1-13318e10ee35" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/190b793a-3888-4da7-a2b8-43fbb4086450" width="50%" height="50%">

<details>
  <summary>계정 탭 구성</summary>
  <ul>
    <li>계정 탭 클릭 시 계정 탭 색 변경 및 계정 탭 창으로 변경</li>
    <li>계정 탈퇴 버튼 클릭시 화면 중앙에 탈퇴 확인 팝업</li>
    <li>로그아웃 버튼 클릭 시 화면 중앙에 로그아웃 확인 팝업</li>
    <li>게임 종료 버튼 클릭 시 화면 중앙에 게임종료 확인 팝업</li>
  </ul>
</details>
<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/06bbd156-836e-4c35-9c74-6fc0141d3d66" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/86313589-bd34-4e1e-8a95-805e1efb61fb" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/ae543bc5-33fb-4644-af00-40625778c421" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/d49e8773-c9ff-4057-8014-7fa6c3c19dd8" width="50%" height="50%">

<details>
  <summary>UI 연출</summary>
  <ul>
    설정 창 팝업 연출
    <ul>
      <li>백그라운드 화면이 블러처리</li>
      <li>아래에서 위로 점점 페이드 인 되어, 중앙에 위치</li>
    </ul>
  </ul>
  <ul>
    설정 창 닫힘 연출
    <ul>
      <li>화면 중앙에 위치한 설정창이 아래로 점점 페이드 아웃되며, 사라짐</li>
      <li>백그라운드 화면 블러처리 제거됨</li>
    </ul>
  </ul>
</details>


### <NPC 대화 시스템 및 퀘스트 상호작용>
<details>
  <summary>특징</summary>
  <ul>
    <details>
      <summary>진입 방법</summary>
      <ul>
        <li>NPC/오브젝트에게 이동→상호작용 버튼 클릭</li>
      </ul>
    </details>
    <details>
      <summary>UI 구성</summary>
      <ul>
        1. 대화 시작
        <ul>
          <li>기능 표시 UI</li>
          <li>NPC/오브젝트 이름</li>
          <li>상호작용 버튼</li>
        </ul>
        2. 대화 진행(플레이어 선택지)
        <ul>
          <li>플레이어 대화 선택지 버튼</li>
          <li>NPC 대화 창</li>
        </ul>
      </ul>
    </details>
    <details>
      <summary>공통 사항</summary>
      <ul>
        NPC(오브젝트) 범위
        <ul>
          <li>각 범위에 플레이어가 들어갈 경우 혼잣말 및 상호작용 버튼 출력</li>
          <li>혼잣말 범위에 플레이어가 들어올 경우 혼잣말 말풍선 출력</li>
          <li>상호작용 범위에 플레이어가 들어올 경우 상호작용 버튼 나타남 + 혼잣말 포함</li>
        </ul>
      </ul>
    </details>
  </ul>
</details>
<details>
  <summary>구성</summary>
  <ul>
    <details>
      <summary>기능 표시 UI</summary>
      <ul>
        <li>NPC 또는 오브젝트의 기능에 따른 머리 위 UI : 느낌표 UI / 말풍선 UI / 물음표 UI</li>
      </ul>
    </details>
    <details>
      <summary>NPC 또는 오브젝트 이름</summary>
      <ul>
        <li>NPC 또는 오브젝트 머리 위에 상시 나타남</li>
      </ul>
    </details>
    <details>
      <summary>NPC 혼잣말</summary>
      <ul>
        <li>NPC의 혼잣말 범위에 플레이어가 들어간 경우 NPC가 혼잣말 출력</li>
        <li>NPC가 혼잣말 출력 중 범위를 벗어나면, 꺼짐</li>
      </ul>
    </details>
    <details>
      <summary>상호작용 버튼</summary>
      <ul>
        1. 공통
        <ul>
          <li>NPC 또는 오브젝트 상호작용 범위에 플레이어가 들어간 경우 상호작용 버튼 생성</li>
        </ul>
        2. 대화 시작 버튼
        <ul>
          <li>버튼 클릭 시 대화 화면으로 전</li>
        </ul>
      </ul>
    </details>
  </ul>
</details>
<details>
  <summary>대화 화면</summary>
  <ul>
    <details>
      <summary>대화 화면 전환</summary>
      <ul>
        1. 화면 전환 시 고정 UI들이 사라짐
        2. 이후, 대화 화면 UI가 생성
        <ul>
          <li>대화 창</li>
          <li>대화 선택지 UI</li>
        </ul>
      </ul>
    </details>
    <details>
      <summary>NPC 대화 창</summary>
      <ul>
        1. NPC 대화 창은 중앙 하단에 위치
        <ul>
          <li>NPC가 출력하는 대사는 데이터 테이블에 작성</li>
          <li>NPC 대사는 화면을 바라보는 기준 좌에서 우로 한 글자씩 출력</li>
        </ul>
        2. 대화 스킵 기능
        <ul>
          <li>대화 스킵 클릭 시, 대화 화면에서 다시 플레이 화면으로 전환환</li>
        </ul>
      </ul>
    </details>
  </ul>
</details>
<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/52ae6030-b0eb-4d42-934b-0b25658e5462" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/e5839bc3-d00b-4cf4-b7c5-9ec2d3d656b6" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/6338cfa0-8179-4cfc-98e8-53746a5cdb54" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/c0d2c243-1965-4d0d-ba88-16b9d49ef06a" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/dbbf1115-eba5-435e-aa8d-2864a590f51e" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/d08dd3cd-1002-45d1-9130-1f6016f21774" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/a39fecb0-3f8b-4304-a7ca-51589271586b" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/a173e6b5-0e03-49f5-8c99-13e44970eae2" width="50%" height="50%">

### <미니맵, 지도>
<details>
  <summary>특징</summary>
  <ul>
    <details>
      <summary>미니맵</summary>
      <ul>
        <li>메인 메뉴의 미니맵 버튼 클릭 시 미니맵 창 출력</li>
        <li>미니맵 창 출력 시에도 조작 가능</li>
        <li>미니맵 창은 메인 메뉴의 미니맵 버튼으로 토글 형식</li>
      </ul>
    </details>
    <details>
      <summary>지도</summary>
      <ul>
        <li>미니맵 클릭 시 전체 지도 창 출력</li>
        <li>전체 지도 창 출력 시 닫기 버튼 외 다른 조작 불가능</li>
      </ul>
    </details>
  </ul>
</details>
<details>
  <summary>구성</summary>
  <ul>
    <details>
      <summary>미니맵</summary>
      <ul>
        <li>플레이어 방향과 같은 화살표 이미지로 표시</li>
        <li>NPC, 오브젝트, 다른 플레이어 따로 이미지 표시</li>
        <li>미니맵 범위에 벗어나면 이미지 제거</li>
      </ul>
    </details>
    <details>
      <summary>지도</summary>
      <ul>
        <li>플레이어 방향과 같은 화살표 이미지로 표시</li>
        <li>NPC, 오브젝트, 다른 플레이어 따로 표시</li>
      </ul>
    </details>
  </ul>
</details>
<img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/3ef0b176-8e0f-4c20-83d4-0003d148dad5" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/d3448794-f63d-464e-adb8-05fd3d897344" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/aecd46f7-56f6-40e1-b0e7-13210e92d81c" width="50%" height="50%"><img src="https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/fe69bdab-f02d-4616-aa19-71fc5cf469e2" width="50%" height="50%">

# 시연 동영상

[인트로, 커스터마이징](https://youtu.be/i7Z545AtglQ?si=VWKJG_QN0DCNQlZ-)   
[인벤토리, 상점](https://youtu.be/A0Bri6zioo8?si=Yc7NVyPbUmDfMZcq)   
[옵션, 설정](https://youtu.be/nz8lhpG_ag8?si=5F3N7Cf-HaKSRqqj)   
[NPC 대화시스템 및 퀘스트 상호작용](https://www.youtube.com/watch?v=jEwB2ixErGU)   
[채팅](https://youtu.be/cH3fYAEDM4Q)   
[채널 이동](https://youtu.be/5utP6cDGx0g?si=Z_b3Bo-yX9iRFpBP)   
