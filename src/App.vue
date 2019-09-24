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
          period: '2019.03-2019.07',
          title:'SAMSUNG : INDIA B2B',
          description: '기존의 site를(HTML+JAVASCRIPT) HTL(html templating language)로 migration 작업<br />'
          +'<span class="hashtag">#HTML #Javascript #Java #AEM #GitHub</span><br /><br />'
          +'<span class="caption-bottom">처음부터 개발하는 것보다 언어 migration 하는 것이 더 어려운 작업이라는 것을 느낀 프로젝트입니다.'
          +' Html+Javascript는 익숙해서 분석하는데 어려움이 없었지만 Htl은 익숙하지 않고 많이 쓰지 않은 언어라서 적응하는데 조금 어려웠습니다.</span><span class="hashtag"> #프리랜서</span>'
        },
        {
          thumbnail: require('./assets/imgs/lg.jpg'),
          period: '2018.11-2019.02',
          title:'LG생활건강 : 디지털 자산 관리 시스템 운영',
          description: 'AEM ASSETS(동적 디지털 경험을 관리, 게시, 전달할 수 있는 시스템)을 이용해서 고객사 내부에서 디지털 자산을 관리하는 플랫폼을 운영<br />'
          +'<span class="hashtag">#HTML #Javascript #AEM #jQuery #GitHub</span><br /><br />'
          +'<span class="caption-bottom">디지털 자산을 올리고 공유를 하는 기능이 사용하기 불편하고 어렵게 구축이 되어있어서, 직접 사용자가 되어서 어떻게 하면 더 편하게 사용할 수 있을까 생각하면서 수정했습니다.'
          +' 디지털 자산을 검토, 승인을 위한 워크플로우를 간편하게 생성하여 자산을 관리하고, 간단히 클릭하여 사용자를 추가하고 역할을 선택하면 시스템이 자동으로 작업을 할당해주는 기능인 워크플로우는 따로 수정 건이 없어서 아쉬웠습니다.</span><span class="hashtag"> #스프링웍스</span>'
        },
        {
          thumbnail: require('./assets/imgs/aia.jpg'),
          period: '2017.11-2018.10',
          title:'AIA생명 : MY AIA(온라인창구) 구축 ~ 운영',
          description: 'AEM FORMS(고객 등록 및 기타 커뮤니케이션에 필요한 양식과 문서의 제작을 간소화하는 문서 관리 시스템)를 이용해서 입/출금 메뉴를 개발<br />'
          +'<span class="hashtag">#HTML #Javascript #AEM(Forms,Site) #jQuery #Trello</span><br /><br />'
          +'<span class="caption-bottom">국내에서 Forms를 사용한 사례가 없고, AIA global site에서는 Forms를 설문조사용으로만 단순하게만 사용했기 때문에 복잡한 입/출금 서비스의 form을 설계를 어떻게 해야 할지 초반부터 어려움을 겪었습니다.'
          +' global site처럼 Forms는 간단한 설문조사용으로만 사용하는 것이 바르다고 생각이 들었습니다.<br />'
          +' 내부에서 인원교체가 빈번하게 일어나서 업무 히스토리와 Forms 인수인계 담당할 사람이 저밖에 없어서 새로운 인력이 들어올 때마다 인수인계를 해줘야 하는 힘듦과, 야근과 공휴일 출근이 일상이 되어서 매우 힘든 프로젝트였습니다.'
          +' 하지만 그런 많은 일을 겪었기 때문에 그에 따른 대처능력이 향상되었고 초반 인원 중에서 끝까지 혼자 남아있어서 다른 것도 끝까지 할 수 있다는 자아존중감도 향상이 되어서 많은 도움이 된 프로젝트입니다.</span><span class="hashtag"> #스프링웍스</span>'
        },
        {
          thumbnail: require('./assets/imgs/amore.jpg'),
          period: '2017.05-2017.10',
          title:'AMOREPACIFIC : HONGKONG',
          description: '기존의 AMOREPACIFIC : KOREA site를 가져와서 만든 프로젝트<br />'
          +'<span class="hashtag">#HTML #Javascript #Java#JSP #AEM #jQuery #GitHub #Trello</span><br /><br />'
          +'<span class="caption-bottom">주로 제품들의 카테고리별 정렬, 간단한 컴포넌트 개발, email 발송을 위한 form을 개발하는 업무를 했습니다.'
          +' 컴포넌트 개발을 처음 해봐서 여러 개의 컴포넌트를 렌더링하는 것에도 흥미를 느끼게 되었고, 컴포넌트를 기반으로 한 언어가 매력이 있다고 느낀 프로젝트였습니다. 또한, email의 인코딩과 디코딩에 대해서도 많은 것을 배웠습니다.</span><span class="hashtag"> #스프링웍스</span>'
        },
        {
          thumbnail: require('./assets/imgs/hallym.jpg'),
          period: '2017.03-2017.04',
          title:'한림대학교 DB, 한림대학원 Magnolia',
          description: '한림대학교 학과별 게시판 DB migration, 한림대학원 메인페이지 수정<br />'
          +'<span class="hashtag">#HTML #Javascript #Java #JSP #Magnolia #JQuery #MySQL #SVN</span><br /><br />'
          +'<span class="caption-bottom">JAVA를 이용해서 한림대학교의 학과별 게시판 DB를 migration 했습니다.'
          +' 한림대학원은 AEM과 비슷한 플랫폼인 Magnolia를 이용해서 만들어졌는데, 그 중 메인페이지 게시판 수정을 맡았습니다. 기본적인 게시판 CRUD를 실무로 경험해볼 수 있는 프로젝트였습니다.</span><span class="hashtag"> #스프링웍스</span>'
        },
        {
          thumbnail: require('./assets/imgs/more_content.png'),
          period: 'MORE',
          title: 'QA 경험',
          description: '모비고 솔루션(스마트폰 데이터 전송 프로그램) 웹/모바일 테스트케이스 작성<br />'
          +'<span class="hashtag">#2015.07-2016.03 #지온네트웍스 #QA<br /><br /></span>'
          +'<span class="caption-bottom">모비고 솔루션을 웹/모바일로 나누어 테스트케이스를 작성하고 테스트를 했습니다.'
          +'기획자, 개발자와 의사소통을 많이 할 수 있었던 경험이었습니다. QA 경험 덕분에 개발을 시작할 때 부터 지금까지 단위테스트 전에도 자체적으로 여러 테스트를 많이 하게 되었습니다.</span>'
        }
      ],
      visible: false,
      index: 0
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

.hashtag {
  color: #0066CC;
}
</style>
