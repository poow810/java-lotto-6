# 우테코 3주차

# 로또 게임 기능 구현 - 박하운

## 기능 요구 사항

- 로또 번호의 숫자 범위는 1~45
- 1개의 로또 발행 시 6개의 숫자는 서로 중복 x
- 당첨 번호 추천 시 숫자 6개와 보너스 번호 1개를 뽑음
- 당첨은 1등 - 5등까지 있음
    - 1등 : 2,000,000,000원 (6개 일치)
    - 2등 : 30,000,000원 (5개+보너스 일치)
    - 3등 : 1,500,000원 (5개 일치)
    - 4등 : 50,000원 (4개 일치)
    - 5등 : 5,000원 (3개 일치)
- 로또 1장의 가격 : 1000원

## 사용자 입력

- 로또 구입 금액 입력 (1000원 단위)
- 당첨 번호 입력 (번호는 쉼표를 기준으로 구분)
- 보너스 번호 입력

## 사용자 입력 유효성 검증

- 로또 구입 금액이 1,000원으로 나누어 떨어지지 않을 시

—> IllegalArgumentException 발생 “[ERROR] 1,000원 단위로 입력해주세요.”

- 숫자가 아닌 문자 입력 시

—> IllegalArgumentException 발생 “[ERROR] 숫자를 입력해주세요.”

- 당첨 번호 입력 시 쉼표가 없을 때, 6가지 숫자가 아닐 때, 중복된 수 일때, 1~45 사이의 수가 아닐 때

—> IllegalArgumentException 발생

- “[ERROR] 번호는 쉼표로 구분하여 주세요.”
- “[ERROR] 숫자 6개를 입력하여 주세요.”
- “[ERROR] 숫자는 중복되지 않은 수여야 합니다.”
- “[ERROR] 로또 번호는 1 ~ 45 사이의 수여야 합니다.”

## 로또 게임 진행 기능

### Game Setting

- 랜덤 수 생성 및 리스트 오름차순

### Play Game

- 생성된 리스트와 사용자가 입력한 번호 비교
- 보너스 번호 비교

### Decide Winning

- 번호 일치 판단 후 개수 별 당첨금 출력

### Calculate Return

- 총 당첨금 / 로또 구입 금액 * 100% 으로 수익률 계산