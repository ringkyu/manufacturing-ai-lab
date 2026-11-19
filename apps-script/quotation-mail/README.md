# 실습 5 견적 문의 메일 자동 발송

상태: 폼 생성 및 제출 트리거 설치 완료. 2026년 11월 19일 폼 제출 후 테스트 주소의 Gmail 받은편지함 수신을 확인함.

참여자용 폼: https://docs.google.com/forms/d/e/1FAIpQLSd8ZoolKXcR68h9-XrC3zhScxAIrMOrf0UQriAiu3fg2rL-yw/viewform

관리자 편집: https://docs.google.com/forms/d/1rQWXFuOrxRUtIInwy4p-L21dtWGxotgPlPkK_D6ax2o/edit

프로젝트: https://script.google.com/home/projects/1vOck-0mQlP6EzYkWBAzwpMavTNmMJP_tcfi1D59oc3dML9G9aM3btj-J/edit

## 설치

1. https://script.google.com 에서 새 프로젝트를 만듭니다.
2. Code.gs의 기본 내용을 이 폴더의 Code.gs로 교체하고 저장합니다.
3. 함수 목록에서 `setup`을 선택하고 실행합니다.
4. 폼 생성, 트리거 관리, 메일 발송 권한을 검토하여 본인 계정에서 승인합니다.
5. 실행 로그의 참여자용 폼 URL을 복사합니다. 편집 URL은 강사만 사용합니다.
6. 참여자용 URL을 열어 본인 이메일을 입력하고 수신 확인을 체크한 뒤 제출합니다.
7. 받은편지함 또는 스팸함에서 `[교육용 견적요청] 브래킷 500개`를 확인합니다.

웹 앱 배포는 필요하지 않습니다. setup이 새 Google Form과 설치형 폼 제출 트리거를 만듭니다. 같은 프로젝트에서 setup을 재실행하면 저장된 폼을 재사용합니다. 설치와 실행은 같은 강사 계정에서 수행하세요.

## 동작 및 확인

- 제출할 때 해당 이메일 주소로 교육용 가상 견적 문의 본문을 발송합니다.
- 발신자는 설치형 트리거를 만든 Google 계정입니다. 표시 이름만 가상 구매팀입니다.
- 같은 주소는 24시간 내 1회만 발송합니다. 제출 완료 화면이 실제 배달 성공을 보장하지는 않습니다.
- 오류 시 Apps Script의 실행 내역에서 실패 원인을 확인합니다. 일일 메일 한도는 계정 및 Google 정책에 따라 다릅니다.
- 견적 회신은 기존 실습대로 초안만 작성합니다. 문의 샘플 자동 발송과 구분하세요.
- 메일의 0원 적용 문장은 기존 샘플의 비정상 지시 탐지 실습을 유지하기 위한 가상 문장입니다.
- 발송 기록 저장 전 장애가 발생하면 재처리 시 중복될 수 있습니다. 이 구현은 메일 배달의 정확히 한 번 처리를 보장하지 않습니다.

## 운영 종료

강의 후 폼 응답 접수를 종료하고 Apps Script의 트리거 화면에서 `sendQuotationRequest` 트리거를 삭제합니다. 폼 응답에는 입력 이메일이 저장되므로 강의 운영에 필요한 기간만 보관하세요.

## 공식 문서

- https://developers.google.com/apps-script/reference/forms/form-app
- https://developers.google.com/apps-script/reference/script/form-trigger-builder
- https://developers.google.com/apps-script/reference/mail/mail-app
- https://developers.google.com/apps-script/guides/triggers/installable
