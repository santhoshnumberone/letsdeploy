<script>
	import { MetaTags } from 'svelte-meta-tags';
	import Viewport from 'svelte-viewport-info';

	import logo from '/src/assets/CompanyName1.png'
	import creditimg from '/src/assets/VideoCredit.png'
	import contactimg from '/src/assets/PleaseContact.png'

	import plogo from '/src/assets/CompanyName2.png'
  import rotatescreen from '/src/assets/RotateToLandscape.png'

  import viav1 from '/src/assets/2021GISStemp.mp4'
  import vix265 from '/src/assets/2021GISStempF-5yrAvgaudiolessx265.mp4'
  import viwebm from '/src/assets/2021GISStempF-5yrAvgaudioless.webm'
  import posterimg from '/src/assets/PosterImage.png'

	let outerWidth = 0
	let outerHeight = 0

	$: condition = outerWidth*1.33 >= outerHeight

</script>
<svelte:window bind:outerWidth bind:outerHeight />
<svelte:body/>

<div class="main_wrapper">
	<div class="video_wrapper">
    <video
      autoplay 
      muted 
      loop
      Playsinline
      controls
      poster={posterimg}>
      <source src={viav1} type="video/mp4"/>
      <source src={vix265} type="video/mp4"/>
      <source src={viwebm} type="video/webm"/>
    </video>
	</div>
	<div class="company_name_wrapper">
		<img class="companynamelogo" src={logo} alt="Svelte Logo"/>
	</div>
	<div class="credit_contact_wrapper">
		<a href="https://svs.gsfc.nasa.gov/4964" class="creditsection">
		<img class="creditlogo"src={creditimg} alt="Svelte Logo" />
		</a>
		<a href="https://www.linkedin.com/in/santhosh-electraanu" class="contactsection">
		<img class="contactlogo"src={contactimg} alt="Svelte Logo" />
		</a>
	</div>
</div>

<div class="message">
<div class="potraitcontent" >
<img class="cimage-basic" class:cimage-conditional={condition} src={plogo} alt="Svelte Logo" />
<img class="rotatephone" class:rotatephoneconditional={condition} src={rotatescreen} alt="Svelte Logo" />
</div>
</div>

<style>

@font-face {
    font-family: 'Gotu';
    src: url("/fonts/Gotu-Regular.woff2") format("woff2");
    font-style: normal;
  }
  @-webkit-keyframes fadeOut {
      from {opacity: 1;}
    to {opacity: 0;
        width:0;
        height:0;
        visibility:hidden;
    }
}
video 
{
  width: 100%;
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
      user-select: none;
  
}


.rotatephone
{
display: -ms-inline-grid;
display: inline-grid;
  -ms-grid-row: 3;
      grid-row-start: 3;
  grid-row-end: 4;
  justify-self: center;
  -ms-grid-row-align: center;
      align-self: center;
  place-self: center;
  height: auto;
  width: 60vw;
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
      user-select: none;
  pointer-events: none;
}

.rotatephoneconditional
{
display: -ms-inline-grid;
display: inline-grid;
  -ms-grid-row: 3;
      grid-row-start: 3;
  grid-row-end: 4;
  justify-self: center;
  -ms-grid-row-align: center;
      align-self: center;
  place-self: center;
  height: auto;
  width: 43vw;
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
      user-select: none;
  pointer-events: none;
}
.cimage-basic
{
  -ms-grid-row: 2;
      grid-row-start: 2;
  grid-row-end: 3;
  display: -ms-inline-grid;
  display: inline-grid;
  justify-self: center;
  -ms-grid-row-align: center;
      align-self: center;
  place-self: center;
  height: 78vw/2.81vh;
  width: 78vw;
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
      user-select: none;
  pointer-events: none;
}

.cimage-conditional
{
  -ms-grid-row: 2;
      grid-row-start: 2;
  grid-row-end: 3;
  display: -ms-inline-grid;
  display: inline-grid;
  justify-self: center;
  -ms-grid-row-align: center;
      align-self: center;
  place-self: center;
  height: 59vw/2.81vh;
  width: 59vw;
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
      user-select: none;
  pointer-events: none;
}
.potraitcontent
{
  box-shadow: rgba(50, 50, 93, 0.25) 0px 50px 100px -20px, rgba(0, 0, 0, 0.3) 0px 30px 60px -30px, rgba(10, 37, 64, 0.35) 0px -2px 6px 0px inset;
  display: -ms-grid;
  display: grid;
  -ms-grid-column-align: center;
      justify-items: center;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  -webkit-box-pack: space-evenly;
      -ms-flex-pack: space-evenly;
          justify-content: space-evenly;
  -ms-flex-line-pack: space-evenly;
      align-content: space-evenly;
  place-items: center;
  -ms-grid-rows: 20% auto auto 20%;
      grid-template-rows: 20% auto auto 20%;
  border-radius: 20px;
  width: 82vw;
  min-height: 69vh;
}

:global(.Portrait .message)
{
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
}

:global(.Landscape .message)
{
  display: none;
}

.message 
{
  height:100%;
  width:100%;
  background:white;
  position:absolute;
  top:0px;
  right:0px;
  bottom:0px;
  left:0px;
}

:global(body) {
    height: 100vh;
    -webkit-box-align: center;
        -ms-flex-align: center;
            align-items: center;
    -webkit-box-pack: center;
        -ms-flex-pack: center;
            justify-content: center;
    background: black;
  }
:global(.Portrait .main_wrapper) {
  display:none;
}

:global(.Landscape .main_wrapper){
  display:-ms-grid;
  display:grid;
  -ms-grid-columns: (1fr)[3];
      grid-template-columns: repeat(3, 1fr);
  gap: 1px;
  grid-auto-rows: minmax(100px, auto);
  background:black;
  width:100vw;
  height:100vh;
}

:global(.Portrait .video_wrapper) {
  display:none;
}

:global(.Landscape .video_wrapper){
  grid-column: 1/4;
  grid-row:1/4;
  display: -ms-grid;
  display: grid;
  position: relative;
  width:100%;
  height:100%;
  background:black;
  -webkit-box-pack: center;
      -ms-flex-pack: center;
          justify-content: center;
  -ms-flex-line-pack: center;
      align-content: center;

}

:global(.Portrait .company_name_wrapper) {
  display:none;
}

:global(.Landscape .company_name_wrapper) {
  grid-column: 1/4;
  -ms-grid-row:1;
      grid-row:1; 

  top: 1.5rem;
  text-align: right;
  right: 1rem;
  position: fixed;
  color: #f1f1f1;
  width: 100%;

}

.companynamelogo 
{
  height: 1.69rem;
  width: 9rem;

  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
      user-select: none;
  pointer-events: none;
}


:global(.Portrait .credit_contact_wrapper) {
  display:none;
}

:global(.Landscape .credit_contact_wrapper)
{
  grid-column: 1/4;
  -ms-grid-row:3;
      grid-row:3; 

  display: -webkit-box; 

  display: -ms-flexbox; 

  display: flex;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  -ms-flex-wrap: wrap;
      flex-wrap: wrap;
  -webkit-box-pack: space-evenly;
      -ms-flex-pack: space-evenly;
          justify-content: space-evenly;
  bottom: 1.5rem;
  text-align: left;
  align-items:center;
  position: relative;
  color: #f1f1f1;
  width: 100%;

}

.creditlogo 
{
  box-shadow: rgba(6, 24, 44, 0.4) 0px 0px 0px 2px, rgba(6, 24, 44, 0.65) 0px 4px 6px -1px, rgba(255, 255, 255, 0.08) 0px 1px 0px inset;    
  height: 1.44rem;
  width: 15rem;
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
      user-select: none;
  pointer-events: none;
}
.creditsection
{
opacity: 0.87;
}
.creditsection:hover
{
opacity: 1.0;
}

.contactlogo 
{
  box-shadow: rgba(6, 24, 44, 0.4) 0px 0px 0px 2px, rgba(6, 24, 44, 0.65) 0px 4px 6px -1px, rgba(255, 255, 255, 0.08) 0px 1px 0px inset; 
  height: 6.78rem;
  width: 19rem;
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
      user-select: none;
  pointer-events: none;
}

.contactsection
{
opacity: 0.87;
}
.contactsection:hover
{
opacity: 1.0;
}
</style>