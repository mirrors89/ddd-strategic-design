# 키친포스

## 요구 사항

### 상품

* 상품을 등록할 수 있다.
* 상품의 가격이 올바르지 않으면 등록할 수 없다.
    * 상품의 가격은 0 원 이상이어야 한다.
* 상품의 목록을 조회할 수 있다.

### 메뉴 그룹

* 메뉴 그룹을 등록할 수 있다.
* 메뉴 그룹의 목록을 조회할 수 있다.

### 메뉴

* 1 개 이상의 등록된 상품으로 메뉴를 등록할 수 있다.
* 메뉴의 가격이 올바르지 않으면 등록할 수 없다.
    * 메뉴의 가격은 0 원 이상이어야 한다.
    * 메뉴에 속한 상품 금액의 합은 메뉴의 가격보다 크거나 같아야 한다.
* 메뉴는 특정 메뉴 그룹에 속해야 한다.
* 메뉴의 목록을 조회할 수 있다.

### 테이블

* 테이블을 등록할 수 있다.
* 테이블의 목록을 조회할 수 있다.
* 빈 테이블 설정 또는 해지할 수 있다.
* 단체 지정된 테이블은 빈 테이블 설정 또는 해지할 수 없다.
* 주문 상태가 조리 또는 식사인 테이블은 빈 테이블 설정 또는 해지할 수 없다.
* 방문한 손님 수를 입력할 수 있다.
* 방문한 손님 수가 올바르지 않으면 입력할 수 없다.
    * 방문한 손님 수는 0 명 이상이어야 한다.
* 빈 테이블은 방문한 손님 수를 입력할 수 없다.

### 단체 지정

* 2 개 이상의 빈 테이블을 단체로 지정할 수 있다.
* 단체 지정은 중복될 수 없다.
* 단체 지정을 해지할 수 있다.
* 단체 지정된 테이블의 주문 상태가 조리 또는 식사인 경우 단체 지정을 해지할 수 없다.

### 주문

* 1 개 이상의 등록된 메뉴로 주문을 등록할 수 있다.
* 빈 테이블에는 주문을 등록할 수 없다.
* 주문의 목록을 조회할 수 있다.
* 주문 상태를 변경할 수 있다.
* 주문 상태가 계산 완료인 경우 변경할 수 없다.

## 용어사전

|한글명|영문명|설명|
|---|---|---|
|고객|Guest|매장에 식사하러 온 사람으로, 1명 이상 입장한다.|
|고객의 수|Number of Guests|매장에 식사하러 온 일행이다. 같은 주문테이블에 앉거나, 단체석에 앉을 수 있다.|
|매장|Place|음식을 조리, 식사를 할 수 있는 공간이다.|

|한글명|영문명|설명|
|---|---|---|
|상품|Product|매장에서 요리 할 수 있는 제품이다|
|상품명|Product Name|상품의 이름으로, 상품이름이 겹치면 안된다.|
|상품번호|Product Index|상품에 부여하는 고유한 자연수이다.|
|상품가격|Product Price|상품의 가격으로, 상품의 가격은 1원 이상이다.|

|한글명|영문명|설명|
|---|---|---|
|메뉴|Menu|메뉴판에서 고객이 주문하는 단위. 상품의 조합으로 구성되어있다|
|메뉴판|MenuBoard|매장에서 주문 할 수 있는 메뉴목록|
|메뉴번호|Menu Index|메뉴에 부여하는 고유한 자연수이다.|
|메뉴구성상품|Menu Product|메뉴를 구성하는 상품이다. 상품을 적어도 하나 가진다.|
|메뉴가격|Menu Price|메뉴가격은 1원 이상이고, 메뉴구성상품의 상품가격의 총합을 초과할 수 없다.|
|메뉴그룹|MenuGroup|메뉴를 분류해놓은 그룹이다.|
|메뉴그룹번호|MenuGroup Index|메뉴그룹에 부여하는 고유한 자연수이다.|

|한글명|영문명|설명|
|---|---|---|
|주문서|Orders|고객이 요청한 주문을 의미한다.|
|주문한메뉴|Order Menus|고객이 주문한 메뉴로, 한가지 이상의 메뉴를 중복없이 주문한다.|
|주문번호|Order Index|주문에 부여하는 고유한 자연수이다.|
|주문정보|Order Info|주분번호, 주문테이블 번호, 주문상태, 주문시간, 주문목록이 적혀있다.|
|주문상태|Order Status|고객이 주문한 주문의 처리상태를 의미한다. 주문상태는 조리중 -> 식사중 -> 식사완료 순으로 변경 할 수 있다.|
|조리중|COOKING|고객이 음식을 주문한 다음 설정되는 상태로, 음식이 고객에게 전달되기 전 까지 상태를 의미한다.|
|식사중|MEAL|음식이 고객에게 전달 된 상태를 의미한다.|
|식사완료|COMPLETION|고객이 음식을 다 먹고, 계산을 완료한 상태를 의미한다.|
|주문테이블|Order Table|물리적 테이블에 대치되는 POS기 상의 테이블 개체. 주문테이블에는 단체석번호, 고객의 수, 주문테이블 상태를 기록한다.|
|주문테이블상태|Order Table Status|주문테이블의 상태를 나타낸다. 점유중, 비어있음으로 나타 낼 수 있다.|
|점유중|Occupied|고객이 자리에 앉아 있는 상태를 의미한다.|
|비어있음|Empty|고객이 식사를 마치고 주문테이블에서 이탈한 상태를 의미한다.|
|단체석|Table Group|주문을 완료한 고객이 요청 할 경우 단체석으로 지정해 관리 할 수 있다. 단체석은 두 테이블 이상인 경우에 지정 할 수 있다. 단체석으로 지정해도 주문은 주문테이블 별로 따로 한다.|
|단체석번호|TableGroupId|단체석에 부여하는 고유한 자연수이다.|
|단체석지정해제|Release GroupTable|단체석 지정을 해제한다. 단체석에 포함된 모든 주문테이블의 상태가 비어있음 일 때, 단체석 지정을 해지 할 수 있다.|
|빈테이블|Empty Table|주문테이블의 상태가 비어있음인 테이블을 빈테이블이라 한다.|

## 흐름도

- 상품
    1. 상품이름과 상품가격을 입력한다.
    2. 상품 등록을 요청한다.

- 메뉴
    1. 메뉴이름, 메뉴가격을 입력한다. 메뉴그룹을 지정한다. 메뉴구성상품을 입력한다.
    1. 메뉴 등록을 요청한다.

- 메뉴그룹
    1. 메뉴그룹 등록을 요청한다.

- 주문
    1. 빈 테이블를 선택한다.
    2. 고객은 메뉴판에 있는 메뉴를 선택한다.
    3. 주문상태를 조리중으로 설정한다.
    4. 주문목록에 고객의 주문을 기록한다.
    5. 고객의 수가 변경 될 수 있다.
    6. 고객이 단체석 지정을 요청하면 단체석으로 지정한다.
    7. 음식이 나오면 주문상태를 식사중으로 설정한다.
    8. 식사를 완료하면 주문상태를 식사완료로 변경한다.
    9. 단체석으로 지정되어있으면 단체석 지정을 해지한다.
    10. 좌석을 빈좌석으로 설정한다.

## 모델링

- 상품
    - 상품은 상품번호, 상품이름, 상품가격으로 구성된다.
    - 이미 등록한 상품명은 사용 할 수 없다.
    - 상품가격은 자연수이다.
    
- 메뉴
    - 메뉴는 메뉴번호, 메뉴가격, 메뉴구성상품으로 구성된다.
    - 이미 등록한 메뉴이름을 다시 등록 할 수 없다.
    - 메뉴는 메뉴 그룹에 포함되어야 한다.
    - 메뉴가격은 자연수이고, 메뉴구성상품을 구성하는 상품가격의 총합보다 비싸면 안된다.
    - 메뉴는 등록된 메뉴 그룹에 포함되어야 한다.
    - 메뉴그룹은 메뉴그룹번호와 메뉴그룹이름으로 구성된다.
    - 이미 등록한 메뉴그룹이름을 다시 등록 할 수 없다.

- 메뉴그룹
    - 메뉴그룹은 메뉴그룹번호와, 메뉴그룹이름으로 구성된다.
    - 이미 등록한 메뉴그룹이름은 등록 할 수 없다.

- 주문테이블
    - 고객을 빈 테이블에 배치한다.
    - 주문테이블에 고객의 수를 기록한다.
    - 고객이 단체석을 요청하면 주문테이블을 2개이상 묶어 단체석으로 묶어 관리한다.
    - 주문테이블 당 메뉴판에서 메뉴를 한 가지 이상 선택해야 한다.
    - 주문서에 주문테이블번호, 주문시간, 주문한 메뉴를 기록한다.
    - 주문을 마치면 주문번호를 기록하고, 주문상태를 요리중 으로 변경한다.
    - 음식이 준비되면, 주문상태를 식사중 으로 변경한다.
    - 고객이 식사를 마치면 주문상태를 식사완료로 변경한다.
    - 주문테이블의 상태를 비어있음으로 변경한다.
    - 단체석의 모든 주문테이블상태가 비어있음이면 단체석지정해제를 할 수 있다.
