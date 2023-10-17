# UE5_RPG_Metaverse
# 메타버스 게임 클라이언트 개발
![image](https://github.com/DevNexy/UE5_RPG_Metaverse/assets/92451281/343eca48-195c-4470-b2a3-36307ceee0c3)

## 요약
- 메타버스 게임 클라이언트 개발

## 역할
- Unreal Engine 5를 활용한 게임 클라이언트 개발
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
<인트로 씬>
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

<로딩 씬>
<details>
  <summary>특징</summary>
  <ul>
    <li>씬이 변경될 때(로딩) 출력되는 씬</li>
  </ul>
</details>

<캐릭터 커스터마이징 UI>
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

<닉네임 설정 기능 및 팝업 UI>
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

<메인메뉴>

<인벤토리>
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

<상점>

<텍스트 채팅>
<ul>
  <li>화면 중앙 하단의 버튼을 통해 채팅 UI를 띄울 수 있음</li>
  <li>채팅 버튼을 클릭하여 채팅 UI가 활성화되면, 채팅 버튼의 테두리가 초록색으로 변함</li>
  <li>채팅 UI는 투명도 존재 (채팅 창을 켜도 게임 화면이 보이도록)</li>
  <li>안드로이드일 경우 채팅 입력 칸을 누르면 가상 키보드가 열리고, 채팅 창이 위로 올라가게 됨</li>
  <li>안드로이드일 경우 가상 키보드 이외의 화면 클릭 시, 가상 키보드가 닫히고 채팅 창이 다시 내려옴</li>
  <li>채팅 UI 우측 상단의 닫기 버튼을 클릭하거나 화면 중앙 하단의 채팅 버튼 클릭 시 채팅 UI 닫힘 → 채팅 버튼의 초록색 테두리 사라짐</li>
</ul>

<팝업 시스템>
인벤토리-아이템 클릭 시
상점-아이템 구매 시
상점-아이템 구매 완료
상점-아이템 구매 불가
옵션-로그 아웃
옵션-회원 탈퇴
옵션-게임 종료
채널 변경-채널 이동
<details>
  <summary>UI 연출</summary>
  <ul>
    <li>메시지 박스 UI : 중앙에서 사방으로 점점 커지며 나타나는 연출</li>
  </ul>
</details>

<설정(옵션) 시스템>   
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
<details>
  <summary>계정 탭 구성</summary>
  <ul>
    <li>계정 탭 클릭 시 계정 탭 색 변경 및 계정 탭 창으로 변경</li>
    <li>계정 탈퇴 버튼 클릭시 화면 중앙에 탈퇴 확인 팝업</li>
    <li>로그아웃 버튼 클릭 시 화면 중앙에 로그아웃 확인 팝업</li>
    <li>게임 종료 버튼 클릭 시 화면 중앙에 게임종료 확인 팝업</li>
  </ul>
</details>
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
