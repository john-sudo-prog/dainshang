<template>
  <div class="min-h-screen bg-gradient-to-br from-blue-50 via-white to-green-50">
    <!-- 导航栏 -->
    <nav class="fixed top-0 w-full z-50 bg-white/80 backdrop-blur-md border-b border-gray-100 shadow-sm">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between items-center h-16">
          <div class="flex items-center">
            <div class="w-10 h-10 bg-gradient-to-r from-blue-500 to-green-500 rounded-xl flex items-center justify-center mr-3">
              <Globe class="h-6 w-6 text-white" />
            </div>
            <span class="text-xl font-bold bg-gradient-to-r from-blue-600 to-green-600 bg-clip-text text-transparent">跨境电商</span>
          </div>
          <div class="hidden md:flex space-x-8">
            <a href="#advantages" class="text-gray-600 hover:text-blue-600 transition-colors duration-300 font-medium">核心优势</a>
            <a href="#business" class="text-gray-600 hover:text-green-600 transition-colors duration-300 font-medium">业务矩阵</a>
            <a href="#milestones" class="text-gray-600 hover:text-purple-600 transition-colors duration-300 font-medium">里程碑</a>
            <a href="#vision" class="text-gray-600 hover:text-indigo-600 transition-colors duration-300 font-medium">使命愿景</a>
          </div>
          <button @click="toggleMobileMenu" class="md:hidden text-gray-600 hover:text-blue-600">
            <Menu class="h-6 w-6" />
          </button>
        </div>
      </div>
      
      <!-- 移动端菜单 -->
      <div v-if="mobileMenuOpen" class="md:hidden bg-white/95 backdrop-blur-md border-t border-gray-100">
        <div class="px-4 pt-2 pb-3 space-y-1">
          <a href="#advantages" class="block px-3 py-2 text-gray-600 hover:text-blue-600 rounded-lg hover:bg-blue-50">核心优势</a>
          <a href="#business" class="block px-3 py-2 text-gray-600 hover:text-green-600 rounded-lg hover:bg-green-50">业务矩阵</a>
          <a href="#milestones" class="block px-3 py-2 text-gray-600 hover:text-purple-600 rounded-lg hover:bg-purple-50">里程碑</a>
          <a href="#vision" class="block px-3 py-2 text-gray-600 hover:text-indigo-600 rounded-lg hover:bg-indigo-50">使命愿景</a>
        </div>
      </div>
    </nav>

    <!-- 英雄区域 -->
    <section class="pt-32 pb-20 px-4 sm:px-6 lg:px-8">
      <div class="max-w-7xl mx-auto text-center">
        <div class="mb-8 animate-fade-in-up">
          <div class="inline-flex items-center px-4 py-2 bg-gradient-to-r from-blue-100 to-green-100 rounded-full text-sm font-medium text-blue-700 mb-6">
            <Sparkles class="h-4 w-4 mr-2" />
            全球跨境电商领航者
          </div>
        </div>
        <h1 class="text-5xl md:text-7xl font-bold text-gray-800 mb-6 animate-fade-in-up animation-delay-200">
          让全球贸易
          <span class="bg-gradient-to-r from-blue-600 via-green-500 to-teal-500 bg-clip-text text-transparent">
            更简单
          </span>
        </h1>
        <p class="text-xl md:text-2xl text-gray-600 mb-12 max-w-3xl mx-auto leading-relaxed animate-fade-in-up animation-delay-400">
          构建下一代跨境电商基础设施，连接全球86个国家，助力您的商业梦想扬帆起航
        </p>
        <div class="flex flex-col sm:flex-row gap-4 justify-center animate-fade-in-up animation-delay-600">
          <button class="px-8 py-4 bg-gradient-to-r from-blue-500 to-green-500 text-white rounded-2xl font-semibold hover:shadow-lg hover:shadow-blue-500/25 transition-all duration-300 transform hover:scale-105 hover:-translate-y-1">
            开始合作
          </button>
          <button class="px-8 py-4 bg-white border-2 border-gray-200 text-gray-700 rounded-2xl font-semibold hover:border-blue-300 hover:bg-blue-50 transition-all duration-300 transform hover:scale-105">
            了解更多
          </button>
        </div>
      </div>
    </section>

    <!-- 核心优势 -->
    <section id="advantages" class="py-20 px-4 sm:px-6 lg:px-8 bg-gradient-to-r from-blue-50/50 to-green-50/50">
      <div class="max-w-7xl mx-auto">
        <div class="text-center mb-16">
          <div class="inline-flex items-center px-4 py-2 bg-blue-100 rounded-full text-sm font-medium text-blue-700 mb-4">
            <Star class="h-4 w-4 mr-2" />
            核心优势
          </div>
          <h2 class="text-4xl md:text-5xl font-bold text-gray-800 mb-4">四大核心能力</h2>
          <p class="text-xl text-gray-600 max-w-2xl mx-auto">专业团队 × 智能技术 × 全球网络 = 您的成功伙伴</p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div v-for="(advantage, index) in advantages" :key="index" 
               class="group bg-white rounded-3xl p-8 shadow-sm hover:shadow-xl border border-gray-100 hover:border-blue-200 transition-all duration-500 hover:transform hover:scale-105 hover:-translate-y-2">
            <div class="mb-6">
              <div :class="advantage.bgColor" class="w-16 h-16 rounded-2xl flex items-center justify-center mb-4 group-hover:scale-110 transition-transform duration-300">
                <component :is="advantage.icon" :class="advantage.iconColor" class="h-8 w-8" />
              </div>
            </div>
            <h3 class="text-xl font-bold text-gray-800 mb-3">{{ advantage.title }}</h3>
            <p class="text-gray-600 leading-relaxed">{{ advantage.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- 业务矩阵 -->
    <section id="business" class="py-20 px-4 sm:px-6 lg:px-8">
      <div class="max-w-7xl mx-auto">
        <div class="text-center mb-16">
          <div class="inline-flex items-center px-4 py-2 bg-green-100 rounded-full text-sm font-medium text-green-700 mb-4">
            <Grid3x3 class="h-4 w-4 mr-2" />
            业务矩阵
          </div>
          <h2 class="text-4xl md:text-5xl font-bold text-gray-800 mb-4">多元化业务模式</h2>
          <p class="text-xl text-gray-600 max-w-2xl mx-auto">从B2C到B2B，从零售到供应链，全方位满足您的需求</p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div v-for="(business, index) in businessMatrix" :key="index"
               class="group bg-white rounded-3xl p-8 shadow-sm hover:shadow-xl border border-gray-100 hover:border-green-200 transition-all duration-500 hover:transform hover:scale-105 hover:-translate-y-2">
            <div class="mb-6">
              <div :class="business.bgColor" class="w-20 h-20 rounded-2xl flex items-center justify-center mx-auto mb-4 group-hover:scale-110 transition-transform duration-300">
                <component :is="business.icon" :class="business.iconColor" class="h-10 w-10" />
              </div>
            </div>
            <h3 class="text-2xl font-bold text-gray-800 mb-4 text-center">{{ business.title }}</h3>
            <p class="text-gray-600 text-center leading-relaxed mb-6">{{ business.description }}</p>
            <div class="space-y-2">
              <div v-for="mode in business.modes" :key="mode" 
                   :class="business.tagColor"
                   class="text-sm rounded-full px-4 py-2 text-center font-medium">
                {{ mode }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- 里程碑 -->
    <section id="milestones" class="py-20 px-4 sm:px-6 lg:px-8 bg-gradient-to-r from-purple-50/50 to-pink-50/50">
      <div class="max-w-7xl mx-auto">
        <div class="text-center mb-16">
          <div class="inline-flex items-center px-4 py-2 bg-purple-100 rounded-full text-sm font-medium text-purple-700 mb-4">
            <Trophy class="h-4 w-4 mr-2" />
            发展里程碑
          </div>
          <h2 class="text-4xl md:text-5xl font-bold text-gray-800 mb-4">见证成长历程</h2>
          <p class="text-xl text-gray-600 max-w-2xl mx-auto">每一个数字背后，都是我们与合作伙伴共同创造的价值</p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div v-for="(milestone, index) in milestones" :key="index"
               class="group text-center bg-white rounded-3xl p-8 shadow-sm hover:shadow-xl border border-gray-100 hover:border-purple-200 transition-all duration-500 hover:transform hover:scale-105 hover:-translate-y-2">
            <div class="mb-6">
              <div :class="milestone.bgColor" class="w-24 h-24 rounded-2xl flex items-center justify-center mx-auto mb-4 group-hover:scale-110 transition-transform duration-300">
                <component :is="milestone.icon" :class="milestone.iconColor" class="h-12 w-12" />
              </div>
            </div>
            <h3 class="text-4xl font-bold text-gray-800 mb-2">{{ milestone.value }}</h3>
            <p class="text-lg text-gray-700 font-semibold mb-3">{{ milestone.title }}</p>
            <p class="text-gray-600 leading-relaxed">{{ milestone.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- 使命愿景 -->
    <section id="vision" class="py-20 px-4 sm:px-6 lg:px-8">
      <div class="max-w-4xl mx-auto text-center">
        <div class="mb-12">
          <div class="inline-flex items-center px-4 py-2 bg-indigo-100 rounded-full text-sm font-medium text-indigo-700 mb-6">
            <Target class="h-4 w-4 mr-2" />
            使命愿景
          </div>
          <h2 class="text-4xl md:text-5xl font-bold text-gray-800 mb-8">我们的使命</h2>
        </div>
        
        <div class="bg-white rounded-3xl p-12 shadow-lg border border-gray-100 hover:shadow-xl transition-all duration-500">
          <div class="w-20 h-20 bg-gradient-to-r from-indigo-500 to-purple-500 rounded-2xl flex items-center justify-center mx-auto mb-8">
            <Rocket class="h-10 w-10 text-white" />
          </div>
          <blockquote class="text-2xl md:text-3xl font-bold text-gray-800 mb-8 leading-relaxed">
            "让全球贸易更简单，成为下一代跨境电商基础设施的构建者！"
          </blockquote>
          <p class="text-lg text-gray-600 leading-relaxed max-w-3xl mx-auto">
            我们致力于通过创新技术和优质服务，为全球商家提供最完善的跨境电商解决方案，
            打破贸易壁垒，连接世界各地的消费者与优质商品，推动全球商业的数字化转型。
          </p>
        </div>
      </div>
    </section>

    <!-- 页脚 -->
    <footer class="py-16 px-4 sm:px-6 lg:px-8 bg-gray-50 border-t border-gray-100">
      <div class="max-w-7xl mx-auto">
        <div class="text-center mb-8">
          <div class="flex items-center justify-center mb-6">
            <div class="w-12 h-12 bg-gradient-to-r from-blue-500 to-green-500 rounded-xl flex items-center justify-center mr-3">
              <Globe class="h-7 w-7 text-white" />
            </div>
            <span class="text-2xl font-bold bg-gradient-to-r from-blue-600 to-green-600 bg-clip-text text-transparent">跨境电商</span>
          </div>
          <p class="text-gray-500 mb-6">连接全球，成就未来</p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-4 gap-8 mb-8">
          <div class="text-center md:text-left">
            <h4 class="font-semibold text-gray-800 mb-4">产品服务</h4>
            <ul class="space-y-2 text-gray-600">
              <li><a href="#" class="hover:text-blue-600 transition-colors">跨境支付</a></li>
              <li><a href="#" class="hover:text-blue-600 transition-colors">海外仓储</a></li>
              <li><a href="#" class="hover:text-blue-600 transition-colors">品牌营销</a></li>
            </ul>
          </div>
          <div class="text-center md:text-left">
            <h4 class="font-semibold text-gray-800 mb-4">解决方案</h4>
            <ul class="space-y-2 text-gray-600">
              <li><a href="#" class="hover:text-green-600 transition-colors">B2C平台</a></li>
              <li><a href="#" class="hover:text-green-600 transition-colors">B2B供应链</a></li>
              <li><a href="#" class="hover:text-green-600 transition-colors">品牌孵化</a></li>
            </ul>
          </div>
          <div class="text-center md:text-left">
            <h4 class="font-semibold text-gray-800 mb-4">关于我们</h4>
            <ul class="space-y-2 text-gray-600">
              <li><a href="#" class="hover:text-purple-600 transition-colors">公司介绍</a></li>
              <li><a href="#" class="hover:text-purple-600 transition-colors">团队介绍</a></li>
              <li><a href="#" class="hover:text-purple-600 transition-colors">加入我们</a></li>
            </ul>
          </div>
          <div class="text-center md:text-left">
            <h4 class="font-semibold text-gray-800 mb-4">联系我们</h4>
            <div class="space-y-3">
              <div class="flex items-center justify-center md:justify-start text-gray-600">
                <Mail class="h-4 w-4 mr-2" />
                <span class="text-sm">contact@example.com</span>
              </div>
              <div class="flex items-center justify-center md:justify-start text-gray-600">
                <Phone class="h-4 w-4 mr-2" />
                <span class="text-sm">+86 400-123-4567</span>
              </div>
            </div>
          </div>
        </div>
        
        <div class="border-t border-gray-200 pt-8 text-center">
          <p class="text-gray-500">© 2024 跨境电商平台. 保留所有权利.</p>
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
  Sparkles,
  Star,
  Grid3x3,
  Trophy,
  Target,
  Rocket,
  Zap, 
  Brain, 
  Truck, 
  Users, 
  Store, 
  Package, 
  Award,
  DollarSign,
  MapPin,
  Mail,
  Phone
} from 'lucide-vue-next'

// 响应式数据
const mobileMenuOpen = ref(false)

// 核心优势数据
const advantages = ref([
  {
    icon: Zap,
    title: '全链路服务',
    description: '覆盖选品采购、跨境支付、关务合规、海外仓储（XX国本土仓）、品牌营销等全流程',
    bgColor: 'bg-blue-100',
    iconColor: 'text-blue-600'
  },
  {
    icon: Brain,
    title: '智能基建',
    description: '自建AI大数据选品平台，实时分析全球56个市场消费趋势',
    bgColor: 'bg-green-100',
    iconColor: 'text-green-600'
  },
  {
    icon: Truck,
    title: '极速物流',
    description: '合作30个家国际承运商，欧美核心市场7日达妥投率超98%',
    bgColor: 'bg-purple-100',
    iconColor: 'text-purple-600'
  },
  {
    icon: Users,
    title: '本地化团队',
    description: '在20个国家设立运营中心，提供多语言客服与本土营销支持',
    bgColor: 'bg-orange-100',
    iconColor: 'text-orange-600'
  }
])

// 业务矩阵数据
const businessMatrix = ref([
  {
    icon: Store,
    title: 'B2C旗舰平台',
    description: '直面消费者的零售平台，提供完整的购物体验',
    modes: ['B2C零售模式'],
    bgColor: 'bg-blue-100',
    iconColor: 'text-blue-600',
    tagColor: 'text-blue-700 bg-blue-100'
  },
  {
    icon: Package,
    title: 'B2B供应链',
    description: '企业级供应链解决方案，连接供应商与分销商',
    modes: ['S2B(S2b2C)模式', 'B2B分销模式'],
    bgColor: 'bg-green-100',
    iconColor: 'text-green-600',
    tagColor: 'text-green-700 bg-green-100'
  },
  {
    icon: Sparkles,
    title: '品牌孵化',
    description: '多商家平台生态，助力品牌成长与发展',
    modes: ['B2B2C多用户（多商家）模式'],
    bgColor: 'bg-purple-100',
    iconColor: 'text-purple-600',
    tagColor: 'text-purple-700 bg-purple-100'
  }
])

// 里程碑数据
const milestones = ref([
  {
    icon: Award,
    value: '福布斯',
    title: '亚洲高增长企业',
    description: '2023年入选福布斯亚洲高增长企业榜单',
    bgColor: 'bg-yellow-100',
    iconColor: 'text-yellow-600'
  },
  {
    icon: DollarSign,
    value: '30亿',
    title: '美元GMV',
    description: '年跨境GMV突破30亿美元大关',
    bgColor: 'bg-green-100',
    iconColor: 'text-green-600'
  },
  {
    icon: MapPin,
    value: '86个',
    title: '国家地区',
    description: '业务覆盖全球86个国家和地区',
    bgColor: 'bg-blue-100',
    iconColor: 'text-blue-600'
  }
])

// 方法
const toggleMobileMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value
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

.animation-delay-200 {
  animation-delay: 0.2s;
}

.animation-delay-400 {
  animation-delay: 0.4s;
}

.animation-delay-600 {
  animation-delay: 0.6s;
}

/* 自定义滚条 */
::-webkit-scrollbar {
  width: 6px;
}

::-webkit-scrollbar-track {
  background: #f1f5f9;
}

::-webkit-scrollbar-thumb {
  background: linear-gradient(to bottom, #3b82f6, #10b981);
  border-radius: 3px;
}

::-webkit-scrollbar-thumb:hover {
  background: linear-gradient(to bottom, #2563eb, #059669);
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