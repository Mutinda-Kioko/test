<script setup>
  import { getPrice } from './fetchCoins';
  const addresses = [
    { symbol:"BTC",
      addr:"0xECe365B379E1dD183B20fc5f022230C044d51404"},
    { symbol:"ETH",
      addr:"0x8A753747A1Fa494EC906cE90E9f37563A8AF630e"},
    { symbol:"USDC",
      addr:"0xa24de01df22b63d23Ebc1882a5E3d4ec0d907bFB"},
    { symbol:"BNB",
      addr:"0xcf0f51ca2cDAecb464eeE4227f5295F2384F84ED"},
    { symbol:"DAI",
      addr:"0x2bA49Aaa16E6afD2a993473cfB70Fa8559B523cF"}]
  async function fetchCoins(){
    for(let i=0;i<addresses.length; i++){
      const value = await getPrice(addresses[i].addr);
      console.log(addresses[i].symbol, value);
    }

  }
  fetchCoins();
</script>

<template>
  <div class="card-container">
    <div class="card">
      <div class="listComponent">
      <div class="box">
        <article class="media">
          <div class="media-left">
            <figure class="image">
              <p>Bitcoin: </p>
            </figure>
          </div>
          <div class="media-content">
            <div class="content">
              <p><strong>123456</strong> </p>
            </div>
          </div>
        </article>
      </div>
    </div>
    </div>
  </div>
</template>

<style>
@import './assets/base.css';

#app {
  max-width: 1280px;
  font-weight: normal;
  display: flex;
  justify-content: center;
  align-items: center;
}
.card-container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: auto;
}
.card {
  margin: auto;
  display: flex;
  flex-direction: column;
  width: 400px;
  height: 500px;
  background: white;
  border: 1px solid #ddd;
}
.listComponent {
  background-color: #fff;
  color: #373737;
  box-shadow: 0 2px 3px rgba(10,10,10,.1), 0 0 0 1px rgba(10,10,10,.1);
  padding: 30px;
  margin-top: 20px;
  }
.listComponent:hover{
  cursor: pointer;
  box-shadow: rgba(0, 0, 0, 0.25) 0px 54px 55px,
              rgba(0, 0, 0, 0.12) 0px -12px 30px, 
              rgba(0, 0, 0, 0.12) 0px 4px 6px,
              rgba(0, 0, 0, 0.17) 0px 12px 13px,
              rgba(0, 0, 0, 0.09) 0px -3px 5px;
}
  .media {
    display: flex;
  }
  img {
    width: 64px;
    margin-right: 15px;
  }
  small {
    font-size: 14px;
    color: #657786;
  }
@media (hover: hover) {
  a:hover {
    background-color: hsla(160, 100%, 37%, 0.2);
  }
}

@media (min-width: 1024px) {
  body {
    display: flex;
    place-items: center;
  }

  #app {
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding: 0 2rem;
  }

  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  .logo {
    margin: 0 2rem 0 0;
  }
  .wrapper {
  color: #000;
}

.content {
  padding: 20px;
}

.title {
  font-size: 30px;
  font-weight: 700;
  margin-bottom: 20px;
}

.actions {
  display: flex;
  justify-content: flex-end;
  padding: 10px 20px;
  border-top: 1px solid rgba(0, 0, 0, 0.12);
}
}
</style>
