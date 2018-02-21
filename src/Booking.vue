<template>
  <div>
    <h1>Booking</h1>
    <form @submit.prevent="">
      <div class="group">
        <label>Name</label><br>
        <input type="text" v-model="name">
      </div>

      <div class="group">
        <label>Tel</label><br>
        <input type="text" v-model="tel">
      </div>

      <div class="group">
        <label>Time</label><br>
        <input type="datetime-local" v-model="time">
      </div>

      <div class="group">
        <label>Course</label><br>
        <select v-model="course">
          <option v-for="course in courses" :value="course.id">{{course.name}}</option>
        </select>
      </div>

      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Fuga tempore beatae laboriosam in magnam totam dolorum eum nemo ipsam et.</p>

      <div class="btns">
        <button type="submit">Submit</button>
      </div>
    </form>
  </div>
</template>

<script>
  import lessons from './lessons';

  export default {
    data(){
      return {
        name: '',
        tel: '',
        time: '',
        course: 1,
        courses: lessons,
      };
    },
  };
</script>

<style scoped>
.group{
  display: flex;
  flex-flow: row nowrap;
  font-size: 1rem;
  margin: 1rem 0;
  align-items: center;
  justify-content: space-between;
}
form{
  display: flex;
  flex-flow: column nowrap;
  justify-content: center;
  margin: 1rem auto;
  max-width: 500px;
}
label{
  width: 30%;
  text-align: left;
  padding-right: 10px; 
}
input, select{
  width: 70%;
  font-size: 1rem;
  box-sizing: border-box;
}
p{
  font-size: .75rem;
}
.btns{
  text-align: center;
  margin-top: 1rem;
}
button{
  background-color: #fff;
  border: 2px solid #42b983;
  color: #42b983;
  font-size: 1rem;
  padding: .75rem 1.5rem;
  cursor: pointer;
  border-radius: 10px;
  font-weight: bold;
}
button:hover{
  background-color: #42b983;
  color: #fff;
}

@media(max-width: 450px){
  .group{
    display: block;
  }
  input, select{
    width: 100%;
  }
}
</style>
