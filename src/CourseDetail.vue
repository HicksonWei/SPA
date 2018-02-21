<template>
  <div>
    <router-link to="/courses">Back</router-link>
    <div class="cover" :style="coverStyle"/>
    <h2>{{course.name}}</h2>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Mollitia aliquid est totam itaque optio asperiores repellendus perspiciatis eos tempora temporibus nemo libero, voluptas sapiente. Pariatur veritatis vero molestias iusto omnis!</p>
  </div>
</template>

<script>
  import lessons from './lessons';

  export default {
    props: ['id'],
    computed: {
      course(){
        return lessons[this.id - 1];
      },
      coverStyle(){
        return {
          backgroundImage: `url(${this.course.img})`,
        };
      },
    },
  };
</script>

<style scoped>
a{
  font-size: 1rem;
  text-decoration: none;
  color: #42b983;
  line-height: 2;
}
a::before{
  content: '< ';
}
a:hover{
  color: red;
}
.cover{
  width: 100%;
  height: 500px;
  background-position: center center;
  background-size: cover;
}
h2{
  color: #42b983;
}
p{
  font-size: 1rem;
  line-height: 2;
}
</style>
