<template>
    <div>   
        <h1>Temperature: {{temp}}°C</h1>
    </div>
</template>

<script>

import axios from "axios";

export default {
    name: "WeatherInfo",
    data() {
        return {
            temp: Number
        }
    },
    created() {
        axios.get('https://opendata-download-metfcst.smhi.se/api/category/pmp3g/version/2/geotype/point/lon/18.0725/lat/59.43942/data.json')
        .then((res) => {
            console.log(res.data.timeSeries[0].parameters[11]);
            this.temp = res.data.timeSeries[0].parameters[11].values[0];
        })
        .catch(err => console.log(err));
    }
}
</script>

<style scoped>

</style>