<template>

    <div >
        <Nav />
        <div class="make-order">
        <div class="border-first">
            <h2 class="border-text">Pay</h2> <br>
            <h3 class="border-text">Your Order</h3>
            <div class="border-menu">
                 <ul>
                     <li>
                         
                     </li>
                 </ul>
            </div>
        </div>
        <div class="border-seccond">
            <h3 class="your-details">Your Details</h3>
            <label class="inputs" for="">Your name</label>
            <input class="details" type="text">
            <label class="inputs"  for="">Street</label>
            <input class="details" type="text">
            
            <div class="left">
            <label class="lable-left"  for="">ZIP Code</label> 
            <label class="lable-right"   for="">City</label>
           
            </div>
            <div class="right">
             <input class="input-details" type="text">
             <input class="input-details" type="text">
            </div>

            <h3 class="payment-text">Payment</h3>
             <label class="inputs"  for="">Card Owner</label>
            <input class="details" type="text">
            <label class="inputs"  for="">Card Number</label>
            <input class="details" type="text">
           
            <div class="left">
            <label class="lable-left"  for="">Valid untill</label> 
            <label class="lable-right"  for="">CVV</label>
            </div>
            <div class="right">
             <input class="input-details" type="text">
             <input class="input-details" type="password">
            </div>
        </div>
        </div>
    </div>
</template>

<script>
//hi
import Nav from '../components/Nav.vue'
export default {
  components: { 
      Nav 
  },
    name: "MakeOrder"
}
</script>

<style lang="scss" scoped>

.make-order{
    display: flex;
    align-content: center;
}
.border-first{
    height: 700px;
    width: 400px;
    margin-top: 3rem;
    margin-left:5rem ;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
}
.border-menu{
    margin-top: 2rem;
    padding: 2rem;
    display: flex;
    border-style: solid;
    height: 500px;
    width: 400px;
    background-color: white;
    border: none;
    box-shadow:
    0 2.8px 2.2px rgba(0, 0, 0, 0.034),
    0 6.7px 5.3px rgba(0, 0, 0, 0.048),
    0 12.5px 10px rgba(0, 0, 0, 0.06),
    0 22.3px 17.9px rgba(0, 0, 0, 0.072),
    0 41.8px 33.4px rgba(0, 0, 0, 0.086),
    0 100px 80px rgba(0, 0, 0, 0.12);

}
.border-seccond{
    height: 500px;
    width: 400px;
    margin-top: 6rem;
    margin-left:5rem ;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
   // justify-content: center;
}
.left{
    display: flex;
    justify-content: space-between;
    //float: left;
    
}
.inputs {
    font-size: 13px;
    color: lightgray;
    margin-top: 5px;
}
.lable-left{
    font-size: 13px;
    color: lightgray;
    margin-top: 5px;
    
}
.lable-right{
    font-size: 13px;
    color: lightgray;
    margin-top: 5px;
    margin-left: 7rem;
}
.details{
    height: 2rem;
    width: 21.8rem;
}
.input-details{
    height: 2rem;
    margin-left: 2px;
}
.payment-text{
    margin-top: 3rem;
}
.your-details{
    margin-bottom: 2rem;
}
</style>