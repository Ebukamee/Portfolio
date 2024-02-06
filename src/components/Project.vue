<script>
export default {
  data() {
    return {
      projects: [
        {
            id: 1,
            name: "Chatter Blog",
            img: "/src/assets/chatter.png",
            repo: "https://github.com/ebukamee/Chatter",
            url: "https://chatter-flame.vercel.app",
            built:'ReactJs, TypeScript, CSS, Redux and Firebase',
            description: "This is a blogging website with user authentication, where authenticated users can post, read and delete their post. It also allows non authenticatedusers to read post from other writers."
        },
        {
            id: 1,
            name: "Retro Ecommerce Website",
            img: "/src/assets/retro.png",
            repo: "https://github.com/ebukamee/ecommerce",
            url: "https://ecommerce-ebukamee.vercel.app",
            built:'VueJs, JavaScript, CSS, vuex and Firebase',
            description: "An Ecommerce website wher users can shop and add desiredproducts to cart. Then users can procced to pay with flutterwave payment service. also, Admin users can lso addproducts to shop."
        }
    ]
    }
  }
}
</script>


<template>
  <div id="project">
  <h3>My Projects</h3>

    <div  v-for="(project, i) in projects" :key="i">
      <img :src="project.img" :alt="project.name" />
      <h3>{{ project.name }}</h3>
      <h4>Built with {{ project.built }}</h4>
      <p>{{ project.description }}</p>
      <a :href="project.repo" target='_blank' id="red"> Repository </a>
      <a :href="project.url" target='_blank' id="red"> Go live </a>
    </div>
  </div>
</template>
