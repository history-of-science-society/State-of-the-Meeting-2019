
<script>
import { generateChart } from 'vue-chartjs'

const customChart = generateChart('no-app-use', 'pie')

export default {
  extends: customChart,
  data: () => ({
    chartdata: {
      labels: ['Other (24%)','Didn\'t know about it (20%)','Didn\'t have time to download it (20%)','Don\'t use a smart phone or tablet (18%)','Not tech savvy (12%)','App not user friendly (7%)'],
      datasets: [
        {
          data: [46,37,37,34,22,13],
          backgroundColor: ['#38a5b8','#b84b38','#d38a45','#ffd657','#82ba5c','#945cba']
        }
      ]
    },
    options: {
      legend: {
        display: true
      },
      title: {
        display: 'true',
        text: 'Reasons for Not Using the Meeting App'
      },
      maintainAspectRatio: false,
    }
  }),
  mounted () {
    this.renderChart(this.chartdata, this.options)
    Chart.defaults.global.defaultFontFamily = '-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol"';
    Chart.defaults.global.defaultFontSize = 15;
    Chart.defaults.global.defaultFontColor = '#333';
    Chart.defaults.global.legend.display = false;

  }
}

</script>