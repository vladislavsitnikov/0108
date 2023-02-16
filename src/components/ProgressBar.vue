<template>
    <div>
        <div class="progress">
            <div class="progress-wrap" v-for="item in progressObject">
                <div class="progress-line">
                <div class="progress-persent" :style="{ width: item.size , background: item.color}">
                    <div class="progress-text">
                    <h3>
                        {{ item.name }}
                    </h3>
                    </div>
                </div>
                </div>
                <div class="progress-calc">
                    <h3>
                        {{ item.number }}
                    </h3>
                </div>
            </div>
        </div>
        <div class="total">
            <h2>Total</h2>
            <h2>{{sum}}</h2>
        </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "ProgressBar",
  
    data() {
      return {
        progressObject: [
          { name: "Manual tour booking", size: "219px", color: "#B1E19B", number: 11  },
          { name: "Package tours", size: "54px", color: "#ACE2F8", number: 3 },
          { name: "Hotels", size: "36px", color: "#ACE2F8", number: 1 },
        ],
        totalSum: 0,
      };
    },
    computed:{
        sum() {
        let result = 0;
        this.progressObject.forEach(el=> result += el.number);
        return result;
        },
    },
  };
  </script>
  
  <style scoped>
  .progress{
    border-top: 1px solid #DADADA;
    border-bottom: 1px solid #DADADA;
    padding: 10px 0  0 0;
  }
  .progress-wrap {
    width: 100%;
    position: relative;
    height: 40px;
  }
  .progress-line {
    width: 320px;
  }
  .progress-persent {
    position: absolute;
    top: 0;
  }
  .progress-text {
    display: flex;
    justify-content: space-between;
    width: max-content;
    border-radius: 0px 3px 3px 0px;
    border-left: 1px solid #333333;
    padding-left: 5px;
  }
  .progress-calc{
    display: flex;
    justify-content: flex-end;
  }
  .total{
    display: flex;
    justify-content: space-between;
  }
  @media (max-width: 600px){
    
  }
  </style>
  