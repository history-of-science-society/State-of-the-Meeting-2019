<script>
import { generateChart } from 'vue-chartjs'

const totalSubs = generateChart('total-abstract-submissions', 'horizontalBar')

export default {
  extends: totalSubs,
  data: () => ({

    chartdata: {
      labels: ['Life Sciences', 'Human and Social Sciences', 'Medicine and Health', 'Historiography', 'Physical Sciences', 'Natural Philosophy', 'Environmental Sciences', 'Technology', 'Non-Western Science', 'Practical Knowledge', 'Mathematics'],
      datasets: [
        {
          data: [52 ,50, 43, 38, 34, 27, 25, 18, 17, 15, 4],
          backgroundColor: ['#38a5b8','#b84b38','#d38a45','#ffd657','#82ba5c','#945cba','#3865b8','#b83865','#ff8257','#d3d145','#ba5cb1']
        }
      ]
    },
    options: {
      legend: {
        display: false
      },
      title: {
        display: 'true',
        text: 'Abstract Submissions by Topic (2018)'
      },
      responsive: true,
      maintainAspectRatio: false,
      scales: {
            yAxes: [{
                ticks: {
                    beginAtZero: true
                }
            }]
        }
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

