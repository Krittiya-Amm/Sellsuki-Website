<template>
  <div id="PortfolioShowcase">
    <div class="container font-df ps-3 pe-3 ps-md-0 pe-md-0">

      <!-- ===== Breadcrumb ===== -->
      <ul class="breadcrumb mt-3 pt-2">
        <li>
          <nuxt-link :to="localePath('/')"><span class="breadcrumb-text color-6B7280">หน้าแรก</span></nuxt-link>
          <i class="bi bi-chevron-right mx-1 color-9CA3AF"></i>
        </li>
        <li>
          <nuxt-link :to="localePath('/portfolio')"><span class="breadcrumb-text color-6B7280">ผลงานของเรา</span></nuxt-link>
          <i class="bi bi-chevron-right mx-1 color-9CA3AF"></i>
        </li>
        <li><span class="text-s-18 text-w-500 color-1F2937">{{ data.title }}</span></li>
      </ul>
    </div>

    <!-- ===== Hero (full width) ===== -->
    <div class="hero-fullwidth hero-detail" :style="{ backgroundImage: 'url(' + data.cover + ')' }">
      <div class="hero-overlay"></div>
      <div class="container hero-inner">
        <div class="hero-content">
          <div class="hero-breadcrumb">
            <nuxt-link :to="localePath('/portfolio')" class="text-s-20 text-w-500 color-FFFFFF"><i class="bi bi-house-door-fill me-2"></i>ผลงานของเรา</nuxt-link>
            <i class="bi bi-chevron-right mx-2 text-s-20 text-w-500 color-FFFFFF"></i>
            <span class="text-s-20 text-w-500 color-FFFFFF">{{ data.title }}</span>
          </div>
          <h1 class="text-s-72 text-w-700 color-FFFFFF mb-3 hero-title">{{ data.title }}</h1>
          <p class="text-s-24 text-w-400 color-FFFFFF hero-desc">{{ data.summary }}</p>
        </div>
        <div class="hero-preview d-none d-lg-block">
          <img class="browser-shot" :src="data.heroPreview" :alt="data.title" />
        </div>
      </div>
    </div>

    <!-- ===== Scroll tab nav (appears on scroll, replaces the site nav) ===== -->
    <div v-if="showDiv" class="tab-nav tab-nav-fixed">
      <div class="container">
        <div class="tab-scroll">
          <a v-for="s in sections" :key="s.id" :href="'#' + s.id"
            @click.prevent="scrollTo(s.id)"
            class="tab-link text-s-24 text-w-500"
            :class="{ 'tab-active': activeSection === s.id }">{{ s.label }}</a>
        </div>
      </div>
    </div>

    <div class="container font-df ps-3 pe-3 ps-md-0 pe-md-0">

      <!-- ===== ภาพรวม ===== -->
      <section id="overview" class="fade-in-up" v-intersect>
        <div class="row">
          <div class="col-lg-8 col-12">
            <h2 class="text-s-60 text-w-700 color-1F2937 mb-3">ภาพรวม</h2>
            <p class="text-s-24 text-w-400 color-64748B">{{ data.overview }}</p>
          </div>
          <div class="col-lg-4 col-12 mt-4 mt-lg-0">
            <div class="mb-3 views-row">
              <span class="views-badge text-s-20 text-w-500"><span class="views-badge-ico" aria-hidden="true"></span>{{ data.views }} views</span>
              <a v-if="data.website" :href="data.website" target="_blank" rel="noopener noreferrer" class="visit-site text-s-20 text-w-500">
                ดูเว็บไซต์จริง
                <svg class="visit-site-ico" width="18" height="18" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                  <path d="M7 17L17 7M17 7H9M17 7V15" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </a>
            </div>
            <p class="text-s-24 text-w-400 color-9CA3AF mb-1">ประเภทธุรกิจ</p>
            <div class="mb-3">
              <span v-for="(t, i) in data.tags" :key="'t' + i" class="tag-blog-1 me-2">{{ t }}</span>
            </div>
            <p class="text-s-24 text-w-400 color-9CA3AF mb-1">การบริการ</p>
            <div class="mb-3">
              <span v-for="(t, i) in data.services" :key="'s' + i" class="tag-blog-1 me-2">{{ t }}</span>
            </div>
            <p class="text-s-24 text-w-400 color-9CA3AF mb-1">ทีมที่เกี่ยวข้อง</p>
            <div class="mb-3">
              <span v-for="(t, i) in data.team" :key="'tm' + i" class="tag-blog-1 me-2">{{ t }}</span>
            </div>
            <p class="text-s-24 text-w-400 color-9CA3AF mb-1">ระยะเวลา</p>
            <p class="text-s-24 text-w-700 color-1F2937">{{ data.duration }}</p>
          </div>
        </div>

        <!-- stats -->
        <div class="row overview-stats">
          <div v-for="(st, i) in data.stats" :key="i" class="col-md-4 col-12 mt-3 mt-md-0">
            <div class="stat-card">
              <div class="stat-top">
                <img class="stat-ico" :src="st.up ? trendUp : trendDown" :alt="st.up ? 'trending up' : 'trending down'" />
                <span class="text-s-60 text-w-700 color-1F2937 stat-value"><span v-countup="st.num"></span>{{ st.suffix }}</span>
              </div>
              <p class="text-s-24 text-w-400 color-64748B mb-0">{{ st.label }}</p>
            </div>
          </div>
        </div>
      </section>

      <!-- ===== โจทย์ของลูกค้า ===== -->
      <section id="challenge" class="fade-in-up sec-gradient" v-intersect>
        <div class="row">
          <div class="col-lg-6 col-12 mb-3 mb-lg-0">
            <h2 class="text-s-60 text-w-700 color-1F2937 mb-0">โจทย์ของลูกค้า</h2>
          </div>
          <div class="col-lg-6 col-12">
            <p class="text-s-24 text-w-400 color-64748B mb-4">{{ data.challengeIntro }}</p>
            <div v-for="(row, i) in data.challenges" :key="i" class="mb-4">
              <p class="text-s-36 text-w-700 color-1F2937 mb-2">{{ row.title }}</p>
              <p class="text-s-24 text-w-400 color-64748B mb-0">{{ row.text }}</p>
            </div>
          </div>
        </div>
      </section>

      <!-- ===== เป้าหมาย ===== -->
      <section class="sec-goal fade-in-up" v-intersect>
        <p class="text-s-60 text-w-700 goal-eyebrow mb-2">เป้าหมายที่คาดหวัง</p>
        <h2 class="text-s-60 text-w-700 color-1F2937 goal-title">เพิ่มยอดขายในช่องทางออนไลน์และนำระบบการจัดการ<br />ลูกค้าสัมพันธ์ (CRM)มาใช้เพื่อเสริมสร้างความสัมพันธ์กับลูกค้า</h2>
        <img class="goal-img" :src="data.preview" :alt="data.title" />
      </section>

      <!-- ===== ผู้เชี่ยวชาญ / บริการที่นำเสนอ ===== -->
      <section class="text-center fade-in-up" v-intersect>
        <h2 class="text-s-40 text-w-700 color-1F2937 mb-5 expert-title">Sellsuki ได้ทำการเลือกกลุ่มผู้เชี่ยวชาญ<br />เพื่อมาช่วยแก้ปัญหานี้</h2>
        <p class="text-s-20 color-9CA3AF mb-3">บริการที่นำเสนอ</p>
        <div>
          <span v-for="(t, i) in data.tags" :key="i" class="tag-blog-1 me-2">{{ t }}</span>
        </div>
      </section>

      <!-- ===== โซลูชั่น ===== -->
      <section id="solution" class="fade-in-up sec-gradient" v-intersect>
        <div class="row">
          <div class="col-lg-6 col-12 mb-3 mb-lg-0">
            <h2 class="text-s-60 text-w-700 color-1F2937 mb-0">โซลูชั่นที่นำเสนอ</h2>
          </div>
          <div class="col-lg-6 col-12">
            <div v-for="(row, i) in data.solutions" :key="i" class="mb-4">
              <p class="text-s-36 text-w-700 color-1F2937 mb-2">{{ row.title }}</p>
              <p class="text-s-24 text-w-400 color-64748B mb-0">{{ row.text }}</p>
            </div>
          </div>
        </div>
      </section>
    </div>

    <!-- ===== การดำเนินงาน (dark banner) ===== -->
    <section id="process" class="process-banner fade-in-up" v-intersect :style="{ backgroundImage: 'url(' + data.cover + ')' }">
      <div class="process-overlay"></div>
      <div class="container process-inner">
        <h2 class="text-s-60 text-w-700 color-FFFFFF mb-4">การดำเนินงาน</h2>
        <div class="row">
          <div v-for="(step, i) in data.process" :key="i" class="col-lg-3 col-md-6 col-12 mt-4 mt-lg-0 process-step">
            <div class="process-icon mb-3">
              <svg v-if="step.handshake" xmlns="http://www.w3.org/2000/svg" width="34" height="34" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <path d="m11 17 2 2a1 1 0 1 0 3-3" />
                <path d="m14 14 2.5 2.5a1 1 0 1 0 3-3l-3.88-3.88a3 3 0 0 0-4.24 0l-.88.88a1 1 0 1 1-3-3l2.81-2.81a5.79 5.79 0 0 1 7.06-.87l.47.28a2 2 0 0 0 1.42.25H21" />
                <path d="m21 3 1 11h-2" />
                <path d="M3 3 2 14l6.5 6.5a1 1 0 1 0 3-3" />
                <path d="M3 4h8" />
              </svg>
              <i v-else :class="step.icon"></i>
            </div>
            <span v-if="i < data.process.length - 1" class="process-line"></span>
            <p class="text-s-36 text-w-700 color-FFFFFF mb-1">{{ step.title }}</p>
            <p class="text-s-24 text-w-400" style="color: #CBD5E1">{{ step.text }}</p>
          </div>
        </div>
      </div>
    </section>

    <div class="container font-df ps-3 pe-3 ps-md-0 pe-md-0">
      <!-- ===== ผลลัพธ์ ===== -->
      <section id="result" class="fade-in-up sec-gradient" v-intersect>
        <div class="row">
          <div class="col-lg-6 col-12 mb-3 mb-lg-0">
            <h2 class="text-s-60 text-w-700 color-1F2937 mb-0">ผลลัพธ์ที่ได้</h2>
          </div>
          <div class="col-lg-6 col-12">
            <div v-for="(row, i) in data.results" :key="i" class="mb-4">
              <p class="text-s-36 text-w-700 color-1F2937 mb-2">{{ row.title }}</p>
              <p class="text-s-24 text-w-400 color-64748B mb-0">{{ row.text }}</p>
            </div>
          </div>
        </div>
      </section>

      <!-- ===== gallery ===== -->
      <section class="fade-in-up" v-intersect>
        <div class="gallery-frame">
          <ssr-carousel
            class="gallery-carousel"
            :slides-per-page="1"
            show-arrows
            show-dots
            paginate-by-slide
            loop
            :autoplay-delay="6"
          >
            <div v-for="(g, i) in data.gallery" :key="i" class="slide">
              <img class="gallery-img" :src="g" :alt="'gallery ' + i" />
            </div>
            <template #dot="{ disabled }">
              <div v-if="disabled == false" class="dot-carousel"></div>
              <div v-if="disabled == true" class="dot-carousel-active"></div>
            </template>
            <template #back-arrow><div class="g-arrow"><i class="bi bi-chevron-left"></i></div></template>
            <template #next-arrow><div class="g-arrow"><i class="bi bi-chevron-right"></i></div></template>
          </ssr-carousel>
        </div>
      </section>

      <!-- ===== เสียงตอบรับจากลูกค้า ===== -->
      <section id="review" class="fade-in-up" v-intersect>
        <h2 class="text-s-60 text-w-700 color-1F2937 text-center mb-5">เสียงตอบรับจากลูกค้าที่ใช้จริง</h2>
        <div class="testimonial-frame">
          <ssr-carousel
            class="testimonial-carousel"
            :slides-per-page="4"
            :breakpoints="{ '992': { slidesPerPage: 2 }, '576': { slidesPerPage: 1 } }"
            show-dots
            paginate-by-slide
            loop
            :autoplay-delay="6"
          >
            <div v-for="(t, i) in data.testimonials" :key="i" class="slide">
              <div class="testimonial-card">
                <p class="text-s-24 text-w-400 color-64748B testimonial-text">{{ t.text }}</p>
                <div class="testimonial-user">
                  <span class="testimonial-avatar" :class="i % 2 === 0 ? 'avatar-blue' : 'avatar-peach'">{{ t.initial }}</span>
                  <span class="testimonial-meta">
                    <span class="text-s-24 font-md color-1F2937 d-block testimonial-name">{{ t.name }}</span>
                    <span class="text-s-20 text-w-400 color-9CA3AF">{{ t.handle }}</span>
                  </span>
                </div>
              </div>
            </div>
            <template #dot="{ disabled }">
              <div v-if="disabled == false" class="dot-carousel"></div>
              <div v-if="disabled == true" class="dot-carousel-active"></div>
            </template>
          </ssr-carousel>
        </div>
      </section>

      <!-- ===== สิ่งที่ได้เรียนรู้ ===== -->
      <section id="lesson" class="fade-in-up sec-gradient" v-intersect>
        <div class="row">
          <div class="col-lg-6 col-12 mb-3 mb-lg-0">
            <h2 class="text-s-60 text-w-700 color-1F2937 mb-0">สิ่งที่ได้เรียนรู้</h2>
          </div>
          <div class="col-lg-6 col-12">
            <div v-for="(row, i) in data.lessons" :key="i" class="mb-4">
              <p class="text-s-36 text-w-700 color-1F2937 mb-2">{{ row.title }}</p>
              <p class="text-s-24 text-w-400 color-64748B mb-0">{{ row.text }}</p>
            </div>
          </div>
        </div>
      </section>

      <!-- ===== CTA banner ===== -->
      <section class="fade-in-up" v-intersect>
        <div class="cta-purple" :style="{ backgroundImage: 'url(' + data.ctaWize + ')' }">
          <div class="cta-purple-text text-center">
            <h2 class="text-s-60 text-w-700 color-1F2937 mb-4">WizeMoves เคียงข้างทุกก้าวที่สำคัญ<br />เติบโตพร้อมธุรกิจของคุณไปอีกขั้น</h2>
            <div class="d-flex flex-wrap gap-2 justify-content-center">
              <a href="tel:0900967526" class="btn-purple text-s-28 text-w-500"><img class="btn-purple-ico" :src="data.icoPhone" alt="" />090 096 7526</a>
              <a href="https://lin.ee/5ljYXPo" target="_blank" rel="noopener" class="btn-purple text-s-28 text-w-500"><img class="btn-purple-ico" :src="data.icoChat" alt="" />แชทผ่านไลน์</a>
              <nuxt-link :to="localePath('/contact-us')" class="btn-purple text-s-28 text-w-500"><img class="btn-purple-ico" :src="data.icoQuote" alt="" />ขอใบเสนอราคา</nuxt-link>
            </div>
          </div>
        </div>
      </section>

      <!-- ===== related ===== -->
      <section class="fade-in-up" v-intersect>
        <h2 class="text-s-60 text-w-700 color-1F2937 text-center mb-4">ผลงานอื่นๆ</h2>
        <div class="row">
          <div v-for="(rel, ri) in related" :key="rel.id" class="col-lg-4 col-md-6 col-12 mt-3 mt-lg-0 d-flex">
            <nuxt-link :to="localePath('/portfolios/showcase/' + rel.id)" class="w-100" style="color: unset !important">
              <div class="card port-card h-100">
                <div class="card-media">
                  <img class="card-media-img" :src="rel.cover" :alt="rel.title" />
                  <div class="card-media-overlay"></div>
                  <div class="card-media-badge">
                    <img class="cmb-client-logo" :src="clientLogos[ri % clientLogos.length]" :alt="rel.title + ' logo'" />
                  </div>
                </div>
                <div class="card-body pt-3 d-flex flex-column">
                  <div class="mb-2">
                    <span v-for="(t, ti) in rel.tags" :key="ti" class="tag-blog-1 me-2">{{ t }}</span>
                  </div>
                  <p class="card-title text-s-36 text-w-700 color-1F2937 text-limit-2 mb-2">{{ rel.title }}</p>
                  <p class="text-limit-3 text-s-24 text-w-400 color-64748B mb-3">{{ rel.description }}</p>
                  <span class="card-cta mt-auto text-s-20 font-md">ดูรายละเอียด <img class="card-cta-ico" :src="chevronRight" alt="chevron-right" /></span>
                </div>
              </div>
            </nuxt-link>
          </div>
        </div>
      </section>

    </div>
  </div>
</template>

<script>
export default {
  name: 'PortfolioShowcase',
  layout: 'layoutV2',
  head() {
    return this.$headUtil({
      lang: this.$i18n.locale == 'th-TH' ? 'th-TH' : 'en-TH',
      title: this.data.title,
      route: process.env.MAIN_URL + this.$route.path
    })
  },
  data() {
    const cover = require('~/assets/SolutionsWizemoves/banner.jpg')
    const cover2 = require('~/assets/joinus/03.webp')
    const cover1 = require('~/assets/SolutionsWizemoves/Consulting/img-bg-1.jpg')
    const preview = require('~/assets/joinus/09.webp')
    const heroPreview = require('~/assets/Portfolio/phufa-preview.png')
    const ctaWize = require('~/assets/Portfolio/cta-wizeMoves.png')
    const icoPhone = require('~/assets/Portfolio/phone.png')
    const icoChat = require('~/assets/Portfolio/chat-bubble-oval-left-ellipsis.png')
    const icoQuote = require('~/assets/Portfolio/newspaper.png')
    const trendUp = require('~/assets/Portfolio/arrow-trending-up.png')
    const trendDown = require('~/assets/Portfolio/arrow-trending-down.png')
    const chevronRight = require('~/assets/SolutionsWizemoves/customer/chevron-right.png')
    const clientLogos = [
      require('~/assets/Portfolio/Logo Client.png'),
      require('~/assets/Portfolio/Logo Client2.png'),
      require('~/assets/Portfolio/Logo Client3.png')
    ]
    const lorem = 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse varius enim in eros elementum tristique. Duis cursus, mi quis viverra ornare, eros dolor interdum nulla.'

    return {
      activeSection: 'overview',
      showDiv: false,
      lastScrollY: 0,
      trendUp,
      trendDown,
      chevronRight,
      clientLogos,
      sections: [
        { id: 'overview', label: 'ภาพรวม' },
        { id: 'challenge', label: 'โจทย์ของลูกค้า' },
        { id: 'solution', label: 'โซลูชั่น' },
        { id: 'process', label: 'การดำเนินงาน' },
        { id: 'result', label: 'ผลลัพธ์' },
        { id: 'review', label: 'รีวิว' },
        { id: 'lesson', label: 'สิ่งที่ได้เรียนรู้' }
      ],
      data: {
        title: 'Phufa Digital Transformation',
        date: '07 October, 2025',
        views: 1020,
        website: 'https://www.phufa.com',
        cover,
        preview,
        heroPreview,
        ctaWize,
        icoPhone,
        icoChat,
        icoQuote,
        summary: 'โครงการนี้คือการเปลี่ยนผ่านสู่ยุคดิจิทัลของร้านภูฟ้า เพื่อยกระดับการบริหารจัดการองค์กรให้มีประสิทธิภาพยิ่งขึ้นและสอดคล้องกับพฤติกรรมผู้บริโภคในปัจจุบัน โดยมุ่งเน้นการสร้างประสบการณ์ที่ดีให้กับลูกค้าผ่านแพลตฟอร์มออนไลน์ต่างๆ',
        overview: lorem + ' ' + lorem,
        tags: ['E-commerce', 'CRM'],
        services: ['Website Development', 'CRM Integration'],
        team: ['SA', 'UX/UI Designer', 'Developer'],
        duration: '3 เดือน',
        stats: [
          { label: 'ยอดขายเพิ่มขึ้น 3 เท่า', num: 1000, suffix: '%', caption: 'เทียบกับก่อนเริ่มโครงการ', up: true },
          { label: 'Conversion Rate', num: 12, suffix: '%', caption: 'เพิ่มขึ้นจากเดิม', up: true },
          { label: 'ระยะเวลาการทำงานที่ลดลง', num: 30, suffix: '%', caption: 'ด้วยระบบอัตโนมัติ', up: false }
        ],
        challengeIntro: lorem,
        challenges: [
          { title: 'ระบบเว็บไซต์ทำได้ยากและควบคุมได้ยาก', text: lorem },
          { title: 'ขาดแคลน CRM ที่นำมาจัดการความสัมพันธ์ลูกค้าอย่างครบวงจร (Marketing Automation)', text: lorem },
          { title: 'การสื่อสารภายในและนอกยังไม่มีจุดศูนย์กลาง', text: lorem }
        ],
        goalTitle: 'เพิ่มยอดขายในช่องทางออนไลน์และนำระบบบริหารจัดการลูกค้าสัมพันธ์ (CRM) มาใช้เพื่อเสริมสร้างความสัมพันธ์กับลูกค้า',
        solutions: [
          { title: 'พัฒนาเว็บไซต์ E-commerce ที่ทันสมัยและเชื่อมต่อได้ง่าย', text: lorem },
          { title: 'ติดตั้งระบบ CRM ที่ช่วยจัดการความสัมพันธ์ลูกค้าและระบบการตลาดอัตโนมัติ (AI-powered Marketing Automation)', text: lorem },
          { title: 'จัดแคมเปญและปรับปรุงกระบวนการทำงานให้เป็นระบบอัตโนมัติ', text: lorem }
        ],
        process: [
          { title: 'รับบรีฟ', text: lorem, icon: 'bi bi-window' },
          { title: 'พัฒนา CRM', text: lorem, handshake: true },
          { title: 'ทดสอบระบบ', text: lorem, icon: 'bi bi-clipboard-check' },
          { title: 'อบรมลูกค้า', text: lorem, icon: 'bi bi-people-fill' }
        ],
        results: [
          { title: 'ยอดขายเพิ่มขึ้น 1,000.00% ใน 3 เดือนหลังเปิดใช้ระบบใหม่', text: lorem },
          { title: 'การมีระบบ CRM ช่วยให้การบริหารลูกค้าดีขึ้น เพิ่ม Conversion Rate 12%', text: lorem },
          { title: 'ลดปัญหาการทำงานซ้ำซ้อนลง 30% ด้วยระบบ CRM ในการเก็บข้อมูล', text: lorem }
        ],
        gallery: [preview, cover1, cover2],
        lessons: [
          { title: 'ระบบ E-commerce และ CRM ที่ช่วยเพิ่มยอดขายได้อย่างเป็นรูปธรรม', text: lorem },
          { title: 'การวางแผน Workflow ช่วยให้การส่งมอบงานเป็นไปได้อย่างราบรื่น', text: lorem },
          { title: 'การสื่อสารกับลูกค้าอย่างต่อเนื่องเป็นกุญแจสำคัญของความสำเร็จ', text: lorem }
        ],
        testimonials: [
          { text: 'ง่ายมาก สะดวก เข้าใจง่าย แอดมินตอบไว ให้บริการดีมาก', name: 'ธิดารัตน์ ศิริธารา', handle: '@871gqgzd', initial: 'T' },
          { text: 'ชอบมากครับ สะดวก จ่ายง่าย ซื้อง่ายกว่าไปทำเอง', name: 'ฐิติมล พงษ์สิริชัย', handle: '@509wlzxl', initial: 'T' },
          { text: 'เจ้าหน้าที่ให้บริการดี เว็บไซต์ออกแบบมาใช้งานง่ายมากค่ะ บริการรวดเร็วทันใจค่ะ', name: 'เดอะโพลิแทนรีฟ นิติบุคคล', handle: '@exy7032a', initial: 'T' },
          { text: 'ตอนแรกงงๆ พอได้รับคำแนะนำก็ใช้งานง่ายค่ะ พนักงานช่วยตอบคำถามได้ดี คอยช่วยเหลือดีค่ะ', name: 'ปุณรดา บุตรากาศ', handle: '@yea6267g', initial: 'P' },
          { text: 'ระบบใช้งานง่าย ทีมงานดูแลดีมาก ตอบคำถามรวดเร็ว ประทับใจครับ', name: 'สมชาย ใจดี', handle: '@a12bcd3', initial: 'S' },
          { text: 'ยอดขายเพิ่มขึ้นเห็นได้ชัดหลังใช้ระบบ คุ้มค่ามากค่ะ', name: 'วราภรณ์ สุขสันต์', handle: '@w98xyz1', initial: 'W' },
          { text: 'บริการหลังการขายดีเยี่ยม มีปัญหาก็แก้ไขให้ทันที', name: 'ณัฐพงษ์ วงศ์ทอง', handle: '@n45qwe6', initial: 'N' },
          { text: 'ใช้งานมาหลายเดือนแล้ว เสถียร ไม่มีปัญหา แนะนำเลยครับ', name: 'กมลชนก แสงเดือน', handle: '@k77rty8', initial: 'K' }
        ]
      },
      related: [
        { id: 2, tags: ['Website Development', 'CRM Integration'], title: 'PATCONNEX LINE Messaging API', description: 'โซลูชันการสื่อสารผ่าน LINE Messaging API สำหรับ Port Authority of Thailand', cover: cover2 },
        { id: 4, tags: ['SEO', 'Content Marketing'], title: 'Skincare SEO Growth Project', description: 'เพิ่มการเข้าถึงและยอดขายของแบรนด์สกินแคร์ผ่าน Search Engine Optimization', cover: cover1 },
        { id: 1, tags: ['LINE OA'], title: 'LINE OA Verification Service', description: 'ปรับเปลี่ยนบัญชีทางการเดิมให้เป็นบัญชีทางการที่ผ่านการยืนยันโดย LINE Agency', cover }
      ]
    }
  },
  methods: {
    scrollTo(id) {
      const el = document.getElementById(id)
      if (el) {
        const y = el.getBoundingClientRect().top + window.pageYOffset - 120
        window.scrollTo({ top: y, behavior: 'smooth' })
      }
    },
    onScroll() {
      const scrollY = window.pageYOffset
      // Show the fixed tab bar (replacing the site nav) once the hero is
      // scrolled past, and hide it again while scrolling up — same behaviour
      // as the Business Consulting page.
      const hero = document.querySelector('.hero-detail')
      const threshold = hero ? hero.offsetTop + hero.offsetHeight - 64 : 500
      this.showDiv = scrollY > threshold
      if (scrollY < this.lastScrollY) {
        this.showDiv = false
      }
      this.lastScrollY = scrollY
      // Highlight the active section
      const offset = scrollY + 140
      let current = this.sections[0].id
      for (const s of this.sections) {
        const el = document.getElementById(s.id)
        if (el && el.offsetTop <= offset) current = s.id
      }
      this.activeSection = current
    }
  },
  mounted() {
    window.addEventListener('scroll', this.onScroll)
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.onScroll)
  }
}
</script>

<style scoped>
.breadcrumb-text { font-size: 18px; }

/* ---------- Consistent section rhythm (80px top/bottom) ---------- */
#PortfolioShowcase section {
  padding-top: 80px;
  padding-bottom: 80px;
}
/* per-section padding overrides */
#PortfolioShowcase .overview-stats { margin-top: 56px !important; }
#PortfolioShowcase section.sec-goal { padding-top: 80px; padding-bottom: 0; }
#PortfolioShowcase #solution { padding-top: 80px; padding-bottom: 120px; }
#PortfolioShowcase #process { padding-top: 120px; padding-bottom: 120px; }
#PortfolioShowcase #result { padding-top: 120px; padding-bottom: 80px; }

/* ---------- Hero ---------- */
.hero-fullwidth {
  position: relative;
  width: 100vw;
  left: 50%; right: 50%;
  margin-left: -50vw; margin-right: -50vw;
}
.hero-detail {
  position: relative;
  overflow: hidden;
  height: 550px;
  background-size: cover;
  background-position: center;
  margin-top: 16px;
}
.hero-overlay {
  position: absolute; inset: 0;
  background: linear-gradient(90deg, rgba(9, 25, 58, 0.88) 0%, rgba(9, 25, 58, 0.5) 60%, rgba(9, 25, 58, 0.2) 100%);
}
.hero-inner {
  position: relative; z-index: 2; height: 100%;
}
.hero-content {
  position: absolute; z-index: 2; top: 50%; transform: translateY(-50%);
  left: var(--bs-gutter-x, 12px); max-width: 56%;
}
.hero-content a { color: #FFF !important; }
.hero-content h1 { white-space: nowrap; }
.hero-title { padding-top: 64px; }
.hero-desc { display: -webkit-box; -webkit-line-clamp: 3; -webkit-box-orient: vertical; overflow: hidden; }
.hero-preview {
  position: absolute; z-index: 2; right: var(--bs-gutter-x, 12px); top: 50%; transform: translateY(calc(-50% + 40px));
  width: 540px;
}
.browser-shot {
  display: block; width: 540px; height: auto;
}
@media (max-width: 991px) {
  .hero-detail { height: 300px; }
  .hero-content { left: 24px; max-width: 92%; }
}

/* ---------- Tab nav (fixed bar shown on scroll, over the site nav) ---------- */
.tab-nav {
  position: fixed; top: 0; left: 0; right: 0; z-index: 1030;
  background: #FFF;
  box-shadow: none;
  border-bottom: none;
  /* match Business Consulting tab height (64px) */
  height: 64px;
  min-height: 64px;
  display: flex;
  align-items: stretch;
}
.tab-nav > .container { width: 100%; display: flex; align-items: stretch; }
.tab-nav-fixed { animation: tabNavFadeIn .3s ease; }
@keyframes tabNavFadeIn {
  from { opacity: 0; transform: translateY(-8px); }
  to { opacity: 1; transform: none; }
}
.tab-scroll {
  display: flex; gap: 40px; overflow-x: auto; scrollbar-width: none;
  justify-content: flex-start; align-items: stretch;
}
.tab-scroll::-webkit-scrollbar { display: none; }
.tab-link {
  white-space: nowrap; padding: 0; color: #6B7280;
  display: flex; align-items: center;
  border-bottom: 5px solid transparent;
}
.tab-active { color: #32A9FF; border-bottom: 5px solid #32A9FF; font-weight: 500; }

/* ---------- Badges (brand blue) ---------- */
.tag-blog-1 {
  background: #EBF8FF !important;
  border: 1px solid #B3E6FF !important;
  color: #2DA3FD !important;
  padding: 4px 16px;
  font-size: 20px !important;
  font-weight: 500;
  font-family: 'Heavent' !important;
  line-height: 1 !important;
}

/* ---------- Stats ---------- */
.stat-card {
  background: #F9FAFB; border: 1px solid #F3F4F6; border-radius: 16px; padding: 36px 24px; height: 100%;
  text-align: center;
}
.stat-top {
  display: flex; align-items: center; justify-content: center; gap: 12px; margin-bottom: 12px;
}
.stat-top i { font-size: 30px; line-height: 1; }
.stat-ico { width: 40px; height: 40px; object-fit: contain; flex: 0 0 auto; }
.views-badge {
  display: inline-flex; align-items: center; gap: 8px;
  background: #F3F4F6; border: 1px solid #E5E7EB; color: #9CA3AF;
  border-radius: 999px; padding: 6px 16px; line-height: 1;
}
.views-badge-ico {
  display: inline-block;
  width: 18px; height: 18px;
  background-color: currentColor;
  -webkit-mask: url(~/assets/Portfolio/eye.png) no-repeat center / contain;
  mask: url(~/assets/Portfolio/eye.png) no-repeat center / contain;
}
.views-row { display: flex; align-items: center; flex-wrap: wrap; gap: 16px; }
.visit-site {
  display: inline-flex; align-items: center; gap: 6px;
  color: #32A9FF !important; text-decoration: none; line-height: 1;
  transition: opacity .2s ease;
}
.visit-site:hover { opacity: .75; text-decoration: underline; }
.visit-site-ico { flex: 0 0 auto; }
.stat-value { line-height: 1; }

/* ---------- section gradient background ---------- */
.sec-gradient {
  position: relative;
  z-index: 0;
}
.sec-gradient::before {
  content: "";
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 100vw;
  height: 520px;
  /* soft airy pastel glow — light blue (replacing purple) with a warm peach accent */
  background:
    radial-gradient(55% 70% at 88% 22%, rgba(253, 222, 190, 0.50) 0%, rgba(253, 222, 190, 0) 60%),
    radial-gradient(60% 80% at 20% 16%, rgba(142, 220, 255, 0.45) 0%, rgba(142, 220, 255, 0) 65%),
    radial-gradient(78% 95% at 2% 40%, rgba(186, 230, 253, 0.60) 0%, rgba(186, 230, 253, 0) 60%);
  -webkit-mask-image: linear-gradient(180deg, rgba(0, 0, 0, 0.95) 0%, rgba(0, 0, 0, 0.55) 45%, rgba(0, 0, 0, 0) 100%);
  mask-image: linear-gradient(180deg, rgba(0, 0, 0, 0.95) 0%, rgba(0, 0, 0, 0.55) 45%, rgba(0, 0, 0, 0) 100%);
  opacity: 1;
  z-index: -1;
  pointer-events: none;
}

/* ---------- goal / gallery ---------- */
.goal-eyebrow {
  color: #8EDCFF !important;
  line-height: 1.1;
}
.goal-title {
  margin-bottom: 40px;
}
.goal-img {
  width: 100%; max-height: 460px; object-fit: cover; border-radius: 16px;
}
.gallery-frame {
  background: transparent; border-radius: 24px; padding: 0;
  position: relative; margin-bottom: 40px;
}
.gallery-carousel ::v-deep .ssr-carousel-dots {
  position: absolute; top: 100%; left: 0; right: 0; margin-top: 20px;
}
/* arrows: overlay the image, hidden until the frame is hovered */
.gallery-carousel ::v-deep .ssr-carousel-arrows {
  position: absolute !important;
  top: 0 !important;
  bottom: auto !important;
  left: 0 !important;
  right: 0 !important;
  height: 100% !important;
  opacity: 0;
  transition: opacity .25s ease;
  pointer-events: none;
}
.gallery-frame:hover .gallery-carousel ::v-deep .ssr-carousel-arrows { opacity: 1; }
.gallery-carousel ::v-deep .ssr-carousel-back-button,
.gallery-carousel ::v-deep .ssr-carousel-next-button {
  position: absolute !important;
  top: 50% !important;
  bottom: auto !important;
  transform: translateY(-50%) !important;
  padding: 0 !important;
  margin: 0 !important;
  background: transparent !important;
  border: none !important;
  pointer-events: auto;
}
.gallery-carousel ::v-deep .ssr-carousel-back-button { left: 16px !important; right: auto !important; }
.gallery-carousel ::v-deep .ssr-carousel-next-button { right: 16px !important; left: auto !important; }
/* round button overlaying the image */
.g-arrow {
  display: inline-flex; align-items: center; justify-content: center;
  width: 44px; height: 44px; line-height: 1; padding: 0; text-align: center;
  background: rgba(255, 255, 255, 0.9); color: #1F2937;
  border-radius: 50%; box-shadow: 0 4px 12px rgba(17, 24, 39, 0.18);
  transition: background .2s ease;
}
.g-arrow:hover { background: #FFFFFF; }
.g-arrow i {
  display: block; line-height: 1; font-size: 18px;
}
.gallery-img {
  width: 100%; height: 420px; object-fit: cover; border-radius: 12px;
  box-shadow: 0 10px 28px rgba(17, 24, 39, 0.14);
  display: block;
}
.gallery-carousel ::v-deep .ssr-carousel-track,
.gallery-carousel ::v-deep .ssr-carousel-slide { align-items: center; }
@media (max-width: 767px) {
  .gallery-carousel ::v-deep .ssr-carousel-back-button { left: 10px !important; }
  .gallery-carousel ::v-deep .ssr-carousel-next-button { right: 10px !important; }
}

/* ---------- process banner ---------- */
.process-banner {
  position: relative; background-size: cover; background-position: center;
  padding: 80px 0; overflow: hidden;
}
.process-overlay { position: absolute; inset: 0; background: rgba(9, 25, 58, 0.82); }
.process-inner { position: relative; z-index: 2; }
.process-step { position: relative; }
.process-icon {
  color: #FFF; font-size: 32px; line-height: 1;
  display: inline-flex; align-items: center; justify-content: center;
}
.process-icon svg { width: 34px; height: 34px; display: block; }
.process-line {
  position: absolute; top: 17px; left: 52px; right: 8px;
  border-top: 2px dashed rgba(255, 255, 255, 0.45);
}

/* ---------- cards ---------- */
.card {
  background: #FFFFFF !important; border-radius: 12px !important; border: 1px solid #E5E7EB;
  box-shadow: 0px 1px 2px 0px rgba(17, 24, 39, 0.07), 0px 3px 3px 0px rgba(17, 24, 39, 0.05);
}
.card.port-card { background: #F9FAFB !important; border: 1px solid #E5E7EB !important; }
.card.port-card:hover { box-shadow: 0px 12px 24px rgba(17, 24, 39, 0.12); transform: translateY(-2px); transition: all .2s ease; }
.card-title { font-family: 'Heavent-med' !important; line-height: 42px; }
.card-body { min-height: 210px; padding: 20px; }
.img-fix-size { width: 100%; height: 200px; object-fit: cover; border-top-left-radius: 12px; border-top-right-radius: 12px; }

/* card badge matches the list page (= hero badge size) */
.port-card .tag-blog-1 {
  padding: 4px 16px;
  font-size: 20px !important;
  font-weight: 500;
  font-family: 'Heavent' !important;
  line-height: 1 !important;
}

/* ---------- Card media (image + overlay + logo lockup) ---------- */
.card-media {
  position: relative; width: 100%; aspect-ratio: 453 / 300; overflow: hidden;
  border-top-left-radius: 12px; border-top-right-radius: 12px;
}
.card-media-img { width: 100%; height: 100%; object-fit: cover; display: block; }
.card-media-overlay { position: absolute; inset: 0; background: rgba(0, 0, 0, 0.5); }
.card-media-badge {
  position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); z-index: 2;
  display: flex; align-items: center; justify-content: center; width: 100%; padding: 0 24px;
}
.cmb-client-logo { width: 200px; max-width: 80%; height: auto; object-fit: contain; display: block; }
.text-limit-2 { overflow: hidden; text-overflow: ellipsis; display: -webkit-box; -webkit-line-clamp: 2; -webkit-box-orient: vertical; }
.text-limit-3 { overflow: hidden; text-overflow: ellipsis; display: -webkit-box; -webkit-line-clamp: 3; -webkit-box-orient: vertical; }
.text-limit-4 { overflow: hidden; text-overflow: ellipsis; display: -webkit-box; -webkit-line-clamp: 4; -webkit-box-orient: vertical; }
.card-cta { display: inline-flex; align-items: center; gap: 6px; color: #1F2937; transition: transform .2s ease; }
.card-cta-ico { width: 20px; height: 20px; }
.port-card:hover .card-cta { transform: translateX(4px); }

/* ---------- CTA purple ---------- */
.cta-purple {
  position: relative; overflow: hidden;
  border-radius: 16px; padding: 56px 48px;
  background-color: transparent;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  aspect-ratio: 1456 / 494;
  display: flex;
  align-items: center;
  justify-content: center;
}
.cta-purple-text { position: relative; z-index: 2; }
.btn-purple {
  display: inline-flex; align-items: center; gap: 8px;
  background: #7C3AED;
  border: 1px solid #7C3AED;
  color: #FFF !important; border-radius: 32px; padding: 10px 22px; font-size: 18px;
}
.btn-purple i { color: #FFFFFF; display: inline-flex; align-items: center; }
.btn-purple-ico { width: 28px; height: 28px; object-fit: contain; }
.btn-purple:hover { background: #6D28D9; border-color: #6D28D9; color: #FFF !important; }

/* ---------- dots / arrows ---------- */
.dot-carousel-active { width: 32px; height: 8px; background: #32A9FF; border-radius: 21px; margin: 0 5px; }
.dot-carousel { width: 24px; height: 8px; background: #D9F2FF; border-radius: 21px; margin: 0 5px; }
.g-arrow {
  display: inline-flex; width: 44px; height: 44px; justify-content: center; align-items: center;
  border-radius: 50%; border: 1px solid #E5E7EB; background: #FFFFFF; color: #1F2937; font-size: 18px;
  box-shadow: 0 4px 12px rgba(17, 24, 39, 0.14);
}

/* ---------- testimonials ---------- */
/* give the mask vertical room so card drop-shadows aren't clipped at the bottom
   (horizontal padding stays 0 so side slides remain clipped) */
.testimonial-carousel ::v-deep .ssr-carousel-mask { padding: 8px 0 32px !important; }
.testimonial-carousel ::v-deep .ssr-carousel-slide { padding: 12px; box-sizing: border-box; }
.testimonial-card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100%;
  min-height: 210px;
  background: #FFFFFF;
  border: 1px solid #F1F3F5;
  border-radius: 16px;
  box-shadow: 0 8px 24px rgba(17, 24, 39, 0.06);
  padding: 28px 24px;
}
.testimonial-text { margin: 0 0 24px; line-height: 1.5; }
.testimonial-user { display: flex; align-items: center; gap: 12px; }
.testimonial-avatar {
  flex: 0 0 auto;
  width: 44px; height: 44px;
  display: inline-flex; align-items: center; justify-content: center;
  border-radius: 50%;
  font-family: inherit;
  font-size: 18px; font-weight: 700;
  color: #FFFFFF;
}
.testimonial-avatar.avatar-blue { background: #A9DDFB; }
.testimonial-avatar.avatar-peach { background: #FCD9A8; }
.testimonial-name { line-height: 1.2; }
.testimonial-meta { display: flex; flex-direction: column; }
.testimonial-carousel ::v-deep .ssr-carousel-dots { margin-top: 8px; }
</style>
