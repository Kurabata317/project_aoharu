<template>
  <body>
    <h4>BlueTune</h4>
    <div class="mfit" v-for="(tracklist, i) in musicname" :key="i" :id="[`mf${i}`]">
      <div class="mbox titlebox" :id="[`mbx${i}`]" v-on:click="dtopen(i)">
        <div class="mtext m_num">{{ tracklist.num }}</div>
        <div class="mtext m_title">{{ tracklist.title }}</div>
        <div class="mtext m_artist">{{ tracklist.artist }}</div>
        <div class="mtext m_playlink">▶</div>
      </div>
      <div class="mbox detail" :id="[`mdt${i}`]">
        <div v-for="(lst, j) in detailtagname" :key="j" :class="[`ct${j}`]">
          <div class="dtcategory" v-if="musicname[i][lst.tagname].length > 0">
            <div class="detailtt" >{{ lst.ctgrname }}</div>
            <div class="detailcontent">
              <div v-for="(element, k) in musicname[i][lst.tagname]" :key="k">
                {{ element }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </body>
</template>

<script>
export default {
  name: 'App',
  data(){
    return {
      detailtagname: [
        {
          ctgrname: "용도",
          tagname: "purpose"
        },
        {
          ctgrname: "메모리얼 로비",
          tagname: "memorial"
        },
        {
          ctgrname: "비고",
          tagname: "note"
        }
      ],
      musicname: {
        1:{
          num: 1,
          title: "Constant Moderato",
          artist: "Mitsukiyo",
          purpose: ["타이틀 스크린"],
          memorial: [],
          note: ["DJMAX RESPECT V 콜라보 수록"],
          link: {
            youtube: "https://www.youtube.com/watch?v=SHkF48SgiSA"
          }
        },
        2:{
          num: 2,
          title: "Luminous Memory",
          artist: "Mitsukiyo",
          purpose: ["메모리얼 로비"],
          memorial: [
            "이오리",
            "하스미",
            "우타하",
            "아즈사(수영복)",
            "미네"
          ],
          note: ["1주년 기념 3rd PV OST"],
          link: {
            youtube: "https://www.youtube.com/watch?v=D3boxTP-ZG8"
          }
        },
        3:{
          num: 3,
          title: "Mischievous Step",
          artist: "Mitsukiyo",
          purpose: ["임무 스테이지"],
          memorial: [],
          note: [],
          link: {
            youtube: "https://www.youtube.com/watch?v=FHW2fNPaHU4"
          }
        },
        4:{
          num: 4,
          title: "Lovely Picnic",
          artist: "Mitsukiyo",
          purpose: ["스토리 범용"],
          memorial: [],
          note: [],
          link: {
            youtube: "https://www.youtube.com/watch?v=dEfXiVI1Euo"
          }
        },
        5:{
          num: 5,
          title: "Colorful Mess",
          artist: "KARUT",
          purpose: ["스토리 범용"],
          memorial: [],
          note: [],
          link: {
            youtube: "https://www.youtube.com/watch?v=OF9cu3cutj0"
          }
        },
        6:{
          num: 6,
          title: "Funky Road",
          artist: "KARUT",
          purpose: ["스토리 범용"],
          memorial: [],
          note: [],
          link: {
            youtube: "https://www.youtube.com/watch?v=8h458BG1-Bo"
          }
        },
        7:{
          num: 7,
          title: "Unwelcome School",
          artist: "Mitsukiyo",
          purpose: ["스토리 범용"],
          memorial: [],
          note: ["일명 '아루 브금'"],
          link: {
            youtube: "https://youtu.be/pEg_d2f6myw"
          }
        },
        8:{
          num: 8,
          title: "Shady Girls",
          artist: "Mitsukiyo",
          purpose: ["스토리 범용"],
          memorial: ["카스미"],
          note: [],
          link: {
            youtube: "https://youtu.be/v7s-gHSs-YM"
          }
        },
        9:{
          num: 9,
          title: "Midsummer cat",
          artist: "Mitsukiyo",
          purpose: ["메모리얼 로비"],
          memorial: [
            "시로코",
            "슌",
            "노노미",
            "시즈코",
            "아카네",
            "요시미",
            "츠바키",
            "하나코",
            "미모리",
            "유우카/체육복",
            "주리",
            "하루나(새해)",
            "토키(바니걸)",
            "미야코(수영복)",
            "하나코(수영복)"
          ],
          note: [],
          link: {
            youtube: "https://youtu.be/v7s-gHSs-YM"
          }
        },
        10:{
          num: 10,
          title: "Romantic Smile",
          artist: "Mitsukiyo",
          purpose: ["스토리 범용"],
          memorial: [],
          note: [],
          link: {
            youtube: "https://youtu.be/EBnOCXXg91o"
          }
        }
      }
    }
  },
  methods: {
    /**
     * 
     * @param {number} index 순서
     */
    dtopen(index) {
      let mdt = document.getElementById("mdt"+index);

      if(!mdt.style.display || mdt.style.display == "none"){
        mdt.style.display = "block";
      } else {
        mdt.style.display = "none";
      }
    }
  },
  components: {

  }
}
</script>

<style>
@import url("https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard-jp.min.css");
@import url("https://cdn.jsdelivr.net/gh/Nyannnnnng/GyeonggiTitleWoff/stylesheet.css");

* {
  font-family: "GyeonggiTitle";
  font-weight: 900;

  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

body {
  max-width: 768px;
  margin: auto;
  padding: 0 6px;
}

h4 {
  font-size: 20pt;
}

.mfit {
  margin: 6px auto;
}

.mbox {
  padding: 12px;
  box-shadow: 0 0 5px #999999;
  border-radius: 6px;
  margin: 6px auto;
  justify-content: center;
  align-items: center;
}

.titlebox {
  display: flex;
  cursor: pointer;
}

.titlebox:active {
  opacity: 0.6;
}

.mtext {
  font-size: 12pt;
}

.m_num {
  color: #999999;
  width: 10%;
}

.m_title {
  color: #128afa;
  font-size: 13pt;
  width: 50%;
}

.m_artist {
  color: #2c4c72;
  width: 30%;
}

.m_playlink {
  color: #00D2FF;
  width: 10%;
}

.m_playlink:active {
  opacity: 0.4;
  cursor: pointer;
}

.detail {
  display: none;
  padding: 6px 18px;
  align-items: flex-start;
}

.detail * {
  font-family: "Pretendard";
  font-weight: 500;
  letter-spacing: -0.75px;
}

.dtcategory {
  display: block;
  text-align: left;
  padding: 6px;
  margin: 0 auto;
  width: 100%;
}

.detailtt {
  font-size: 10.5pt;
  font-weight: 800;
  color: #333333;
}

.detailcontent {
  font-size: 10pt;
  color: #777777;
}
</style>
