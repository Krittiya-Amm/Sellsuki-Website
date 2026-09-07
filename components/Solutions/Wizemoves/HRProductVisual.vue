<template>
  <div class="hrv">
    <!-- ===== HR Template : ตัวอย่างหน้า Salepage บนมือถือ ===== -->
    <div v-if="type === 'template'" class="hrv-phone">
      <img class="hrv-frame" src="~/assets/SolutionsWizemoves/Consulting/phone-frame2.png" alt="" aria-hidden="true" />
      <div class="hrv-screen hrv-screen-doc">
        <div class="hrv-doc-head">
          <p class="hrv-kicker mb-0">HR Template</p>
          <p class="hrv-doc-title mb-0">ชุดเอกสาร HR พร้อมใช้<br />สำหรับองค์กรที่ยังไม่มีฝ่าย HR</p>
        </div>
        <div class="hrv-list">
          <div v-for="(item, i) in items" :key="i" class="hrv-item">
            <span class="hrv-ico" aria-hidden="true" v-html="item.icon"></span>
            <span class="hrv-item-text">{{ item.text }}</span>
          </div>
        </div>
        <!-- ไอคอนเอกสารจาง ๆ เติมพื้นที่ว่างด้านล่างจอ -->
        <div class="hrv-doc-watermark" aria-hidden="true">
          <svg viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M38 8H16a4 4 0 0 0-4 4v40a4 4 0 0 0 4 4h32a4 4 0 0 0 4-4V22L38 8Z"
              stroke="#7B64AF" stroke-width="2.4" stroke-linejoin="round" />
            <path d="M37 8v13a2 2 0 0 0 2 2h12" stroke="#7B64AF" stroke-width="2.4" stroke-linejoin="round" />
            <path d="M20 32h24M20 40h24M20 48h16" stroke="#7B64AF" stroke-width="2.4" stroke-linecap="round" />
          </svg>
        </div>
      </div>
    </div>

    <!-- ===== HR Chatbot : ตัวอย่างแชทบนมือถือ ===== -->
    <div v-else-if="type === 'chatbot'" class="hrv-phone">
      <img class="hrv-frame" src="~/assets/SolutionsWizemoves/Consulting/phone-frame2.png" alt="" aria-hidden="true" />
      <div class="hrv-screen">
        <div class="hrv-chat-head">
          <span class="hrv-bot" aria-hidden="true">
            <svg viewBox="0 0 48 48" fill="none">
              <rect x="8" y="14" width="32" height="24" rx="8" fill="#DDD6FE" />
              <rect x="8" y="14" width="32" height="24" rx="8" stroke="#7B64AF" stroke-width="2.8" />
              <path d="M24 14V7" stroke="#7B64AF" stroke-width="2.8" stroke-linecap="round" />
              <circle cx="24" cy="5.5" r="2.6" fill="#7B64AF" />
              <circle cx="18" cy="25" r="3" fill="#7B64AF" />
              <circle cx="30" cy="25" r="3" fill="#7B64AF" />
              <path d="M19 32h10" stroke="#7B64AF" stroke-width="2.8" stroke-linecap="round" />
            </svg>
          </span>
          <span class="hrv-bot-name">WM HR Chatbot</span>
        </div>
        <div class="hrv-chat">
          <div class="hrv-bubble hrv-bubble-out">ลาออกแจ้งล่วงหน้ากี่วัน</div>
          <div class="hrv-bubble hrv-bubble-in">แจ้งล่วงหน้า 30 วัน ค่ะ</div>
          <div class="hrv-bubble hrv-bubble-out">เบิกค่ารักษาพยาบาลยังไง</div>
          <div class="hrv-bubble hrv-bubble-in hrv-typing">
            <span></span><span></span><span></span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HRProductVisual',
  props: {
    type: {
      type: String,
      required: true
    },
    items: {
      type: Array,
      default: () => []
    }
  }
}
</script>

<style scoped>
.hrv {
  position: relative;
  padding: 24px 0;
}

.hrv::before {
  content: "";
  position: absolute;
  z-index: 0;
  inset: 0;
  background: radial-gradient(64% 64% at 50% 46%, #7B64AF2E 0%, #7B64AF00 74%);
  pointer-events: none;
}

/* ----- กรอบมือถือจากรูปจริง (iPhone mockup) ----- */
.hrv-phone {
  position: relative;
  z-index: 1;
  width: 320px;
  max-width: 100%;
  margin: 0 auto;
  aspect-ratio: 741 / 1487;
}

.hrv-frame {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  z-index: 2;
  pointer-events: none;
  filter: drop-shadow(0px 18px 36px rgba(62, 48, 91, 0.28));
}

/* หน้าจอ = ซ้อนทับพื้นที่จอของรูปกรอบ (เว้นใต้ Dynamic Island) */
.hrv-screen {
  position: absolute;
  z-index: 3;
  left: 6.2%;
  top: 2.5%;
  width: 87.6%;
  height: 94.9%;
  background: #F4F2F8;
  border-radius: 40px;
  overflow: hidden;
  display: flex;
  flex-direction: column;
}

/* ----- Salepage preview (ในกรอบมือถือ) ----- */
.hrv-screen-doc {
  background: linear-gradient(180deg, #FAF8FF 0%, #FFFFFF 58%);
  padding: 40px 16px 18px;
  text-align: center;
}

.hrv-doc-head {
  text-align: center;
}

.hrv-kicker {
  font-family: 'Heavent-med', sans-serif;
  font-size: 18px;
  line-height: 18px;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: #7B64AF;
}

.hrv-doc-title {
  font-family: 'Heavent', sans-serif;
  font-size: 20px;
  line-height: 25px;
  color: #1F2937;
  margin-top: 6px !important;
}

.hrv-list {
  margin-top: 16px;
  text-align: left;
  position: relative;
  z-index: 1;
}

.hrv-item {
  display: flex;
  align-items: center;
  background: #FFFFFF;
  border: 1px solid #EDE9FE;
  border-radius: 12px;
  padding: 11px 13px;
  margin-bottom: 10px;
  box-shadow: 0px 1px 2px 0px #7B64AF0F;
}

.hrv-ico {
  flex: 0 0 auto;
  width: 30px;
  height: 30px;
  margin-right: 9px;
  border-radius: 10px;
  background: linear-gradient(135deg, #F5F3FF 0%, #FBF7EE 100%);
  border: 1px solid #EDE9FE;
  display: flex;
  align-items: center;
  justify-content: center;
}

.hrv-ico >>> svg {
  width: 20px;
  height: 20px;
  display: block;
}

.hrv-item-text {
  font-family: 'Heavent-med', sans-serif;
  font-size: 16px;
  line-height: 20px;
  color: #3E305B;
  white-space: nowrap;
}

/* ไอคอนเอกสารจาง ๆ เติมพื้นที่ว่างด้านล่างจอ */
.hrv-doc-watermark {
  position: absolute;
  z-index: 0;
  left: 50%;
  bottom: 8%;
  transform: translateX(-50%);
  width: 118px;
  height: 118px;
  opacity: 0.09;
  pointer-events: none;
}

.hrv-doc-watermark svg {
  width: 100%;
  height: 100%;
  display: block;
}

/* ----- chat ----- */
.hrv-chat-head {
  display: flex;
  align-items: center;
  gap: 9px;
  background: #FFFFFF;
  border-bottom: 1px solid #EDE9FE;
  padding: 34px 16px 12px;
}

.hrv-bot {
  flex: 0 0 auto;
  width: 30px;
  height: 30px;
  display: block;
}

.hrv-bot svg {
  width: 30px;
  height: 30px;
  display: block;
}

.hrv-bot-name {
  font-family: 'Heavent-med', sans-serif;
  font-size: 20px;
  line-height: 20px;
  color: #7B64AF;
}

.hrv-chat {
  flex: 1 1 auto;
  display: flex;
  flex-direction: column;
  gap: 10px;
  padding: 18px 14px;
}

.hrv-bubble {
  max-width: 80%;
  font-family: 'Heavent-body', sans-serif;
  font-size: 18px;
  line-height: 24px;
  border-radius: 16px;
  padding: 10px 14px 8px;
}

.hrv-bubble-out {
  align-self: flex-end;
  background: #7B64AF;
  color: #FFFFFF;
  border-bottom-right-radius: 6px;
}

.hrv-bubble-in {
  align-self: flex-start;
  background: #FFFFFF;
  color: #3E305B;
  border: 1px solid #EDE9FE;
  border-bottom-left-radius: 6px;
}

.hrv-typing {
  display: flex;
  align-items: center;
  gap: 5px;
  padding: 14px 14px;
}

.hrv-typing span {
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: #B7A9D5;
  animation: hrv-blink 1.2s infinite ease-in-out;
}

.hrv-typing span:nth-child(2) {
  animation-delay: 0.2s;
}

.hrv-typing span:nth-child(3) {
  animation-delay: 0.4s;
}

@keyframes hrv-blink {

  0%,
  80%,
  100% {
    opacity: 0.3;
  }

  40% {
    opacity: 1;
  }
}

@media only screen and (max-width: 600px) {
  .hrv-phone {
    width: 280px;
  }

  .hrv-screen {
    border-radius: 35px;
  }
}
</style>
