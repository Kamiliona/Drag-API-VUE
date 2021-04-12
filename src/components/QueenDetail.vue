<template>
   <div v-if="queen" id="queenDetail">
    <div id="detailWrapper">
      <h2>{{queen.name}}</h2>
      <div id="flexWrapper">
        </div>
        <div id="image">
          <img :src="queen.image_url" :alt="queen.name">
        </div>
        <div id="quote">
          <p> "{{queen.quote}}"</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'queen-detail',
  props: ['queen']
}
</script>

<style>

body {
    background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
    background-size: 400% 400%;
    animation: gradient 15s ease infinite;
}

@keyframes gradient {
    0% {
        background-position: 0% 50%;
    }
    50% {
        background-position: 100% 50%;
    }
    100% {
        background-position: 0% 50%;
    }
}
#queenDetail {
    margin: 0 auto;
    margin-top: 100px;
    box-sizing: border-box;
    height: 1300px;
    width: 60%;
    background: linear-gradient(-45deg,  #fcb606, #ffff00);
    background-size: 400% 600%;
    animation: gradient 15s ease infinite;
    padding: 10px;
    border-radius: 25px;
  }

  #detailWrapper {
    
    box-sizing: border-box;
    background: linear-gradient(-45deg, #fc7aac, #f97ede, #ff81a9);
    background-size: 400% 800;
    animation: gradient 2s ease infinite;
    padding: 10px;
    height: 100%;
    border-radius: 25px;
    
  }

  #flexWrapper {
    display: flex;
    justify-content: space-between;
  }

  h2 {
    text-align: center;
  font-size: 50px;
  text-transform: uppercase;
  color: transparent;
  background-image: linear-gradient(to right, #fcb606d6, #ffff00);
  -webkit-background-clip: text;
  animation: animate 5s linear infinite;
  background-size: 1000%;
  }

  p {
    font-weight: bold;
    text-align: center;
  font-size: 40px;
  text-transform: uppercase;
  color: transparent;
  background-image: linear-gradient(to right, #ffb700, #ffff00);
  -webkit-background-clip: text;
  animation: animate 5s linear infinite;
  background-size: 1000%;
    
  }

  img {
      display: block;
    margin-left: auto;
    margin-right: auto;
      mix-blend-mode: multiply;
      width: 70%;
      height: 50%;
  }

  #image {
      margin-top: 30px;
  }
  
  #quote {
      margin-top: 40px;

  }

</style>
