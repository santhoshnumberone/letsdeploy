<script>
  
  import Loader from './lib/Loader.svelte';
  import {path} from './lib/path';
  
  import { MetaTags } from 'svelte-meta-tags';
  import Viewport from 'svelte-viewport-info'

  let outerWidth = 0;
  let outerHeight = 0;
  
  $: custom_landscape_or_potrait_condition = outerWidth*1.33 >= outerHeight;

  import { fade, fly } from 'svelte/transition';
  import { onMount } from 'svelte';

  let greet = true;
  let visible = false;
  onMount(() => {
    setInterval(() => {
      greet = !greet;
      visible = true;
      console.group(greet);
    }, 5000)
  });

</script>

<svelte:window bind:outerWidth bind:outerHeight />
<MetaTags title="Electraanu Energy Private Limited" description="Electric Vehicle Startup Pocket Friendly" />
<svelte:body/>
<Loader
  this={() => import('./lib/Thing.svelte')}>  
  <div slot="fallback" >

    <div class="landscape_wrapper">

      <div class="loading" style="">
        <div class="loading__ring">
          <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1" x="0px" y="0px" viewBox="0 0 100 100" style="enable-background:new 0 0 100 100;" xml:space="preserve">
            {@html path}
          </svg>
        </div>
        <div class="loading__ring">
          <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1" x="0px" y="0px" viewBox="0 0 100 100" style="enable-background:new 0 0 100 100;" xml:space="preserve">
            {@html path}
          </svg>
        </div>

      </div>
      
      <div class = "name" style="width:100%;">
      {#if greet}
<p class="company_name"> 
          <span class="expl_letter">E</span>
          <span class="expl_letter">l</span>
          <span class="expl_letter">e</span>
          <span class="expl_letter">c</span>
          <span class="expl_letter">t</span>
          <span class="expl_letter">r</span>
          <span class="expl_letter">o</span>
                    <span class="expl_letter">n</span><span class="expl_letter">&nbsp;</span>
          <span class="expl_letter">+</span>
          <span class="expl_letter">&nbsp;</span>
          <span class="expl_letter">A</span>
          <span class="expl_letter">n</span>
                    <span class="expl_letter">u</span><span class="expl_letter">(</span>
          <span class="expl_letter">A</span>
                    <span class="expl_letter">t</span>
  <span class="expl_letter">o</span>
                    <span class="expl_letter">m</span>
  <span class="expl_letter">)</span>
                    </p>
{:else}
<p class="company_name"> 
          <span class="comp_letter">E</span>
          <span class="comp_letter">L</span>
          <span class="comp_letter">E</span>
          <span class="comp_letter">C</span>
          <span class="comp_letter">T</span>
          <span class="comp_letter">R</span>
          <span class="comp_letter">A</span>
                    <span class="comp_letter">A</span>
          <span class="comp_letter">N</span>
          <span class="comp_letter">U</span>
                    </p>
{/if}
      </div>

      <div class = "vision" >
      {#if visible}

      <span class = "vision_content" in:fly="{{ x: 100, duration:5000 }}">ACCLERATING ADOPTION OF ELECTRIC MOBILITY</span>
      {/if}
      </div>

    </div>

    <div class="portrait_wrapper">

      <div class="portrait_loading">
        <div class="portrait_loading__ring">
          <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1" x="0px" y="0px" viewBox="0 0 100 100" style="enable-background:new 0 0 100 100;" xml:space="preserve">
            {@html path}
          </svg>
        </div>
        <div class="portrait_loading__ring">
          <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1" x="0px" y="0px" viewBox="0 0 100 100" style="enable-background:new 0 0 100 100;" xml:space="preserve">
            {@html path}
          </svg>
        </div>
      </div>

      <div class = "portrait_name">
       {#if greet}

        <p class="portrait_company_name" style="line-height: 5.1vh;height:24vh;"align="center"> 
          <span class="portrait_expl_letter">E</span>
          <span class="portrait_expl_letter">l</span>
          <span class="portrait_expl_letter">e</span>
          <span class="portrait_expl_letter">c</span>
          <span class="portrait_expl_letter">t</span>
          <span class="portrait_expl_letter">r</span>
          <span class="portrait_expl_letter">o</span>
                    <span class="portrait_expl_letter">n</span><br><span class="portrait_expl_letter">&nbsp;</span>
          <span class="portrait_expl_letter">+</span>
          <span class="portrait_expl_letter">&nbsp;</span>
          <br><span class="portrait_expl_letter">A</span>
          <span class="portrait_expl_letter">n</span>
                    <span class="portrait_expl_letter">u</span><span class="portrait_expl_letter">(</span>
          <span class="portrait_expl_letter">A</span>
                    <span class="portrait_expl_letter">t</span>
  <span class="portrait_expl_letter">o</span>
                    <span class="portrait_expl_letter">m</span>
  <span class="portrait_expl_letter">)</span>
                    </p>
{:else}
<p class="company_name" style="width:99%;"align="center"> 
          <span class="portrait_comp_letter">E</span>
          <span class="portrait_comp_letter">L</span>
          <span class="portrait_comp_letter">E</span>
          <span class="portrait_comp_letter">C</span>
          <span class="portrait_comp_letter">T</span>
          <span class="portrait_comp_letter">R</span>
          <span class="portrait_comp_letter">A</span>
                    <span class="portrait_comp_letter">A</span>
          <span class="portrait_comp_letter">N</span>
          <span class="portrait_comp_letter">U</span>
                    </p>
{/if}
      </div>
      {#if visible}
      <div class = "portrait_vision"  style="height:19vh;display:-webkit-box;display:-ms-flexbox;display:flex;-webkit-box-align: center;-ms-flex-align: center;align-items: center;">
      <span class = "portrait_vision_content" in:fly="{{ x: 46, duration:5000 }}">ACCLERATING ADOPTION OF ELECTRIC MOBILITY</span>
      </div>
      {/if}
    </div>





  </div>
</Loader>

<style>

  /* Variables */
  :root {
    --atomsize: 19vh;
    --atomsize_portrait: 42vw;
    --companynamesize: 6.9vw;
    --portraitcompanynamesize:11vw;
    --companyexplnamesize: 3.6vw;
    --portraitcompanyexplnamesize: 4vh;
    --companynamesize_portrait: 9.2vw;
    --companynamewidthsize: 55vw;
    --companynamewidthsize_portrait: 90vw;
    --gsize: 1.5vh;
    --companyvisionsize: 1.6vw;
    --companyvisionsize_portrait: 4.2vw;
  }

:global(body) {
    height: 100vh;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-align: center;
        -ms-flex-align: center;
            align-items: center;
    -webkit-box-pack: center;
        -ms-flex-pack: center;
            justify-content: center;
    background: white;
  }
  
  /* Portrait */
:global(.Portrait .landscape_wrapper)
{
  display: none;
}

:global(.Landscape .landscape_wrapper) {
background:transparent;
  display: -ms-grid;
  display: grid;
  -ms-grid-columns: ()[1fr];
      grid-template-columns: repeat(1fr);
  grid-auto-rows: 10vh;
  gap: 1vh 1vw;
}

:global(.Portrait .portrait_wrapper)
{background:transparent;
  display: -ms-grid;
  display: grid;
  -ms-grid-columns: ()[1fr];
      grid-template-columns: repeat(1fr);
  
  }

:global(.Landscape .portrait_wrapper) {
  display: none;
}

@font-face {
    font-family: 'Gotu';
    src: url("/fonts/Gotu-Regular.woff2") format("woff2");
    font-style: normal;
  }

.company_name {
  font-family: 'Gotu';
  margin: 0;
  position: relative;
  top: 50%;
  left: 50%;
    -webkit-transform: translate(-50%, -50%);
          transform: translate(-50%, -50%);

    background: -webkit-linear-gradient(left, #fff, #000, #fff); 
    background: linear-gradient(90deg, #fff, #000, #fff);
      -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  background-repeat: no-repeat;
    background-size: 80%;
  -webkit-animation: shine 5s linear infinite;
          animation: shine 5s linear infinite;
  letter-spacing: 0.01em;
}
.expl_letter{
   font-size: var(--companyexplnamesize);
}
.portrait_expl_letter{
   font-size: var(--portraitcompanyexplnamesize);

}
.comp_letter{
  font-size: var(--companynamesize);

}
.portrait_comp_letter{
  font-size: var(--portraitcompanynamesize);

}
@-webkit-keyframes shine {
  0% {
    background-position-x: -500%;
  }
  100% {
    background-position-x: 500%;
  }
}
@keyframes shine {
  0% {
    background-position-x: -500%;
  }
  100% {
    background-position-x: 500%;
  }
}
.portrait_company_name {
  font-family: 'Gotu';
  margin: 0;
  position: relative;

  letter-spacing: 0.01em;
  background: -webkit-linear-gradient(left, #fff, #000, #fff);
  background: linear-gradient(90deg, #fff, #000, #fff);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  background-repeat: no-repeat;
  background-size: 80%;
  -webkit-animation: shine 5s linear infinite;
          animation: shine 5s linear infinite;

  
  font-size: var(--companynamesize_portrait);
  }


@-webkit-keyframes rotate {
  to {
    -webkit-transform: rotate(360deg);
            transform: rotate(360deg);
  }
}
@keyframes rotate {
  to {
    -webkit-transform: rotate(360deg);
            transform: rotate(360deg);
  }
}

.portrait_wrapper{
background:transparent;
  -ms-grid-columns: (1fr)[3];
      grid-template-columns: repeat(3, 1fr);
  -ms-grid-rows: auto 60% 18% 10% auto;
      grid-template-rows: auto 60% 18% 10% auto;
  -ms-grid-column-align: center;
      justify-items: center;
  -ms-flex-line-pack: center;
      align-content: center; 
  gap: 1vh 1vh;
}

.loading {
background:transparent;
  width: var(--atomsize);
  height: var(--atomsize);
  -ms-grid-column: 1;
      grid-column-start: 1;
  grid-column-end: 1;
  -ms-grid-row: 1;
      grid-row-start: 1;
  grid-row-end: 2;
  position:relative;
}

.portrait_loading {
background:transparent;
  width: var(--atomsize_portrait);
  height: var(--atomsize_portrait);
  -ms-grid-column: 2;
      grid-column-start: 2;
  grid-column-end: 3;
  -ms-grid-row: 2;
      grid-row-start: 2;
  grid-row-end: 3;
  position:relative;
}
.name{
background:transparent;
  -webkit-user-select: none;
     -moz-user-select: none;
      -ms-user-select: none;
          user-select: none;
  width: var(--companynamewidthsize);
  -ms-grid-column: 2;
      grid-column-start: 2;
  grid-column-end: 2;
  -ms-grid-row: 1;
      grid-row-start: 1;
  grid-row-end: 2;
}
.portrait_name{
background:transparent;
  -webkit-user-select: none;
     -moz-user-select: none;
      -ms-user-select: none;
          user-select: none; 
  width: var(--companynamewidthsize_portrait);
  -ms-grid-column: 2;
      grid-column-start: 2;
  grid-column-end: 3;
  -ms-grid-row: 3;
      grid-row-start: 3;
  grid-row-end: 4;
  height:18vh;
  width:91vw;

}
.vision{
    -webkit-user-select: none; /* Safari */ /* Konqueror HTML */
       -moz-user-select: none; /* Old versions of Firefox */
        -ms-user-select: none; /* Internet Explorer/Edge */
            user-select: none; /* Non-prefixed version, currently supported by Chrome, Edge, Opera and Firefox */
  background:white;
  width: var(--companynamewidthsize);
  text-align: left;
  height: 4vh;
  -ms-grid-column: 2;
      grid-column-start: 2;
  grid-column-end: 2;
  -ms-grid-row: 2;
      grid-row-start: 2;
  grid-row-end: 2;
}
.portrait_vision{
    -webkit-user-select: none; /* Safari */ /* Konqueror HTML */
       -moz-user-select: none; /* Old versions of Firefox */
        -ms-user-select: none; /* Internet Explorer/Edge */
            user-select: none; /* Non-prefixed version, currently supported by Chrome, Edge, Opera and Firefox */
  background:transparent;
  width: var(--companynamewidthsize_portrait);
  text-align: center;
  height: 4vh;
  -ms-grid-column: 2;
      grid-column-start: 2;
  grid-column-end: 3;
  -ms-grid-row: 4;
      grid-row-start: 4;
  grid-row-end: 5;
  -ms-flex-item-align: start;
      -ms-grid-row-align: start;
      align-self: start;
}
.vision_content{
  font-family: 'Gotu';
  display: inline-block;
  width: var(--companynamewidthsize);
  font-size: var(--companyvisionsize);
  display: inline-block;
  background:transparent;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  -webkit-box-pack: center;
      -ms-flex-pack: center;
          justify-content: center;

}
.portrait_vision_content{
background:transparent;
top:10vh;
  font-family: 'Gotu';
  width: var(--companynamewidthsize_portrait);
  font-size: var(--companyvisionsize_portrait);
  display: inline-block;
  background:white;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  -webkit-box-pack: center;
      -ms-flex-pack: center;
          justify-content: center;

}
.loading__ring {
  position: absolute;
  width: var(--atomsize);
  height: var(--atomsize);
}
.portrait_loading__ring {
  position: absolute;
  width: var(--atomsize_portrait);
  height: var(--atomsize_portrait);
}
.loading__ring:first-child {
-webkit-transform: skew(130deg,15deg);
  transform: skew(130deg,15deg);
}
.portrait_loading__ring:first-child {
  -webkit-transform: skew(130deg,15deg);
  transform: skew(130deg,15deg);
}
.loading__ring:last-child {
  -webkit-transform: skew(-130deg,-1deg) scale(-1, 1);
  transform: skew(-130deg,-1deg) scale(-1, 1);
}
.portrait_loading__ring:last-child {
  -webkit-transform: skew(-130deg,-1deg) scale(-1, 1);
          transform: skew(-130deg,-1deg) scale(-1, 1);
}
.loading__ring:last-child svg {
  -webkit-animation-delay: -0.91s;
          animation-delay: -0.91s;
}
.portrait_loading__ring:last-child svg {
  -webkit-animation-delay: -0.91s;
          animation-delay: -0.91s;
}
.loading__ring svg {
  -webkit-animation: rotate 1s linear infinite;
          animation: rotate 1s linear infinite;
  fill: rgba(0, 0, 0, 0.2);
}
.portrait_loading__ring svg {
  -webkit-animation: rotate 1s linear infinite;
          animation: rotate 1s linear infinite;
  fill: rgba(0, 0, 0, 0.2);
}
</style>