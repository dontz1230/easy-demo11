<template>
  <div class="plan-catelogue">
    <div class="stepList" v-for="(item,index) in steps" :key="index">
      <div
        class="stepList__dot"
        :class="{'activeDot' : item.page === step, 'ad1' : item.index ===  '三.' && step ===3 ,'ad2' : item.index ===  '三.' && step ===4,'ad3' : item.index ===  '三.' && step ===5,'ad4' : item.index ===  '三.' && step ===6,'ad5' : item.index ===  '四.' && step ===8,'ad6' : item.index ===  '四.' && step ===9,'ad7' : item.index ===  '四.' && step ===10,'ad8' : item.index ===  '四.' && step ===11,'ad9' : item.index ===  '五.' && step ===15,'ad10' : item.index ===  '七.' && step ===16}"
      ></div>
      <div class="stepList__index" :class="{'active' : step===item.page}">{{item.index}}</div>
      <div class="stepList__title" :class="{'active' : step===item.page && step !==3 &&step!==7}">
        <span
          @click="changeStep(item.page)"
          class="pointer"
          :class="{'active' : step===item.page && step !==3}"
        >{{item.title}}</span>
        <div v-if="item.index === '三.'" class="subTitle pointer">
          <ul v-if="step ===3 || step ===4 || step ===5  ||step ===6 ">
            <li :class="{'active' : step===3}" class="pointer" @click="changeStep(3)">(一)自然災害風險檢查結果</li>
            <li :class="{'active' : step===4}" class="pointer" @click="changeStep(4)">(二)受災經驗</li>
            <li :class="{'active' : step===5}" class="pointer" @click="changeStep(5)">(三)災害潛勢地圖分析</li>
            <li :class="{'active' : step===6}" class="pointer" @click="changeStep(6)">(四)綜合研判結果</li>
          </ul>
        </div>
        <div v-if="item.index === '四.'" class="subTitle pointer">
          <ul
            v-if="step===7 || step===8 || step===9|| step ===10 || step ===11||step===12 ||step===13||step===14"
          >
            <li
              :class="{'active' : step===7}"
              class="pointer infoSetting"
              @click="changeStep(7)"
            >應變人員資料設定</li>
            <li>
              <div :class="{'active' : step===8 ||step===9||step===10}" class="pointer">
                <span @click="changeStep(8)" class="pointer">(一)地震災害應變流程</span>
              </div>
              <ul v-if="step===8 || step===9 || step ===10" class="subTitleContainer pointer">
                <li @click="changeStep(8)" class="pointer">
                  <span v-if=" step ===8" class="activeCircle"></span> 流程圖
                </li>
                <li @click="changeStep(9)" class="pointer">
                  <span v-if=" step ===9" class="activeCircle"></span> 應變工作
                </li>
                <li @click="changeStep(10)" class="pointer">
                  <span v-if=" step ===10" class="activeCircle"></span> 應變檢核表
                </li>
              </ul>
            </li>
            <!-- <li :class="{'active' : step===11}" @click="changeStep(11)">(二)颱虹災害應變流程</li> -->
            <li>
              <div
                :class="{'active' : step===12 ||step===13||step===14||step===11}"
                class="pointer"
              >
                <span @click="changeStep(12)" class="pointer">(二)颱虹災害應變流程</span>
              </div>
              <ul
                v-if="step === 12 || step ===13 || step === 14||step===11"
                class="subTitleContainer pointer"
              >
                <li @click="changeStep(12)" class="pointer">
                  <span v-if=" step ===12" class="activeCircle"></span> 流程圖
                </li>
                <li @click="changeStep(13)" class="pointer">
                  <span v-if=" step ===13" class="activeCircle"></span> 應變工作
                </li>
                <li @click="changeStep(14)" class="pointer">
                  <span v-if=" step ===14" class="activeCircle"></span> 應變檢核表
                </li>
              </ul>
            </li>
            <!-- <li :class="{'active' : step===11}" @click="changeStep(11)">(二)颱虹災害應變流程</li> -->
          </ul>
        </div>
        <div v-if="item.index === '五.'" class="subTitle pointer">
          <ul v-if="step===15|| step===16" class="subTitleContainer pointer">
            <li @click="changeStep(15)" class="pointer">
              <span v-if=" step ===15" class="activeCircle"></span> 就近避難
            </li>
            <li>垂直避難</li>
            <li @click="changeStep(16)" class="pointer">
              <span v-if=" step ===16" class="activeCircle"></span> 異地避難
            </li>
          </ul>
        </div>
        <div v-if="item.index === '七.'" class="subTitle pointer">
          <ul v-if="step===18|| step===19 || step===20" class="subTitleContainer pointer">
            <li @click="changeStep(18)" class="pointer">
              <span v-if=" step ===18" class="activeCircle"></span> 物資清單
            </li>
            <li @click="changeStep(19)" class="pointer">
              <span v-if=" step ===19" class="activeCircle"></span> 災害應變設備
            </li>
            <li @click="changeStep(20)" class="pointer">
              <span v-if=" step ===20" class="activeCircle"></span> 緊急聯絡網
            </li>
          </ul>
        </div>
        <div v-if="item.index === '七.'" class="subTitle pointer">
          <ul
            v-if="step===18|| step===19 || step===20"
            style="background:#FF8A8A;margin-top:4px;"
            class="subTitleContainer"
          >
            <li>
              <span></span> 加入其它附件，
            </li>
            <li>可自行利用匯出</li>
            <li>
              <span></span> 之Word檔新增
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      step: 1,
      steps: [
        {
          index: "一.",
          page: 1,
          title: "計畫說明",
        },
        {
          inde: "二.",
          page: 2,
          title: "二.機構基本資料",
        },
        {
          index: "三.",
          page: 3,
          title: "計畫說明",
        },
        {
          index: "四.",
          page: 7,
          title: "天然災害應變流程",
        },
        {
          index: "五.",
          page: 15,
          title: "避難收容",
        },
        {
          index: "六.",
          page: 17,
          title: "教育訓練/演練",
        },
        {
          index: "七.",
          page: 18,
          title: "附件",
        },
      ],
    };
  },
  methods: {
    changeStep(step) {
      if (step !== 3 || step !== 4) {
        this.$emit("changeStep", step);
        this.step = step;
      }
    },
  },
};
</script>
<style lang="scss" scoped>
.subTitleContainer {
  background: #66cdb6;
  color: #fff;
  border-radius: 10px;
  padding: 10px;
}

.active {
  color: #66cdb6;
}

.activeCircle {
  border-radius: 100%;
  width: 20px;
  height: 20px;
  border: 4px solid #eaeaea;
  background: #66cdb6;
  display: inline-block;
  vertical-align: middle;
}

.stepList {
  &:before {
    content: "";
    position: absolute;
    left: 14px;
    width: 4px;
    background: #d6d6d6;
    height: calc(100% + 35px);
  }
  &:last-of-type {
    &:before {
      content: "";
      position: absolute;
      left: 14px;
      width: 0;
      height: 0 !important;
    }
  }
}

.infoSetting {
  background: #66cdb6;
  border-radius: 10px;
  color: #fff;
  text-align: center;
  padding: 5px 0;
}
</style>