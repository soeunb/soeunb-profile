<template>
  <div id="app">
    <ProfileHeader></ProfileHeader>
    <ProfileContent v-bind:items="projectItems"/>
  </div>
</template>

<script>
import ProfileHeader from './components/ProfileHeader.vue'
import ProfileContent from './components/ProfileContent.vue'

export default {
  components: {
    'ProfileHeader': ProfileHeader,
    'ProfileContent': ProfileContent
  },
  data () {
    return {
      projectItems: [
        {
          thumbnail: require('./assets/imgs/samsung.jpg'),
          period: '2019.03 - 2019.07',
          title:'SAMSUNG  :  INDIA b2b  #프리랜서',
          description: '<b>기존에 있는 site를(HTML+JAVASCRIPT) HTL(html templating language)로 migration</b><br/>'
          +'처음부터 개발하는거보다 언어 migration 하는게 더 어려운 작업이라는 것을 느낀 프로젝트입니다.'
			    +'html + javascript 는 익숙해서 분석하는데 어려움이 없었지만 htl은 익숙하지 않고 많이 쓰지 않은 언어라서 적응하는데 조금 어려웠습니다.'
        },
        {
          thumbnail: require('./assets/imgs/lg.jpg'),
          period: '2018.11 - 2019.02',
          title:'LG생활건강 : 디지털 자산 관리 시스템 운영 #스프링웍스',
          description: '<b>AEM ASSETS(동적 디지털 경험을 관리, 게시, 전달할 수 있는 시스템)을 이용해서 고객사 내부에서 디지털 자산을 관리하는 플랫폼을 운영</b><br/>'
          +'디지털 자산을 올리고 공유를 하는 기능이 사용하기 불편하고 어렵게 구축이 되어있어서, 사용자 입장에서 바라보면서 어떻게 하면 더 편하게 사용할 수 있을까 생각하면서 수정했습니다.'
          +'디지털 자산을 검토, 승인을 위한 워크플로우를 간편하게 생성하여 자산을 관리하고, 간단히 클릭하여 사용자를 추가하고 역할을 선택하면 시스템이 자동으로 작업을 할당해주는 기능인 워크플로우는 따로 수정건이 없어서 아쉬웠습니다.'
        },
        {
          thumbnail: require('./assets/imgs/aia.jpg'),
          period: '2017.11 - 2018.10',
          title:'AIA생명 : MY AIA(온라인창구) 구축 ~ 운영 #스프링웍스',
          description: '<b>AEM FORMS(고객 등록 및 기타 커뮤니케이션에 필요한 양식과 문서의 제작을 간소화하는 문서 관리 시스템)를 이용해서 입/출금 메뉴를 개발</b><br/>'
			    +'국내에서 Forms를 사용한 사례가 없고, AIA global site에서는 Forms를 설문조사용으로만 단순하게만 사용했어서 초반에 분석하는데 어려움을 겪었습니다.'
			    +'global site처럼 Forms는 간단한 설문조사용으로만 사용하는게 맞다고 생각이 들었습니다. Forms 버그인지 개발이 잘못된건지 구분이 어려워서 개발하는데 시간이 많이 걸렸습니다.'
        },
        {
          thumbnail: require('./assets/imgs/amore.jpg'),
          period: '2017.05 - 2017.10',
          title:'AMOREPACIFIC : HONGKONG #스프링웍스',
          description: '<b>기존에 있는 AMOREPACIFIC : KOREA site를 가져와서 만든 프로젝트</b><br/>'
			    +'주로 제품들의 카테고리별 정렬, email 관련된 업무를 맡았습니다. email의 인코딩과 디코딩에 대해서 많은 것을 배웠습니다.'
        },
        {
          thumbnail: require('./assets/imgs/hallym.jpg'),
          period: '2017.03 - 2017.04',
          title:'한림대학교 DB, 한림대학원 Magnolia #스프링웍스',
          description: '<b>한림대학교 학과별 게시판 DB migration, 한림대학원 메인페이지 수정</b>'
          +'JAVA를 이용해서 한림대학교의 학과별 게시판 DB를 migration했습니다. 한림대학원은 AEM과 비슷한 플랫폼인 Magnolia를 이용해서 만들어졌는데, 그 중 메인페이지 수정을 맡았습니다.'
        },
        {
          thumbnail: require('./assets/imgs/more.jpg'),
          period: '',
          description: 'more(지온네트웍스 QA 경력)'
        }
      ],
      visible: false,
      index: 0 // default
    }
  }
}
</script>

<style>
:root {
    font-size: 10px;
}

*,
*::before,
*::after {
    box-sizing: border-box;
}

body {
    font-family: "Open Sans", Arial, sans-serif;
    min-height: 100vh;
    background-color: #fafafa;
    color: #262626;
    padding-bottom: 3rem;
}

img {
    display: block;
}

.container {
    max-width: 93.5rem;
    margin: 0 auto;
    padding: 0 2rem;
}

.btn {
    display: inline-block;
    font: inherit;
    background: none;
    border: none;
    color: inherit;
    padding: 0;
    cursor: pointer;
}

.btn:focus {
    outline: 0.5rem auto #4d90fe;
}

.visually-hidden {
    position: absolute !important;
    height: 1px;
    width: 1px;
    overflow: hidden;
    clip: rect(1px, 1px, 1px, 1px);
}
</style>
