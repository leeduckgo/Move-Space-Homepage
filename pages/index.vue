<template>
  <div class="flex flex-col w-content mx-auto pt-9">
    <div class="header h-16 flex justify-between items-center">
      <div class="flex items-center space-x-3">
        <img src="/img/logo.png" alt="logo" class="h-12" />
        <img src="/img/logo-title.png" alt="logo" class="h-6 dark:brightness-0 dark:invert" />
      </div>
      <div class="links flex items-center space-x-5 text-black-1 dark:text-white font-['Poppins'] text-[17px]">
        <template v-for="link in links" :key="link">
          <a v-if="link.url" :href="link.url" class="relative h-7 flex items-center cursor-pointer hover:underline underline-offset-4">
            <span>{{ link.title }}</span>
            <img class="w-6 h-6 dark:brightness-0 dark:invert" src="~/assets/svg/down-select.svg" alt="select">
          </a>
          <a v-else class="group relative h-7 flex items-center cursor-pointer">
            <span>{{ link.title }}</span>
            <img class="w-6 h-6 dark:brightness-0 dark:invert" src="~/assets/svg/down-select.svg" alt="select">
            <p
              class="hidden group-hover:flex absolute -bottom-6 left-1/2 -translate-x-1/2 w-32 h-6 rounded-xl bg-[#FFDC02] justify-center items-center text-xs font-['Poppins'] dark:text-black">
              Coming soon
            </p>
          </a>
        </template>
        <div class="flex justify-center ml-2" @click="toggleColorMode">
          <input type="checkbox" name="light-switch" class="light-switch sr-only" />
          <label
            class="relative h-[30px] p-[3px] bg-[#F0F2F5] dark:bg-[#2C2C2C] rounded-full after:content-[''] after:transition-transform after:duration-500 after:absolute after:dark:translate-x-full after:w-6 after:h-6 after:p-[6px] after:rounded-full after:bg-gradient-to-r after:from-[#439DFF] after:to-[#6052FF] flex items-center cursor-pointer select-none"
            for="light-switch">
            <img class="m-[6px] z-20 w-3 h-3" src="~/assets/svg/light-mode.svg" alt="light-mode">
            <img class="m-[6px] z-20 w-3 h-3" src="~/assets/svg/dark-mode.svg" alt="dark-mode">
            <span class="sr-only">Switch to light / dark version</span>
          </label>
        </div>
      </div>
    </div>
    <div class="slogon mt-12 flex justify-between items-center">
      <div class="flex flex-col space-y-12">
        <div class="texts flex flex-col space-y-6">
          <div class="titles flex flex-col space-y-9">
            <div class="flex flex-col space-y-4 text-black-1 dark:text-white">
              <span class="w-[450px] text-[72px] leading-none font-['Poppins'] font-medium tracking-[0.6px]">Web 3 AI
                Powerhouse</span>
              <span class="w-[510px] text-[36px] leading-tight font-['Poppins']">For Search, AIGC, Data
                Marketplace, and Apps</span>
            </div>
            <LinearLine classText="w-[615px]" />
          </div>
          <div class="flex items-center space-x-2 text-third-gray dark:text-gray-4 text-[21px]">
            <span class="leading-8">Powered by BNB Greenfield</span>
            <img class="w-8 h-8" src="/img/logo-bnb.png" alt="bnb">
          </div>
        </div>
        <div class="buttons flex items-center space-x-8">
          <template v-for="button in buttons" :key="button">
            <TheButton :text="button.text" :uppercase="true" :high="true" :colored-border="button.coloredBorder"
              :change-text="true" />
          </template>
        </div>
      </div>
      <img class="w-[568px]" src="/img/dataism.png" alt="dataism">
    </div>
    <div class="mt-[72px]">
      <img class="mx-auto h-[30px] dark:brightness-0 dark:invert" src="/img/clients.png" alt="clients">
    </div>
    <div class="mt-[26px] text-center text-third-gray dark:text-gray-5 text-[20px] font-['Poppins']">
      Trusted by and integrated with the world’s most ambitious teams
    </div>
    <div class="mt-40 mx-auto w-[1160px] flex flex-col items-center space-y-[142px]">
      <div class="w-full flex justify-start items-center space-x-60">
        <div class="w-[555px] flex flex-col space-y-6 items-start">
          <div class="w-full flex flex-col space-y-2 text-[20px] text-second-gray dark:text-white font-['Poppins']">
            <span>MOVESPACE is a Web 3 AI Powerhouse. We utilize
              decentralized storage solutions including BNB Greenfield and Arweave to power on-chain data labeling, data
              monetization, AI-powered search, AIGC & AI-based UGC, NFT, and gaming use cases.</span>
            <span>Our team consists of Web 3 natives and veteran builders from Tencent, Huawei, Microsoft, Google, and
              Netease, etc.</span>
          </div>
          <div class="w-[575px] p-2.5">
            <LinearLine />
          </div>
          <TheButton text="Learn more" :colored-border="true" @click="scrollToTop" />
        </div>
        <div class="title text-black-2 dark:text-white text-[40px] font-['Poppins'] font-semibold">ABOUT US</div>
      </div>
      <div class="w-full flex justify-start items-center space-x-60">
        <div class="title w-[555px] text-black-2 dark:text-white text-[40px] font-['Poppins'] font-semibold">APPLICATIONS
        </div>
        <div class="w-[555px] flex flex-col space-y-6 items-start">
          <div class="w-full flex flex-col space-y-2 text-[20px] text-second-gray dark:text-white">
            <ul class="list-disc">
              <li><b>MoveSpace Data Explorer:</b> an AI-powered search engine for on-chain and off-chain data.</li>
              <li><b>MoveSpace Data Marketplace:</b> a data publishing and marketplace platform built on BNBChain & BNB
                Greenfield.</li>
              <li><b>MoveSpace Review Platform:</b> a review-to-earn platform for everyone to earn while leaving a review
                and rating campaigns, NFTs, & events.</li>
              <li><b>MoveSpace Data Labeling Platform:</b> an on-chain data labeling platform for LLMs and applications,
                built on BNBChain, opBNB and BNB Greenfield.</li>
            </ul>
          </div>
          <div class="w-[575px] p-2.5">
            <LinearLine />
          </div>
          <TheButton text="Learn more" :colored-border="true" @click="scrollToTop" />
        </div>
      </div>
    </div>
    <div class="footer mt-60 pb-24 flex flex-col space-y-3">
      <LinearLine />
      <div class="flex justify-between items-center text-third-gray dark:text-white font-['Montserrat']">
        <span v-for="text in footerTexts" :key="text">{{ text }}</span>
      </div>
    </div>
  </div>
</template>

<script setup>
const links = [
  {
    title: 'AI Data Explorer',
    url: 'https://explorer.movespace.xyz/',
  },
  {
    title: 'Review & Earn',
    url: '',
  },
  {
    title: 'Label & Earn',
    url: '',
  },
  {
    title: 'Data Marketplace',
    url: '',
  },
]
const buttons = [
  {
    text: 'testnet',
    coloredBorder: true,
  },
  {
    text: 'read docs',
    coloredBorder: false,
  },
]
const footerTexts = [
  '𑖌𑖼Copyright © 2023 MOVESPACE. All rights reserved.𑖌𑖼',
  'Terms of Use & Privacy Policy',
]

const colorMode = useColorMode('dark');
const toggleColorMode = () => {
  if (colorMode.preference === 'dark') {
    colorMode.preference = 'light'
  } else {
    colorMode.preference = 'dark'
  }
}

const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth',
  })
}
</script>

<style scoped></style>