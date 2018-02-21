<template>
  <div>
    <div class="course" v-for="course in courses"> 
      <div class="img" :style="imgStyle(course.img)"/>
      <div class="text">
        <router-link :to="`/courses/${course.id}`">
          {{course.name}}
        </router-link>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Delectus placeat ad velit laboriosam quo? Facere esse est consequuntur hic reprehenderit.</p>
      </div>
    </div>
  </div>
</template>

<script>
  import lessons from './lessons';

  export default {
    data(){
      return {
        courses: lessons,
      };
    },
    methods: {
      imgStyle(img){
        return {
          backgroundImage: `url(${img})`,
        };
      },
    },
  };
</script>

<style scoped>
.course{
  display: flex;
  flex-flow: row nowrap;
  justify-content: center;
  margin-bottom: 1rem;
}
.img{
  display: inline-block;
  height: 80px;
  flex: 0 0 150px;
  background-position: center center;
  background-size: cover;
}
.text{
  display: inline-block;
  padding-left: 10px;
}
a{
  display: inline-block;
  color: #42b983;
  font-size: 1rem;
  text-decoration: none;
}
a:hover{
  font-weight: bold;
}
p{
  font-size: 1rem;
}

@media(max-width: 500px){
  .course{
    flex-flow: column nowrap;
  }
  .text{
    padding: 20px 0;
  }
}
</style>
