<template>
  <div class="plan-section plan-section-three-four">
    <div class="planHeader">
      <div class="planHeader__title">天然災害應變流程</div>
      <div class="planHeader__option">
        <img src="~@/assets/img/planList/advice.png" alt />
        <span>撰寫原則或建議</span>
      </div>
      <div class="planHeader__option">
        <img src="~@/assets/img/planList/template.png" alt />
        <span>參考撰寫範本</span>
      </div>
    </div>
    <div class="planTopic">
      <div class="themeColor">(一)地震災害應變流程</div>
      <div
        class="planTitle__redIcon"
        style="
    display: inline-block;
    text-align: center;
    line-height: 34px;
    font-size: 16px;"
        data-red="天然災害應變流程應考慮機構本身的地理環境、設備，以及人力等實際情況進行規劃。
可依據機構需求自行上傳流程圖，或是採用本系統提供的範本。
目前範本上為預先設定的應變步驟，實際的災害應變流程並非一成不變，機構人員要依照現場情況調整應變步驟。"
      >
        <i class="fas fa-question"></i>
      </div>
    </div>
    <div class="planJob">
      <div class="planTitle__text inline">應變流程</div>
      <div
        class="planTitle__redIcon"
        style="
    display: inline-block;
    text-align: center;
    line-height: 34px;
    font-size: 16px;"
        data-red="可選擇使用範本或自行上傳：
若使用範本，僅能修改既定流程中的文字，無法彈性增加或刪減應變時序。
若自行上傳流程圖，較符合機構需求，但後續應變時序須自行編輯。"
      >
        <i class="fas fa-question"></i>
      </div>
    </div>

    <div class="teamClass">
      <div class="styleBlock__text">
        <input type="radio" value name="style" id @change="uploadThing" v-model="upload" />
        <label for="style">使用範本流程圖</label>
      </div>
      <div class="styleBlock__text">
        <input type="radio" value="upload" name="style" @change="uploadThing" id v-model="upload" />
        <label for="style">自行上傳流程圖</label>
      </div>
    </div>
    <div class="uploadImg" v-if="upload === 'upload'">
      <span class="greyText">上傳圖片</span>
      <input type="file" name id />
    </div>
    <div class="greyText" style="margin:20px 0;">目前已上傳的圖片：</div>
    <img src="~@/assets/img/planList/process-template.jpg" alt />
  </div>
</template>
<script>
export default {
  data() {
    return {
      upload: false,
    };
  },
  methods: {
    uploadThing() {
      this.$emit("uploadThing", this.upload);
    },
  },
};
</script>
<style lang="scss" scoped>
.planTopic {
  margin: 30px auto;
}

.teamClass {
  display: flex;
  width: 500px;
  justify-content: space-between;
  margin-bottom: 15px;
  &__block {
    display: flex;
    align-items: center;
    input[type="checkbox"] {
      position: relative !important;
      left: auto;
      -webkit-appearance: checkbox;
    }

    button {
      background: #ff8a8a;
      padding: 4px 23px;
      border-radius: 4px;
      color: #fff;
      margin-left: 16px;
    }
  }
}

.label {
  padding: 0 !important;
  font-size: 1rem !important;
  font-weight: normal !important;
  &:before {
    display: none;
  }
  &:after {
    display: none;
  }
}

.planJob {
  margin: 10px auto;
  img {
    vertical-align: bottom;
    margin-left: 20px;
    margin-bottom: 4px;
  }
  .addBtn {
    display: inline-block;
    float: right;
  }
}

input[type="radio"] {
  display: inline-block;
  left: unset;
  position: relative;
  width: 30px;
  height: 30px;
  border-radius: 50em;
  -webkit-appearance: auto;
  margin-right: 8px;
  &::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 30px;
    height: 30px;
    border-radius: 50em;
    border: 4px solid #d4d4d4;
  }
  &:checked::before {
    background: #66cdb6;
  }
}

.styleBlock__text input[type="radio"] {
  top: 0 !important;
}

.styleBlock__text {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  width: 182px;
  margin-bottom: 2px;
  color: #777;
}
</style>
