# TypeScript 계산기 프로젝트 (pwd-week3)

## 1. 프로젝트 소개
* TypeScript 기반으로 작성된 웹 계산기입니다.
* 함수들을 사용하여 계산기의 기본 기능을 구현하는 프로젝트입니다. 

## 2. 실행 방법

1. 설치
npm install

2. TypeScript 컴파일 (빌드)
npm run build

3. 빌드 후 html 파일을 웹브라우저로 열면 됩니다.

## 3. 파일별 역할 및 담당 기능
operations.ts: 사칙연산 함수 및, 연산 유효성을 검사해줍니다. 

calculator.ts: 계산 상태(CalculatorState) 관리, 입력 처리(inputDigit), 연산 대기(selectOperator), 계산 완료(equals), 오류 제어 담당을 해줍니다. 

app.ts: 화면(DOM) 렌더링, 이벤트 리스너 연결, 천단위 쉼표 포맷팅 및 오류 표시 담당을 합니다. 

## 4. 실습 결과와 예시 동작
* 기본 사칙연산: 12 + 3 = 15, 12 - 3 = 9 등 정상 동작 (operation.ts)
* 소수점 연산: 0.1 + 0.2 = 0.3 정상 처리 (operation.ts)
* 백스페이스: 입력 중인 마지막 숫자 삭제 (calculatior.ts - handlekey)
* 부호 전환 : 양수/음수 전환 (calculator.ts - handlekey)
* 백분율 (%): 값을 100으로 나눔 (calculator.ts - hanelekey)

* 식 미리보기: pendingExpression() 함수를 이용, 수식을 실시간으로 표시 (calculator.ts)
* 초기화: AC 버튼 클릭시 상태 초기화 및 화면 0 복귀 (clear())

* 오류 발생: divide() 에서 예외 발생 -> state.error 저장 -> "0으로 나눌 수 없습니다" 오류 출력 + 숫자를 누르면 에러 해제, 새로운 입력 시작 (inputDigit())