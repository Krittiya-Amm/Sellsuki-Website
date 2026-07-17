<template>
  <div id="Portfolios" class="container font-df ps-3 pe-3 ps-md-0 pe-md-0">

    <!-- ===== Hero carousel (full width) ===== -->
    <div class="hero-fullwidth">
      <ssr-carousel :slides-per-page="1" show-dots paginate-by-slide loop :autoplay-delay="6">
        <div v-for="(hero, i) in highlights" :key="i" class="slide">
          <nuxt-link :to="localePath('/portfolios/showcase/' + hero.id)" style="color: unset !important">
            <div class="hero-banner" :style="{ backgroundImage: 'url(' + hero.cover + ')' }">
              <div class="hero-overlay"></div>
              <div class="container hero-inner ps-3 pe-3 ps-md-0 pe-md-0">
                <div class="hero-content">
                  <div class="hero-textblock">
                    <h1 class="text-s-72 text-w-700 color-FFFFFF mb-3">{{ hero.title }}</h1>
                    <p class="text-s-24 text-w-400 color-FFFFFF hero-desc mb-3">{{ hero.description }}</p>
                    <div class="d-flex flex-wrap">
                      <span v-for="(t, ti) in hero.tags" :key="ti" class="hero-tag me-2">
                        <img class="hero-tag-ico" src="~/assets/SolutionsWizemoves/Consulting/Subtract.png" alt="" />{{ t }}
                      </span>
                    </div>
                  </div>
                  <span class="btn-hero text-s-24 font-md">รายละเอียดผลงาน <i class="bi bi-arrow-right"></i></span>
                </div>
                <div class="hero-preview d-none d-lg-block">
                  <img class="browser-shot" :src="hero.preview" :alt="hero.title" />
                </div>
              </div>
            </div>
          </nuxt-link>
        </div>
        <template #dot="{ disabled }">
          <div v-if="disabled == false" class="dot-carousel"></div>
          <div v-if="disabled == true" class="dot-carousel-active"></div>
        </template>
      </ssr-carousel>
    </div>

    <!-- ===== Heading ===== -->
    <div class="row sec-top text-center color-1F2937 fade-in-up" v-intersect>
      <div class="col-12">
        <h2 class="text-s-60 text-w-700 mb-2">ผลงานของเรา</h2>
        <p class="text-s-24 text-w-400 color-6B7280">เรื่องเล่าจากลูกค้าเรา ส่วนหนึ่งจากลูกค้าที่ใช้บริการเรา</p>
      </div>
    </div>

    <!-- ===== Search ===== -->
    <div class="row gap-56 fade-in-up" v-intersect>
      <div class="col-12">
        <form class="search-form" @submit.prevent>
          <div class="search-box">
            <i class="bi bi-search color-9CA3AF search-icon"></i>
            <input v-model="search" class="search-input" type="text" placeholder="ค้นหาผลงาน" />
          </div>
          <button type="submit" class="search-submit">ค้นหา</button>
        </form>
      </div>
    </div>

    <!-- ===== Filter + Sort ===== -->
    <div class="filter-row gap-56 fade-in-up" v-intersect>
      <div class="filter-scroll-wrap">
        <img v-if="filterLeft" @click="scrollFilter(-1)" class="filter-chevron filter-chevron-l"
          src="~/assets/icon/chevron-l.svg" alt="เลื่อนซ้าย" />
        <div ref="filterScroll" class="filter-scroll" @scroll="updateFilterArrows">
          <div v-for="cat in categories" :key="cat"
            @click="activeCat = cat"
            class="btn-df filter-pill"
            :class="{ 'border-B3E6FF color-2DA3FD bg-EBF8FF': activeCat === cat }">
            <span class="text-s-24 text-w-700">{{ cat }}</span>
          </div>
        </div>
        <img v-if="filterRight" @click="scrollFilter(1)" class="filter-chevron filter-chevron-r"
          src="~/assets/icon/chevron-r.svg" alt="เลื่อนขวา" />
      </div>
      <div class="sort-wrap">
        <div ref="sortDd" class="sort-dd">
          <button type="button" class="sort-trigger text-s-24 text-w-400" @click="sortOpen = !sortOpen">
            <span>{{ currentSortLabel }}</span>
            <i class="bi color-6B7280" :class="sortOpen ? 'bi-chevron-up' : 'bi-chevron-down'"></i>
          </button>
          <ul v-show="sortOpen" class="sort-menu">
            <li v-for="opt in sortOptions" :key="opt.value"
              class="sort-option text-s-24 text-w-400"
              :class="{ 'bg-EBF8FF color-2DA3FD': sort === opt.value }"
              @click="selectSort(opt.value)">
              {{ opt.label }}
            </li>
          </ul>
        </div>
      </div>
    </div>

    <!-- ===== Cards grid ===== -->
    <div class="row gap-56 cards-grid">
      <div v-for="item in displayedItems" :key="item.id"
        class="col-xl-4 col-lg-4 col-md-6 col-sm-6 col-12 d-flex fade-in-up" v-intersect>
        <nuxt-link :to="localePath('/portfolios/showcase/' + item.id)" class="w-100" style="color: unset !important">
          <div class="card port-card h-100">
            <div class="card-media">
              <img class="card-media-img" :src="item.cover" :alt="item.title" />
              <div class="card-media-overlay"></div>
              <div class="card-media-badge">
                <img class="cmb-client-logo" :src="clientLogos[(item.id - 1) % clientLogos.length]" :alt="item.title + ' logo'" />
              </div>
            </div>
            <div class="card-body pt-3 d-flex flex-column">
              <div class="mb-2">
                <span v-for="(t, ti) in item.tags" :key="ti" class="tag-blog-1 me-2">{{ t }}</span>
              </div>
              <p class="card-title text-s-36 text-w-700 color-1F2937 text-limit-2 mb-2">{{ item.title }}</p>
              <p class="text-limit-3 text-s-24 text-w-400 color-64748B mb-3">{{ item.description }}</p>
              <span class="card-cta mt-auto text-s-20 font-md">ดูรายละเอียด <img class="card-cta-ico" :src="chevronRight" alt="chevron-right" /></span>
            </div>
          </div>
        </nuxt-link>
      </div>
    </div>

    <!-- ===== Load more ===== -->
    <div class="row gap-56 sec-bottom">
      <div class="col-12 text-center">
        <button v-if="visible < filteredItems.length" @click="visible += 6" class="btn-view">
          <span>โหลดเพิ่มเติม</span>
        </button>
      </div>
    </div>

    <!-- ===== CTA: start success with expert team (from Home) ===== -->
    <div class="cta-cardcontact">
      <CardContact />
    </div>

    <!-- ===== Other services ===== -->
    <div class="row sec-top text-center color-1F2937">
      <div class="col-12">
        <h2 class="text-s-60 text-w-700 mb-4">บริการอื่นๆ ที่คุณอาจสนใจ</h2>
      </div>
    </div>
    <div class="row sec-bottom last color-1F2937">
      <div v-for="svc in services" :key="svc.title" class="col-lg-3 col-md-6 col-12 mt-4 mt-lg-0">
        <div class="card">
          <div class="card-body">
            <img class="mb-2" :src="svc.icon" :alt="svc.title" />
            <p class="mb-2 text-s-28 font-md">{{ svc.title }}</p>
            <p class="mb-2 text-s-24 text-limit-3">{{ svc.description }}</p>
            <nuxt-link :to="localePath(svc.link)" class="svc-cta">
              <p class="mt-5 mb-0 text-s-20 font-md">
                สนใจบริการ
                <img :src="chevronRight" alt="chevron-right" />
              </p>
            </nuxt-link>
          </div>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
const CardContact = () => import('@/components/Home/CardContact')

export default {
  name: 'Portfolio',
  layout: 'layoutV2',
  components: {
    CardContact
  },
  head() {
    return this.$headUtil({
      lang: this.$i18n.locale == 'th-TH' ? 'th-TH' : 'en-TH',
      title: 'ผลงานของเรา',
      route: process.env.MAIN_URL + this.$route.path
    })
  },
  data() {
    const photoMeeting = require('~/assets/SolutionsWizemoves/Consulting/img-bg-1.jpg')
    const photoStrategy = require('~/assets/SolutionsWizemoves/banner.jpg')
    const photoWarehouse = require('~/assets/SolutionsAkita/DSC03283.JPG')
    const photoTeam = require('~/assets/joinus/01.webp')
    const photoTownhall = require('~/assets/joinus/03.webp')
    const photoOffice = require('~/assets/joinus/09.webp')
    const phufaPreview = require('~/assets/Portfolio/phufa-preview.png')
    const ctaBg = require('~/assets/Portfolio/cta-bg.png')
    const handRaised = require('~/assets/Portfolio/hand-raised.png')

    const items = [
      { id: 1, category: 'LINE Official Account', tags: ['LINE OA'], title: 'LINE OA Verification Service', description: 'โครงการนี้มีการปรับเปลี่ยนบัญชีทางการเดิมให้เป็นบัญชีทางการที่ผ่านการยืนยันโดย LINE Agency เพื่อช่วยยกระดับภาพลักษณ์และเพิ่มความน่าเชื่อถือให้กับแบรนด์', cover: photoTownhall },
      { id: 2, category: 'Website Development', tags: ['Website Development', 'CRM Integration'], title: 'PATCONNEX LINE Messaging API', description: 'โซลูชันที่พัฒนาขึ้นเพื่อการสื่อสารของ Port Authority of Thailand ผ่าน LINE Messaging API เป็นเครื่องมือที่ช่วยให้การสื่อสารรวดเร็วและมีประสิทธิภาพ', cover: photoStrategy },
      { id: 3, category: 'Website Development', tags: ['Website Development', 'CRM Integration'], title: 'Phufa Digital Transformation', description: 'โครงการนี้มีการปรับเปลี่ยนผ่านสู่ดิจิทัลของร้านภูฟ้า เพื่อยกระดับการบริหารจัดการทั้งช่องทางการขายออนไลน์และระบบบริหารความสัมพันธ์ลูกค้า', cover: photoMeeting },
      { id: 4, category: 'Content Marketing', tags: ['SEO', 'Content Marketing'], title: 'Skincare SEO Growth Project', description: 'โครงการนี้มีเป้าหมายเพื่อเพิ่มการเข้าถึงและยอดขายของแบรนด์สกินแคร์ผ่าน Search Engine Optimization ให้ติดอันดับต้นๆ บนหน้าผลการค้นหา', cover: photoOffice },
      { id: 5, category: 'Business Consulting', tags: ['Business Consulting'], title: 'Retail Business Consulting', description: 'บริการให้คำปรึกษาเชิงกลยุทธ์เพื่อวางรากฐานธุรกิจค้าปลีก ครอบคลุมตั้งแต่การวิเคราะห์ตลาด การวางแผน จนถึงการลงมือปฏิบัติจริง', cover: photoMeeting },
      { id: 6, category: 'Fulfillment', tags: ['Fulfillment'], title: 'Akita Fulfillment Solution', description: 'ระบบคลังสินค้าครบวงจรที่ช่วยจัดการสต๊อกและการจัดส่งอย่างมีประสิทธิภาพ ลดต้นทุนและเพิ่มความพึงพอใจให้กับลูกค้า', cover: photoWarehouse },
      { id: 7, category: 'Advertising', tags: ['Advertising'], title: 'Performance Ads Campaign', description: 'แคมเปญโฆษณาออนไลน์ที่เน้นผลลัพธ์ ครอบคลุมทุกแพลตฟอร์มหลัก เข้าถึงกลุ่มเป้าหมายได้ตรงจุด กระตุ้นยอดขายอย่างต่อเนื่อง', cover: photoStrategy },
      { id: 8, category: 'Website Development', tags: ['Website Development', 'CRM Integration'], title: 'Phufa Digital Transformation', description: 'โครงการนี้มีการปรับเปลี่ยนผ่านสู่ดิจิทัลของร้านภูฟ้า เพื่อยกระดับการบริหารจัดการทั้งช่องทางการขายออนไลน์', cover: photoTeam },
      { id: 9, category: 'LINE Official Account', tags: ['LINE OA'], title: 'LINE OA Verification Service', description: 'โครงการนี้มีการปรับเปลี่ยนบัญชีทางการเดิมให้เป็นบัญชีทางการที่ผ่านการยืนยันโดย LINE Agency เพื่อช่วยยกระดับภาพลักษณ์ของแบรนด์', cover: photoOffice },
      { id: 10, category: 'Website Development', tags: ['Website Development', 'CRM Integration'], title: 'PATCONNEX LINE Messaging API', description: 'โซลูชันที่พัฒนาขึ้นเพื่อการสื่อสารของ Port Authority of Thailand ผ่าน LINE Messaging API เป็นเครื่องมือที่ช่วยให้การสื่อสารรวดเร็วและมีประสิทธิภาพ', cover: photoStrategy },
      { id: 11, category: 'Fulfillment', tags: ['Fulfillment'], title: 'Akita Fulfillment Solution', description: 'ระบบคลังสินค้าครบวงจรที่ช่วยจัดการสต๊อกและการจัดส่งอย่างมีประสิทธิภาพ ลดต้นทุนและเพิ่มความพึงพอใจให้กับลูกค้า', cover: photoWarehouse },
      { id: 12, category: 'Content Marketing', tags: ['SEO', 'Content Marketing'], title: 'Skincare SEO Growth Project', description: 'โครงการนี้มีเป้าหมายเพื่อเพิ่มการเข้าถึงและยอดขายของแบรนด์สกินแคร์ผ่าน Search Engine Optimization ให้ติดอันดับต้นๆ บนหน้าผลการค้นหา', cover: photoOffice },
      { id: 13, category: 'Business Consulting', tags: ['Business Consulting'], title: 'Retail Business Consulting', description: 'บริการให้คำปรึกษาเชิงกลยุทธ์เพื่อวางรากฐานธุรกิจค้าปลีก ครอบคลุมตั้งแต่การวิเคราะห์ตลาด การวางแผน จนถึงการลงมือปฏิบัติจริง', cover: photoMeeting },
      { id: 14, category: 'Advertising', tags: ['Advertising'], title: 'Performance Ads Campaign', description: 'แคมเปญโฆษณาออนไลน์ที่เน้นผลลัพธ์ ครอบคลุมทุกแพลตฟอร์มหลัก เข้าถึงกลุ่มเป้าหมายได้ตรงจุด กระตุ้นยอดขายอย่างต่อเนื่อง', cover: photoStrategy },
      { id: 15, category: 'Website Development', tags: ['Website Development', 'CRM Integration'], title: 'Phufa Digital Transformation', description: 'โครงการนี้มีการปรับเปลี่ยนผ่านสู่ดิจิทัลของร้านภูฟ้า เพื่อยกระดับการบริหารจัดการทั้งช่องทางการขายออนไลน์และระบบบริหารความสัมพันธ์ลูกค้า', cover: photoTeam }
    ]

    return {
      items,
      search: '',
      sort: 'latest',
      sortOpen: false,
      sortOptions: [
        { value: 'latest', label: 'วันที่สร้างล่าสุด' },
        { value: 'oldest', label: 'วันที่สร้างเก่าสุด' },
        { value: 'views', label: 'ยอดนิยม' },
        { value: 'name-asc', label: 'เรียงตามชื่อ ก–ฮ' },
        { value: 'name-desc', label: 'เรียงตามชื่อ ฮ–ก' }
      ],
      activeCat: 'ทั้งหมด',
      filterLeft: false,
      filterRight: false,
      visible: 9,
      mascot: require('~/assets/New/Home/Character.svg'),
      ctaBg,
      handRaised,
      categories: ['ทั้งหมด', 'Business Consulting', 'Advertising', 'Content Marketing', 'Fulfillment', 'Website Development', 'LINE Official Account'],
      highlights: [
        { id: 3, title: 'Phufa Digital Transformation', description: 'โครงการนี้คือการเปลี่ยนผ่านสู่ยุคดิจิทัลของร้านภูฟ้า เพื่อยกระดับการบริหารจัดการองค์กรให้มีประสิทธิภาพยิ่งขึ้นและสอดคล้องกับพฤติกรรมผู้บริโภคในปัจจุบัน โดยมุ่งเน้นการสร้างประสบการณ์ที่ดีให้กับลูกค้าผ่านแพลตฟอร์มออนไลน์ต่างๆ', tags: ['Website Development', 'CRM Integration'], cover: photoStrategy, preview: phufaPreview },
        { id: 2, title: 'PATCONNEX LINE Messaging API', description: 'โซลูชันการสื่อสารผ่าน LINE Messaging API สำหรับ Port Authority of Thailand ที่ช่วยให้การสื่อสารรวดเร็วและมีประสิทธิภาพยิ่งขึ้น', tags: ['Website Development', 'CRM Integration'], cover: photoTeam, preview: phufaPreview }
      ],
      services: [
        { title: 'Consulting', icon: require('~/assets/SolutionsLine/customer/Icon (1).png'), description: 'ผู้ช่วยวางกลยุทธ์การตลาด เพิ่มยอดขาย ครบทุกด้าน บริการให้คำปรึกษาและทำการตลาดแบบครบวงจร เป็นผู้ช่วยธุรกิจ พร้อมผลักดันธุรกิจสู่ความสำเร็จที่ยั่งยืน', link: '/solutions/wizemoves/business-consulting' },
        { title: 'Advertising', icon: require('~/assets/SolutionsLine/customer/Icon (2).png'), description: 'ทำโฆษณาออนไลน์บน Social Media ครบทุกแพลตฟอร์ม ได้แก่ รับยิง Facebook Ads, Google Ads และ Youtube Ads รวมถึงยิง Ads ใน TikTok, LINE, X และ Instagram ให้ความแม่นยำสูง เข้าถึงกลุ่มเป้าหมายได้ตรงจุด', link: '/solutions/wizemoves' },
        { title: 'Influencer Marketing', icon: require('~/assets/SolutionsLine/customer/Icon (3).png'), description: 'บริการหาอินฟลูเอนเซอร์ ตอบโจทย์กลุ่ม เป้าหมาย คอยติดตามและวัดผลผ่านเครื่องมือ Social Listening และ Marketing Tool Visualize Data อย่างมีประสิทธิภาพ', link: '/solutions/wizemoves' },
        { title: 'Martech', icon: require('~/assets/SolutionsLine/customer/Icon (4).png'), description: 'พัฒนาเว็บไซต์ และ Tech เชื่อมต่อ ที่ทันสมัย พร้อมรองรับ Line Messaging API, CRM และ CDP เพื่อเพิ่มความน่าเชื่อถือและโอกาสในการขาย เราช่วยวิเคราะห์ข้อมูลเชิงลึก ให้คุณเข้าใจพฤติกรรมลูกค้า', link: '/solutions/wizemoves/martech' }
      ],
      chevronRight: require('~/assets/SolutionsWizemoves/customer/chevron-right.png'),
      clientLogos: [
        require('~/assets/Portfolio/Logo Client.png'),
        require('~/assets/Portfolio/Logo Client2.png'),
        require('~/assets/Portfolio/Logo Client3.png')
      ]
    }
  },
  computed: {
    filteredItems() {
      let list = this.items
      if (this.activeCat !== 'ทั้งหมด') {
        list = list.filter(i => i.category === this.activeCat)
      }
      if (this.search.trim()) {
        const q = this.search.trim().toLowerCase()
        list = list.filter(i => i.title.toLowerCase().includes(q) || i.description.toLowerCase().includes(q))
      }
      if (this.sort === 'oldest') {
        list = [...list].reverse()
      } else if (this.sort === 'name-asc') {
        list = [...list].sort((a, b) => a.title.localeCompare(b.title, 'th'))
      } else if (this.sort === 'name-desc') {
        list = [...list].sort((a, b) => b.title.localeCompare(a.title, 'th'))
      }
      return list
    },
    displayedItems() {
      return this.filteredItems.slice(0, this.visible)
    },
    currentSortLabel() {
      const o = this.sortOptions.find(o => o.value === this.sort)
      return o ? o.label : ''
    }
  },
  methods: {
    selectSort(v) {
      this.sort = v
      this.sortOpen = false
    },
    onDocClick(e) {
      if (this.$refs.sortDd && !this.$refs.sortDd.contains(e.target)) {
        this.sortOpen = false
      }
    },
    scrollFilter(dir) {
      const el = this.$refs.filterScroll
      if (!el) return
      el.scrollBy({ left: dir * 240, behavior: 'smooth' })
      setTimeout(this.updateFilterArrows, 350)
    },
    updateFilterArrows() {
      const el = this.$refs.filterScroll
      if (!el) return
      this.filterLeft = el.scrollLeft > 4
      this.filterRight = el.scrollLeft + el.clientWidth < el.scrollWidth - 4
    }
  },
  mounted() {
    document.addEventListener('click', this.onDocClick)
    this.$nextTick(this.updateFilterArrows)
    window.addEventListener('resize', this.updateFilterArrows)
    document.documentElement.classList.add('portfolio-light-scroll')
  },
  beforeDestroy() {
    document.removeEventListener('click', this.onDocClick)
    window.removeEventListener('resize', this.updateFilterArrows)
    document.documentElement.classList.remove('portfolio-light-scroll')
  }
}
</script>

<style scoped>
/* ---------- Consistent section rhythm (80px top/bottom) ---------- */
.sec-top { padding-top: 80px !important; }
.sec-bottom { padding-bottom: 80px !important; }
.gap-56 { margin-top: 56px !important; }
.cards-grid { row-gap: 56px; margin-left: -20px; margin-right: -20px; }
.cards-grid > div { padding-left: 20px; padding-right: 20px; }

/* ---------- Hero (full width) ---------- */
.hero-fullwidth {
  position: relative;
  width: 100vw;
  left: 50%;
  right: 50%;
  margin-left: -50vw;
  margin-right: -50vw;
  margin-top: -24px;
}
.hero-banner {
  position: relative;
  overflow: hidden;
  height: 550px;
  background-size: cover;
  background-position: center;
}
.hero-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(90deg, rgba(9, 25, 58, 0.9) 0%, rgba(9, 25, 58, 0.6) 50%, rgba(9, 25, 58, 0.25) 100%);
}
.hero-inner {
  position: relative;
  z-index: 2;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.hero-content {
  max-width: 58%;
}
.hero-content h1 {
  white-space: nowrap;
}
.hero-textblock {
  height: 342px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.hero-desc {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
.hero-preview {
  width: 540px;
  flex-shrink: 0;
  transform: translateY(60px);
}
/* dots overlaid at bottom center of hero */
.hero-fullwidth >>> .ssr-carousel-dots {
  position: absolute;
  bottom: 18px;
  left: 0;
  right: 0;
  z-index: 3;
}
.browser-shot {
  display: block;
  width: 540px;
  height: auto;
}
.hero-tag {
  display: inline-flex;
  align-items: center;
  background-color: #F5F3FF1A;
  border: 1px solid #DDD6FE33;
  color: #FFFFFF !important;
  border-radius: 999px;
  padding: 4px 16px 4px 10px;
  font-size: 20px;
  font-weight: 500;
  line-height: 1;
}
.hero-tag-ico { width: 16px; height: 16px; margin-right: 6px; }
.btn-hero {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: #FFFFFF;
  color: #1F2937 !important;
  border-radius: 999px;
  padding: 8px 18px;
  line-height: 1;
}
.btn-hero i {
  display: inline-flex;
  align-items: center;
  position: relative;
  top: 0;
}
.svc-cta, .svc-cta p { color: #1F2937 !important; }
@media (max-width: 991px) {
  .hero-banner { height: 340px; }
  .hero-content { max-width: 90%; }
}

/* Match this page's margins to the portfolio detail page (which uses plain
   Bootstrap container widths). #Portfolios is itself a .container and inherits
   the layout scope's wider custom widths (1100/1200/1400/1440), so force it
   back to Bootstrap defaults. hero-inner (inside ssr-carousel) already gets the
   Bootstrap defaults, so both align with each other and with the detail page. */
@media (min-width: 768px)  { #Portfolios.container { max-width: 720px !important; } }
@media (min-width: 992px)  { #Portfolios.container { max-width: 960px !important; } }
@media (min-width: 1200px) { #Portfolios.container { max-width: 1140px !important; } }
@media (min-width: 1400px) { #Portfolios.container { max-width: 1320px !important; } }

/* ---------- Search ---------- */
.search-form {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 16px;
}
.search-box {
  display: flex;
  align-items: center;
  width: 358px;
  max-width: 100%;
  height: 44px;
  box-sizing: border-box;
  border: 1px solid #E5E7EB;
  border-radius: 8px;
  background: #FFF;
  padding: 0 6px 0 12px;
}
.search-icon {
  font-size: 24px;
  line-height: 1;
  margin-right: 16px;
  flex-shrink: 0;
}
.search-input {
  border: none;
  outline: none;
  flex: 1;
  min-width: 0;
  font-size: 24px;
  padding: 0;
  background: transparent;
}
.search-submit {
  border: none;
  background: #2DA3FD;
  color: #FFF;
  border-radius: 8px;
  height: 44px;
  padding: 0 28px;
  font-size: 24px;
}
::placeholder { color: #9CA3AF !important; }

/* Card badges: use the brand blue (#2DA3FD / #EBF8FF / #B3E6FF) consistently
   with the active tab + links, matching the mockup, instead of tag-blog-1's
   indigo. Give them the chip padding shown in the mockup. */
.port-card .tag-blog-1 {
  background: #EBF8FF !important;
  border: 1px solid #B3E6FF !important;
  color: #2DA3FD !important;
  padding: 4px 16px;
  font-size: 20px !important;
  font-weight: 500;
  font-family: 'Heavent' !important;
  line-height: 1 !important;
}

/* ---------- Filters ---------- */
.filter-row {
  display: flex;
  align-items: center;
  gap: 40px;
  position: relative;
  z-index: 20;
}
.filter-scroll-wrap {
  position: relative;
  flex: 1 1 auto;
  min-width: 0;
}
.filter-scroll {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  gap: 0;
  overflow-x: auto;
  scrollbar-width: none;
  width: 100%;
}
.filter-scroll::-webkit-scrollbar { display: none; }
.filter-pill { white-space: nowrap; }
.filter-chevron {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: 24px;
  height: 24px;
  cursor: pointer;
  z-index: 999;
}
.filter-chevron-l { left: -8px; }
.filter-chevron-r { right: -8px; }
.sort-wrap { flex-shrink: 0; }
@media (max-width: 991px) {
  .filter-row { flex-direction: column; align-items: stretch; gap: 16px; }
}
.sort-dd { position: relative; display: inline-block; text-align: left; }
.sort-trigger {
  display: inline-flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
  min-width: 210px;
  border: 1px solid #E5E7EB;
  border-radius: 12px;
  background: #FFF;
  color: #1F2937;
  padding: 10px 16px;
  cursor: pointer;
}
.sort-trigger i { font-size: 14px; }
.sort-menu {
  position: absolute;
  z-index: 30;
  left: 0;
  right: 0;
  margin-top: 8px;
  list-style: none;
  padding: 8px;
  background: #FFF;
  border: 1px solid #F3F4F6;
  border-radius: 12px;
  box-shadow: 0px 12px 24px rgba(17, 24, 39, 0.12);
  max-height: 220px;
  overflow-y: auto;
}
.sort-option {
  padding: 12px 14px;
  border-radius: 8px;
  color: #1F2937;
  cursor: pointer;
  white-space: nowrap;
}
.sort-option:hover { background: #F9FAFB; }

/* ---------- Cards ---------- */
.card {
  background: #FFFFFF !important;
  box-shadow: 0px 1px 2px 0px rgba(17, 24, 39, 0.07), 0px 3px 3px 0px rgba(17, 24, 39, 0.05), 0px 7px 4px 0px rgba(17, 24, 39, 0.03);
  border-radius: 12px !important;
  border: 1px solid #E5E7EB;
}
.card.port-card { background: #F9FAFB !important; border: 1px solid #E5E7EB !important; }

/* ---------- Card media (image + overlay + logo lockup) ---------- */
.card-media {
  position: relative;
  width: 100%;
  aspect-ratio: 453 / 300;
  overflow: hidden;
  border-top-left-radius: 12px;
  border-top-right-radius: 12px;
}
.card-media-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}
.card-media-overlay {
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0.5);
}
.card-media-badge {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 2;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  padding: 0 24px;
}
.cmb-client-logo {
  width: 200px;
  max-width: 80%;
  height: auto;
  object-fit: contain;
  display: block;
}
.card.port-card:hover {
  box-shadow: 0px 12px 24px rgba(17, 24, 39, 0.12);
  transform: translateY(-2px);
  transition: all .2s ease;
}
.card-title {
  font-family: 'Heavent-med' !important;
  line-height: 42px;
}
.card-body { min-height: 210px; padding: 20px; }
.img-fix-size {
  width: 100%;
  height: 200px;
  object-fit: cover;
  border-top-left-radius: 12px;
  border-top-right-radius: 12px;
}
.text-limit-2 {
  overflow: hidden; text-overflow: ellipsis; display: -webkit-box;
  -webkit-line-clamp: 2; -webkit-box-orient: vertical;
}
.text-limit-3 {
  overflow: hidden; text-overflow: ellipsis; display: -webkit-box;
  -webkit-line-clamp: 3; -webkit-box-orient: vertical;
}
.card-cta {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  color: #1F2937;
  transition: transform .2s ease;
}
.card-cta-ico {
  width: 20px;
  height: 20px;
}
.port-card:hover .card-cta {
  transform: translateX(4px);
}

/* ---------- Load more ---------- */
.btn-view {
  border: 1px solid #E5E7EB;
  background: #FFFFFF;
  border-radius: 999px !important;
  width: 144px;
  height: 48px;
  padding: 0;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: all .2s ease;
}
.btn-view:hover { background: #F9FAFB; border-color: #D1D5DB; }
.btn-view span { color: #374151; font-size: 28px; font-weight: 500; }

/* ---------- Dots ---------- */
.dot-carousel-active {
  width: 32px; height: 8px; background-color: rgba(255, 255, 255, 1);
  border-radius: 21px; margin: 20px 5px;
}
.dot-carousel {
  width: 24px; height: 8px; background-color: rgba(255, 255, 255, 0.5);
  border-radius: 21px; margin: 20px 5px;
}

/* ---------- CTA ---------- */
/* ---------- CTA: reuse Home CardContact section ---------- */
.cta-cardcontact ::v-deep .container {
  padding-left: 0;
  padding-right: 0;
  max-width: 100%;
}

/* ---------- Service cards (ported from Wizemoves CardContact) ---------- */
.last .card {
  height: 100%;
  background: #fff !important;
  border: 1px solid #e5e7eb !important;
  border-radius: 16px !important;
  box-shadow: 0px 1px 3px 0px #6783bc12, 0px 5px 5px 0px #6783bc0f,
    0px 12px 7px 0px #6783bc0a, 0px 20px 8px 0px #6783bc03,
    0px 32px 9px 0px #6783bc00;
}
.last .card-body { padding: 24px; }
</style>

<!-- Lighter page scrollbar (only while on the portfolio list page) -->
<style>
html.portfolio-light-scroll {
  scrollbar-width: thin;
  scrollbar-color: #E5E7EB transparent;
}
html.portfolio-light-scroll::-webkit-scrollbar {
  width: 10px;
  height: 10px;
}
html.portfolio-light-scroll::-webkit-scrollbar-track {
  background: transparent;
}
html.portfolio-light-scroll::-webkit-scrollbar-thumb {
  background-color: #E5E7EB;
  border-radius: 999px;
  border: 2px solid transparent;
  background-clip: content-box;
}
html.portfolio-light-scroll::-webkit-scrollbar-thumb:hover {
  background-color: #D1D5DB;
}
</style>
