# 볼링 게임 점수판
## 진행 방법
* 볼링 게임 점수판 요구사항을 파악한다.
* 요구사항에 대한 구현을 완료한 후 자신의 github 아이디에 해당하는 브랜치에 Pull Request(이하 PR)를 통해 코드 리뷰 요청을 한다.
* 코드 리뷰 피드백에 대한 개선 작업을 하고 다시 PUSH한다.
* 모든 피드백을 완료하면 다음 단계를 도전하고 앞의 과정을 반복한다.

## 온라인 코드 리뷰 과정
* [텍스트와 이미지로 살펴보는 온라인 코드 리뷰 과정](https://github.com/next-step/nextstep-docs/tree/master/codereview)

## 1단계 - 질문 삭제하기 기능 리팩토링
* [X] Question - 삭제 권한 여부 확인 메소드 생성으로 로직 분리
* [X] 답변들을 관리하는 Answers 생성 
* [X] Answer - 삭제 가능 여부 확인 메소드 생성으로 로직 분리
* [X] 삭제 기록 관리하는 DeleteHistories 생성 
* [X] Question - 삭제 설정 로직 분리 
* [X] Answer - 삭제 설정 로직 분리 

## 2단계 - 볼링 점수판 (그리기)
* [X] 볼링 게임 규칙 숙지

#### view 
* [X] 플레이어 이름 입력 
* [X] 각 프레임 출력
* [X] 플레이어 프레임별 게임 결과 표시 출력
* [X] N 프레임 투구 값 입력

#### domain 
* [X] 플레이어 생성 Player(이름)
    * [X] 이름 3글자 생성 제한
    
* [ ] N 프레임 투구 값 유효성 체크
    * [ ] 투구 값 (0 ~ 10) 숫자 입력
    * [ ] 1번째 2번째 투구 합 10 초과 불가
    
* [X] 기본 실행결과판 생성 Bowling Score Board
    * [X] 10 frame (9 NormalFrame + 1 FinalFrame)
    
* [ ] 게임 결과 표시
    * 첫번째 투구 = 초구 , 두번째 투구 = 2구
    * [ ] 초구가 스트라이크이면 투구 한번만, 스트라이크가 아니면 투구 두번 수행
    * [ ] 10 프레임은 스트라이크이거나 스페어이면 한 번을 더 투구 (2구 혹은 3구)
    * [ ] 초구에서 0개 쓰러트리고, 2구에서 스트라이크면 ? "0 | /" 
    * 스트라이크이면 "X", 스페어이면 "9 | /", 미스이면 "8 | 1"
    * 스트라이크(strike) : 프레임의 첫번째 투구에서 모든 핀(10개)을 쓰러트린 상태
    * 스페어(spare) : 프레임의 두번재 투구에서 모든 핀(10개)을 쓰러트린 상태
    * 미스(miss) : 프레임의 두번재 투구에서도 모든 핀이 쓰러지지 않은 상태
    * 거터(gutter) : 핀을 하나도 쓰러트리지 못한 상태. 거터는 "-"로 표시