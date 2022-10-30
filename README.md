## :mag: [문제 1] 구현할 기능 목록

* 입력값 `validationArr` 함수 생성 
  + 배열 크기(`array.length`)가 2인지 확인.
  + 왼쪽, 오른쪽 값 차이가 1만 나야함.
  + 입력값이 1이상 400이하여야 함. 

* 전체 프로세서관리 `pageGameApp` 함수 생성
  + `validationArr` 함수 통과 후 전체 프로세스를 관리할 함수로 구현
  + 두 값을 받아서 같으면 0, A가 크면 1, B가 크면 2 를 리턴                                                                         

* 수를 받아서 각 자리를 배열로 return 하는 `splitNumber` 함수 구현
  > B안 선택: 변수의 형태가 변형되지 않도록 하는 것이 합산시 오류발생이 낮아 택함.
  + [ ] A안: `split()` 내부 함수로 구현하는 방법
    - 주의사항: 형이 String으로 바뀌는 문제가 발생할 수 있음.
  + [x] B안: 10으로 나눈 나머지로 일자리부터 빼서 배열 구현 하는 방법
    - ~~일자리부터 처리 되긴 하지만 문제없어보임.~~
    - 내부함수 `unshift()`로 자리수 대로 index 위치 맞춰서 구현.

* 배열 더하기 값 반환 `sumArr` 함수 구현
  + 변수 `totalSum` 에 Arr 값만큼 for문 돌면서 더한 후 totalSum 반환 

* 배열 곱하기 값 반환 `mulArr` 함수 구현
  + 변수 `totalMul` 에 Arr 값만큼 for문 돌면서 곱한 후 totalMul 반환

* 값을 받아 최대값을 리턴하는 maxValueCalculator 함수 구현
  > A안 선택: 비교값 크기가 작아 시간복잡도 차이가 없을 것으로 예상하여, 가독성이 더 좋은 `Math.max()`로 택함.
  + [x] A안: `Math.max()`로 각 왼쪽/오른쪽에 더하기/곱하기 값에서 최대값 반환
  + [ ] B안: for문을 사용해서 4번 돌면서 변수 `maxValue` 랑 비교하여 최대값 반환

***

## :mag: [문제 2] 구현할 기능 목록

> B안 선택: A안은 예외상황 발생: "zyelleyyez" > 기대값: "zyz" / 출력값 : "zez"
단계별로 삭제가 되지 않아 문제발생 (1단계에서 'll' 과 'yy'가 먼저 삭제된 후 2단계에서 'eee'가 한번에 지워져야함.)

* [ ] A안 : Stack 배열을 만들어서 한글자씩 중복문자 체크하며, `push()` / `pop()` 으로 채워넣는 방안.
  + 단계별로 삭제가 아닌 앞에서부터 하나씩 소거해가면서 처리.
* [x] B안 : 문자 하나씩 앞에서부터 연속된 글자를 파악 후 단계별로 삭제하는 방안.

* 전체 프로세서 관리 `cryptogramSolver` 함수 생성
  + 문자열을 배열로 담아둘 `cryptogramArr` 변수 생성
  + 연속된 중복문자를 제거할 함수 `removeDuplicatesChar`가 `false`를 반환될 때까지 반복 호출

* 연속된 중복문자를 제거할 함수 `removeDuplicatesChar` 생성

***
## :mag: [문제 3] 구현할 기능 목록

* 전체 프로세서 관리할 `game369App` 함수 생성.

* input의 크기만큼의 Array 생성 후, 각 index의 value는 'index+1'를 넣어서 return 하는 `createNumberArr` 함수 구현.

* 전체 배열을 `join("")`을 통해 한 글자로 합친 후, '3','6','9' 의 각 갯수를 return 하는 `getCount369` 함수 구현.

***
## :mag: [문제 4] 구현할 기능 목록

> A안 선택: A안이 B안보다 간단한 알고리즘 순서도로 그려지고, 클린 코디로 짜기 좋은 방법일 것 같아 채택.

* [X] A안: UTF-16 코드를 활용할 수 있는 내장함수 `String.prototype.charCodeAt(index)`과 `String.fromCharCode(number)`을 사용해서 한 번 에 변경할 수 있는 방법
  예) 'E'의 경우 '`(E).charCodeAt(0)` => 69'가 되며, A인 65와의 차이가 4이기 떄문에, Z인 90에 4를 뺀 86의 값을 `String.fromCharCode(86)` 코드로 읽어오게되면, 'V'가 출력됨.
* [ ] B안: 대소문자 알파벳 배열을 각각 만들어서 입력된 값을 한글자씩 가져와서 대소문자 구분하는 함수를 구현하고, 각 대소문자 순서대로 정렬된 배열에서 위치를 찾아 해당 위치의 역순으로 불러와 나열하는 방법
  예) 'E'의 경우 index 위치가 4이며, 역순으로 `UpperAlphabetArr[-5]`를 불러와서 'V'가 출력됨.

* 전체 프로세서 관리할 `treeFrogApp` 함수 생성.
  + 변수 `eachCharArr`를 함수 `createStringArr`에서 받아온다.
  + 해당 배열 길이만큼 반복해서 한글자씩 변경해준다.

* 입력된 문자열을 배열로 만들어줄 함수 `createStringArr` 생성.
  + 입력된 문자열을 `.split("")`로 한글자씩 나눠서 배열을 만든 후, return 한다.

* 입력된 문자를 UTF16코드로 변경해 줄 함수 `getFromCharToUTF16Code(char)` 를 구현.

* 입력된 UTF16코드를 문자로 변경해 줄 함수 `getFromUTF16CodeToChar(utf16Code)` 를 구현. 

* 입력된 UTF-16 코드가 알파벳인지 판단하는 함수 `checkAlphabet(utf16Code)`
  + 대문자 A : 65 / 대문자 Z : 90 / 소문자 a : 97/ 소문자 z : 122
  + 알파벳이 아니면, `false`를 return 하게 구현.

* 입력된 숫자에 반대되는 문자로 출력해 줄 함수 `getTreeFrogChar(utf16Code)` 를 구현.

* 반대로 저장된 배열을 `.join("")`을 통해 한 문자열로 다시 만든 후, return 하는 `getFromCharArrToString` 를 구현.

***

## :mag: [문제 5] 구현할 기능 목록

* 전체 프로세서 관리할 `withdrawApp` 함수 생성.
  + 각 지폐 종류를 저장하고 있는 `billType`을 선언.
  + `calcWithdraw`에서 return 해주는 잔여금액을 변수 `currAccount`에 저장.
  + `calcWithdraw`에서 return 해주는 지폐 수를 배열 `currBillCount`에 저장.
  + ~~잔여 금액이 0원이 될 때 까지~~,(예외 입력값이 들어올 경우 무한 루프에 빠질 수 있기 때문에 변경함.) billType의 크기만큼, `calcWithdraw`을 호출함.
  + ~~잔여 금액이 0원이 되면,~~ billType의 크기만큼, `curMoney`를 return 한다.

* `money`(현재 금액)과 `billType`(출금할 지폐 크기)를 입력하면, `currAccount`(남은 금액)과 `billCount`(최대 지폐수)를 출력하는 함수 `calcWithdraw`를 구현.

***

## :mag: [문제 6] 구현할 기능 목록

* 입력값 `validationArr` 함수 생성
  + 이메일 중복값 제거
  + 닉네임 한글이 아니면 제거
  + 이메일 `email.com` 아니면 제거
  + 닉네임 길이가 2이상 20자 미만이 아니면 제거
  + 이메일 길이가 11자이상 20자 미만이 아니면 제거

* 전체 프로세서 관리할 `duplicateCheckApp` 함수 생성.
  + 입력된 배열 `CrewDataArr` 길이만큼 계속해서 반복.
  + ~~함수 `getDuplicateDataArr`에 `CrewDataArr`와 `CrewNickName`를 입력 후 함수 반환값을 return 한다.~~
  + `CrewNickName`(닉네임)으로 함수 `getNameByTwoLetterArr`을 호출하여, 출력값을 배열 `TwoLetterNameArr`(닉네임검사리스트)에 저장 
  + `CrewDataArr`(크루데이터)를 하나씩 돌면서 `checkNickNameFromCrewData(CrewDataArr, twoLetter)` 함수의 boolean 값으로 체크한 후, true일 경우, **(+추가) 임시 배열 `delCrewDataIndexArr`에 index 저장 한다.**  
  + 탐색이 완료하면, 배열 `delCrewDataIndexArr`의 데이터 여부를 확인하고, 데이터가 있을 경우, 탐색대상인 크루정보와 함께  `delCrewDataIndexArr`에 저장된 인덱스를 배열 `duplicateDataArr`(중복된 데이터 배열)에 저장하고, `CrewDataArr`(크루데이터)`에서 삭제.
  + return 값 : 배열 `duplicateDataArr`

* 닉네임을 2글자씩 잘라서 배열로 return 해주는 `getNameByTwoLetterArr` 함수 구현.

* `CrewNickName`(닉네임)과 `twoLetter`(중복체크할단어)를 받아서 boolean값으로 출력할 `checkNickNameFromCrewData` 함수 구현.

***

# 미션 - 온보딩

## 🔍 진행 방식

- 미션은 **기능 요구 사항, 프로그래밍 요구 사항, 과제 진행 요구 사항** 세 가지로 구성되어 있다.
- 세 개의 요구 사항을 만족하기 위해 노력한다. 특히 기능을 구현하기 전에 기능 목록을 만들고, 기능 단위로 커밋 하는 방식으로 진행한다.
- 기능 요구 사항에 기재되지 않은 내용은 스스로 판단하여 구현한다.

## 📮 미션 제출 방법

- 미션 구현을 완료한 후 GitHub을 통해 제출해야 한다.
  - GitHub을 활용한 제출 방법은 [프리코스 과제 제출](https://github.com/woowacourse/woowacourse-docs/tree/master/precourse) 문서를 참고해
    제출한다.
- GitHub에 미션을 제출한 후 [우아한테크코스 지원](https://apply.techcourse.co.kr) 사이트에 접속하여 프리코스 과제를 제출한다.
  - 자세한 방법은 [제출 가이드](https://github.com/woowacourse/woowacourse-docs/tree/master/precourse#제출-가이드) 참고
  - **Pull Request만 보내고 지원 플랫폼에서 과제를 제출하지 않으면 최종 제출하지 않은 것으로 처리되니 주의한다.**

## 🚨 과제 제출 전 체크 리스트 - 0점 방지

- 기능 구현을 모두 정상적으로 했더라도 **요구 사항에 명시된 출력값 형식을 지키지 않을 경우 0점으로 처리**한다.
- 기능 구현을 완료한 뒤 아래 가이드에 따라 테스트를 실행했을 때 모든 테스트가 성공하는지 확인한다.
- **테스트가 실패할 경우 0점으로 처리**되므로, 반드시 확인 후 제출한다.

### 테스트 실행 가이드

- 테스트 패키지 설치를 위해 `Node.js` 버전 `14` 이상이 필요하다.
- 다음 명령어를 입력해 패키지를 설치한다.

```bash
npm install
```

- 설치가 완료되었다면, 다음 명령어를 입력해 테스트를 실행한다.

```bash
npm test
```

---

## 🚀 기능 요구 사항

아래의 7가지 기능 요구 사항을 모두 해결해야 한다.

1. [문제 1](docs/PROBLEM1.md)
2. [문제 2](docs/PROBLEM2.md)
3. [문제 3](docs/PROBLEM3.md)
4. [문제 4](docs/PROBLEM4.md)
5. [문제 5](docs/PROBLEM5.md)
6. [문제 6](docs/PROBLEM6.md)
7. [문제 7](docs/PROBLEM7.md)

---

## 🎯 프로그래밍 요구 사항

- Node.js 14 버전에서 실행 가능해야 한다. **Node.js 14에서 정상적으로 동작하지 않을 경우 0점 처리한다.**
- `package.json`을 변경할 수 없고 외부 라이브러리(jQuery, Lodash 등)를 사용하지 않는다. 순수 Vanilla JS로만 구현한다.
- 프로그램 종료 시 `process.exit()`를 호출하지 않는다.
- 프로그램 구현이 완료되면 `ApplicationTest`의 모든 테스트가 성공해야 한다. **테스트가 실패할 경우 0점 처리한다.**
- 프로그래밍 요구 사항에서 달리 명시하지 않는 한 파일, 패키지 이름을 수정하거나 이동하지 않는다.

---

## ✏️ 과제 진행 요구 사항

- 미션은 [javascript-onboarding](https://github.com/woowacourse-precourse/javascript-onboarding) 저장소를 Fork & Clone해 시작한다.
- 과제 진행 및 제출 방법은 [프리코스 과제 제출](https://github.com/woowacourse/woowacourse-docs/tree/master/precourse) 문서를 참고한다.
