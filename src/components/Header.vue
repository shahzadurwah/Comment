<template>
  <div class="row">
    <div class="col-sm-12 col-md-10">
        <h1>Quotes Added</h1>
      <div class="progress">
        <div
          class="progress-bar"
          role="progressbar"
          
          
          :style="{width:(quotelength/maxquotes)*100 + '%'}"
          aria-valuenow="100"
          aria-valuemin="0"
          aria-valuemax="100">{{maxquotes}} / {{quotelength}}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name:'Header',
    props:['maxquotes','quotelength']
};
</script>

<style>
</style>