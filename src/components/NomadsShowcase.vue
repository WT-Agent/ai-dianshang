<template>
  <section class="nomads-showcase-section">
    <div class="showcase-header">
      <div class="header-left">
        <h2 class="showcase-title">实战案例与爆款模板库 (Nomads Showcase)</h2>
        <p class="showcase-subtitle">精选高转化电商爆款场景，点击“一键套用”快速生成专业文案</p>
      </div>
      <span class="showcase-badge">已收录 {{ showcaseItems.length }} 个电商实战模板</span>
    </div>

    <div class="showcase-grid">
      <div 
        v-for="item in showcaseItems" 
        :key="item.id" 
        class="glass-card showcase-card"
      >
        <div class="card-header">
          <span class="scenario-tag">{{ item.tag }}</span>
          <span class="usage-count">{{ item.usageCount }} 次应用</span>
        </div>

        <div class="card-content">
          <h3 class="item-title">{{ item.title }}</h3>
          <p class="item-prompt">“{{ item.prompt }}”</p>
        </div>

        <div class="card-action">
          <button class="apply-btn" @click="applyTemplate(item)">
            <span>一键套用</span>
            <svg class="arrow-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <line x1="5" y1="12" x2="19" y2="12"></line>
              <polyline points="12 5 19 12 12 19"></polyline>
            </svg>
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { computed } from 'vue';

export interface ShowcaseItem {
  id: string;
  tag: string;
  title: string;
  prompt: string;
  copywritingType?: string;
  platform?: string;
  targetAudience?: string;
  usageCount: string;
}

const emit = defineEmits<{
  (e: 'apply-template', payload: {
    prompt: string;
    copywritingType?: string;
    platform?: string;
    targetAudience?: string;
  }): void;
}>();

const showcaseItems = computed<ShowcaseItem[]>(() => [
  {
    id: 'dianshang-1',
    tag: '美妆护肤',
    title: '水光玻尿酸保湿精华爆款文案',
    prompt: '针对30+精致妈妈群体，主打熬夜急救补水与抗初老，需包含5张主图文案构图与小红书真实痛点种草脚本。',
    copywritingType: '商品主图与详情页文案',
    platform: '小红书',
    targetAudience: '精致妈妈',
    usageCount: '38.5k'
  },
  {
    id: 'dianshang-2',
    tag: '智能数码',
    title: '主动降噪蓝牙耳机短视频前3秒爆点',
    prompt: '面向Z世代学生与职场白领，主打地铁公交极速降噪与无感佩戴，生成抖音短视频黄金前3秒吸睛台词与画质建议。',
    copywritingType: '小红书/抖音种草文案',
    platform: '抖音电商',
    targetAudience: 'Z世代青年',
    usageCount: '42.1k'
  },
  {
    id: 'dianshang-3',
    tag: '数码家电',
    title: '全自动扫拖一体机器人直播促单',
    prompt: '面向职场忙碌白领与家庭主妇，强调解放双手与智能避障，设计主播双簧逼单话术与限时买一赠五优惠倒计时。',
    copywritingType: '直播间带货与促单话术',
    platform: '淘宝天猫',
    targetAudience: '职场白领',
    usageCount: '29.8k'
  },
  {
    id: 'dianshang-4',
    tag: '服装服饰',
    title: '法式复古收腰连衣裙主图与卖点',
    prompt: '面向都市女性与品质银发族，突出显瘦遮肉版型与天然桑蚕丝面料，提炼3大超级卖点与详情页视觉图文层级。',
    copywritingType: '商品主图与详情页文案',
    platform: '京东',
    targetAudience: '银发高质感',
    usageCount: '31.4k'
  },
  {
    id: 'dianshang-5',
    tag: '休闲零食',
    title: '0糖低卡纯黑巧克力大促活动方案',
    prompt: '面向健身减脂人与小镇青年，强调好吃不胖与真材实料，撰写聚划算前1小时买2送1满减促销方案与爆款口号。',
    copywritingType: '电商爆款活动与聚划算方案',
    platform: '拼多多',
    targetAudience: '小镇青年',
    usageCount: '26.7k'
  },
  {
    id: 'dianshang-6',
    tag: '户外运动',
    title: '轻量化黑胶露营天幕种草笔记',
    prompt: '面向露营爱好者与户外达人，强调UPF50+防晒防暴雨与3分钟快速搭建，撰写符合平台流量推荐的小红书笔记。',
    copywritingType: '小红书/抖音种草文案',
    platform: '小红书',
    targetAudience: 'Z世代青年',
    usageCount: '24.3k'
  }
]);

function applyTemplate(item: ShowcaseItem) {
  emit('apply-template', {
    prompt: item.prompt,
    copywritingType: item.copywritingType,
    platform: item.platform,
    targetAudience: item.targetAudience
  });
}
</script>

<style scoped>
.nomads-showcase-section {
  margin-top: 2rem;
  width: 100%;
}

.showcase-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  margin-bottom: 1.25rem;
  padding-bottom: 0.75rem;
  border-bottom: 1px solid var(--card-border);
}

.showcase-title {
  font-size: 1.2rem;
  font-weight: 700;
  color: var(--text-primary);
  background: var(--primary-gradient);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.showcase-subtitle {
  font-size: 0.825rem;
  color: var(--text-secondary);
  margin-top: 0.25rem;
}

.showcase-badge {
  font-size: 0.75rem;
  color: #a5b4fc;
  background: rgba(99, 102, 241, 0.12);
  border: 1px solid rgba(99, 102, 241, 0.25);
  padding: 4px 10px;
  border-radius: 20px;
}

.showcase-grid {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  gap: 1.25rem;
}

@media (min-width: 640px) {
  .showcase-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .showcase-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

.showcase-card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100%;
  padding: 1.25rem;
  background: rgba(255, 255, 255, 0.02);
  border: 1px solid var(--card-border);
  border-radius: 14px;
  transition: all 0.25s ease;
}

.showcase-card:hover {
  background: rgba(255, 255, 255, 0.05);
  border-color: rgba(99, 102, 241, 0.4);
  transform: translateY(-3px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.4);
}

.card-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 0.75rem;
}

.scenario-tag {
  font-size: 0.75rem;
  font-weight: 600;
  padding: 3px 8px;
  border-radius: 6px;
  background: rgba(168, 85, 247, 0.15);
  color: #c084fc;
  border: 1px solid rgba(168, 85, 247, 0.3);
}

.usage-count {
  font-size: 0.75rem;
  color: var(--text-secondary);
}

.card-content {
  margin-bottom: 1rem;
  flex: 1;
}

.item-title {
  font-size: 0.95rem;
  font-weight: 600;
  color: var(--text-primary);
  margin-bottom: 0.4rem;
}

.item-prompt {
  font-size: 0.825rem;
  color: var(--text-secondary);
  line-height: 1.45;
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
  font-style: italic;
}

.card-action {
  padding-top: 0.75rem;
  border-top: 1px solid rgba(255, 255, 255, 0.04);
}

.apply-btn {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 6px;
  padding: 0.5rem 1rem;
  background: rgba(99, 102, 241, 0.1);
  border: 1px solid rgba(99, 102, 241, 0.3);
  border-radius: 8px;
  color: #a5b4fc;
  font-size: 0.825rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s ease;
}

.showcase-card:hover .apply-btn {
  background: var(--primary-gradient);
  border-color: transparent;
  color: white;
}

.arrow-icon {
  width: 14px;
  height: 14px;
  transition: transform 0.2s ease;
}

.apply-btn:hover .arrow-icon {
  transform: translateX(3px);
}
</style>
