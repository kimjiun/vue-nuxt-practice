axios를 네트워크 통신을 위해 기본으로 설정가능

nuxt.config.js 파일에 글로벌 설정 가능

layout의 default.vue가 시작접
<nuxt/> 컴포넌트는 pages/index.vue를 렌더링

<nuxt-link> : 페이지 이동을 위해 사용

page vue 파일에서
head() 함수로 메타 데이터 지정 가능

export default {
head() {
return {
title: 'About Nuxt',
meta: [
{name: 'description', content: 'This is my about desc'},
{name: 'keywords', content: 'about next info'},
]  
 }
}
}

===
Router 전환 애니메이션
=> 글로벌 css 파일에 아래 코드 추가
.page-enter-active, .page-leave-active {
transition: opacity .5s;
}

.page-enter, .page-leave-active {
opacity: 0;
}
