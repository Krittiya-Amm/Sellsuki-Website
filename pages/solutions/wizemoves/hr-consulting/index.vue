<template>
  <div id="HRConsulting">

    <div class="modal fade" id="exampleModalToggle" aria-hidden="true" aria-labelledby="exampleModalToggleLabel"
      tabindex="-1">
      <div class="modal-dialog modal-lg modal-dialog-centered">
        <div class="modal-content modal-custom-size">
          <div class="modal-header p-0">
            <span id="exampleModalLabel" class="header-model">
              สนใจรับคำปรึกษา
            </span>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"
              data-tag="close_modal_button"></button>
          </div>
          <div class="modal-body p-0">
            <FormDataUser :interested="interested" :blog="this.$route.query.blog" />
          </div>
        </div>
      </div>
    </div>
    <SuccessForm bu="Wizemoves" />
    <section class="hero-section">
      <div class="bg-img d-none d-md-block mt-5">
        <div class="pb-md-0 pb-5 bg-color">
          <div class="container">
            <div class="row">
              <div class="col-xxl-6 col-xl-6 col-lg-6 col-md-7 col-sm-6 col-6">
                <table class="align-middle banner-main" style="width: 100%">
                  <td class="banner-height">
                    <ol class="font-md">
                      <ul class="breadcrumb">
                        <li>
                          <img class="mb-1 me-1" src="~/assets/SolutionsWizemoves/home.png" /><nuxt-link
                            :to="localePath('/')" data-tag="breadcrumb_business_desktop"><span
                              class="text-s-20 color-FFFFFF ms-1">Business</span></nuxt-link>
                          <img class="mb-1 ms-1" src="~/assets/SolutionsWizemoves/chevron-right.png" />
                        </li>
                        <li>
                          <nuxt-link :to="localePath('/solutions/wizemoves')"
                            data-tag="breadcrumb_wizemoves_desktop"><span
                              class="text-s-20 color-FFFFFF ms-1">WizeMoves</span></nuxt-link>
                          <img class="mb-1 ms-1" src="~/assets/SolutionsWizemoves/chevron-right.png" />
                        </li>
                        <li>
                          <span class="text-s-20 color-FFFFFF ms-1">HR Consulting</span>
                        </li>
                      </ul>
                    </ol>
                    <div class="mt-5">
                      <h1 class="font-bd text-s-52 color-FFFFFF">
                        HR Consulting
                      </h1>
                    </div>
                    <p class="font-bd text-s-36 mt-3 color-FFFFFF">
                      เปลี่ยนศักยภาพคนให้เป็นผลลัพธ์ธุรกิจ<br />
                      ด้วยระบบ HR ที่ SME วัดผลได้จริง
                    </p>
                    <p class="text-s-24 mt-3 color-FFFFFF">
                      วางรากฐานด้วย Structured HR Data และกลยุทธ์
                      HR Business Partner โดยมืออาชีพ<br />
                      เพื่อสร้างการเติบโตที่ยั่งยืนผ่าน Performance Management &amp; Skill Matrix
                    </p>
                    <div class="d-flex flex-wrap mt-3">
                      <div class="badge-wizemoves">
                        <img src="~/assets/SolutionsWizemoves/Consulting/Subtract.png" alt="Subtract.png"
                          class="icon" />
                        <span class="text text-s-20 font-df">ที่ปรึกษางานทรัพยากรบุคคล</span>
                      </div>
                      <div class="badge-wizemoves ms-2">
                        <img src="~/assets/SolutionsWizemoves/Consulting/Subtract.png" alt="Subtract.png"
                          class="icon" />
                        <span class="text text-s-20 font-df">วางระบบ HR</span>
                      </div>
                    </div>
                    <div class="d-flex flex-wrap mt-4">
                      <nuxt-link :to="{ path: '/solutions/wizemoves/business-consulting/af' }"
                        class="btn-gradient text-s-24 font-md py-2" data-tag="hero_get_free_consultation_desktop">
                        <img src="~/assets/SolutionsWizemoves/Consulting/cursor-arrow-rays.png"
                          alt="cursor-arrow-rays.png" class="icon" />
                        <span class="text">นัดปรึกษาผู้เชี่ยวชาญฟรี</span>
                      </nuxt-link>
                      <a href="tel:0900967526" class="btn-white-violet text-s-24 font-bd py-2 ms-3"
                        data-tag="hero_call_button_desktop"><img class="me-2"
                          src="~/assets/SolutionsWizemoves/Consulting/chat-bubble-left-right-color.png"
                          alt="chat-bubble-left-right-color.png.png" />090-096-7526
                      </a>
                    </div>
                  </td>
                </table>
              </div>
              <!-- hero visual now comes from the background photo (HRConsulting/hero-banner.jpg),
                   so the cut-out portrait overlay is no longer needed here -->
              <div class="col-xxl-6 col-xl-6 col-lg-6 col-md-5 col-sm-6 col-6 d-flex"></div>
            </div>
          </div>
        </div>
      </div>
      <div class="bg-img-mobile d-block d-md-none" style="height: 652px;margin-top:64px">
        <div class="bg-color-mobile">
          <div class="container p-4">
            <div class="row">
              <div class="col-xxl-12 col-xl-12 col-lg-12 col-md-12 col-sm-12 col-12">
                <ol class="font-md mt-2">
                  <ul class="breadcrumb">
                    <li>
                      <img class="mb-1 me-1" src="~/assets/SolutionsWizemoves/home.png" /><nuxt-link
                        @click="scrollToTop" :to="localePath('/')" data-tag="breadcrumb_business_mobile"><span
                          class="text-s-20 color-FFFFFF">Business</span></nuxt-link> <img class="mb-1"
                        src="~/assets/SolutionsWizemoves/chevron-right.png" />  
                    </li>
                    <li>
                      <nuxt-link @click="scrollToTop" :to="localePath('/solutions/wizemoves')"
                        data-tag="breadcrumb_wizemoves_mobile"><span
                          class="text-s-20 color-FFFFFF ms-1">WizeMoves</span></nuxt-link> <img class="mb-1"
                        src="~/assets/SolutionsWizemoves/chevron-right.png" />
                    </li>
                    <li>
                      <span class="text-s-20 color-FFFFFF ms-1">HR Consulting</span>
                    </li>
                  </ul>
                </ol>
                <div class="mt-3">
                  <h1 class="font-bd text-s-44 mb-0 color-FFFFFF">
                    HR Consulting
                  </h1>
                </div>
                <p class="font-bd text-s-24 mt-2 mb-2 color-FFFFFF">
                  เปลี่ยนศักยภาพคนให้เป็นผลลัพธ์ธุรกิจ<br />
                  ด้วยระบบ HR ที่ SME วัดผลได้จริง
                </p>
                <p class="text-s-20 mb-1 color-FFFFFF">
                  วางรากฐานด้วย Structured HR Data และกลยุทธ์
                  HR Business Partner โดยมืออาชีพ
                  เพื่อสร้างการเติบโตที่ยั่งยืนผ่าน Performance Management &amp; Skill Matrix
                </p>
                <div class="d-flex flex-wrap mt-3">
                  <div class="badge-wizemoves">
                    <img src="~/assets/SolutionsWizemoves/Consulting/Subtract.png" alt="Subtract.png" class="icon" />
                    <span class="text text-s-18 font-df">ที่ปรึกษางานทรัพยากรบุคคล</span>
                  </div>
                  <div class="badge-wizemoves ms-2">
                    <img src="~/assets/SolutionsWizemoves/Consulting/Subtract.png" alt="Subtract.png" class="icon" />
                    <span class="text text-s-18 font-df">วางระบบ HR</span>
                  </div>
                </div>
                <div class="d-flex flex-wrap mt-4">
                  <nuxt-link :to="{ path: '/solutions/wizemoves/business-consulting/af' }"
                    class="btn-gradient text-s-20 font-md py-2" data-tag="hero_get_free_consultation_mobile">
                    <img src="~/assets/SolutionsWizemoves/Consulting/cursor-arrow-rays.png" alt="cursor-arrow-rays.png"
                      class="icon" />
                    <span class="text">นัดปรึกษาผู้เชี่ยวชาญฟรี</span>
                  </nuxt-link>
                  <a href="tel:0900967526" class="btn-white-violet text-s-20 font-bd py-2 ms-3"
                    data-tag="hero_call_button_mobile"><img class="me-2"
                      src="~/assets/SolutionsWizemoves/Consulting/chat-bubble-left-right-color.png"
                      alt="chat-bubble-left-right-color.png.png" />090-096-7526
                  </a>
                </div>
              </div>
              <!-- spacer: lets the background photo show below the copy on mobile -->
              <div class="row">
                <div class="col-12" style="min-height: 300px;"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>


    <section class="scroll-div animate__animated  animate__fadeIn" v-if="showDiv"
      style="position: fixed;top: 0px;z-index: 999;width: 100%;background: #7C3AED;">
      <nav class="navbar navbar-expand-lg ps-md-0 pe-md-0 ps-3 pe-3 p-0"
        style="z-index: 9999;box-shadow: 0px 1px 3px 0px #7B64AF12,0px 5px 5px 0px #7B64AF0F,0px 12px 7px 0px #7B64AF0A,0px 20px 8px 0px #7B64AF03,0px 32px 9px 0px #7B64AF00;">
        <div class="container">
          <div class="ml-2 d-lg-block d-none">
            <ul class="navbar-nav text-s-24 text-w-500">
              <div v-for="(button, index) in buttons" :key="index"
                :class="{ 'nav-active': activeSection === button.name }" @click="setActiveButton(index)">
                <a :href="button.id" :data-tag="`navbar_scroll_${button.name}`">
                  <li class="nav-item d-flex ps-3 pe-3" style="padding-top: 19px;padding-bottom: 19px;">
                    <div class="nav-link p-0 text-s-24 m-auto">{{ button.label }}</div>
                  </li>
                </a>
              </div>
            </ul>
          </div>
          <div class="ml-2 d-lg-none d-block">
            <select @change="handleChange(activeSection)" v-model="activeSection"
              class="form-select custom-select mt-3 mb-3 text-s-24 font-md custom-select"
              aria-label="Default select example" data-tag="navbar_scroll_dropdown">
              <option v-for="(button, index) in buttons" :key="index" :value="button.name">{{ button.label }}</option>
            </select>
          </div>
          <div class="mt-1">
            <a href="#" data-bs-target="#exampleModalToggle" data-bs-toggle="modal"
              class="btn-violet-white text-s-24 font-df p-1 ps-3 pe-3" data-tag="navbar_scroll_free_consultation"><img
                class="me-2" src="~/assets/SolutionsWizemoves/Consulting/chat-bubble-left-right-color.png"
                alt="chat-bubble-left-right-color.png.png" />ปรึกษาฟรี
            </a>
          </div>
        </div>
      </nav>
    </section>

    <section id="PainPoints" class="section-active pb-lg-5 pb-0">
      <div class="container pb-0 p-md-0 p-4">
        <div class="row pt-5">
          <div class="col-12 mt-md-5 mt-0 text-center fade-in-up" v-intersect>
            <div class="m-auto" style="
                  width: 115px;
                  border: 2px solid #00000008;
                  backdrop-filter: blur(10px);
                  border-radius: 32px;
                  background: #fff;
                ">
              <p class="text-ranbow text-s-24 text-w-700 m-0 p-1">Pain Points</p>
            </div>
            <h2 class="text-s-60 text-w-700 color-1F2937 mt-5 d-none d-lg-block">
              ยอดขายโต แต่ทำไมเจ้าของยิ่งเหนื่อย?
            </h2>
            <h2 class="text-s-44 text-w-700 color-1F2937 mt-5 d-block d-lg-none">
              ยอดขายโต<br />แต่ทำไมเจ้าของยิ่งเหนื่อย?
            </h2>

            <p class="text-s-24 text-w-700 color-1F2937 mt-3 mb-0 d-none d-lg-block">
              การ<span class="pp-hl">บริหารคน</span>แบบเดิม ๆ อาจกำลังฉุดรั้งธุรกิจคุณอยู่
            </p>
            <p class="text-s-24 text-w-700 color-1F2937 mt-3 mb-0 d-block d-lg-none">
              การ<span class="pp-hl">บริหารคน</span>แบบเดิม ๆ<br />อาจกำลังฉุดรั้งธุรกิจคุณอยู่
            </p>
          </div>
          <div class="row mt-md-5 mt-2 mb-3 fade-in-up" v-intersect>
            <div class="col-xxl-4 col-xl-4 col-lg-4 col-md-6 col-sm-12 col-12 p-3">
              <div class="card-1 p-1 d-none d-lg-block">
                <div class="card-body">
                  <img class="pp-card-icon"
                    src="~/assets/SolutionsWizemoves/Consulting/pp-chart.svg" alt="KPI">
                  <p class="text-s-36 font-bd color-1F2937 mb-2 mt-4"><span class="pp-hl">ไม่มี KPI</span>
                    ประเมินผลด้วย “ความรู้สึก”</p>
                  <p class="text-s-24 font-df color-1F2937 mb-0">ขึ้นเงินเดือนตามความพึงพอใจ ทำให้คนเก่งค่อย ๆ หายไป</p>
                </div>
              </div>
              <div class="card-1 d-block d-lg-none">
                <div class="card-body p-3 d-flex align-items-center">
                  <img class="pp-card-icon"
                    src="~/assets/SolutionsWizemoves/Consulting/pp-chart.svg" alt="KPI">
                  <div class="ms-3">
                    <p class="text-s-24 font-bd color-1F2937 mb-1"><span class="pp-hl">ไม่มี KPI</span>
                      ประเมินผลด้วย “ความรู้สึก”</p>
                    <p class="text-s-20 font-df color-1F2937 mb-1">ขึ้นเงินเดือนตามความพึงพอใจ ทำให้คนเก่งค่อย ๆ หายไป
                    </p>
                  </div>
                </div>
              </div>
            </div>
            <div class="col-xxl-4 col-xl-4 col-lg-4 col-md-6 col-sm-12 col-12 p-3">
              <div class="card-1 p-1 d-none d-lg-block">
                <div class="card-body">
                  <img class="pp-card-icon"
                    src="~/assets/SolutionsWizemoves/Consulting/pp-document.svg" alt="ข้อมูล">
                  <p class="text-s-36 font-bd color-1F2937 mb-2 mt-4">งานพัง ข้อมูลหาย เมื่อ “คนลาออก”</p>
                  <p class="text-s-24 font-df color-1F2937 mb-0">ธุรกิจรันด้วย “ตัวบุคคล” ไม่ใช่ “ระบบงาน” พอคนลาออก
                    งานสะดุด ข้อมูลหายไปด้วย</p>
                </div>
              </div>
              <div class="card-1 d-block d-lg-none">
                <div class="card-body p-3 d-flex align-items-center">
                  <img class="pp-card-icon"
                    src="~/assets/SolutionsWizemoves/Consulting/pp-document.svg" alt="ข้อมูล">
                  <div class="ms-3">
                    <p class="text-s-24 font-bd color-1F2937 mb-1">งานพัง ข้อมูลหาย เมื่อ “คนลาออก”</p>
                    <p class="text-s-20 font-df color-1F2937 mb-1">ธุรกิจรันด้วย “ตัวบุคคล” ไม่ใช่ “ระบบงาน” พอคนลาออก
                      งานสะดุด ข้อมูลหายไปด้วย</p>
                  </div>
                </div>
              </div>
            </div>
            <div class="col-xxl-4 col-xl-4 col-lg-4 col-md-6 col-sm-12 col-12 p-3">
              <div class="card-1 p-1 d-none d-lg-block">
                <div class="card-body">
                  <img class="pp-card-icon"
                    src="~/assets/SolutionsWizemoves/Consulting/pp-users.svg" alt="เจ้าของ">
                  <p class="text-s-36 font-bd color-1F2937 mb-2 mt-4">เจ้าของคือ “คอขวด” ของธุรกิจ</p>
                  <p class="text-s-24 font-df color-1F2937 mb-0">ทุกเรื่องต้องรอคุณตัดสินใจ คุณจึงไม่ใช่ “เจ้าของธุรกิจ”
                    แต่คือ “ลูกจ้างที่ค่าตัวแพงที่สุด” ในบริษัทตัวเอง</p>
                </div>
              </div>
              <div class="card-1 d-block d-lg-none">
                <div class="card-body p-3 d-flex align-items-center">
                  <img class="pp-card-icon"
                    src="~/assets/SolutionsWizemoves/Consulting/pp-users.svg" alt="เจ้าของ">
                  <div class="ms-3">
                    <p class="text-s-24 font-bd color-1F2937 mb-1">เจ้าของคือ “คอขวด” ของธุรกิจ</p>
                    <p class="text-s-20 font-df color-1F2937 mb-1">ทุกเรื่องต้องรอคุณตัดสินใจ คุณจึงไม่ใช่
                      “เจ้าของธุรกิจ” แต่คือ “ลูกจ้างที่ค่าตัวแพงที่สุด” ในบริษัทตัวเอง</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="row mt-5 fade-in-up" v-intersect>
          <div class="col-lg-6 col-12">
            <img class="img-fluid" src="~/assets/SolutionsWizemoves/Consulting/wizemoves.png" alt="wizemoves.png">
          </div>
          <div class="col-lg-6 col-12 d-flex align-items-center">
            <div class="text-center">
              <img class="img-fluid" style="width: 400px; max-width: 100%;" src="~/assets/SolutionsWizemoves/Consulting/wizemoves-hr-logo.png" alt="WizeMoves HR Business Solutions">
              <p class="text-s-44 font-bd mt-4">หยุดแก้ปัญหาคนเดียว</p>
              <p class="text-s-24 mb-lg-4 mb-4">หยุดแก้ปัญหาคนเดียว ให้ WizeMoves HR ช่วยวางระบบ HR อัตโนมัติ
                ทั้ง Structured HR Data, Performance Management และ Employer Branding</p>
              <nuxt-link :to="{ path: '/solutions/wizemoves/business-consulting/af' }"
                class="btn-gradient text-s-24 font-md py-2" data-tag="pain_points_section_get_free_consultation">
                <span class="text">ปรึกษาการวางระบบ HR ฟรี</span>
              </nuxt-link>
            </div>
          </div>
        </div>
      </div>
    </section>

    <div id="WhyUS" class="pt-5"></div>
    <section id="WhyUS" class="bg-img-3 mb-md-0 mb-5 section-active">
      <div class="pt-5 pb-5">
        <div class="container">
          <div class="d-none d-md-block">
            <div class="row py-80">
              <div class="col-12 text-center mb-5">
                <div class="border-ranbow d-inline-flex mt-5">
                  <span class="text-ranbow text-s-24 text-w-700 m-0">Why Us</span>
                </div>
              </div>
              <div class="col-6 col-6-custom-1 color-FFFFFF d-flex fade-in-up" v-intersect>
                <div class="text-start">
                  <div class="d-lg-block d-md-none">
                    <h2 class="text-s-60 font-bd mb-0">
                      ทำไมผู้ประกอบการ SME<br />ที่กำลังโต ถึงเลือกวางใจ<br />เคียงข้างไปกับ WizeMoves HR?
                    </h2>
                    <p class="text-s-24 mt-4 mb-0">
                      เพราะเราคือ “คนทำธุรกิจที่ลองผิดลองถูกจนเจอสูตรสำเร็จ” ไม่ใช่แค่ที่ปรึกษาจากตำรา
                    </p>
                  </div>
                  <div class="d-lg-none d-md-block">
                    <h2 class="text-s-44 font-bd mb-0">
                      ทำไมผู้ประกอบการ SME<br />ที่กำลังโต ถึงเลือกวางใจ<br />เคียงข้างไปกับ WizeMoves HR?
                    </h2>
                    <p class="text-s-24 mt-3 mb-0">
                      เพราะเราคือ “คนทำธุรกิจที่ลองผิดลองถูกจนเจอสูตรสำเร็จ” ไม่ใช่แค่ที่ปรึกษาจากตำรา
                    </p>
                  </div>
                </div>
              </div>
              <div class="col-6 col-6-custom-2 fade-in-up" v-intersect>
                <CardBgImg type="HRConsulting" />
              </div>
            </div>
          </div>
          <div class="row ps-4 pe-4 d-block d-md-none">
            <div class="col-12 text-center pt-4 pb-4">
              <div class="border-ranbow d-inline-flex">
                <span class="text-ranbow text-s-24 text-w-700 m-0">Why Us</span>
              </div>
            </div>
            <div class="col-12 color-FFFFFF fade-in-up" v-intersect>
              <div class="text-start mb-5">
                <h2 class="text-s-44 font-bd mb-0">
                  ทำไมผู้ประกอบการ SME ที่กำลังโต<br /> ถึงเลือกวางใจเคียงข้างไปกับ WizeMoves HR?
                </h2>
                <p class="text-s-20 mt-3 mb-0">
                  เพราะเราคือ “คนทำธุรกิจที่ลองผิดลองถูกจนเจอสูตรสำเร็จ” ไม่ใช่แค่ที่ปรึกษาจากตำรา
                </p>
              </div>
            </div>
            <div class="col-12 fade-in-up" v-intersect>
              <CardBgImg type="HRConsulting" />
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="container mt-lg-5 pt-md-5 ps-lg-4 pe-lg-4 mt-0 pt-0 ps-4 pe-4">
      <div class="cart-img-text">
        <div class="cart-color-text">
          <div class="row d-none d-md-block">
            <div class="col-12 text-center color-FFFFFF d-flex" style="height: 370px">
              <div class="my-auto mx-auto d-lg-block d-md-none">
                <h2 class="text-s-60 mb-0 font-bd mt-auto mx-auto">
                  WizeMoves HR ที่ปรึกษาการพัฒนาทรัพยากรมนุษย์<br />และการวางระบบ HR เพื่อสเกลธุรกิจอย่างยั่งยืน
                </h2>
                <p class="text-s-28 mb-0">เพราะระบบ HR ที่ดี... ไม่ใช่แค่แก้ปัญหาความขัดแย้งรายวัน
                  แต่คือรากฐาน System-led ที่พิสูจน์ได้
                </p>
              </div>
              <div class="my-auto mx-auto d-lg-none d-md-block">
                <h2 class="text-s-44 mb-0 font-bd mt-auto mx-auto">
                  WizeMoves HR ที่ปรึกษาการพัฒนาทรัพยากรมนุษย์<br />และการวางระบบ HR เพื่อสเกลธุรกิจอย่างยั่งยืน
                </h2>
                <p class="text-s-20 mb-0 mt-3">เพราะระบบ HR ที่ดี... ไม่ใช่แค่แก้ปัญหาความขัดแย้งรายวัน<br />
                  แต่คือรากฐาน System-led ที่พิสูจน์ได้</p>
              </div>
            </div>
          </div>
          <div class="row d-block d-md-none">
            <div class="col-12 text-center color-FFFFFF d-flex ps-3 pe-3" style="height: 500px">
              <div class="my-auto mx-auto">
                <h2 class="text-s-44 mb-0 font-bd mt-auto mx-auto">
                  WizeMoves HR<br /> ที่ปรึกษาการพัฒนาทรัพยากรมนุษย์<br /> และการวางระบบ HR<br />
                  เพื่อสเกลธุรกิจอย่างยั่งยืน
                </h2>
                <p class="text-s-20 mt-3 mb-0">เพราะระบบ HR ที่ดี...<br />
                  ไม่ใช่แค่แก้ปัญหาความขัดแย้งรายวัน<br />แต่คือรากฐาน System-led ที่พิสูจน์ได้</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- ===== Service Zoning : how we scope a package to the customer's zone ===== -->
    <section id="ServiceZoning" class="section-spacing section-active">
      <div class="container ps-4 pe-4 ps-md-0 pe-md-0">
        <div class="row">
          <div class="col-12 text-center">
            <div class="border-ranbow d-inline-flex zoning-badge">
              <span class="text-ranbow text-s-24 text-w-700 m-0">Service Zoning</span>
            </div>
          </div>
        </div>

        <!-- layout : heading + intro + mascot (left) + zone staircase (right) -->
        <div class="row align-items-center zoning-layout">
          <!-- ลูกศร trending ขึ้น (เดคอเรชันทับการ์ด) -->
          <div class="zoning-arrow" aria-hidden="true">
            <svg viewBox="0 0 480 720" fill="none" xmlns="http://www.w3.org/2000/svg">
              <defs>
                <linearGradient id="zoneArrowGrad" x1="0.15" y1="1" x2="0.85" y2="0">
                  <stop offset="0" stop-color="#FBFAFF" />
                  <stop offset="1" stop-color="#EDE9FE" />
                </linearGradient>
              </defs>
              <path d="M70 726 L235 355 L298 448 L384 230" stroke="url(#zoneArrowGrad)" stroke-width="95"
                stroke-linecap="butt" stroke-linejoin="miter" stroke-miterlimit="8" fill="none" />
              <polygon points="445,93 471,269 297,191" fill="url(#zoneArrowGrad)" />
            </svg>
          </div>
          <!-- left : ข้อความหัวข้อ + มาสคอต -->
          <div class="col-12 text-center text-lg-start zoning-intro-col zoning-col-left">
            <h2 class="font-bd color-1F2937 mb-0 text-s-60 d-none d-lg-block">
              ตรวจโรคองค์กรด้วย <span class="text-nowrap">Service Zoning</span>
            </h2>
            <h2 class="font-bd color-1F2937 mb-0 text-s-44 d-lg-none">
              ตรวจโรคองค์กรด้วย <span class="text-nowrap">Service Zoning</span>
            </h2>
            <p class="text-s-24 font-df color-6B7280 mb-0 mt-3 zoning-intro">
              แต่ละองค์กรมี “ความพร้อม” และ “รอยรั่ว” ต่างกัน
              เราจึงประเมินตาม <span class="font-md color-1F2937">4 Performance Zones</span>
              เพื่อออกแบบบริการที่ตอบโจทย์และคุ้มค่าที่สุด
              มาเช็กว่าตอนนี้พนักงานคุณอยู่โซนไหน
              แมตช์โซลูชันที่ใช่ ให้ตรงขนาดองค์กรและงบประมาณ
            </p>
            <div class="zoning-mascot mt-4">
              <img src="~/assets/SolutionsWizemoves/Consulting/wizemoves.png" alt="WizeMoves mascot"
                class="img-fluid zoning-mascot-img" />
            </div>
          </div>

          <!-- right : zone list (การ์ดโซน สไตล์เดียวกับทั้งหน้า) -->
          <div class="col-12 mt-4 mt-lg-0 zoning-col-right">
            <div class="zoning-list">
              <div v-for="(zone, i) in serviceZones" :key="'zone-' + zone.key" class="zoning-item"
                :class="'zone-' + zone.key">
                <div class="zoning-item-no">{{ '0' + (i + 1) }}</div>
                <div class="zoning-item-content">
                  <span class="text-s-16 font-md d-block zoning-zone-name">{{ zone.name }}</span>
                  <span class="text-s-28 font-bd color-1F2937 d-block zoning-zone-role">{{ zone.role }}</span>
                  <p class="text-s-24 mb-0 mt-2 zoning-item-desc">
                    <span v-if="zone.lead" class="font-bd zoning-desc-lead">{{ zone.lead }} </span>
                    <span class="font-df color-6B7280">{{ zone.desc }}</span>
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- ===== Product line-up : ภาพรวม 6 บริการ ===== -->
    <section id="ProductLineup" class="section-spacing">
      <div class="container ps-4 pe-4 ps-md-0 pe-md-0">
        <div class="product-panel">
          <div class="row">
            <div class="col-12 text-center">
              <div class="border-ranbow d-inline-flex product-badge">
                <span class="text-ranbow text-s-24 text-w-700 m-0">Products</span>
              </div>
              <h2 class="font-bd color-1F2937 mb-0 mt-3 text-s-60 d-none d-xl-block">
                บริการของ WizeMoves HR
              </h2>
              <h2 class="font-bd color-1F2937 mb-0 mt-3 text-s-44 d-xl-none">
                บริการของ WizeMoves HR
              </h2>
            </div>
          </div>

          <!-- แถวบน : 2 การ์ด (เต็มความกว้าง container การ์ดละครึ่ง) -->
          <div class="row mt-4 mt-md-5 justify-content-center product-row-top">
            <div v-for="product in hrProductCards.slice(0, 2)" :key="product.name" class="col-lg-6 col-md-6 col-12 p-2 p-md-3">
              <div class="product-card h-100">
                <span v-if="product.comingSoon" class="product-flag">Coming soon</span>
                <div class="product-icon-group">
                  <div class="product-icon-aura"></div>
                  <div class="product-icon-tile">
                    <span class="product-icon" v-html="product.icon"></span>
                  </div>
                </div>
                <p class="text-s-24 font-bd color-1F2937 mb-0 product-name">{{ product.name }}</p>
                <p v-if="product.sub" class="text-s-20 font-df mb-0 product-sub">{{ product.sub }}</p>
                <p v-if="product.desc" class="text-s-20 font-df mb-0 product-desc">{{ product.desc }}</p>
              </div>
            </div>
          </div>

          <!-- แถวล่าง : 3 การ์ด -->
          <div class="row justify-content-center product-row-bottom">
            <div v-for="product in hrProductCards.slice(2)" :key="product.name" class="col-lg-4 col-md-6 col-12 p-2 p-md-3">
              <div class="product-card h-100">
                <span v-if="product.comingSoon" class="product-flag">Coming soon</span>
                <div class="product-icon-group">
                  <div class="product-icon-aura"></div>
                  <div class="product-icon-tile">
                    <span class="product-icon" v-html="product.icon"></span>
                  </div>
                </div>
                <p class="text-s-24 font-bd color-1F2937 mb-0 product-name">{{ product.name }}</p>
                <p v-if="product.sub" class="text-s-20 font-df mb-0 product-sub">{{ product.sub }}</p>
                <p v-if="product.desc" class="text-s-20 font-df mb-0 product-desc">{{ product.desc }}</p>
              </div>
            </div>
          </div>

          <div class="row">
            <div class="col-12 text-center product-closing">
              <p class="font-bd mb-0 product-closing-1 text-s-36 d-none d-md-block">
                ทางลัดสำหรับองค์กรเริ่มต้น แก้ปัญหาได้เองทันที
              </p>
              <p class="font-bd mb-0 product-closing-1 text-s-24 d-block d-md-none">
                ทางลัดสำหรับองค์กรเริ่มต้น<br />แก้ปัญหาได้เองทันที
              </p>
              <p class="font-md mb-0 product-closing-2 text-s-24 d-none d-md-block">
                ยกระดับแบบมีพาร์ทเนอร์ดูแล เน้นการลงมือทำจริง เจาะลึก และแก้ปัญหาเชิงโครงสร้าง
              </p>
              <p class="font-md mb-0 product-closing-2 text-s-20 d-block d-md-none">
                ยกระดับแบบมีพาร์ทเนอร์ดูแล เน้นการลงมือทำจริง<br />เจาะลึก และแก้ปัญหาเชิงโครงสร้าง
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- ===== Product : รายละเอียด Product ที่เริ่มใช้ได้เอง ===== -->
    <section id="Product" class="section-spacing section-active">
      <div class="container ps-md-0 pe-md-0 ps-4 pe-4">
        <div class="row">
          <div class="col-12 text-center mt-5 mb-5 pb-5">
            <div class="m-auto" style="
                width: 95px;
                border: 2px solid #00000008;
                backdrop-filter: blur(10px);
                border-radius: 32px;
                background: #fff;
              ">
              <p class="text-ranbow text-s-24 text-w-700 m-0 p-1">Product</p>
            </div>
          </div>
          <div class="col-md-6 col-12">
            <p class="text-s-60 font-bd mb-0 d-none d-xl-block" style="line-height: 120%;">
              เครื่องมือ HR พร้อมใช้<br />สำหรับองค์กรที่กำลังโต</p>
            <p class="text-s-44 font-bd mb-0 d-none d-md-block d-xl-none">
              เครื่องมือ HR พร้อมใช้<br />สำหรับองค์กร<br />ที่กำลังโต</p>
            <p class="text-s-44 font-bd mb-0 d-block d-md-none">เครื่องมือ HR พร้อมใช้<br />สำหรับองค์กรที่กำลังโต
            </p>
          </div>
          <div class="col-md-6 col-12">
            <div class="d-none d-xl-block">
              <p class="text-s-24 font-df mb-0 mt-3">องค์กรที่เพิ่งเริ่มต้นไม่จำเป็นต้องรอมีฝ่าย HR เต็มรูปแบบ
                <span class="font-bd">WizeMoves</span> ออกแบบ
                <span class="font-bd">Product ด้าน HR ที่เริ่มใช้ได้ทันที</span>
                ตั้งแต่ชุดเอกสารและระบบพื้นฐาน ไปจนถึงเครื่องมือที่ช่วยตอบคำถามพนักงานแทนคุณ
              </p>
              <p class="text-s-24 font-df mb-0 mt-4">ทุก Product ถอดมาจากปัญหาจริงที่เจ้าของธุรกิจเจอบ่อยที่สุด
                <span class="font-bd">ลดความเสี่ยงด้านกฎหมายแรงงาน ลดงานซ้ำซ้อน
                  และทำให้คุณกลับไปโฟกัสงานที่สร้างการเติบโตได้จริง</span>
              </p>
            </div>
            <div class="d-block d-xl-none">
              <p class="text-s-20 font-df mb-0 mt-2">องค์กรที่เพิ่งเริ่มต้นไม่จำเป็นต้องรอมีฝ่าย HR เต็มรูปแบบ
                WizeMoves ออกแบบ Product ด้าน HR ที่เริ่มใช้ได้ทันที ตั้งแต่ชุดเอกสารและระบบพื้นฐาน
                ไปจนถึงเครื่องมือที่ช่วยตอบคำถามพนักงานแทนคุณ</p>
              <p class="text-s-20 font-df mb-0 mt-4">ทุก Product ถอดมาจากปัญหาจริงที่เจ้าของธุรกิจเจอบ่อยที่สุด
                ลดความเสี่ยงด้านกฎหมายแรงงาน ลดงานซ้ำซ้อน และทำให้คุณกลับไปโฟกัสงานที่สร้างการเติบโตได้จริง</p>
            </div>
          </div>
        </div>
        <div class="mt-5 pt-5">
          <div class="row pt-lg-5 mt-lg-5 pt-0 mt-0">
            <!-- ซ้าย : เนื้อหา Product -->
            <div class="col-xxl-6 col-xl-6 col-lg-6 col-md-6 col-sm-12 col-12 pe-0 ps-0 pb-200">

              <!-- Product 1 : HR Template -->
              <HRProductVisual type="template" :items="hrTemplateItems"
                class="mb-4 d-block d-md-none" />
              <span class="text-s-24 font-md text-hl">“เพิ่งตั้งบริษัท ยังไม่มีฝ่าย HR”</span>
              <p class="text-s-52 font-md color-1F2937 mb-0 mt-4">
                HR Template
              </p>
              <p class="text-s-24 color-1F2937 mb-0 mt-4">
                จากพนักงานใหม่ที่ลาออกกลางคัน เสี่ยงผิดกฎหมายแรงงานเพราะเอกสารไม่รัดกุม
                ไปจนถึงการประเมินผลที่ไม่มีมาตรฐานชัดเจน
                ทุกความเสี่ยงด้าน HR มีทางป้องกันได้
              </p>
              <p class="text-s-24 font-bd color-1F2937 mb-0 mt-4">ปัญหาที่องค์กรเริ่มต้นเจอบ่อย</p>
              <div class="row mt-4 space-tigger">
                <div v-for="item in hrTemplateProblems" :key="item.title" class="col-lg-6 col-12 pe-0">
                  <div class="card card-01">
                    <div class="card-body d-flex align-items-center">
                      <span class="svc-card-icon" v-html="item.icon"></span>
                      <span class="ms-2">{{ item.title }}</span>
                    </div>
                    <p class="text-s-24 font-df pe-4 mb-0">{{ item.desc }}</p>
                    <p class="text-s-24 font-df svc-solution mb-0"><span v-if="item.solPre">{{ item.solPre }}</span><span class="svc-sol-name">{{ item.solName }}</span><span v-if="item.solPost">{{ item.solPost }}</span></p>
                  </div>
                </div>
              </div>
              <div class="row mt-4">
                <div class="col-12">
                  <a href="https://www.sellsuki.co.th/solutions/wizemoves/hr-consult/hr-template"
                    target="_blank" rel="noopener noreferrer"
                    class="btn-transparent-violet text-s-24 font-md py-2" data-tag="product_hr_template_view_packages">
                    <span class="text">ดูรายละเอียดแพ็กเกจ</span>
                  </a>
                </div>
              </div>


              <div class="space-services"></div>

              <!-- Product 2 : HR Chatbot & Employee Insight Dashboard -->
              <HRProductVisual type="chatbot" class="mb-4 d-block d-md-none" />
              <span class="text-s-24 font-md text-hl">“พนักงานถามซ้ำ ๆ ทุกวัน จนไม่มีเวลาทำงานสำคัญ”</span>
              <p class="text-s-52 font-md color-1F2937 mb-0 mt-4">
                HR Chatbot<br class="d-none d-lg-block" />
                & Employee Insight Dashboard
              </p>
              <p class="text-s-24 color-1F2937 mb-0 mt-4">
                พนักงานสอบถามผ่านไลน์ตลอดทั้งวัน ลาพักร้อนยังไง เบิกจ่ายยังไง
                จนเจ้าของธุรกิจไม่มีเวลาทำงานสำคัญ
                ยิ่งองค์กรเติบโต ยิ่งเสียเวลากับคำถามที่ซ้ำซ้อน
              </p>
              <p class="text-s-24 color-1F2937 mb-0">
                เปลี่ยน LINE OA ให้เป็น <span class="font-bd">HR Chatbot</span> ที่ตอบคำถามพนักงานได้ไม่จำกัด 24 ชม.
                พร้อมสรุปสิ่งที่พนักงานถามและรู้สึกเป็น <span class="font-bd">Insight Dashboard</span>
                ให้ผู้บริหารดูได้ในคลิกเดียว
              </p>
              <div class="row mt-4 space-tigger">
                <div v-for="item in hrChatbotFeatures" :key="item.title" class="col-lg-6 col-12 pe-0">
                  <div class="card card-01">
                    <div class="card-body d-flex align-items-center">
                      <span class="svc-card-icon" v-html="item.icon"></span>
                      <span class="ms-2">{{ item.title }}</span>
                    </div>
                    <p class="text-s-24 font-df pe-4">{{ item.desc }}</p>
                  </div>
                </div>
              </div>
              <div class="mt-2">
                <span v-for="tag in hrChatbotTags" :key="tag" class="svc-tag text-s-20 font-md">{{ tag }}</span>
              </div>
              <p class="text-s-24 font-bd color-1F2937 mb-0 mt-2">ราคาตามขนาดองค์กร</p>
              <div class="row mt-4">
                <div class="col-12">
                  <span class="svc-coming-soon text-s-24 font-md">Coming soon</span>
                </div>
              </div>


            </div>
            <!-- ขวา : ภาพประกอบ Product (sticky) -->
            <div class="col-xxl-6 col-xl-6 col-lg-6 col-md-6 col-sm-12 col-12 d-none d-md-block">
              <div class="svc-sticky">
                <transition name="fade" mode="out-in">
                  <HRProductVisual :key="activeProduct" :type="activeProduct"
                    :items="hrTemplateItems" class="fade-transition" />
                </transition>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- ===== Services : บริการที่ปรึกษาแบบมีพาร์ทเนอร์ดูแล ===== -->
    <section id="Services" class="section-spacing section-active">
      <div class="container ps-md-0 pe-md-0 ps-4 pe-4">
        <div class="row">
          <div class="col-12 text-center mt-5 mb-5 pb-5">
            <div class="m-auto" style="
                width: 95px;
                border: 2px solid #00000008;
                backdrop-filter: blur(10px);
                border-radius: 32px;
                background: #fff;
              ">
              <p class="text-ranbow text-s-24 text-w-700 m-0 p-1">Services</p>
            </div>
          </div>
          <div class="col-md-6 col-12">
            <p class="text-s-60 font-bd mb-0 d-none d-xl-block" style="line-height: 120%;">
              บริการที่ปรึกษา HR<br />แบบลงมือทำจริง</p>
            <p class="text-s-44 font-bd mb-0 d-none d-md-block d-xl-none">
              บริการที่ปรึกษา HR<br />แบบลงมือทำจริง</p>
            <p class="text-s-44 font-bd mb-0 d-block d-md-none">บริการที่ปรึกษา HR<br />แบบลงมือทำจริง</p>
          </div>
          <div class="col-md-6 col-12">
            <div class="d-none d-xl-block">
              <p class="text-s-24 font-df mb-0 mt-3">เลือกระดับการดูแลที่ตรงกับสถานการณ์องค์กรคุณ ตั้งแต่
                <span class="font-bd">แก้วิกฤตเฉพาะหน้า</span> ไปจนถึง
                <span class="font-bd">วางกลยุทธ์คนระยะยาว</span></p>
              <p class="text-s-24 font-df mb-0 mt-4"><span class="font-bd">WizeMoves</span>
                ไม่ใช่แค่ที่ปรึกษา แต่เป็นพาร์ทเนอร์ที่ลงมือทำจริงเคียงข้างทีมคุณ
                ตั้งแต่การวางระบบไปจนถึงการโค้ชผลงานให้เห็นผลที่วัดได้</p>
            </div>
            <div class="d-block d-xl-none">
              <p class="text-s-20 font-df mb-0 mt-2">เลือกระดับการดูแลที่ตรงกับสถานการณ์องค์กรคุณ ตั้งแต่แก้วิกฤตเฉพาะหน้า
                ไปจนถึงวางกลยุทธ์คนระยะยาว</p>
              <p class="text-s-20 font-df mb-0 mt-4">WizeMoves ไม่ใช่แค่ที่ปรึกษา
                แต่เป็นพาร์ทเนอร์ที่ลงมือทำจริงเคียงข้างทีมคุณ ตั้งแต่การวางระบบไปจนถึงการโค้ชผลงานให้เห็นผลที่วัดได้</p>
            </div>
          </div>
        </div>
        <div class="mt-5 pt-5">
          <div class="row pt-lg-5 mt-lg-5 pt-0 mt-0">
            <div class="col-xxl-6 col-xl-6 col-lg-6 col-md-6 col-sm-12 col-12 pe-0 ps-0 pb-200">
              <template v-for="(item, i) in hrServiceList">
                <div v-if="i !== 0" :key="item.name + '-space'" class="space-services"></div>

                <img :key="item.name + '-img'" class="img-fluid mb-4 d-block d-md-none"
                  :src="serviceImages[i]" :alt="item.name" />
                <span :key="item.name + '-sub'" class="text-s-24 font-md text-hl">{{ item.headline }}</span>
                <p :key="item.name + '-title'" class="text-s-52 font-md color-1F2937 mb-0 mt-4">
                  {{ item.name }}
                </p>
                <p :key="item.name + '-desc'" class="text-s-24 color-1F2937 mb-0 mt-3">
                  {{ item.desc }}
                </p>
                <div :key="item.name + '-cards'" class="row mt-4 space-tigger">
                  <div v-for="b in item.bullets" :key="b.text" class="col-lg-6 col-12 pe-0">
                    <div class="card card-01">
                      <div class="card-body d-flex align-items-start">
                        <span class="svc-card-icon" v-html="b.icon" aria-hidden="true"></span>
                        <span class="ms-2 text-s-24 font-df">{{ b.text }}</span>
                      </div>
                    </div>
                  </div>
                </div>
                <div :key="item.name + '-cta'" class="row mt-4">
                  <div class="col-12">
                    <a href="#" data-bs-target="#exampleModalToggle" data-bs-toggle="modal"
                      class="btn-transparent-violet text-s-24 font-md py-2" :data-tag="item.tag">
                      <span class="text">นัดปรึกษาผู้เชี่ยวชาญทันที</span>
                    </a>
                  </div>
                </div>
              </template>
            </div>
            <div class="col-xxl-6 col-xl-6 col-lg-6 col-md-6 col-sm-12 col-12 d-none d-md-block">
              <div class="sticky-macbook">
                <transition name="fade" mode="out-in">
                  <img class="p-xl-4 p-0 fade-transition" :key="currentServiceImage" :src="currentServiceImage"
                    :alt="currentServiceImage" />
                </transition>
                <img class="p-xl-4 p-0" src="~/assets/SolutionsWizemoves/Consulting/Macbook Air.png" alt="Macbook Air"
                  style="position: absolute;max-width: 95%;width: 100%;" />
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="OurSolution" class="section-spacing section-active">
      <div class="container">
        <div class="container pb-md-5 pb-0 p-md-0 p-4">
          <div class="row">
            <div class="col-12 mt-0 text-center fade-in-up" v-intersect>
              <div class="m-auto" style="
                  width: 110px;
                  border: 2px solid #00000008;
                  backdrop-filter: blur(10px);
                  border-radius: 32px;
                  background: #fff;
                ">
                <p class="text-ranbow text-s-24 text-w-700 m-0 p-1">Process</p>
              </div>
              <h2 class="text-s-60 text-w-700 color-1F2937 mt-3 d-none d-xl-block">
                ขั้นตอนการให้คำปรึกษา
              </h2>
              <h2 class="text-s-44 text-w-700 color-1F2937 mt-3 d-block d-xl-none">
                ขั้นตอนการให้คำปรึกษา
              </h2>
            </div>
            <div class="row mt-xl-5 mt-2 mb-3 fade-in-up" v-intersect>
              <div class="col-3 align-self-center d-none d-xl-block">
                <p class="text-s-44 font-bd mb-0">ขั้นตอนการ</p>
                <p class="text-s-44 font-bd mb-0">ทำงาน<span class="text-ranbow">หลังเซ็นสัญญา</span></p>
              </div>
              <div class="col-12 text-center d-block d-xl-none">
                <p class="text-s-36 font-bd mb-4 mt-4">ขั้นตอนการทำงาน<span class="text-ranbow">หลังเซ็นสัญญา</span></p>
              </div>
              <div class="col-xl-9 col-12 d-none d-md-block">
                <div class="row">
                  <div class="col-3">
                    <div class="d-flex justify-content-center">
                      <div class="outer-circle" :class="{ 'outer-circle-hover': active === 'รับบรีฟ' }">
                        <img @mouseover="active = 'รับบรีฟ'"
                          src="~/assets/SolutionsWizemoves/Consulting/clipboard-document-list.png" alt="profile"
                          class="inner-circle" :class="{ 'inner-circle-hover': active === 'รับบรีฟ' }" />
                      </div>
                      <img class="img-fluid ms-2 icon-process" src="~/assets/SolutionsWizemoves/Consulting/Line.png"
                        alt="Line.png">
                    </div>
                    <p class="text-s-36 font-md mt-4 mb-2">รวบรวมความต้องการ</p>
                    <p class="text-s-24 font-df">ทีมที่ปรึกษาและธุรกิจประชุมเพื่อเก็บข้อมูลและวิเคราะห์ความต้องการ</p>
                  </div>
                  <div class="col-3">
                    <div class="d-flex justify-content-center">
                      <div class="outer-circle" :class="{ 'outer-circle-hover': active === 'Walktrough' }">
                        <img @mouseover="active = 'Walktrough'"
                          src="~/assets/SolutionsWizemoves/Consulting/chat-bubble-left-right.png" alt="profile"
                          class="inner-circle" :class="{ 'inner-circle-hover': active === 'Walktrough' }" />
                      </div>
                      <img class="img-fluid ms-2 icon-process" src="~/assets/SolutionsWizemoves/Consulting/Line.png"
                        alt="Line.png">
                    </div>
                    <p class="text-s-36 font-md mt-4 mb-2">Walktrough</p>
                    <p class="text-s-24 font-df">ทีมที่ปรึกษา ศึกษาวิเคราะห์ปัญหาและทรัพยากรด้านบุคคลของธุรกิจ</p>
                  </div>
                  <div class="col-3">
                    <div class="d-flex justify-content-center">
                      <div class="outer-circle" :class="{ 'outer-circle-hover': active === 'Strategic Plan' }">
                        <img @mouseover="active = 'Strategic Plan'"
                          src="~/assets/SolutionsWizemoves/Consulting/cube-transparent.png" alt="profile"
                          class="inner-circle" :class="{ 'inner-circle-hover': active === 'Strategic Plan' }" />
                      </div>
                      <img class="img-fluid ms-2 icon-process" src="~/assets/SolutionsWizemoves/Consulting/Line.png"
                        alt="Line.png">
                    </div>
                    <p class="text-s-36 font-md mt-4 mb-2">Strategic Plan</p>
                    <p class="text-s-24 font-df">ทีมที่ปรึกษา วางแผนกลยุทธ์และจัดทำแผนงาน Roadmap</p>
                  </div>
                  <div class="col-3">
                    <div class="d-flex justify-content-start">
                      <div class="outer-circle" :class="{ 'outer-circle-hover': active === 'วัดผลและปรับปรุง' }">
                        <img @mouseover="active = 'วัดผลและปรับปรุง'"
                          src="~/assets/SolutionsWizemoves/Consulting/presentation-chart-bar.png" alt="profile"
                          class="inner-circle" :class="{ 'inner-circle-hover': active === 'วัดผลและปรับปรุง' }" />
                      </div>
                    </div>
                    <p class="text-s-36 font-md mt-4 mb-2">วัดผลและปรับปรุง</p>
                    <p class="text-s-24 font-df">อัพเดตการทำงาน วัดผลและปรับปรุง</p>
                  </div>
                </div>
              </div>
              <div class="col-12 d-block d-md-none">
                <div class="row">
                  <div class="col-12">
                    <div class="d-flex align-items-center">
                      <div class="d-flex flex-column align-items-center">
                        <div class="outer-circle" :class="{ 'outer-circle-hover': active === 'รับบรีฟ' }">
                          <img @mouseover="active = 'รับบรีฟ'"
                            src="~/assets/SolutionsWizemoves/Consulting/clipboard-document-list.png" alt="profile"
                            class="inner-circle" :class="{ 'inner-circle-hover': active === 'รับบรีฟ' }" />
                        </div>
                        <img class="img-fluid mt-2" src="~/assets/SolutionsWizemoves/Consulting/Line-m.png"
                          alt="Line.png">
                      </div>
                      <div class="ms-3" style="margin-top: -12px;">
                        <p class="font-md mb-2" style="font-size: 24px;line-height: 24px;">รวบรวมความต้องการ</p>
                        <p class="text-s-20 font-df">ทีมที่ปรึกษาและธุรกิจประชุมเพื่อเก็บข้อมูลและวิเคราะห์ความต้องการ</p>
                      </div>
                    </div>
                  </div>
                  <div class="col-12">
                    <div class="d-flex align-items-center mt-2">
                      <div class="d-flex flex-column align-items-center">
                        <div class="outer-circle" :class="{ 'outer-circle-hover': active === 'Walktrough' }">
                          <img @mouseover="active = 'Walktrough'"
                            src="~/assets/SolutionsWizemoves/Consulting/chat-bubble-left-right.png" alt="profile"
                            class="inner-circle" :class="{ 'inner-circle-hover': active === 'Walktrough' }" />
                        </div>
                        <img class="img-fluid mt-2" src="~/assets/SolutionsWizemoves/Consulting/Line-m.png"
                          alt="Line.png">
                      </div>
                      <div class="ms-3" style="margin-top: -12px;">
                        <p class="font-md mb-2" style="font-size: 24px;line-height: 24px;">Walktrough</p>
                        <p class="text-s-20 font-df">ทีมที่ปรึกษา ศึกษาวิเคราะห์ปัญหาและทรัพยากรด้านบุคคลของธุรกิจ</p>
                      </div>
                    </div>
                  </div>
                  <div class="col-12">
                    <div class="d-flex align-items-center mt-2">
                      <div class="d-flex flex-column align-items-center">
                        <div class="outer-circle" :class="{ 'outer-circle-hover': active === 'Strategic Plan' }">
                          <img @mouseover="active = 'Strategic Plan'"
                            src="~/assets/SolutionsWizemoves/Consulting/cube-transparent.png" alt="profile"
                            class="inner-circle" :class="{ 'inner-circle-hover': active === 'Strategic Plan' }" />
                        </div>
                        <img class="img-fluid mt-2" src="~/assets/SolutionsWizemoves/Consulting/Line-m.png"
                          alt="Line.png">
                      </div>
                      <div class="ms-3" style="margin-top: -12px;">
                        <p class="font-md mb-2" style="font-size: 24px;line-height: 24px;">Strategic Plan</p>
                        <p class="text-s-20 font-df">ทีมที่ปรึกษา วางแผนกลยุทธ์และจัดทำแผนงาน Roadmap</p>
                      </div>
                    </div>
                  </div>
                  <div class="col-12">
                    <div class="d-flex align-items-center mt-2">
                      <div class="d-flex flex-column align-items-center">
                        <div class="outer-circle" :class="{ 'outer-circle-hover': active === 'วัดผลและปรับปรุง' }">
                          <img @mouseover="active = 'วัดผลและปรับปรุง'"
                            src="~/assets/SolutionsWizemoves/Consulting/presentation-chart-bar.png" alt="profile"
                            class="inner-circle" :class="{ 'inner-circle-hover': active === 'วัดผลและปรับปรุง' }" />
                        </div>
                        <img class="img-fluid mt-2" src="~/assets/SolutionsWizemoves/Consulting/Line-m.png"
                          alt="Line.png">
                      </div>
                      <div class="ms-3" style="margin-top: -12px;">
                        <p class="font-md mb-2" style="font-size: 24px;line-height: 24px;">วัดผลและปรับปรุง</p>
                        <p class="text-s-20 font-df">อัพเดตการทำงาน วัดผลและปรับปรุง</p>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
              <div class="col-12 mt-4">
                <img class="img-fluid img-Process" src="~/assets/SolutionsWizemoves/Consulting/ImageGG.png"
                  alt="ImageGG.png">
              </div>
              <div class="col-12 mt-4 mt-xl-5">
                <p class="text-s-24 font-df proc-note text-center mb-0">
                  <span class="font-bd">หมายเหตุ:</span> ธุรกิจสามารถรับคำปรึกษาเบื้องต้นได้ในครั้งแรก และจะมีการประเมิน Zone ของธุรกิจก่อนเซ็นสัญญา
                </p>
              </div>
              <div class="col-12 text-center mt-5 pt-4">
                <nuxt-link :to="{ path: '/solutions/wizemoves/business-consulting/af' }"
                  class="btn-gradient text-s-24 font-md py-2" data-tag="process_get_free_consultation">
                  <span class="text">รับคำปรึกษากับผู้เชี่ยวชาญฟรี</span>
                </nuxt-link>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="section-spacing">
      <BlogWizemoves :responseData="responseData" />
    </section>

    <section class="section-spacing">
      <CardContact page="BusinessConsulting" />
    </section>
  </div>
</template>

<script>
import CardBgImg from '@/components/Solutions/Wizemoves/CardBgImg'
import BlogWizemoves from '@/components/Solutions/Wizemoves/BlogWizemoves'
import CardContact from '@/components/Solutions/Wizemoves/CardContact'
import FormDataUser from '@/components/Solutions/Wizemoves/FormDataUser'
import SuccessForm from '@/components/Solutions/SuccessForm'
import HRProductVisual from '@/components/Solutions/Wizemoves/HRProductVisual'

export default {
  name: 'HRConsulting',

  layout: 'layoutV2',
  components: {
    CardBgImg,
    BlogWizemoves,
    CardContact,
    FormDataUser,
    SuccessForm,
    HRProductVisual
  },
  head() {
    return this.$headUtil({
      lang: this.$i18n.locale == 'th-TH' ? 'th-TH' : 'en-TH',
      title: 'HR Consulting ที่ปรึกษางานทรัพยากรบุคคล HROD & HRBP',
      route: process.env.MAIN_URL + this.$route.path,
      description:
        'Sellsuki ที่ปรึกษางานทรัพยากรบุคคลครบวงจร ทั้ง HROD และ HRBP ช่วยออกแบบโครงสร้างองค์กร วางระบบบริหารคน พัฒนาศักยภาพทีมงาน และวางระบบประเมินผลที่วัดได้จริง',
    })
  },
  data() {
    return {
      isHidden: false,
      lang: this.$i18n.locale || 'th-TH',
      responseData: [
        { id: 1, attributes: { title: "5 กลยุทธ์การตลาดออนไลน์ที่ได้ผลในปี 2024", description: "เรียนรู้กลยุทธ์การตลาดดิจิทัลที่จะช่วยให้ธุรกิจของคุณเติบโตอย่างยั่งยืน", url: "5-digital-marketing-strategies-2024", createdAt: "2024-03-15T00:00:00.000Z", publishedAt: "2024-03-15T00:00:00.000Z", illustration: { data: { attributes: { url: "https://placehold.co/600x400/FF6603/FFFFFF/png?text=Blog+1", alternativeText: "blog image 1" } } }, blog_tags: { data: [{ attributes: { name: "Digital Marketing" } }] }, blog_category: { data: { id: 1, attributes: { name: "Marketing" } } } } },
        { id: 2, attributes: { title: "วิธีเพิ่มยอดขายออนไลน์ด้วย Social Commerce", description: "Social Commerce คืออะไรและทำไมถึงสำคัญต่อธุรกิจออนไลน์ของคุณ", url: "social-commerce-boost-sales", createdAt: "2024-02-20T00:00:00.000Z", publishedAt: "2024-02-20T00:00:00.000Z", illustration: { data: { attributes: { url: "https://placehold.co/600x400/0F225A/FFFFFF/png?text=Blog+2", alternativeText: "blog image 2" } } }, blog_tags: { data: [{ attributes: { name: "E-Commerce" } }] }, blog_category: { data: { id: 2, attributes: { name: "E-Commerce" } } } } },
        { id: 3, attributes: { title: "LINE OA สำหรับธุรกิจ: คู่มือฉบับสมบูรณ์", description: "เปิดร้านค้าบน LINE OA และเชื่อมต่อกับลูกค้าได้อย่างมีประสิทธิภาพ", url: "line-oa-business-complete-guide", createdAt: "2024-01-10T00:00:00.000Z", publishedAt: "2024-01-10T00:00:00.000Z", illustration: { data: { attributes: { url: "https://placehold.co/600x400/06C755/FFFFFF/png?text=Blog+3", alternativeText: "blog image 3" } } }, blog_tags: { data: [{ attributes: { name: "LINE" } }] }, blog_category: { data: { id: 3, attributes: { name: "LINE Agency" } } } } },
        { id: 4, attributes: { title: "Data Analytics เพื่อการตัดสินใจทางธุรกิจ", description: "ใช้ข้อมูลเพื่อขับเคลื่อนธุรกิจและเพิ่มประสิทธิภาพการทำงาน", url: "data-analytics-business-decisions", createdAt: "2023-12-05T00:00:00.000Z", publishedAt: "2023-12-05T00:00:00.000Z", illustration: { data: { attributes: { url: "https://placehold.co/600x400/7B64AF/FFFFFF/png?text=Blog+4", alternativeText: "blog image 4" } } }, blog_tags: { data: [{ attributes: { name: "Analytics" } }] }, blog_category: { data: { id: 4, attributes: { name: "Technology" } } } } }
      ],
      animation1: false,
      showDiv: false,
      activeSection: "PainPoints",
      active: "รับบรีฟ",
      buttons: [
        { label: "Pain Points", id: "#PainPoints", name: "PainPoints" },
        { label: "Why Us", id: "#WhyUS", name: "WhyUS" },
        { label: "Service Zoning", id: "#ServiceZoning", name: "ServiceZoning" },
        { label: "Product", id: "#Product", name: "Product" },
        { label: "Services", id: "#Services", name: "Services" },
        { label: "Our Solution", id: "#OurSolution", name: "OurSolution" },
        // { label: "Customers", id: "#Customers", name: "Customers" },
      ],
      activeButtonIndex: null,
      // Service Zoning: 4 Performance Zones, ordered top (best) -> bottom
      serviceZones: [
        {
          key: 'green', name: 'GREEN ZONE', role: 'TALENT',
          lead: '', desc: 'มีระบบ HR ที่แข็งแรงและเป็นมาตรฐาน พร้อมต่อยอดด้วยแนวคิดและ Framework HR ใหม่ ๆ เพื่อยกระดับองค์กร'
        },
        {
          key: 'yellow', name: 'YELLOW ZONE', role: 'UNLOCKING GROWTH',
          lead: '', desc: 'มีระบบ HR พื้นฐานรองรับ แต่ยังมีบางส่วนที่ต้องพัฒนาและปรับปรุง เพื่อสร้างระบบ HR เพื่อรองรับการเติบโต'
        },
        {
          key: 'orange', name: 'ORANGE ZONE', role: 'UNDERPERFORM',
          lead: '', desc: 'ระบบ HR ยังไม่มีโครงสร้าง หรือมีช่องว่างสำคัญที่ส่งผลต่อประสิทธิภาพการทำงาน จำเป็นต้องวางรากฐานและพัฒนาระบบให้เป็นมาตรฐาน'
        },
        {
          key: 'red', name: 'RED ZONE', role: 'UNSUCCESSOR',
          lead: '', desc: 'พบปัญหาหรือจุดบอดด้าน HR ที่ส่งผลกระทบต่อการดำเนินงานและผลลัพธ์ขององค์กร จำเป็นต้องเร่งแก้ไขและวางระบบเพื่อยกระดับประสิทธิภาพอย่างเป็นรูปธรรม'
        }
      ],
      hrProducts: [
        {
          name: 'HR Core-Kit',
          sub: '(The SME Starter Pack)',
          comingSoon: false,
          icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><rect x="5" y="4" width="14" height="17" rx="2"/><path d="M9 4V3a1 1 0 0 1 1-1h4a1 1 0 0 1 1 1v1"/><path d="M8.5 11l2 2 3.5-3.5M8.5 16.5h5"/></svg>'
        },
        {
          name: 'HR Chatbot & Employee Insight Dashboard',
          sub: '',
          comingSoon: false,
          icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><path d="M4 5.5a2 2 0 0 1 2-2h12a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2h-6l-4.5 3.5V15.5H6a2 2 0 0 1-2-2z"/><path d="M8.5 12v-2M12 12V8.5M15.5 12v-3"/></svg>'
        },
        {
          name: 'HR Express Strategy Session',
          sub: '(1-on-1 Urgent Consult)',
          comingSoon: false,
          icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><path d="M13.5 3 5.5 13.5h5.5l-1 7.5 8-10.5H12.5l1-7z"/></svg>'
        },
        {
          name: 'Human OS Customization',
          sub: '',
          comingSoon: false,
          icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><rect x="9" y="3" width="6" height="4.5" rx="1"/><rect x="3" y="15.5" width="6" height="4.5" rx="1"/><rect x="15" y="15.5" width="6" height="4.5" rx="1"/><path d="M12 7.5v3.5M6 15.5v-2.5h12v2.5M12 13v-2"/></svg>'
        },
        {
          name: 'Performance & Implementation Coaching',
          sub: '',
          comingSoon: false,
          icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4v15a1 1 0 0 0 1 1h15"/><path d="M7.5 15l3.5-4 3 2 5-6"/><path d="M16.5 8H20v3.5"/></svg>'
        },
        {
          name: 'Full Strategic Transformation',
          sub: '',
          comingSoon: false,
          icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><circle cx="11" cy="13" r="8"/><circle cx="11" cy="13" r="4"/><path d="M11 13 20 4M16 4h4v4"/></svg>'
        }
      ],
      hrTemplateProblems: [
        {
          title: '“พนักงานใหม่ไม่มีระบบต้อนรับ”',
          desc: 'งงตั้งแต่วันแรก ลาออกไวเพราะไม่รู้สึกผูกพัน',
          solPre: '',
          solName: 'ชุดปฐมนิเทศ & สร้างความผูกพัน',
          solPost: ' ช่วยสร้างประสบการณ์ที่ดีตั้งแต่วันแรก',
          icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><circle cx="9" cy="7" r="4"/><path d="M3 21v-1a6 6 0 0 1 6-6h1"/><path d="M17 11v6M14 14h6"/></svg>'
        },
        {
          title: '“กลัวโดนพนักงานฟ้องร้อง?”',
          desc: 'ต่อให้คุณเป็นฝ่ายถูก แต่เอกสารไม่รัดกุม อาจต้องจ่ายค่าชดเชยหลักแสน',
          solPre: 'ป้องกันความเสี่ยงก่อนกลายเป็นข้อพิพาท ด้วย',
          solName: 'ชุดเกราะป้องกันกฎหมายและข้อพิพาทแรงงาน',
          solPost: '',
          icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M12 3l7 3v5c0 4.5-3 8.5-7 9.5C8 19.5 5 15.5 5 11V6l7-3Z"/><path d="M9 12l2 2 4-4"/></svg>'
        },
        {
          title: '“พนักงานทำงานเรื่อยเปื่อย ไม่มีเป้าหมาย”',
          desc: 'ประเมินผลด้วยความรู้สึก ไม่ใช่ข้อมูล จับต้องประสิทธิภาพจริงไม่ได้',
          solPre: 'เปลี่ยนทุกผลงานให้วัดผลได้ชัดเจน ด้วย',
          solName: 'ชุดเกราะป้องกันกฎหมายและข้อพิพาทแรงงาน',
          solPost: '',
          icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="9"/><circle cx="12" cy="12" r="5"/><circle cx="12" cy="12" r="1.5"/></svg>'
        }
      ],
      hrChatbotFeatures: [
        {
          title: 'ตอบคำถามพนักงาน 24 ชม.',
          desc: 'ตอบคำถามเรื่องสวัสดิการ นโยบายบริษัท หรือประเภทการลา 24 ชม. ลดงานตอบซ้ำได้มากกว่า 70%',
          icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M4 5.5a2 2 0 0 1 2-2h12a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2h-6l-4.5 3.5V15.5H6a2 2 0 0 1-2-2z"/><circle cx="9" cy="9.5" r="0.9" fill="#8B5CF6" stroke="none"/><circle cx="12" cy="9.5" r="0.9" fill="#8B5CF6" stroke="none"/><circle cx="15" cy="9.5" r="0.9" fill="#8B5CF6" stroke="none"/></svg>'
        },
        {
          title: 'วิเคราะห์ Sentiment',
          desc: 'วิเคราะห์ sentiment รู้ปัญหาก่อนลุกลาม',
          icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="9"/><path d="M9 10h.01M15 10h.01"/><path d="M8.5 14.5c.9 1.2 2.1 1.8 3.5 1.8s2.6-.6 3.5-1.8"/></svg>'
        },
        {
          title: 'แนะนำ Action Plan',
          desc: 'แนะนำ action plan เรียงตาม impact',
          icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M4 20h16"/><rect x="5" y="13" width="3.5" height="5" rx="1"/><rect x="10.25" y="9" width="3.5" height="9" rx="1"/><rect x="15.5" y="5" width="3.5" height="13" rx="1"/></svg>'
        }
      ],
      hrChatbotTags: ['Fast', 'Lean', 'Insights'],
      activeProduct: 'template',
      // ภาพ mockup ทางขวาของ section Services สลับตามบริการที่กำลังอ่านอยู่
      currentServiceImage: require('~/assets/SolutionsWizemoves/Consulting/Device-Macbook-Air.png'),
      serviceImages: [
        require('~/assets/SolutionsWizemoves/Consulting/Device-Macbook-Air.png'),
        require('~/assets/SolutionsWizemoves/Consulting/Device-Macbook-Air1.png'),
        require('~/assets/SolutionsWizemoves/Consulting/Device-Macbook-Air2.png'),
        require('~/assets/SolutionsWizemoves/Consulting/Device-Macbook-Air3.png')
      ],
      // ไอคอนดึงจาก hrProducts ผ่าน computed hrServiceList (แหล่งเดียว ไม่ซ้ำ)
      hrServices: [
        {
          name: 'HR Blueprint Customization',
          headline: 'เลิกแบกบริษัทคนเดียว ให้ระบบทำงานแทนคุณได้จริง',
          desc: 'บริการออกแบบโครงสร้างองค์กรและระบบทรัพยากรบุคคล ผ่านงาน Organization Design ให้ธุรกิจเดินต่อได้จริงในระยะยาว',
          bullets: [
            { text: 'ได้ Framework ที่ชัดเจนในการวางระบบ HR ขององค์กร', icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><rect x="9" y="3" width="6" height="4.5" rx="1"/><rect x="2.5" y="16.5" width="6" height="4.5" rx="1"/><rect x="15.5" y="16.5" width="6" height="4.5" rx="1"/><path d="M12 7.5v4M5.5 16.5v-2.5h13v2.5M12 14v-2.5"/></svg>' },
            { text: 'ข้อมูลพนักงานเป็นระบบดิจิทัล พร้อมขยายทีม', icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><ellipse cx="12" cy="5.5" rx="7" ry="2.8"/><path d="M5 5.5v6c0 1.5 3.1 2.8 7 2.8s7-1.3 7-2.8v-6"/><path d="M5 11.5v6c0 1.5 3.1 2.8 7 2.8s7-1.3 7-2.8v-6"/></svg>' },
            { text: 'พัฒนาโครงสร้างเดิมให้แข็งแรงขึ้น', icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4v16h16"/><path d="M7.5 15l3.5-4 3 2 5-6"/></svg>' }
          ],
          tone: 'p1',
          imageLeft: true,
          tag: 'services_human_os_book_expert'
        },
        {
          name: 'Full Strategic Transformation',
          headline: 'เปลี่ยนผลงานที่แกว่ง ให้กลายเป็นผลลัพธ์ที่ยั่งยืน',
          desc: 'บริการที่ปรึกษากลยุทธ์ทรัพยากรบุคคลระยะยาว วางระบบ OKR/KPI ควบคู่กับวางกลยุทธ์ Salary Structure และ Employer Branding จัดสรรตามองค์กรของคุณ เพื่อผลลัพธ์ที่วัดผลได้และการเติบโตอย่างยั่งยืน',
          bullets: [
            { text: 'วางระบบ OKR & KPI พร้อมแผน PIP แก้จุดบอดทีมงาน', icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="8"/><circle cx="12" cy="12" r="4.3"/><circle cx="12" cy="12" r="1.2" fill="#8B5CF6" stroke="none"/></svg>' },
            { text: 'ออกแบบเงินเดือนและสวัสดิการ อ้างอิงฐานข้อมูลตลาดจริง แข่งขันได้เต็มที่', icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><rect x="2.5" y="6" width="19" height="12" rx="2"/><circle cx="12" cy="12" r="2.6"/><line x1="6" y1="9.5" x2="6" y2="14.5"/><line x1="18" y1="9.5" x2="18" y2="14.5"/></svg>' },
            { text: 'วางแผนคนเก่งและผู้สืบทอดตำแหน่ง สร้างวัฒนธรรมองค์กรที่คนอยากอยู่', icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><circle cx="8" cy="9" r="2.6"/><circle cx="16" cy="9" r="2.6"/><path d="M2.5 19c0-3 2.5-5 5.5-5s5.5 2 5.5 5"/><path d="M14.5 14.2c.5-.13 1-.2 1.5-.2 3 0 5.5 2 5.5 5"/></svg>' }
          ],
          tone: 'p2',
          imageLeft: false,
          tag: 'services_full_transformation_book_expert'
        },
        {
          name: 'HR Express Strategy Session',
          headline: 'แก้วิกฤตคนให้จบใน 2 ชั่วโมง ไม่ต้องเดาเองอีกต่อไป',
          desc: 'ที่ปรึกษาด่วน 1-on-1 เจาะลึกวิกฤตเรื่องคน พร้อมแนวทางแก้ปัญหาที่สามารถใช้งานต่อได้ทันที',
          bullets: [
            { text: 'เจาะปัญหาที่เกิดขึ้นจริงในทีมคุณ ไม่ใช่คำแนะนำทั่วไป', icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><circle cx="10.5" cy="10.5" r="6.5"/><line x1="15.5" y1="15.5" x2="21" y2="21"/></svg>' },
            { text: 'ออกจากห้องคุยพร้อมแผนที่สั่งการต่อได้ทันที', icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><rect x="5" y="3.5" width="14" height="17" rx="2"/><line x1="8.5" y1="9" x2="15.5" y2="9"/><line x1="8.5" y1="12.5" x2="15.5" y2="12.5"/><line x1="8.5" y1="16" x2="13" y2="16"/></svg>' },
            { text: 'รู้ทันทีว่าทีมคุณอยู่ zone ไหน แก้ให้ตรงจุด ไม่เสียเวลา', icon: '<svg viewBox="0 0 24 24" fill="none" stroke="#8B5CF6" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M12 21c4-4.5 6-7.6 6-10.5A6 6 0 0 0 6 10.5C6 13.4 8 16.5 12 21z"/><circle cx="12" cy="10.3" r="2.2"/></svg>' }
          ],
          tone: 'p3',
          imageLeft: true,
          tag: 'services_hr_express_book_expert'
        }
      ],
      lastScrollY: 0,
      scrollDirection: "None",
      interested: !this.$route.query.bu ? 'WizemovesConsult' : this.$route.query.bu
    }
  },
  jsonld() {
    return [
      {
        '@context': 'https://schema.org',
        '@type': 'BreadcrumbList',
        itemListElement: [
          {
            '@type': 'ListItem',
            position: 1,
            name: this.$t('Menu.Home'),
            item: 'https://www.sellsuki.co.th/',
          },
          {
            '@type': 'ListItem',
            position: 1,
            name: 'WizeMoves',
            item: 'https://www.sellsuki.co.th/solutions/wizemoves',
          },
          {
            '@type': 'ListItem',
            position: 3,
            name: 'hr consulting',
            item: 'https://www.sellsuki.co.th/solutions/wizemoves/hr-consulting',
          },
        ],
      },
      {
        "@context": "https://schema.org/", 
        "@type": "Service", 
        "name": "WizeMoves HR Consulting",
        "image": "",
        "description": "ที่ปรึกษางานทรัพยากรบุคคลครบวงจร ทั้ง HROD และ HRBP ช่วยออกแบบโครงสร้างองค์กร วางระบบบริหารคนให้สอดคล้องกับกลยุทธ์ธุรกิจ พัฒนาศักยภาพทีมงาน และวางระบบประเมินผลที่วัดได้จริง",
        "brand": {
          "@type": "Brand",
          "name": "Sellsuki"
        },
        "sku": "WizeMoves HR Consulting",
        "offers": {
          "@type": "Offer",
          "url": "https://www.sellsuki.co.th/solutions/wizemoves/hr-consulting",
          "priceCurrency": "THB",
          "price": "0",
          "availability": "https://schema.org/InStock"
        }
      }
    ]
  },
  async asyncData({ $axios, store }) {
    store.commit('setTitle', 'WizemovesConsult')
    return {}
  },
  computed: {
    // การ์ดในหน้าภาพรวมบริการ (แถวบน 2 / แถวล่าง 3) — ดึงไอคอนจาก hrProducts แหล่งเดียว
    hrProductCards() {
      const iconOf = (name) => {
        const p = this.hrProducts.find((item) => item.name === name)
        return p ? p.icon : ''
      }
      return [
        { name: 'HR Core-Kit', sub: '(The SME Starter Pack)', comingSoon: false, icon: iconOf('HR Core-Kit'), desc: 'ชุดเอกสาร HR มาตรฐาน อัปเดตตามกฎหมายฉบับล่าสุด สำหรับธุรกิจ SME วางระบบบริหารคนได้มีประสิทธิภาพ' },
        { name: 'HR Chatbot & Employee Insight Dashboard', sub: '', comingSoon: true, icon: iconOf('HR Chatbot & Employee Insight Dashboard'), desc: 'AI Chatbot ตอบคำถามพนักงาน 24 ชั่วโมง ลดงานซ้ำซ้อน พร้อม Dashboard วิเคราะห์ข้อมูลเชิงลึกเพื่อการบริหารคนที่แม่นยำ' },
        { name: 'HR Blueprint Customization', sub: '', comingSoon: false, icon: iconOf('Human OS Customization'), desc: 'ที่ปรึกษาออกแบบแผนโครงสร้างองค์กรและระบบทรัพยากรบุคคลใหม่ทั้งหมด ผ่าน Organization Design' },
        { name: 'Full Strategic Transformation', sub: '', comingSoon: false, icon: iconOf('Full Strategic Transformation'), desc: 'ที่ปรึกษาด้าน HR วางกลยุทธ์ทรัพยากรบุคคลให้สอดคล้องทิศทางและเป้าหมายธุรกิจ เช่น OKR/KPI, โครงสร้างเงินเดือน ฯลฯ' },
        { name: 'HR Express Strategy Session', sub: '(1-on-1 Urgent Consult)', comingSoon: false, icon: iconOf('HR Express Strategy Session'), desc: 'ที่ปรึกษาด่วน 1-on-1 แก้วิกฤตเรื่องคนถาโถม พร้อมแนวทางสั่งการต่อได้ทันที' }
      ]
    },
    // ผูกไอคอนของแต่ละบริการกับ hrProducts เพื่อไม่ให้ต้องเก็บ SVG ซ้ำสองที่
    hrServiceList() {
      return this.hrServices.map((s) => {
        const product = this.hrProducts.find((p) => p.name === s.name)
        return { ...s, icon: product ? product.icon : '' }
      })
    },
    // รายการในหน้าจอมือถือของ HR Template : ข้อความ 1 บรรทัด + ไอคอนแบบเดียวกับการ์ด Product
    hrTemplateItems() {
      const onboarding = '<svg viewBox="0 0 24 24" fill="none" stroke="#7C3AED" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><circle cx="7.5" cy="8" r="3"/><path d="M2.6 19.4c0-2.8 2.2-5 4.9-5"/><rect x="11.8" y="8.8" width="9.6" height="7.4" rx="2"/><path d="M14.3 11.7h4.6M14.3 13.7h2.6"/></svg>'
      const legal = '<svg viewBox="0 0 24 24" fill="none" stroke="#7C3AED" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"><path d="M12 3.2l6.8 2.5v5.2c0 4.2-2.9 7.8-6.8 8.9-3.9-1.1-6.8-4.7-6.8-8.9V5.7L12 3.2Z"/><path d="M12 7.6v7.2M8.4 10.2h7.2"/><path d="M8.4 10.2 6.9 13.2h3L8.4 10.2Z"/><path d="M15.6 10.2 14.1 13.2h3l-1.5-3Z"/></svg>'
      return [
        { text: 'ชุดปฐมนิเทศ & สร้างความผูกพัน', icon: onboarding },
        { text: 'ชุดเกราะป้องกันกฎหมายแรงงาน', icon: legal }
      ]
    }
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll); // Add the scroll event listener
    const options = {
      root: null, // Uses the viewport as the container
      rootMargin: '0px',
      threshold: [0.1], // เพิ่ม threshold หลายค่า
    };

    const observer = new IntersectionObserver(this.handleIntersect, options);

    const sections = document.querySelectorAll('.section-active');
    sections.forEach((section) => observer.observe(section));

    // สลับภาพประกอบ Product ทางขวาตาม block ที่กำลังอ่านอยู่
    const productOrder = ['template', 'chatbot'];
    const productObserver = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting && entry.intersectionRatio >= 0.3) {
          const key = entry.target.dataset.product;
          if (key) {
            setTimeout(() => {
              this.activeProduct = key;
            }, 100);
          }
        }
      });
    }, {
      threshold: [0.3, 0.6, 1],
      rootMargin: '-50px 0px -50px 0px'
    });

    document.querySelectorAll('#Product .space-tigger').forEach((section, index) => {
      if (!productOrder[index]) return;
      section.dataset.product = productOrder[index];
      productObserver.observe(section);
    });

    // สลับภาพ mockup ทางขวาของ section Services ตามบริการที่กำลังอ่านอยู่
    const macbookObserver = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting && entry.intersectionRatio >= 0.3) {
          const idx = Number(entry.target.dataset.svcIndex);
          if (!Number.isNaN(idx) && this.serviceImages[idx]) {
            setTimeout(() => {
              this.currentServiceImage = this.serviceImages[idx];
            }, 100);
          }
        }
      });
    }, {
      threshold: [0.3, 0.6, 1],
      rootMargin: '-50px 0px -50px 0px'
    });

    document.querySelectorAll('#Services .space-tigger').forEach((section, index) => {
      section.dataset.svcIndex = index;
      macbookObserver.observe(section);
    });
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.handleScroll); // Clean up the listener
  },
  methods: {
    scrollToTop() {
      window.scrollTo(0, 0)
    },
    handleIntersect(entries) {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          console.log(entry.target.id);
          this.activeSection = entry.target.id;
        }
      });
    },
    setActiveButton(index) {
      this.activeButtonIndex = index; // Set the active button index
    },
    handleScroll() {
      const scrollY = window.scrollY; // Get the current scroll position
      const threshold = 650; // Define the scroll threshold
      this.showDiv = scrollY > threshold; // Show the div if scrolled beyond the threshold

      let currentScrollY = window.scrollY;

      if (currentScrollY > this.lastScrollY) {
        this.scrollDirection = "Down";
      } else if (currentScrollY < this.lastScrollY) {
        this.scrollDirection = "Up";
        this.showDiv = false;
      }
      this.lastScrollY = currentScrollY;
    },
    handleChange(sectionId) {
      // รับ element ของ section ที่ต้องการ scroll ไป
      const element = document.getElementById(sectionId)

      if (element) {
        // คำนวณระยะห่างจากด้านบน
        const offset = 80 // ปรับตามความสูงของ navbar หรือ header
        const elementPosition = element.getBoundingClientRect().top
        const offsetPosition = elementPosition + window.pageYOffset - offset

        // ทำการ scroll แบบ smooth
        window.scrollTo({
          top: offsetPosition,
          behavior: 'smooth'
        })
      }
    },
  },
}
</script>

<style scoped>
@import url('~/assets/styles/css/customNew.css');

/* คำเน้นใน Pain Points : ใช้สีเดียวกับข้อความอื่น */
.pp-hl {
  color: #1F2937;
}

/* ไอคอนการ์ด Pain Points : ขนาดเท่ากันทุกใบ + คมชัด (เวกเตอร์) */
.pp-card-icon {
  width: 40px;
  height: 40px;
  flex: 0 0 auto;
  object-fit: contain;
}

@media only screen and (max-width: 991px) {
  .pp-card-icon {
    width: 40px;
    height: 40px;
  }
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
  position: absolute;
  width: 100%;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}

.fade-transition {
  position: relative;
  transition: opacity 0.3s ease-in-out;
  width: 100%;
  max-width: 95%;
  /* ป้องกันรูปล้นพื้นที่ */
  height: auto;
  /* ให้ความสูงปรับตามสัดส่วน */
}

.accordion-button {
  background-color: #fbfbfb !important;
  padding: 5px;
}

.form-select {
  border: 0 !important;
  background-color: #7C3AED !important;
  /* สีเดียวกับ navbar */
  color: #FFFFFF !important;
  /* สีตัวอักษรเป็นสีขาว */
}

/* ปรับสี dropdown arrow */
.form-select {
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill='none' stroke='%23FFFFFF' stroke-linecap='round' stroke-linejoin='round' stroke-width='2' d='m2 5 6 6 6-6'/%3e%3c/svg%3e") !important;
}

/* ปรับ style ตอน focus */
.form-select:focus {
  border-color: #FFFFFF !important;
  box-shadow: none !important;
}

/* ปรับสี option ใน dropdown */
.form-select option {
  background-color: #7C3AED;
  color: #FFFFFF;
}

.accordion-button:not(.collapsed)::after {
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16' fill='%23212529'%3e%3cpath fill-rule='evenodd' d='M1.646 4.646a.5.5 0 0 1 .708 0L8 10.293l5.646-5.647a.5.5 0 0 1 .708.708l-6 6a.5.5 0 0 1-.708 0l-6-6a.5.5 0 0 1 0-.708z'/%3e%3c/svg%3e");
}

.accordion-button:not(.collapsed) {
  box-shadow: none;
}

.item-center {
  display: block !important;
}

.space-services {
  margin-top: 160px !important;
  /* เพิ่มจาก 80px เป็น 160px */
  padding-bottom: 80px !important;
  /* เพิ่ม padding ด้านล่าง */
  position: relative;
}

.outer-circle {
  display: inline-block;
  padding: 8px;
  border-radius: 50%;
  background-color: transparent;
  /* ชั้นที่ 1 */
  border: 2px solid transparent;
  /* ชั้นที่ 2 */
}

.inner-circle {
  padding: 8px;
  border-radius: 50%;
  object-fit: cover;
  border: 2px solid transparent;
  /* ชั้นด้านในสุด */
}

.outer-circle-hover {
  display: inline-block;
  padding: 8px;
  border-radius: 50%;
  background-color: transparent;
  /* ชั้นที่ 1 */
  border: 2px solid #8B5CF61A !important;
  /* ชั้นที่ 2 */
}

.inner-circle-hover {
  padding: 8px;
  border-radius: 50%;
  object-fit: cover;
  border: 2px solid #8B5CF64D !important;
  /* ชั้นด้านในสุด */
}

.btn-transparent-violet {
  display: inline-flex;
  align-items: center;
  color: #8B5CF6 !important;
  border: 1px solid #8B5CF6;
  background: white;
  border-radius: 999px;
  padding: 4px 22px 4px 18px;
}

.btn-white-violet {
  display: inline-flex;
  align-items: center;
  color: #8B5CF6 !important;
  background: white;
  border-radius: 999px;
  padding: 4px 22px 4px 18px;
}

.btn-white-violet .icon {
  width: 24px;
  height: 24px;
  margin-right: 6px;
}

.btn-gradient .icon {
  width: 24px;
  height: 24px;
  margin-right: 6px;
}

.btn-gradient {
  display: inline-flex;
  align-items: center;
  color: white !important;
  background: linear-gradient(82.53deg, #6D28D9 7.45%, #FBBF24 113.56%);
  border-radius: 999px;
  padding: 4px 22px 4px 18px;
}

.btn-gradient .icon {
  width: 24px;
  height: 24px;
  margin-right: 6px;
}

.badge-wizemoves {
  display: inline-flex;
  align-items: center;
  background-color: #F5F3FF1A;
  color: white;
  border-radius: 999px;
  border: 1px solid #DDD6FE33;
  padding: 4px 16px 4px 10px;
}

.badge-wizemoves .icon {
  width: 16px;
  height: 16px;
  margin-right: 6px;
}

.image-container {
  position: relative;
  display: inline-block;
}

.image-container img {
  display: block;
  width: 100%;
  height: auto;
}

.col-6-custom-1 {
  width: 43% !important;
}

.col-6-custom-2 {
  width: 57% !important;
}

.centered-text {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.card-01 {
  height: 100%;
}

.card-01 .card-body {
  flex: 0 0 auto;
  padding: 14px 0px 14px 0px;
}

.card-01 img {
  border-radius: 8px;
  padding: 0px;
}

.card-01 div {
  font-family: "Heavent-body" !important;
  font-size: 24px;
  line-height: 24px;
  color: #1F2937;
}

.text-hl {
  background-color: #F5F3FF;
  border: 1px solid #DDD6FE;
  color: #7C3AED;
  border-radius: 24px;
  padding: 4px 16px 3px 16px;
  margin-top: 8px;
}

.text-hl-blue {
  background-color: #F0F9FF;
  border: 1px solid #D9F2FF;
  color: #32A9FF;
  border-radius: 24px;
  padding: 4px 16px 3px 16px;
  margin-top: 8px;
}

.bg {
  background: url('~/assets/image94.webp');
  background-position: center;
  background-repeat: no-repeat;
  height: 350px;
}

.bg-icon {
  width: 146px;
  height: 146px;
  background-color: #7c3aed;
  border-radius: 50%;
  left: 8px;
  position: relative;
}

.bg-img-mobile {
  background-image: url(~/assets/SolutionsWizemoves/HRConsulting/hero-banner.jpg);
  background-position: center;
  background-repeat: no-repeat !important;
  background-size: cover !important;
}

.bg-img-2 {
  background-image: url(~/assets/SolutionsWizemoves/img-bg-1.jpg);
  background-position: center;
  background-repeat: no-repeat !important;
  background-size: cover !important;
}

.bg-img-3 {
  background-image: url(~/assets/SolutionsWizemoves/Consulting/whyus.png);
  background-position: center;
  background-repeat: no-repeat !important;
  background-size: cover !important;
}

.bg-color {
  background: linear-gradient(90deg,
      rgba(28, 14, 58, 0.86) 0%,
      rgba(40, 18, 82, 0.78) 22%,
      rgba(58, 28, 112, 0.60) 44%,
      rgba(80, 42, 150, 0.34) 62%,
      rgba(109, 40, 217, 0) 82%);
}

.bg-color-mobile {
  background: linear-gradient(180deg, rgba(28, 14, 58, 0.74) 0%, rgba(48, 22, 96, 0.5) 52%, rgba(70, 34, 130, 0.24) 80%, rgba(109, 40, 217, 0) 100%);

}

.bg-icon-main {
  margin-left: -10px !important;
  margin-top: -10px !important;
  background-color: #fcd34d;
  width: 146px;
  height: 146px;
  border-radius: 50%;
}

.theme-background-main {
  background-color: #7c3aed;
}

.theme-background-sub {
  background-color: #fcd34d;
}

.theme-text-main {
  color: #7c3aed;
}

.theme-text-sub {
  color: #fcd34d;
}

.theme-border {
  border-bottom: 1px solid #fcd34d !important;
}

.img-banner-top {
  margin-top: 80px !important;
}

.text-ranbow,
.text-ranbow>* {
  background: linear-gradient(51.93deg, #8B5CF6 -8.45%, #FACC15 113.97%);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  line-height: 30px;
}

.border-ranbow {
  background: #FFF;
  border-radius: 32px;
  padding: 4px 16px;
}

.cart-img-text {
  border-radius: 16px;
  /* ซ้อน overlay บนรูป : สีม่วง #4C1D95 20% + radial เข้มตรงกลาง 80% เพื่อให้อ่านข้อความชัดขึ้น */
  background-image:
    linear-gradient(0deg, rgba(76, 29, 149, 0.2), rgba(76, 29, 149, 0.2)),
    radial-gradient(75% 120% at 50% 55%, rgba(23, 8, 46, 0.8) 0%, rgba(23, 8, 46, 0.25) 55%, rgba(23, 8, 46, 0) 80%),
    url(~/assets/SolutionsWizemoves/Consulting/wizemoves-hr-banner.jpg);
  background-position: center;
  background-repeat: no-repeat !important;
  background-size: cover !important;
}

.bg-1 {
  background-size: cover;
}

.nav-active {
  border-bottom: 5px solid #FFFFFF;
  color: #FFFFFF !important;
}

.nav-link {
  color: #FFFFFF !important;
}

.nav-active .nav-link {
  color: #FFFFFF !important;
}

.text-s-158 {
  font-size: 158px;
  line-height: 94.8px;
}

.text-s-86 {
  font-size: 86px;
  line-height: 86px;
}

.text-s-52 {
  line-height: 52px;
}

.text-s-44 {
  line-height: 44px;
}

.text-s-24 {
  line-height: 24px;
}

.text-s-36 {
  line-height: 36px;
}

.text-s-20 {
  line-height: 20px;
}

.text-s-18 {
  line-height: 18px;
}

.img-Process {
  min-height: 300px;
  width: 100%;
  object-fit: cover;
  object-position: center;
  border-radius: 16px;
}

/* ===== Products ===== */
#ProductLineup {
  background-image: url('~/assets/New/Home/Solutions/BG-purple.png');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  /* เว้นช่องว่างสีขาวเหนือแถบสีม่วง ให้ระยะห่างเท่ากับ section อื่น
     และย้าย padding-top ออกจากพื้นที่สี ไม่ให้แถบม่วงหัวโล่งเกินไป */
  margin-top: 80px;
  padding-top: 0 !important;
}

.product-panel {
  background: transparent;
  border: none;
  border-radius: 0;
  padding: 56px 40px 52px;
}

.product-badge {
  border: 2px solid #00000008;
  backdrop-filter: blur(10px);
}

.product-card {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
  text-align: left;
  background: rgba(255, 255, 255, 0.8);
  border: 1px solid #e5e7eb;
  border-radius: 20px;
  padding: 30px 22px 26px;
  box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.05);
  transition: transform 0.28s ease, box-shadow 0.28s ease, border-color 0.28s ease;
}

.product-card:hover {
  transform: translateY(-4px);
  border-color: #DDD6FE;
  box-shadow: 0px 2px 4px 0px #7B64AF1F, 0px 14px 26px 0px #7B64AF17;
}

.product-icon-group {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 8px;
  position: relative;
  border-radius: 20px;
  border: 1px solid #8B5CF61A;
  margin-bottom: 18px;
}

.product-icon-tile {
  position: relative;
  width: 64px;
  height: 64px;
  border-radius: 16px;
  border: 1px solid #8B5CF6;
  background: transparent;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background-color 0.1s ease;
}

.product-icon-aura {
  position: absolute;
  top: calc(50% - 32px);
  left: calc(50% - 32px);
  width: 64px;
  height: 64px;
  border-radius: 16px;
  background-color: transparent;
}

.product-card:hover .product-icon-tile {
  background-color: #8B5CF6;
}

.product-card:hover .product-icon-aura {
  background-color: #8B5CF6;
  filter: blur(10px);
}

.product-icon {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  flex: 0 0 auto;
  width: 32px;
  height: 32px;
}

.product-icon >>> svg {
  width: 32px;
  height: 32px;
  display: block;
  transition: filter 0.1s ease;
}

.product-card:hover .product-icon >>> svg {
  filter: brightness(0) invert(1);
}

.product-name {
  line-height: 32px;
}

.product-sub {
  color: #6B7280;
  line-height: 26px;
  margin-top: 6px;
}

.product-desc {
  color: #6B7280;
  line-height: 28px;
  margin-top: 12px;
}

/* แถวล่าง 3 การ์ด : เปลี่ยนโทนสีจากม่วง เป็นเหลืองทองแบรนด์ WizeMoves (ตามโลโก้ #E5AF43) */
.product-row-bottom .product-icon-group {
  border-color: rgba(229, 175, 67, 0.20);
}

.product-row-bottom .product-icon-tile {
  border-color: #E5AF43;
}

.product-row-bottom .product-card:hover {
  border-color: #EDC873;
  box-shadow: 0px 2px 4px 0px rgba(180, 130, 30, 0.14), 0px 14px 26px 0px rgba(180, 130, 30, 0.10);
}

.product-row-bottom .product-card:hover .product-icon-tile {
  background-color: #E5AF43;
}

.product-row-bottom .product-card:hover .product-icon-aura {
  background-color: #E5AF43;
}

.product-row-bottom .product-icon >>> svg {
  stroke: #E5AF43;
}

.product-flag {
  position: absolute;
  top: 14px;
  right: 14px;
  font-size: 18px !important;
  line-height: 18px;
  font-family: 'Heavent-med', sans-serif;
  color: #7C3AED;
  background: #F5F3FF;
  border: 1px solid #DDD6FE;
  border-radius: 20px;
  padding: 4px 12px;
}

/* badge Coming soon แบบ inline (แทนปุ่มแจ้งความสนใจในการ์ด HR Chatbot) */
.svc-coming-soon {
  display: inline-flex;
  align-items: center;
  font-family: 'Heavent-med', sans-serif;
  color: #8B5CF6;
  background: white;
  border: 1px solid #8B5CF6;
  border-radius: 999px;
  padding: 8px 22px 8px 18px;
}

.product-closing {
  margin-top: 44px;
}

.product-closing-1 {
  color: #7C3AED;
  line-height: 46px;
}

.product-closing-2 {
  color: #7B64AF;
  line-height: 34px;
  margin-top: 10px;
}

/* ===== Product (ใน layout Services) ===== */
.hrt-quote {
  background: linear-gradient(120deg, #F8F5FF 0%, #F3EFFC 100%);
  border: 1px solid #DDD6FE;
  border-left: 6px solid #7B64AF;
  border-radius: 16px;
  padding: 22px 26px;
  color: #3E305B;
}

.hrt-quote p {
  line-height: 34px;
}

.hrt-quote-hl {
  color: #7C3AED;
}

/* ไอคอนใน card-01 ของ Product */
.svc-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  flex: 0 0 auto;
  width: 32px;
  height: 32px;
}

.svc-icon >>> svg {
  width: 32px;
  height: 32px;
  display: block;
}

.svc-solution {
  color: #1F2937;
  line-height: 26px;
  padding-right: 16px;
  padding-bottom: 4px;
}

.svc-sol-name {
  color: #7C3AED;
}


.svc-tag {
  display: inline-block;
  margin: 0 10px 10px 0;
  padding: 7px 18px 5px;
  border: 1px solid #DDD6FE;
  border-radius: 999px;
  background: #F5F3FF;
  color: #7C3AED;
  line-height: 22px;
}

.btn-soon {
  display: inline-block;
  padding-left: 26px;
  padding-right: 26px;
  border-radius: 999px;
  background: #F3F4F6;
  border: 1px solid #E5E7EB;
  color: #9CA3AF;
  cursor: not-allowed;
  user-select: none;
}

/* ภาพประกอบ Product ทางขวา (sticky) — จัดวางแบบเดียวกับ mockup ของ Services */
.svc-sticky {
  margin-top: 245px;
  position: sticky;
  top: 52%;
  transform: translateY(-50%);
  display: flex;
  align-items: center;
  justify-content: center;
}

.svc-sticky .fade-transition {
  max-width: 480px;
  margin-left: auto;
  margin-right: auto;
}

@media only screen and (max-width: 600px) {
  .svc-sticky {
    position: relative;
    transform: none;
    margin-top: 0;
  }
}

/* ===== Services : ภาพ mockup ทางขวา (sticky) + การ์ดหัวข้อ ===== */
.sticky-macbook {
  margin-top: 245px;
  position: sticky;
  top: 52%;
  transform: translateY(-50%);
  height: 400px;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
}

@media only screen and (max-width: 600px) {
  .sticky-macbook {
    position: relative;
    transform: none;
    height: auto;
  }
}

/* ไอคอนเส้นสีม่วง CI ในการ์ดแต่ละหัวข้อ (สไตล์เดียวกับ section Services หน้า business-consulting) */
.svc-card-icon {
  flex: 0 0 auto;
  width: 24px;
  height: 24px;
  margin-top: 2px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
}

.svc-card-icon >>> svg {
  width: 24px;
  height: 24px;
  display: block;
}

/* ===== Process : หมายเหตุใต้ขั้นตอน ===== */
.proc-note {
  color: #6B7280;
  max-width: 900px;
  margin-left: auto;
  margin-right: auto;
  line-height: 32px;
}

/* ===== Service Zoning ===== */
.zoning-badge {
  border: 2px solid #00000008;
  backdrop-filter: blur(10px);
}

.zoning-intro {
  max-width: 860px;
  margin-left: auto;
  margin-right: auto;
}

/* กันสกอร์ลแนวนอนจากการ์ดที่ลากพื้นหลังชนขอบจอ (clip = ไม่สร้าง scroll container แนวตั้ง) */
#ServiceZoning {
  overflow-x: clip;
}

.zoning-layout {
  margin-top: 48px;
}

/* สัดส่วนคอลัมน์ซ้าย/ขวา ให้เท่ากับ section Why Us (43% / 57%) บนจอ ≥992px */
@media (min-width: 992px) {
  .zoning-col-left {
    width: 43%;
  }

  .zoning-col-right {
    width: 57%;
  }

  /* การ์ดโซนฝั่งขวา : พื้นหลังลากยาวชนขอบจอด้านขวา + มุมขวาเหลี่ยม
     --bleed = ระยะจากขอบขวาของ container ไปถึงขอบจอ (container กว้าง 882px, จัดกึ่งกลาง) */
  .zoning-item {
    --bleed: calc((100vw - 882px) / 2);
    margin-right: calc(-1 * var(--bleed));
  }

  /* มุมขวาเหลี่ยม (specificity สูงกว่า base .zoning-item เพื่อ override) */
  .zoning-list .zoning-item {
    border-radius: 20px 0 0 20px;
  }

  /* staircase : ล่างสุดยาวสุด แล้วค่อย ๆ สั้นขึ้นไปด้านบน (บวก --bleed เพื่อดันขอบขวาชนจอ โดยขอบซ้ายคงเดิม) */
  .zoning-list .zone-green {
    width: calc(76% + var(--bleed));
  }

  .zoning-list .zone-yellow {
    width: calc(84% + var(--bleed));
  }

  .zoning-list .zone-orange {
    width: calc(92% + var(--bleed));
  }

  .zoning-list .zone-red {
    width: calc(100% + var(--bleed));
  }
}

/* อัปเดต --bleed ตาม max-width ของ container ในแต่ละ breakpoint (customNew.css) */
@media (min-width: 1200px) {
  .zoning-item { --bleed: calc((100vw - 1100px) / 2); }
}

@media (min-width: 1260px) {
  .zoning-item { --bleed: calc((100vw - 1200px) / 2); }
}

@media (min-width: 1400px) {
  .zoning-item { --bleed: calc((100vw - 1400px) / 2); }
}

@media (min-width: 1500px) {
  .zoning-item { --bleed: calc((100vw - 1440px) / 2); }
}

/* ----- mascot ----- */
.zoning-mascot {
  position: relative;
  display: inline-block;
  padding: 18px;
}

.zoning-mascot::before {
  content: "";
  position: absolute;
  z-index: 0;
  inset: -6% -4%;
  background: radial-gradient(58% 58% at 50% 48%, #7B64AF33 0%, #7B64AF00 72%);
  pointer-events: none;
}

.zoning-mascot-img {
  position: relative;
  z-index: 1;
  max-width: 400px;
  width: 100%;
}

/* ----- zone list (การ์ดโซน สไตล์เดียวกับทั้งหน้า) ----- */
.zoning-layout {
  position: relative;
}

.zoning-col-left,
.zoning-col-right {
  position: relative;
  z-index: 1;
}

/* ลูกศร trending ขึ้น (เดคอเรชันวางหน้าการ์ด ฝั่งซ้ายของกลุ่มการ์ด) */
.zoning-arrow {
  position: absolute;
  left: 18%;
  bottom: 0;
  width: 40%;
  z-index: 0;
  opacity: 0.9;
  pointer-events: none;
}

.zoning-arrow svg {
  width: 100%;
  height: auto;
  display: block;
}

.zoning-list {
  position: relative;
  z-index: 1;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  gap: 0;
}

@media (max-width: 991px) {
  .zoning-arrow {
    display: none;
  }
}

.zoning-item {
  position: relative;
  width: 100%;
  display: flex;
  align-items: flex-start;
  gap: 20px;
  background: #FFFFFF;
  border-radius: 20px;
  padding: 24px 28px;
  overflow: hidden;
  box-shadow: 0px 1px 3px 0px #7B64AF14, 0px 8px 18px 0px #7B64AF0A;
  transition: transform 0.28s ease, box-shadow 0.28s ease, border-color 0.28s ease;
}

.zoning-item:hover {
  transform: translateY(-4px);
  border-color: #DDD6FE;
  box-shadow: 0px 2px 4px 0px #7B64AF1F, 0px 14px 26px 0px #7B64AF14;
}

/* เลขโซนตัวใหญ่ ไม่มีกรอบ สีอ่อน (สไตล์เดียวกับหน้า wizemoves) */
.zoning-item-no {
  flex: 0 0 auto;
  width: 72px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Heavent-body', sans-serif;
  font-size: 76px;
  line-height: 1;
  letter-spacing: 0.01em;
  color: #E4DBF6;
}

.zoning-item-content {
  min-width: 0;
}

.zoning-zone-name {
  letter-spacing: 0.16em;
  text-transform: uppercase;
  color: #7C3AED;
  margin-bottom: 2px;
}

.zoning-zone-role {
  line-height: 32px;
}

.zoning-item-desc {
  line-height: 30px;
}

.zoning-desc-lead {
  color: #7C3AED;
}

/* เลขโซน : ใช้โทนม่วงอ่อนเหมือนกันทุกโซน / ชื่อโซนใช้สีประจำโซน */
.zone-green .zoning-item-no,
.zone-yellow .zoning-item-no,
.zone-orange .zoning-item-no,
.zone-red .zoning-item-no {
  color: #E9E4FE;
}

.zone-green .zoning-zone-name {
  color: #15A34A;
}

.zone-yellow .zoning-zone-name {
  color: #CA8A04;
}

.zone-orange .zoning-zone-name {
  color: #E0700F;
}

.zone-red .zoning-zone-name {
  color: #DC2626;
}

/* Extra small devices (phones, 600px and down) */
@media only screen and (max-width: 600px) {
  .zoning-layout {
    margin-top: 28px;
  }

  .zoning-mascot-img {
    max-width: 220px;
  }

  .zoning-item {
    gap: 14px;
    padding: 20px 20px;
    border-radius: 16px;
  }

  .zoning-item-no {
    width: 54px;
    font-size: 54px;
  }

  .hrt-quote {
    border-radius: 14px;
    padding: 18px 18px 18px 16px;
    border-left-width: 5px;
  }

  .hrt-quote p {
    line-height: 28px;
  }

  .svc-tag {
    padding: 6px 14px 4px;
    margin: 0 8px 8px 0;
  }

  .svc2-row {
    margin-top: 36px;
  }

  .svc2-panel {
    border-radius: 20px;
    padding: 24px 20px 22px;
  }

  /* ชื่อบริการยาว ต้องลดขนาดลงไม่ให้กินพื้นที่ 2-3 บรรทัด */
  .svc2-name {
    font-size: 32px !important;
    line-height: 38px;
  }

  .svc2-desc,
  .svc2-headline {
    line-height: 28px;
  }

  .svc2-item {
    padding: 11px 14px;
  }

  .svc2-item-text {
    line-height: 26px;
  }

  .svc2-visual {
    min-height: 180px;
    border-radius: 20px;
  }

  .svc2-visual-icon {
    width: 104px;
    height: 104px;
    border-radius: 26px;
  }

  .svc2-visual-icon >>> svg {
    width: 62px;
    height: 62px;
  }

  #ProductLineup {
    margin-top: 50px;
  }

  .product-panel {
    border-radius: 24px;
    padding: 36px 16px 40px;
  }

  .product-card {
    padding: 26px 18px 22px;
  }

  .product-closing {
    margin-top: 32px;
  }

  .product-closing-1 {
    line-height: 32px;
  }

  .product-closing-2 {
    line-height: 28px;
  }

  .card-1 {
    box-shadow: 0px 1px 3px 0px #7B64AF12, 0px 5px 5px 0px #7B64AF0F, 0px 12px 7px 0px #7B64AF0A, 0px 20px 8px 0px #7B64AF03, 0px 32px 9px 0px #7B64AF00;
    border-radius: 16px;
    border: 2px solid #F3F4F6;
    background-color: #FFFFFF;
  }

  .cart-color-text {
    border-radius: 16px;
    padding: 40px 0px;
    background: linear-gradient(180deg, rgba(46, 21, 89, 0) 43.78%, rgba(21, 10, 40, 0.8) 100%);
  }

  .space-services {
    margin-top: 50px !important;
    padding-bottom: 20px !important;
  }

  #Services .text-s-52 {
    font-size: 36px !important;
    line-height: 36px !important;
  }

  #Services .text-s-24 {
    font-size: 20px !important;
    line-height: 20px !important;
  }

  .section-spacing {
    padding-top: 0px;
  }

  .hero-section .text-s-52 {
    font-size: 44px !important;
    line-height: 44px !important;
  }

  .hero-section .text-s-36 {
    font-size: 24px !important;
    line-height: 24px !important;
  }

  .hero-section .text-s-20 {
    font-size: 20px !important;
    line-height: 20px !important;
  }

  .pb-200 {
    padding-bottom: 100px;
  }
}

@media only screen and (max-width: 380px) {
  .btn-gradient {
    padding: 0px 12px 0px 12px;
  }
  .btn-white-violet {
    padding: 0px 12px 0px 12px;
  }
  .hero-section .text-s-20 {
    font-size: 16px !important;
    line-height: 16px !important;
    padding: 4px 10px !important;
  }
  .hero-section .text-s-24 {
    font-size: 20px !important;
    line-height: 20px !important;
  }
  .breadcrumb .text-s-20 {
    font-size: 16px !important;
    padding: 0px !important;
  }
  .img-360 {
    margin-top: 40px;
  }
}

/* Small devices (portrait tablets and large phones, 600px and up) */
@media only screen and (min-width: 600px) {
  .card-1 {
    box-shadow: 0px 1px 3px 0px #7B64AF12, 0px 5px 5px 0px #7B64AF0F, 0px 12px 7px 0px #7B64AF0A, 0px 20px 8px 0px #7B64AF03, 0px 32px 9px 0px #7B64AF00;
    border-radius: 16px;
    border: 2px solid #F3F4F6;
    background-color: #FFFFFF;
  }

  .cart-color-text {
    border-radius: 16px;
    padding: 40px 0px;
    background: linear-gradient(180deg, rgba(46, 21, 89, 0) 43.78%, rgba(21, 10, 40, 0.8) 100%);
  }

  .section-spacing {
    padding-top: 0px;
  }

  .space-services {
    margin-top: 50px !important;
    padding-bottom: 20px !important;
  }

  #Services .text-s-52 {
    font-size: 36px !important;
    line-height: 36px !important;
  }

  #Services .text-s-24 {
    font-size: 20px !important;
    line-height: 20px !important;
  }

  .hero-section .text-s-52 {
    font-size: 44px !important;
    line-height: 44px !important;
  }

  .hero-section .text-s-36 {
    font-size: 24px !important;
    line-height: 24px !important;
  }

  .hero-section .text-s-20 {
    font-size: 20px !important;
    line-height: 20px !important;
  }

  .banner-main {
    height: 400px;
  }

  .bg-img {
    background-image: url(~/assets/SolutionsWizemoves/HRConsulting/hero-banner.jpg);
    background-position: -550px center;
    background-repeat: no-repeat !important;
    background-size: cover !important;
  }

  .pb-200 {
    padding-bottom: 100px;
  }
}

/* Medium devices (landscape tablets, 768px and up) */
@media only screen and (min-width: 768px) {
  .card-1 {
    box-shadow: 0px 1px 3px 0px #7B64AF12, 0px 5px 5px 0px #7B64AF0F, 0px 12px 7px 0px #7B64AF0A, 0px 20px 8px 0px #7B64AF03, 0px 32px 9px 0px #7B64AF00;
    border-radius: 16px;
    border: 2px solid #F3F4F6;
    background-color: #FFFFFF;
    height: 100%;
  }

  .cart-color-text {
    border-radius: 16px;
    padding: 40px 40px;
    background: linear-gradient(180deg, rgba(46, 21, 89, 0) 43.78%, rgba(21, 10, 40, 0.8) 100%);
  }

  .section-spacing {
    padding-top: 0px;
  }

  .space-services {
    margin-top: 50px !important;
    padding-bottom: 20px !important;
  }

  #Services .text-s-52 {
    font-size: 36px !important;
    line-height: 36px !important;
  }

  #Services .text-s-24 {
    font-size: 20px !important;
    line-height: 20px !important;
  }

  #OurSolution .text-s-36 {
    font-size: 24px !important;
    line-height: 24px !important;
  }

  #OurSolution .text-s-24 {
    font-size: 20px !important;
    line-height: 20px !important;
  }

  .hero-section .text-s-52 {
    font-size: 44px !important;
    line-height: 44px !important;
  }

  .hero-section .text-s-36 {
    font-size: 24px !important;
    line-height: 24px !important;
  }

  .hero-section .text-s-20 {
    font-size: 20px !important;
    line-height: 20px !important;
  }

  .banner-main {
    height: 470px;
  }

  .bg-img {
    background-image: url(~/assets/SolutionsWizemoves/HRConsulting/hero-banner.jpg);
    background-position: center;
    background-repeat: no-repeat !important;
    background-size: cover !important;
  }

  .icon-process {
    width: 60%;
  }

  .pb-200 {
    padding-bottom: 100px;
  }

  .card-1 .card-body {
    padding: 28px 20px;
  }

  .btn-gradient {
    padding: 4px 12px 4px 12px;
  }
}

@media only screen and (min-width: 992px) and (max-width: 1199px) {
  .zoning-mascot-img {
    max-width: 300px;
  }
}

@media only screen and (min-width: 992px) {
  .card-1 {
    box-shadow: 0px 1px 3px 0px #7B64AF12, 0px 5px 5px 0px #7B64AF0F, 0px 12px 7px 0px #7B64AF0A, 0px 20px 8px 0px #7B64AF03, 0px 32px 9px 0px #7B64AF00;
    border-radius: 16px;
    border: 2px solid #F3F4F6;
    background-color: #FFFFFF;
    height: 100%;
  }

  .cart-color-text {
    border-radius: 16px;
    padding: 40px 40px;
    background: linear-gradient(180deg, rgba(46, 21, 89, 0) 43.78%, rgba(21, 10, 40, 0.8) 100%);
  }

  .section-spacing {
    padding-top: 0px;
  }

  .space-services {
    padding-top: 100px !important;
    padding-bottom: 20px !important;
  }

  .banner-main {
    height: 550px;
  }

  .bg-img {
    background-image: url(~/assets/SolutionsWizemoves/HRConsulting/hero-banner.jpg);
    background-position: center;
    background-repeat: no-repeat !important;
    background-size: cover !important;
  }

  .icon-process {
    width: 60%;
  }

  #Services .text-s-52 {
    font-size: 52px !important;
    line-height: 52px !important;
  }

  #Services .text-s-24 {
    font-size: 24px !important;
    line-height: 24px !important;
  }

  #OurSolution .text-s-36 {
    font-size: 36px !important;
    line-height: 36px !important;
  }

  #OurSolution .text-s-24 {
    font-size: 24px !important;
    line-height: 24px !important;
  }

  .hero-section .text-s-52 {
    font-size: 52px !important;
    line-height: 52px !important;
  }

  .hero-section .text-s-36 {
    font-size: 36px !important;
    line-height: 36px !important;
  }

  .hero-section .text-s-20 {
    font-size: 20px !important;
    line-height: 20px !important;
  }

  .pb-200 {
    padding-bottom: 80px;
  }
}

/* Extra large devices (large laptops and desktops, 1200px and up) */
@media only screen and (min-width: 1200px) {
  .card-1 {
    box-shadow: 0px 1px 3px 0px #7B64AF12, 0px 5px 5px 0px #7B64AF0F, 0px 12px 7px 0px #7B64AF0A, 0px 20px 8px 0px #7B64AF03, 0px 32px 9px 0px #7B64AF00;
    border-radius: 16px;
    border: 2px solid #F3F4F6;
    background-color: #FFFFFF;
    height: 100%;
  }

  .cart-color-text {
    border-radius: 16px;
    padding: 40px 40px;
    background: linear-gradient(180deg, rgba(46, 21, 89, 0) 43.78%, rgba(21, 10, 40, 0.8) 100%);
  }

  .section-spacing {
    padding-top: 80px;
  }

  .banner-main {
    height: 550px;
  }

  .bg-img {
    background-image: url(~/assets/SolutionsWizemoves/HRConsulting/hero-banner.jpg);
    background-position: center;
    background-repeat: no-repeat !important;
    background-size: cover !important;
  }

  .icon-process {
    width: 74%;
  }

  .space-services {
    padding-top: 100px !important;
    padding-bottom: 20px !important;
  }

  .pb-200 {
    padding-bottom: 200px;
  }
}

@media only screen and (min-width: 1280px) and (max-width: 1440px) {
  .text-s-36 {
    font-size: 30px !important;
    line-height: 30px !important;
  }

  .text-s-44 {
    font-size: 40px !important;
    line-height: 40px !important;
  }
}


/* ----------------------- model ----------------- */
.header-model {
  font-weight: 700;
  line-height: 72px;
  text-align: center;
}

.modal-footer {
  border-top: 0px;
}

.modal-header {
  border-bottom: 0px;
}

.modal-custom-size {
  border-radius: 16px;
  background-color: #FAF5FF;
}
</style>
