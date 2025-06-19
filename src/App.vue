<template>
  <div class="min-h-screen bg-gradient-to-br from-slate-900 via-purple-900 to-slate-900">
    <!-- 导航栏 -->
    <nav class="fixed top-0 w-full z-50 bg-black/20 backdrop-blur-md border-b border-white/10">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-16">
          <div class="flex items-center">
            <Globe class="h-8 w-8 text-blue-400 mr-3" />
            <span class="text-xl font-bold text-white">跨境电商</span>
          </div>
          <div class="hidden md:flex space-x-8">
            <a href="#advantages" class="text-gray-300 hover:text-white transition-colors duration-300">核心优势</a>
            <a href="#business" class="text-gray-300 hover:text-white transition-colors duration-300">业务矩阵</a>
            <a href="#milestones" class="text-gray-300 hover:text-white transition-colors duration-300">里程碑</a>
            <a href="#vision" class="text-gray-300 hover:text-white transition-colors duration-300">使命愿景</a>
          </div>
          <button @click="toggleMobileMenu" class="md:hidden text-white">
            <Menu class="h-6 w-6" />
          </button>
        </div>
      </div>
      
      <!-- 移动端菜单 -->
      <div v-if="mobileMenuOpen" class="md:hidden bg-black/90 backdrop-blur-md">
        <div class="px-2 pt-2 pb-3 space-y-1">
          <a @click="scrollToSection('advantages')" class="block px-3 py-2 text-gray-300 hover:text-white cursor-pointer">核心优势</a>
          <a @click="scrollToSection('business')" class="block px-3 py-2 text-gray-300 hover:text-white cursor-pointer">业务矩阵</a>
          <a @click="scrollToSection('milestones')" class="block px-3 py-2 text-gray-300 hover:text-white cursor-pointer">里程碑</a>
          <a @click="scrollToSection('vision')" class="block px-3 py-2 text-gray-300 hover:text-white cursor-pointer">使命愿景</a>
        </div>
      </div>
    </nav>

    <!-- 点击外部关闭移动端菜单的遮罩 -->
    <div v-if="mobileMenuOpen" @click="closeMobileMenu" class="fixed inset-0 z-40 md:hidden"></div>

    <!-- 英雄区域 -->
    <section class="pt-32 pb-20 px-4 sm:px-6 lg:px-8">
      <div class="max-w-7xl mx-auto text-center">
        <h1 class="text-5xl md:text-7xl font-bold text-white mb-6 animate-fade-in-up">
          全球跨境电商
          <span class="bg-gradient-to-r from-blue-400 to-purple-400 bg-clip-text text-transparent">
            领航者
          </span>
        </h1>
        <p class="text-xl md:text-2xl text-gray-300 mb-12 animate-fade-in-up animation-delay-300">
          构建下一代跨境电商基础设施，让全球贸易更简单
        </p>
        <div class="flex flex-col sm:flex-row gap-4 justify-center animate-fade-in-up animation-delay-600">
          <button @click="scrollToSection('business')" class="px-8 py-4 bg-gradient-to-r from-blue-500 to-purple-600 text-white rounded-lg font-semibold hover:shadow-lg hover:shadow-blue-500/25 transition-all duration-300 transform hover:scale-105">
            开始合作
          </button>
          <button @click="scrollToSection('milestones')" class="px-8 py-4 border border-white/20 text-white rounded-lg font-semibold hover:bg-white/10 transition-all duration-300">
            了解更多
          </button>
        </div>
      </div>
    </section>

    <!-- 核心优势 -->
    <section id="advantages" class="py-20 px-4 sm:px-6 lg:px-8">
      <div class="max-w-7xl mx-auto">
        <div class="text-center mb-16">
          <h2 class="text-4xl md:text-5xl font-bold text-white mb-4">核心优势</h2>
          <p class="text-xl text-gray-300">四大核心能力，助力您的全球化征程</p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div v-for="(advantage, index) in advantages" :key="index" 
               class="group bg-gradient-to-br from-white/10 to-white/5 backdrop-blur-sm rounded-2xl p-6 border border-white/10 hover:border-blue-400/50 transition-all duration-500 hover:transform hover:scale-105 hover:shadow-xl hover:shadow-blue-500/20">
            <div class="mb-4">
              <component :is="advantage.icon" class="h-12 w-12 text-blue-400 group-hover:text-blue-300 transition-colors duration-300" />
            </div>
            <h3 class="text-xl font-bold text-white mb-3">{{ advantage.title }}</h3>
            <p class="text-gray-300 leading-relaxed">{{ advantage.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- 业务矩阵 -->
    <section id="business" class="py-20 px-4 sm:px-6 lg:px-8 bg-gradient-to-r from-purple-900/20 to-blue-900/20">
      <div class="max-w-7xl mx-auto">
        <div class="text-center mb-16">
          <h2 class="text-4xl md:text-5xl font-bold text-white mb-4">业务矩阵</h2>
          <p class="text-xl text-gray-300">多元化业务模式，满足不同需求</p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div v-for="(business, index) in businessMatrix" :key="index"
               class="group bg-gradient-to-br from-white/10 to-white/5 backdrop-blur-sm rounded-2xl p-8 border border-white/10 hover:border-purple-400/50 transition-all duration-500 hover:transform hover:scale-105">
            <div class="mb-6">
              <component :is="business.icon" class="h-16 w-16 text-purple-400 group-hover:text-purple-300 transition-colors duration-300 mx-auto" />
            </div>
            <h3 class="text-2xl font-bold text-white mb-4 text-center">{{ business.title }}</h3>
            <p class="text-gray-300 text-center leading-relaxed mb-4">{{ business.description }}</p>
            <div class="space-y-2">
              <div v-for="mode in business.modes" :key="mode" 
                   class="text-sm text-blue-300 bg-blue-500/10 rounded-full px-3 py-1 text-center">
                {{ mode }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- 里程碑 -->
    <section id="milestones" class="py-20 px-4 sm:px-6 lg:px-8">
      <div class="max-w-7xl mx-auto">
        <div class="text-center mb-16">
          <h2 class="text-4xl md:text-5xl font-bold text-white mb-4">发展里程碑</h2>
          <p class="text-xl text-gray-300">见证我们的成长历程</p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div v-for="(milestone, index) in milestones" :key="index"
               class="group text-center bg-gradient-to-br from-white/10 to-white/5 backdrop-blur-sm rounded-2xl p-8 border border-white/10 hover:border-yellow-400/50 transition-all duration-500 hover:transform hover:scale-105">
            <div class="mb-6">
              <component :is="milestone.icon" class="h-20 w-20 text-yellow-400 group-hover:text-yellow-300 transition-colors duration-300 mx-auto" />
            </div>
            <h3 class="text-3xl font-bold text-white mb-2">{{ milestone.value }}</h3>
            <p class="text-lg text-gray-300 font-semibold mb-3">{{ milestone.title }}</p>
            <p class="text-gray-400">{{ milestone.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- 使命愿景 -->
    <section id="vision" class="py-20 px-4 sm:px-6 lg:px-8 bg-gradient-to-r from-blue-900/20 to-purple-900/20">
      <div class="max-w-4xl mx-auto text-center">
        <div class="mb-12">
          <Target class="h-20 w-20 text-blue-400 mx-auto mb-6" />
          <h2 class="text-4xl md:text-5xl font-bold text-white mb-8">使命愿景</h2>
        </div>
        
        <div class="bg-gradient-to-br from-white/10 to-white/5 backdrop-blur-sm rounded-3xl p-12 border border-white/10">
          <blockquote class="text-2xl md:text-3xl font-bold text-white mb-8 leading-relaxed">
            "让全球贸易更简单，成为下一代跨境电商基础设施的构建者！"
          </blockquote>
          <p class="text-lg text-gray-300 leading-relaxed">
            我们致力于通过创新技术和优质服务，为全球商家提供最完善的跨境电商解决方案，
            打破贸易壁垒，连接世界各地的消费者与优质商品，推动全球商业的数字化转型。
          </p>
        </div>
      </div>
    </section>

    <!-- 页脚 -->
    <footer class="py-12 px-4 sm:px-6 lg:px-8 border-t border-white/10">
      <div class="max-w-7xl mx-auto text-center">
        <div class="flex items-center justify-center mb-6">
          <Globe class="h-8 w-8 text-blue-400 mr-3" />
          <span class="text-xl font-bold text-white">跨境电商</span>
        </div>
        <p class="text-gray-400 mb-4">© 2024 跨境电商平台. 保留所有权利.</p>
        <div class="flex justify-center space-x-6">
          <a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">
            <Mail class="h-5 w-5" />
          </a>
          <a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">
            <Phone class="h-5 w-5" />
          </a>
          <a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">
            <MapPin class="h-5 w-5" />
          </a>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'
import { 
  Globe, 
  Menu, 
  Zap, 
  Brain, 
  Truck, 
  Users, 
  Store, 
  Package, 
  Sparkles,
  Award,
  DollarSign,
  MapPin as MapPinIcon,
  Target,
  Mail,
  Phone,
  MapPin
} from 'lucide-vue-next'

// 响应式数据
const mobileMenuOpen = ref(false)

// 核心优势数据
const advantages = ref([
  {
    icon: Zap,
    title: '全链路服务',
    description: '覆盖选品采购、跨境支付、关务合规、海外仓储（XX国本土仓）、品牌营销等全流程'
  },
  {
    icon: Brain,
    title: '智能基建',
    description: '自建AI大数据选品平台，实时分析全球56个市场消费趋势'
  },
  {
    icon: Truck,
    title: '极速物流',
    description: '合作30个家国际承运商，欧美核心市场7日达妥投率超98%'
  },
  {
    icon: Users,
    title: '本地化团队',
    description: '在20个国家设立运营中心，提供多语言客服与本土营销支持'
  }
])

// 业务矩阵数据
const businessMatrix = ref([
  {
    icon: Store,
    title: 'B2C旗舰平台',
    description: '直面消费者的零售平台',
    modes: ['B2C零售模式']
  },
  {
    icon: Package,
    title: 'B2B供应链',
    description: '企业级供应链解决方案',
    modes: ['S2B(S2b2C)模式', 'B2B分销模式']
  },
  {
    icon: Sparkles,
    title: '品牌孵化',
    description: '多商家平台生态',
    modes: ['B2B2C多用户（多商家）模式']
  }
])

// 里程碑数据
const milestones = ref([
  {
    icon: Award,
    value: '福布斯',
    title: '亚洲高增长企业',
    description: '2023年入选福布斯亚洲高增长企业榜单'
  },
  {
    icon: DollarSign,
    value: '30亿',
    title: '美元GMV',
    description: '年跨境GMV突破30亿美元大关'
  },
  {
    icon: MapPinIcon,
    value: '86个',
    title: '国家地区',
    description: '业务覆盖全球86个国家和地区'
  }
])

// 方法
const toggleMobileMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value
}

const scrollToSection = (sectionId: string) => {
  const element = document.getElementById(sectionId)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}

const closeMobileMenu = () => {
  mobileMenuOpen.value = false
}

// 生命周期
onMounted(() => {
  // 添加滚动动画观察器
  const observerOptions = {
    threshold: 0.1,
    rootMargin: '0px 0px -50px 0px'
  }

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('animate-fade-in-up')
      }
    })
  }, observerOptions)

  // 观察所有需要动画的元素
  document.querySelectorAll('.group').forEach(el => {
    observer.observe(el)
  })
})
</script>

<style scoped>
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in-up {
  animation: fadeInUp 0.8s ease-out forwards;
}

.animation-delay-300 {
  animation-delay: 0.3s;
}

.animation-delay-600 {
  animation-delay: 0.6s;
}

/* 自定义滚动条 */
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  background: rgba(0, 0, 0, 0.1);
}

::-webkit-scrollbar-thumb {
  background: rgba(59, 130, 246, 0.5);
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: rgba(59, 130, 246, 0.7);
}

/* 平滑滚动 */
html {
  scroll-behavior: smooth;
}

/* 响应式字体 */
@media (max-width: 640px) {
  .text-5xl {
    font-size: 2.5rem;
  }
  .text-7xl {
    font-size: 3.5rem;
  }
}
</style>