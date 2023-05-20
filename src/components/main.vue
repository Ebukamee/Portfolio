<script>
  import Contact from "./Contact.vue";
  import Project from "./Project.vue";
  import Nav from "./Nav.vue";
  import Stack from "./Stack.vue";
  export default {
    name:"Main",
    components: {
      Contact,
      Project,
      Nav,
      Stack,
    },
  };
</script>

<template>
  <div id="main">
    <Nav />
    <div id="bold">
      <h2>Hello, I am <span>Chukwuebuka Nwokike</span></h2>
      <br />
      <h1><span>Software</span> Engineer</h1>
    </div>
    <div id="about">
      <p>
        I am a dediacted Frontend engineer who likes to create and build
        challenging projects. My carrer objective is to strive for excellence
        and precision at all times. I love bringing web designs to live with my
        knowledge and technical skills of web technologies in accesible way for
        better user experience
      </p>

      <a download="ebuka_cv" href="https://drive.google.com/file/d/15W8DrsHYVEfEHAYF5Vjq-rh_v0GKr6Jr/view?usp=sharing"
        target="_blank"><button>View CV</button></a
      >
    </div>
    <Stack />
    <Project />
    <Contact />
  </div>
</template>
