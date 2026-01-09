<template>
  <div class="common-container">
    <section>
      <el-descriptions
        v-for="item of repairSitesList"
        :column="2"
        direction="vertical"
        :title="item.city"
        border
      >
        <el-descriptions-item>
          <template #label>
            <div class="cell-item">
              <el-icon>
                <user />
              </el-icon>
              {{ $t('repair.contact') }}
            </div>
          </template>
          {{ item.contact }}
        </el-descriptions-item>
        <el-descriptions-item>
          <template #label>
            <div class="cell-item">
              <el-icon>
                <iphone />
              </el-icon>
              {{ $t('repair.telephone') }}
            </div>
          </template>
          {{ item.telephone }}
        </el-descriptions-item>
        <el-descriptions-item>
          <template #label>
            <div class="cell-item">
              <el-icon>
                <office-building />
              </el-icon>
              {{ $t('repair.address') }}
            </div>
          </template>
          {{ item.address }}
        </el-descriptions-item>
      </el-descriptions>
    </section>
  </div>
</template>

<script lang="ts" setup>
import { ElIcon, ElDescriptions, ElDescriptionsItem } from 'element-plus'

const locale = useCookie('locale')
const repairSitesList = computed(() => {
  switch (locale.value) {
    case 'cn':
      return repairSitesListCN
    case 'ru':
      return repairSitesListRU
    default:
      return repairSitesListEN
  }
})
const repairSitesListCN = [
  {
    city: '中东迪拜test',
    contact: '方成test',
    address: 'Warehouse 13, JAMS CONTRACTING (L.L.C) , Al Qusais , Dubai',
    telephone: '+971 0585499703',
  },
    {
    city: '中东迪拜',
    contact: '罗金萍',
    address: 'Warehouse 13, JAMS CONTRACTING (L.L.C) , Al Qusais , Dubai',
    telephone: '+971 58 520 9136',
  },
  {
    city: '美国德克萨斯',
    contact: '王赠涵',
    address: '美国德克萨斯州休斯顿哈文区10611号 邮编：77036',
    telephone: '(432)924-7069',
  },
  {
    city: '中国. 深圳',
    contact: '唐乾高',
    address: '深圳市宝安区石岩街道伟泰工业园1号厂房404',
    telephone: ' +86 176 8876 7856',
  },
]

const repairSitesListEN = [
  {
    city: 'Dubai,UAE',
    contact: 'Suhail Fang',
    address: 'Warehouse 13, JAMS CONTRACTING (L.L.C) , Al Qusais , Dubai',
    telephone: ' +971 0585499703',
  },
  {
    city: 'Dubai,UAE',
    contact: 'Judy Luo ',
    address: 'Warehouse 13, JAMS CONTRACTING (L.L.C) , Al Qusais , Dubai',
    telephone: ' +971 58 520 9136',
  },
  {
    city: 'Texas,USA',
    contact: 'Zenghan Wang',
    address: '10611 Harwin Dr. Suite 400Houston, TX 77036 US ',
    telephone: '(432)924-7069',
  },
  {
    city: 'Shenzhen,China',
    contact: 'Tang Qiangao ',
    address: 'Room 404, Building 1, Weitai Industrial Park, Shiyan Street, Baoan District, Shenzhen',
    telephone: '+86 176 8876 7856',
  },

]

const repairSitesListRU = [
  {
    city: 'Ближний Восток Дубай',
    contact: 'Suhail Fang',
    address: 'Склад 13, JAMS CONTRACTING (L.L.C), Аль-Кусейс, Дубай',
    telephone: '+971 0585499703',
  },
  {
    city: 'Ближний Восток Дубай',
    contact: 'Judy Luo ',
    address: 'Склад 13, JAMS CONTRACTING (L.L.C), Аль-Кусейс, Дубай',
    telephone: '+971 58 520 9136',
  },
  {
    city: 'Техас, США',
    contact: 'Zenghan Wang',
    address: '10611 Доктор Харвин, Люкс 400, Хьюстон, Техас 77036 ',
    telephone: ' (432)924-7069',
  },
  {
    city: 'Shenzhen,China',
    contact: 'Tang Qiangao ',
    address: 'Комната 404, заводское здание № 1, промышленный парк Вэйтай, улица Шиянь, район Баоань, город Шэньчжэнь',
    telephone: '+86 176 8876 7856',
  },
  
]
</script>

<style lang="less" scoped>
section {
  width: 1080px;
  margin: 0 auto 50px;
  padding-top: 50px;
}

.el-descriptions {
  margin-top: 20px;
}

.cell-item {
  display: flex;
  align-items: center;
}

.el-icon {
  margin-bottom: 2px;
}

@media (max-width: 1024px) {
  section {
    width: 100%;
  }
}
</style>
