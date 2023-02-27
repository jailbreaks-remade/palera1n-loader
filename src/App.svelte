<script lang="ts">
  import { onMount } from "svelte";
  import platform from 'platform'
  import palerain from '../src/palera1n.png'
  import { escape } from "svelte/internal";
    import ButtonContainer from "./comp/ButtonContainer.svelte";

  function iPhoneVersion() {
      var iHeight = window.screen.height;
      var iWidth = window.screen.width;

      if (iWidth === 375 && iHeight === 812) {
        return "X-Xs";
      }
      if (iWidth === 414 && iHeight === 896) {
        return "Xsmax-Xr";
      }
      else if (iWidth === 320 && iHeight === 480) {
        return "4";
      }
      else if (iWidth === 414 && iHeight === 896) {
        return "11";
      }
      else if (iWidth === 375 && iHeight === 812) {
        return "11 Pro";
      }
      else if (iWidth === 414 && iHeight === 896) {
        return "11 Pro Max";
      }
      else if (iWidth === 375 && iHeight === 667) {
        return "SE 2nd gen";
      }
      else if (iWidth === 414 && iHeight === 736) {
        return "6+";
      }
      else if (iWidth === 320 && iHeight === 568) {
        return "5";
      }
      else if (iWidth === 390 && iHeight === 844) {
        return "12-12 Pro";
      }
      else if (iWidth === 428 && iHeight === 926) {
        return "12/13 Pro Max";
      }
      else if (iWidth === 430 && iHeight === 932) {
        return "14 Pro Max";
      }
      else if (iWidth === 360 && iHeight === 780) {
        return "12 mini";
      }
      else if (iHeight <= 480) {
        return "2-3";
      }
      return '';
    }

  let info: any;
  let name: any;
  let device: any;
  let deviceWidth: string;
  let prefix: string = "[*]"
  onMount(async () => {
    device = platform.product;
    name = platform.version;
    info = platform.os;
    deviceWidth = iPhoneVersion();
  });

  let deleteElements: boolean = false;
  let showFirstText: boolean;
  let showSecondText: boolean;
  let showThirdText: boolean;
  let showFourthText: boolean;
  let showFifthText: boolean;
  let showSixthText: boolean;

  const runJailbreak = async() => {
    deleteElements = true
    setTimeout(() => {  showFirstText = true; }, 2500);
    setTimeout(() => {  showSecondText = true; }, 2500 * 2);
    setTimeout(() => {  showThirdText = true; }, 2500 * 2.5);
    setTimeout(() => {  showFourthText = true; }, 2500 * 3.5);
    setTimeout(() => {  showFifthText = true; }, 2500 * 4);
    setTimeout(() => {  showSixthText = true; }, 2500 *  6);
  }
</script>

<div class="allbox">
  <h1><img alt="" class="header" src={palerain}/>palera1n</h1>

  <div class="bigbox">
    <div class="padding RobotoMono-Regular">
      <p>Welcome to palera1n loader</p>
      <p>Darwin Kernel Version 21.6.0: Thu Aug 11 21:44:33 PDT 2022; root:xnu-8020.241.2~1/RELEASE_ARM64_S8000</p>
      <p>{device} {deviceWidth} running {info} </p>
      {#if deleteElements}
        {prefix} ...
      {/if}
      {#if showFirstText}
        <p>{prefix} Starting bootsrap process</p>
      {/if}
      {#if showSecondText}
        <p>{prefix} Installing packages</p>
      {/if}
      {#if showThirdText}
        <p>{prefix} Running uichache</p>
      {/if}
      {#if showFourthText}
        <p>{prefix} Installing palera1n</p>
      {/if}
      {#if showFifthText}
        <p>{prefix} Preparing Sileo...</p>
      {/if}
      {#if showSixthText}
        <p>{prefix} Something went wrong... </p>
      {/if}
    </div>
  </div>

  {#if deleteElements === true}
    <ButtonContainer func style="scale: 0%"/>
  {:else}
    <ButtonContainer func={runJailbreak} style="scale: 100%"/>
  {/if}
</div>