<template>
<div id="app">
  <div class="container">
  <div class="cow-wrap" :class="'is-' + selected">
      <div class="cow">
        <div class="cow-head">
          <div class="party-hat"></div>
          <div class="party-hat-bobble"></div>
          
          <div class="pizza"></div>
          <div class="pizza-crust"></div>
          <div class="pizza-topping"></div>
          <div class="pizza-topping pizza-topping--2"></div>
          <div class="pizza-topping pizza-topping--3"></div>
          
          <div class="bow"></div>
          <div class="bow-ear bow-ear--left"></div>
          <div class="bow-ear bow-ear--right"></div>
          
          <div class="gem">
            <i class="fas fa-gem"></i>
          </div>
          
          <div class="glasses-lense glasses-lense--left"></div>
          <div class="glasses-lense glasses-lense--right"></div>
          <div class="glasses-middle"></div>
          
          <div class="cow-ears">
            <div class="cow-ear cow-ear--left"></div>
            <div class="cow-ear cow-ear--right"></div>
          </div>
          <div class="cow-horns">
            <div class="cow-horn cow-horn--left"></div>
            <div class="cow-horn cow-horn--right"></div>
          </div>
          <div class="cow-eyes">
            <div class="cow-eye cow-eye--left"></div>
            <div class="cow-eye cow-eye--right"></div>
          </div>
          <div class="cow-muzzle"></div>
          <div class="cow-mouth">
            <div class="cow-mouth-line cow-mouth-line--left"></div>
            <div class="cow-mouth-line cow-mouth-line--right"></div>
            <div class="cow-mouth-moo"></div>
          </div>
        </div>
        <div class="cow-body"></div>
      </div>
    </div>
    <div class="controls">    
    <button
      type="button"
      class="controls-button"
      :class="{'is-active': selected === button.name}"
      :key="button.name"
      v-for="button in types"
      @click="changeType(button.name)"
    >
      <i class="fas" :class="button.icon"></i>
    </button>
  </div>
  </div>
</div>
</template>

<script>


export default {
  name: 'App',
   data() {
     return {
       selected: 'default',
       types: [
        {
          icon: 'fa-meh',
          name: 'default',
        },
        {
          icon: 'fa-gift',
          name: 'party',
        },
        {
          icon: 'fa-pizza-slice',
          name: 'pizza',
        },
        {
          icon: 'fa-user-tie',
          name: 'tie',
        },
        {
          icon: 'fa-eye',
          name: 'glow',
        },
        {
          icon: 'fa-glasses',
          name: 'glasses',
        },
      ]
     }
  },
  methods: {
    changeType: function(type) {
      this.selected = type;
    }
  }


}
</script>

<style>
body {
  background-color: #fe7dbd;
  margin: 0;
  padding: 0;
}
#app {
  display: flex;
  height: 100vh;
  align-items: center;
  justify-content: center;
}

.container{
  width: 40vw;
  height: 40vw;
}

.cow-wrap{
  width: 80%;
  height: 80%;
  border-radius: 50%;
  overflow: hidden;
  border: 1rem solid white ;
  background-color: #dfb8f1;
}

.cow{
  width: 100%;
  height: 100%;
  position: relative;
}

.cow-head{
  position: absolute;
  width: 70%;
  height: 65%;
  background-color: #fff;
  border-radius: 50% 50% 40% 40%;
  top: 25%;
  left: 50%;
  transform: translate(-50%, 0);
  /* left: 15%; */
  z-index: 1;
}

.cow-body{
  position: absolute;
  width: 70%;
  height: 50%;
  background-color: #fff;
  border-radius: 60% 60% 50% 50%;
  top: 60%;
  left: 15%
}

.cow-ears{
  width: 100%;
  height: 30%;
  top: 15%;
  position: absolute;
}

.cow-ear{
  width: 20%;
  height: 150%;
  background-color: #fff;
  border-radius: 70% 30% 0 0;
  position: absolute;
}

.cow-ear--left{
  left: -6%;
  transform: rotate(-125deg);
}

.cow-ear--right{
  right: -6%;
  transform: rotate(125deg) scaleX(-1);
}

.cow-horns{
  width: 100%;
  height: 30%;
  top: 3%;
  position: absolute;
}

.cow-horn{
  position: absolute;
  background-color: #fae8d9;
  width: 18%;
  height: 100%;
  border-radius: 90% 50% 45% 45%;
}

/* .cow-horn::before{
  position: absolute;
  content: '';
  width: 100%;
  height: 50%;
  background-color: #fae8d9;
  border-radius: 50%;
  top: 55%;
} */

.cow-horn--left{
  left: 0;
  transform: rotate(-60deg);
}

.cow-horn--right{
  right: 0;
  transform: rotate(60deg) scaleX(-1);
}

.cow-eyes{
  width: 100%;
  height: 20%;
  top: 50%;
  position: absolute;
}

.cow-eye{
  background-color: #8947aa;
  border-radius: 50%;
  width: 10%;
  height: 50%;
  position: absolute;
}

.cow-eye--left{
  left: 17%;
}

.cow-eye--right{
  right: 17%;
}

.cow-muzzle {
  width: 40%;
  height: 40%;
  border-radius: 50%;
  background-color: #fecacc;
  top: 32%;
  left: 15%;
  left: 50%;
  transform: translate(-50%);
  position: absolute;
}

.cow-mouth {
  width: 100%;
  height: 20%;
  top: 50%;
  position: absolute;
}

.cow-mouth-line {
  position: absolute;
  width: 8%;
  height: 15%;
  background-color: #8947aa;
  border-radius: 0.375rem;
}

.cow-mouth-line--left{
  left: 44.1%;
  transform: rotate(-45deg);
}

.cow-mouth-line--right{
  right: 44.1%;
  transform: rotate(45deg);
}

.controls-button {
  border: 0;
  background-color: #fff;
  width: 3rem;
  height: 3rem;
  border-radius: 50%;
  font-size: 1.5rem;
  margin: 0 0.5rem;
  cursor: pointer;
  transition: 0.2s ease-in;
  color: #8947aa;
}

.controls-button:hover{
   background-color: #fae8d9;
}

.controls-button.is-active {
    background-color: #8947aa;
    color: #fff;
  }



</style>
