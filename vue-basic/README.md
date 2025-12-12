# 파일 생성 후 option

vbase-3 로 템플릿 생성

===

## UI 핵심 문법1

data 객체 안에 컴포넌트에서 사용할 데이터 선언,
methods 객체 안에 컴포넌트에서 사용할 함수 선언

# 선언적 렌더링

데이터 바인딩의 가장 기본
이중중괄호 안에 변수 {{}}
변수가 아닌 텍스트로 출력됨

html 요소를 사용할땐 v-html="변수" 로 처리

# class와 style 바인딩

v-bind: class

style 바인딩은 카멜케이스로 작성
ex) <h3 :style="{color :fontColor, fontSize: fontSize}">스타일 바인딩 테스트입니다.</h3>

# 조건부 렌더링

v-if / v-else-if / v-else
조건이 truethy일 경우에만 렌더링됨
실행중에 조건이 변경되지 않는 경우
v-show
항상 렌더링이되어 DOM에 남아있음
css display 속성만 전환됨
매우 자주 전환되는 경우

# 리스트 렌더링

v-for
item in items 문법 필요

<li v-for="item in items">
{{ item.message }}
</li>

    vue.js 2.2 버전 부터 성능을 위해
    렌더링 대상을 식별하면 부하가 적음
    :key="변수" 로 바인딩해야함

    XXX 리스트의 index는 사용하지 않는다 XXX
    v-for"(user, index) in users" :key="index"

========

## 핵심 문법2

# Data 문법

인라인 핸들러, 메소드 핸들러

Computed
복잡한 로직을 미리 처리하여 반복된 로직처리를 캐싱
methods와 동일하게 함수처럼 작성하지만 사용할땐 데이터 취급이라 '()' 를 붙이지 않음

watch 속성
데이터를 감시하고 있다가 값이 변했을때 감지해서 특정 로직 실행
watch 객체 안에 data 변수 이름 뒤에 ()를 붙여 동작
computed로 계산된 형태의 데이터도 watch로 감지 가능

Props
상위 컴포넌트 => 하위 컴포넌트로 데이터 전송
자식에서 조회만 가능 수정은 불가
defineProps()

Emits
하위 컴포넌트 => 상위 컴포넌트
부모로 이벤트를 전달
defineEmits()

v-model
양방향 데이터 바인딩
Props와 Emits의 기능이 동시에 진행
input의 기능에 따라
보통 input 태그의 inputValue값과 연관지어 많이 사용
input 행위가 끝나야 값이 대입됨

아래와 같이 실시간으로 대입되게 처리 가능
"<input type="text" :value="inputValue2" @input="inputValue2 = $event.target.value"/>"
