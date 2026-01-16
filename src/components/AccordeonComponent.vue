<script setup>
import starIcon from '@/assets/images/icon-star.svg'
import AccordeonItem from '@/components/Accordeon.vue';

const items = [
  {
    id: '1',
    question: 'What is Frontend Mentor, and how will it help me?',
    answer: 'Frontend Mentor offers realistic coding challenges to help developers improve their frontend coding skills with projects in HTML, CSS, and JavaScript. It’s suitable for all levels and ideal for portfolio building.',
  },
  {
    id: '2',
    question: 'Is Frontend Mentor free?',
    answer: 'The majority of our challenges are free, yes. We do have some that are premium and require a Pro subscription to access. It will say on each challenge whether they are free or premium, so it\'s easy to tell the difference.',
  },
  {
    id: '3',
    question: 'Can I use Frontend Mentor projects in my portfolio?',
    answer: 'Definitely! Please do feel free to use whatever you build in your portfolio. Helping developers add professional-looking projects to their portfolio was one of the reasons we created this platform!',
  },
  {
    id: '4',
    question: 'How can I get help if I\'m stuck on a challenge?',
    answer: 'The best (and quickest) way to get help on a challenge is in our Discord server. There are thousands of other developers in there, so it\'s a great place to ask questions. We even have a dedicated \"help\" channel! If you haven\'t joined yet, you can get an invite to our Discord server here.',
  },
]
</script>

<template>
  <div class="w-full p-6 mx-auto bg-white rounded-lg -mt-25 md:rounded-xl md:p-10 md:-mt-38 max-w-150">
    <div class="flex items-center gap-6">
      <div class="size-6 md:size-10">
        <img alt="star" :src="starIcon">
      </div>
      <h1 class="text-purple-950 font-bold text-[32px] leading-9.5 md:text-[56px]">
        FAQs
      </h1>
    </div>
    <AccordeonItem :items="items"/>
  </div>
</template>
