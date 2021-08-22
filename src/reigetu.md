{{first:2021-04-05}}

{{description:令和3年1月から12月に報告された小平市の現金出納検査結果です。基金残高の推移などをグラフで分かりやすく表示しています。}}

# 例月現金出納検査

令和3年1月から12月に報告された現金収支、現金保管の状況（各月末日時点）等についての検査結果報告です。

<table>
<thead>
<tr>
<th>定例会</th>
<th>報告された分</th>
</tr>
</thead>
<tr><td>3月定例会</td><td>令和2年10月,11月,12月分</td></tr>
<tr><td>4月臨時会</td><td>令和3年1月分</td></tr>
<tr><td>6月定例会</td><td>令和3年2月分,3月分</td></tr>
</table>

## 1. 予算現額推移
参考として、予算額の推移です。年度中の額は補正予算によって変更されます。

令和2年10月から令和3年3月分については、特記することはありません。

<script type="text/javascript" src="https://www.gstatic.com/charts/loader.js"></script>

<div id="yosan-gengaku-dashboard">
  <div id="yosan-gengaku-chart" class="reigetu-chart"></div>
  <div id="yosan-gengaku-control" class="reigetu-control"></div>
</div>

<script type="text/javascript">
  //global
  var startDate = new Date(2019, 9, 0);
  var endDate =   new Date(2021, 3, 0);
  var tickDates = [
    {v: new Date(2019, 4, 1), f: '平成31年4月'},
    {v: new Date(2020, 4, 0), f: '令和2年4月'},
  ];
  var chartOptions = {
    fontName: "UD デジタル 教科書体 N-R",
    fontSize: 14,
    chart: {
      title: '予算現額推移',
      titleTextStyle: {
          fontSize: 18
      },
    },
    vAxis: {
      format: '#.##億円',
      textStyle: {
        fontSize: 16,
      },
    },
    hAxis: { slantedText: false },
    chartArea:{ top:30, left:80, height:'80%', width: '85%' },
    legend: { position: 'top' },
    annotations: { style: 'line' }
  }
  var CustomFormatter = function(formatValue) {
    this.formatValue = formatValue;
  }
  CustomFormatter.prototype.format = function(dt, column) {
    for (var i = 0; i < dt.getNumberOfRows(); i++) {
      var value = dt.getValue(i, column);
      dt.setFormattedValue(i, column, this.formatValue(value));
    }
  }
  var customFormatter = new CustomFormatter(function(date) {
    return(new Intl.DateTimeFormat('ja-JP-u-ca-japanese', { era: 'short', year:'numeric', month:'numeric' }).format(date));
  });
  var chartViewColumn0 = {
    calc: function(dataTable, rowIndex) {
      return dataTable.getFormattedValue(rowIndex, 0);
    },
    type: 'string'
  };
  google.charts.load('current', { packages: ['controls', 'corechart', 'line'] });
  </script>

  <script type="text/javascript">
  google.charts.setOnLoadCallback(drawChart1);
  function drawChart1() {
    var dashboard = new google.visualization.Dashboard(document.getElementById('yosan-gengaku-dashboard'));
    var control = new google.visualization.ControlWrapper({
      controlType: 'ChartRangeFilter',
      containerId: 'yosan-gengaku-control',
      options: {
        filterColumnIndex: 0,
        ui: {
          chartType: 'LineChart',
          chartOptions: {
            chartArea: { width: '95%' },
            hAxis: { ticks: tickDates }
          },
          chartView: { columns: [0, 2] },
        }
      },
      state: { range: { start: startDate, end: endDate }}
    });
    var chart = new google.visualization.ChartWrapper({
      chartType: 'LineChart',
      containerId: 'yosan-gengaku-chart',
      options: chartOptions,
      view: { columns: [chartViewColumn0, 1, 2, 3, 4, 5] },
    });
    const data = new google.visualization.DataTable();
    data.addColumn('date', '年月');
    data.addColumn({type: 'string', role: 'annotation'});
    data.addColumn('number', '一般会計');
    data.addColumn('number', '国保特会');
    data.addColumn('number', '後期高医特会');
    data.addColumn('number', '介護保険特会');
    data.addRows([
      [new Date(2019, 4, 0), "平成31年4月", 663.5, 168.7, 43.49, 135.5],
      [new Date(2019, 5, 0), null, 663.5, 168.7, 43.49, 135.5],
      [new Date(2019, 6, 0), null, 665.8, 168.7, 43.49, 135.5],
      [new Date(2019, 7, 0), null, 665.8, 168.7, 43.49, 135.5],
      [new Date(2019, 8, 0), null, 665.8, 168.7, 43.49, 135.5],
      [new Date(2019, 9, 0), null, 685.4, 170.2, 43.76, 138.1],
      [new Date(2019, 10, 0), null, 685.4, 170.2, 43.76, 138.1],
      [new Date(2019, 11, 0), null, 685.4, 170.2, 43.76, 138.1],
      [new Date(2019, 12, 0), null, 688.9, 170.2, 43.76, 138.1],
      [new Date(2020, 1, 0), null, 688.7, 170.2, 43.76, 138.1],
      [new Date(2020, 2, 0), null, 688.7, 170.2, 43.76, 138.1],
      [new Date(2020, 3, 0), null, 677.8, 172.2, 43.4, 138.1],
      [new Date(2020, 4, 0), "令和2年4月", 690.9, 170, 44.7, 141.7],
      [new Date(2020, 5, 0), null, 906.2, 170, 44.7, 141.7],
      [new Date(2020, 6, 0), null, 908.7, 170, 44.7, 141.7],
      [new Date(2020, 7, 0), null, 908.7, 170, 44.7, 141.7],
      [new Date(2020, 8, 0), null, 924.8, 170, 44.7, 141.7],
      [new Date(2020, 9, 0), null, 942.6, 171, 44.91, 144.1],
      [new Date(2020, 10, 0), null, 942.6, 171, 44.91, 144.1],
      [new Date(2020, 11, 0), null, 944.4, 171, 44.91, 144.1],
      [new Date(2020, 12, 0), null, 943.7, 171, 44.91, 144.1],
      [new Date(2021, 1, 0), null, 943.7, 171, 44.91, 144.1],
      [new Date(2021, 2, 0), null, 956.8, 171, 44.91, 144.1],
      [new Date(2021, 3, 0), null, 949.4, 171, 44.56, 144.1],
    ]);
    customFormatter.format(data, 0);
    dashboard.bind(control, chart);
    dashboard.draw(data);
  }
</script>

## 2. 収入・支出の推移

### 2.1. 一般会計

<div id="ippan-syunyu-syusyutu-dashboard">
  <div id="ippan-syunyu-syusyutu-chart" class="reigetu-chart"></div>
  <div id="ippan-syunyu-syusyutu-control" class="reigetu-control"></div>
</div>

<script type="text/javascript">
  google.charts.setOnLoadCallback(drawChart2);
  function drawChart2() {
    var dashboard = new google.visualization.Dashboard(document.getElementById('ippan-syunyu-syusyutu-dashboard'));
    var control = new google.visualization.ControlWrapper({
      controlType: 'ChartRangeFilter',
      containerId: 'ippan-syunyu-syusyutu-control',
      options: {
        filterColumnIndex: 0,
        ui: {
          chartType: 'ComboChart',
          chartOptions: {
            chartArea: {width: '95%'},
            hAxis: {ticks: tickDates },
            seriesType: 'bars',
          },
          chartView: {
            columns: [0, 2, 3],
          },
        }
      },
      state: { range: { start: startDate, end: endDate }}
    });
    var chart = new google.visualization.ChartWrapper({
      chartType: 'ComboChart',
      containerId: 'ippan-syunyu-syusyutu-chart',
      options: Object.assign({}, chartOptions, {seriesType: "bars"}),
      view: { columns: [chartViewColumn0, 1, 2, 3] }
    });
    const data = new google.visualization.DataTable();
    data.addColumn('date', '年月');
    data.addColumn({type: 'string', role: 'annotation'});
    data.addColumn('number', '一般会計・収入');
    data.addColumn('number', '一般会計・支出');
    data.addRows([
      [new Date(2019, 4, 0), "平成31年4月", 17.62, 32.08],
      [new Date(2019, 5, 0), null, 48.85, 34.12],
      [new Date(2019, 6, 0), null, 108.1, 55.61],
      [new Date(2019, 7, 0), null, 35.92, 49.5],
      [new Date(2019, 8, 0), null, 50.43, 50.98],
      [new Date(2019, 9, 0), null, 57.36, 48.72],
      [new Date(2019, 10, 0), null, 26.88, 63.18],
      [new Date(2019, 11, 0), null, 37.15, 33.05],
      [new Date(2019, 12, 0), null, 35.3, 63.92],
      [new Date(2020, 1, 0), null, 53.85, 45.84],
      [new Date(2020, 2, 0), null, 25.97, 47.85],
      [new Date(2020, 3, 0), null, 156.8, 79.9],
      [new Date(2020, 4, 0), "令和2年4月", 17.96, 35.08],
      [new Date(2020, 5, 0), null, 146.1, 39.04],
      [new Date(2020, 6, 0), null, 217.7, 211.1],
      [new Date(2020, 7, 0), null, 40.61, 95.07],
      [new Date(2020, 8, 0), null, 52.32, 35.24],
      [new Date(2020, 9, 0), null, 56.67, 52.25],
      [new Date(2020, 10, 0), null, 20.28, 58.81],
      [new Date(2020, 11, 0), null, 33.77, 42.89],
      [new Date(2020, 12, 0), null, 59.63, 71.67],
      [new Date(2021, 1, 0), null, 50.81, 47.78],
      [new Date(2021, 2, 0), null, 32.46, 53.91],
      [new Date(2021, 3, 0), null, 176.8, 94.87],
    ]);
    customFormatter.format(data, 0);
    dashboard.bind(control, chart);
    dashboard.draw(data);
  }
</script>

### 2.2. 国民健康保険特別会計

<div id="kokuho-syunyu-syusyutu-dashboard">
  <div id="kokuho-syunyu-syusyutu-chart" class="reigetu-chart"></div>
  <div id="kokuho-syunyu-syusyutu-control" class="reigetu-control"></div>
</div>

<script type="text/javascript">
  google.charts.setOnLoadCallback(drawChart3);
  function drawChart3() {
    var dashboard = new google.visualization.Dashboard(document.getElementById('kokuho-syunyu-syusyutu-dashboard'));
    var control = new google.visualization.ControlWrapper({
      controlType: 'ChartRangeFilter',
      containerId: 'kokuho-syunyu-syusyutu-control',
      options: {
        filterColumnIndex: 0,
        ui: {
          chartType: 'ComboChart',
          chartOptions: {
            chartArea: { width: '95%' },
            hAxis: { ticks: tickDates },
            seriesType: 'bars',
          },
          chartView: {
            columns: [0, 2, 3],
          },
        }
      },
      state: { range: { start: startDate, end: endDate }}
    });
    var chart = new google.visualization.ChartWrapper({
      chartType: 'ComboChart',
      containerId: 'kokuho-syunyu-syusyutu-chart',
      options: Object.assign({}, chartOptions, {seriesType: "bars"}),
      view: { columns: [chartViewColumn0, 1, 2, 3] }
    });
    const data = new google.visualization.DataTable();
    data.addColumn('date', '年月');
    data.addColumn({ type: 'string', role: 'annotation' });
    data.addColumn('number', '国保特会・収入');
    data.addColumn('number', '国保特会・支出');
    data.addRows([
      [new Date(2019, 4, 0), "平成31年4月", 1.566, 1.175],
      [new Date(2019, 5, 0), null, 9.304, 9.185],
      [new Date(2019, 6, 0), null, 10.77, 9.415],
      [new Date(2019, 7, 0), null, 12.08, 8.874],
      [new Date(2019, 8, 0), null, 24.14, 16.24],
      [new Date(2019, 9, 0), null, 14.39, 16.74],
      [new Date(2019, 10, 0), null, 13.85, 17.13],
      [new Date(2019, 11, 0), null, 12.74, 16.12],
      [new Date(2019, 12, 0), null, 23.99, 24.12],
      [new Date(2020, 1, 0), null, 13.25, 9.585],
      [new Date(2020, 2, 0), null, 12.08, 16.08],
      [new Date(2020, 3, 0), null, 16.44, 17.28],
      [new Date(2020, 4, 0), "令和2年4月", 1.605, 1.258],
      [new Date(2020, 5, 0), null, 9.223, 9.1],
      [new Date(2020, 6, 0), null, 9.68, 8.736],
      [new Date(2020, 7, 0), null, 21.38, 7.763],
      [new Date(2020, 8, 0), null, 13.72, 15.56],
      [new Date(2020, 9, 0), null, 13.28, 15.79],
      [new Date(2020, 10, 0), null, 12.64, 15.78],
      [new Date(2020, 11, 0), null, 13.24, 15.97],
      [new Date(2020, 12, 0), null, 23.10, 17.17],
      [new Date(2021, 1, 0), null, 14.19, 16.47],
      [new Date(2021, 2, 0), null, 12.61, 16.51],
      [new Date(2021, 3, 0), null, 13.49, 17.31],
    ]);
    customFormatter.format(data, 0);
    dashboard.bind(control, chart);
    dashboard.draw(data);
  }
</script>

### 2.3. 後期高齢者医療保険特別会計

現状で特記することはありません。

<div id="kouki-syunyu-syusyutu-dashboard">
  <div id="kouki-syunyu-syusyutu-chart" class="reigetu-chart"></div>
  <div id="kouki-syunyu-syusyutu-control" class="reigetu-control"></div>
</div>

<script type="text/javascript">
  google.charts.setOnLoadCallback(drawChart4);
  function drawChart4() {
    var dashboard = new google.visualization.Dashboard(document.getElementById('kouki-syunyu-syusyutu-dashboard'));
    var control = new google.visualization.ControlWrapper({
      controlType: 'ChartRangeFilter',
      containerId: 'kouki-syunyu-syusyutu-control',
      options: {
        filterColumnIndex: 0,
        ui: {
          chartType: 'ComboChart',
          chartOptions: {
            chartArea: { width: '95%' },
            hAxis: { ticks: tickDates },
            seriesType: 'bars',
          },
          chartView: {
            columns: [0, 2, 3],
          },
        }
      },
      state: { range: { start: startDate, end: endDate }}
    });
    var chart = new google.visualization.ChartWrapper({
      chartType: 'ComboChart',
      containerId: 'kouki-syunyu-syusyutu-chart',
      options: Object.assign({}, chartOptions, {seriesType: "bars"}),
      view: { columns: [chartViewColumn0, 1, 2, 3] }
    });
    const data = new google.visualization.DataTable();
    data.addColumn('date', '年月');
    data.addColumn({ type: 'string', role: 'annotation' });
    data.addColumn('number', '後期高医特会・収入');
    data.addColumn('number', '後期高医特会・支出');
    data.addRows([
      [new Date(2019, 4, 0), "平成31年4月", 3.407, 2.919],
      [new Date(2019, 5, 0), null, 2.197, 2.206],
      [new Date(2019, 6, 0), null, 2.832, 2.177],
      [new Date(2019, 7, 0), null, 2.511, 2.223],
      [new Date(2019, 8, 0), null, 2.1, 2.248],
      [new Date(2019, 9, 0), null, 3.057, 2.281],
      [new Date(2019, 10, 0), null, 3.48, 4.075],
      [new Date(2019, 11, 0), null, 4.175, 4.159],
      [new Date(2019, 12, 0), null, 3.688, 4.18],
      [new Date(2020, 1, 0), null, 4.842, 4.447],
      [new Date(2020, 2, 0), null, 3.887, 4.266],
      [new Date(2020, 3, 0), null, 7.053, 7.803],
      [new Date(2020, 4, 0), "令和2年4月", 3.408, 2.954],
      [new Date(2020, 5, 0), null, 2.108, 2.205],
      [new Date(2020, 6, 0), null, 2.891, 2.264],
      [new Date(2020, 7, 0), null, 2.313, 2.265],
      [new Date(2020, 8, 0), null, 2.333, 2.373],
      [new Date(2020, 9, 0), null, 3.019, 2.31],
      [new Date(2020, 10, 0), null, 3.463, 4.316],
      [new Date(2020, 11, 0), null, 4.419, 4.241],
      [new Date(2020, 12, 0), null, 3.810, 4.336],
      [new Date(2021, 1, 0), null, 5.038, 4.65],
      [new Date(2021, 2, 0), null, 3.797, 4.306],
      [new Date(2021, 3, 0), null, 7.812, 7.899],
    ]);
    customFormatter.format(data, 0);
    dashboard.bind(control, chart);
    dashboard.draw(data);
  }
</script>

### 2.4. 介護保険特別会計

現状で特記することはありません。

<div id="kaigo-syunyu-syusyutu-dashboard">
  <div id="kaigo-syunyu-syusyutu-chart" class="reigetu-chart"></div>
  <div id="kaigo-syunyu-syusyutu-control" class="reigetu-control"></div>
</div>

<script type="text/javascript">
  google.charts.setOnLoadCallback(drawChart5);
  function drawChart5() {
    var dashboard = new google.visualization.Dashboard(document.getElementById('kaigo-syunyu-syusyutu-dashboard'));
    var control = new google.visualization.ControlWrapper({
      controlType: 'ChartRangeFilter',
      containerId: 'kaigo-syunyu-syusyutu-control',
      options: {
        filterColumnIndex: 0,
        ui: {
          chartType: 'ComboChart',
          chartOptions: {
            chartArea: { width: '95%' },
            hAxis: { ticks: tickDates },
            seriesType: 'bars',
          },
          chartView: {
            columns: [0, 2, 3],
          },
        }
      },
      state: { range: { start: startDate, end: endDate }}
    });
    var chart = new google.visualization.ChartWrapper({
      chartType: 'ComboChart',
      containerId: 'kaigo-syunyu-syusyutu-chart',
      options: Object.assign({}, chartOptions, {seriesType: "bars"}),
      view: { columns: [chartViewColumn0, 1, 2, 3] }
    });
    const data = new google.visualization.DataTable();
    data.addColumn('date', '年月');
    data.addColumn({ type: 'string', role: 'annotation' });
    data.addColumn('number', '介護保険特会・収入');
    data.addColumn('number', '介護保険特会・支出');
    data.addRows([
      [new Date(2019, 4, 0), "平成31年4月", 0.02409, 0.9843],
      [new Date(2019, 5, 0), null, 12.7, 10.83],
      [new Date(2019, 6, 0), null, 8.778, 10.48],
      [new Date(2019, 7, 0), null, 19.62, 11.3],
      [new Date(2019, 8, 0), null, 6.703, 10.39],
      [new Date(2019, 9, 0), null, 11.11, 10.89],
      [new Date(2019, 10, 0), null, 13.9, 11.73],
      [new Date(2019, 11, 0), null, 10.71, 10.51],
      [new Date(2019, 12, 0), null, 6.554, 11.19],
      [new Date(2020, 1, 0), null, 16.79, 11.65],
      [new Date(2020, 2, 0), null, 6.634, 10.98],
      [new Date(2020, 3, 0), null, 15.32, 13.19],
      [new Date(2020, 4, 0), "令和2年4月", 0.02818, 1.01],
      [new Date(2020, 5, 0), null, 12.94, 11.37],
      [new Date(2020, 6, 0), null, 14.98, 10.64],
      [new Date(2020, 7, 0), null, 15.1, 11.44],
      [new Date(2020, 8, 0), null, 7.161, 10.81],
      [new Date(2020, 9, 0), null, 11.37, 11.5],
      [new Date(2020, 10, 0), null, 15.24, 12.1],
      [new Date(2020, 11, 0), null, 11.27, 11.22],
      [new Date(2020, 12, 0), null, 5.145, 11.75],
      [new Date(2021, 1, 0), null, 20.67, 11.98],
      [new Date(2021, 2, 0), null, 7.066, 11.52],
      [new Date(2021, 3, 0), null, 16.23, 13.39],
    ]);
    customFormatter.format(data, 0);
    dashboard.bind(control, chart);
    dashboard.draw(data);
  }
</script>

### 2.5. 下水道特別会計

<div id="gesuido-syunyu-syusyutu-dashboard">
  <div id="gesuido-syunyu-syusyutu-chart" class="reigetu-chart"></div>
  <div id="gesuido-syunyu-syusyutu-control" class="reigetu-control"></div>
</div>

<script type="text/javascript">
  google.charts.setOnLoadCallback(drawChart6);
  function drawChart6() {
    var dashboard = new google.visualization.Dashboard(document.getElementById('gesuido-syunyu-syusyutu-dashboard'));
    var control = new google.visualization.ControlWrapper({
      controlType: 'ChartRangeFilter',
      containerId: 'gesuido-syunyu-syusyutu-control',
      options: {
        filterColumnIndex: 0,
        ui: {
          chartType: 'ComboChart',
          chartOptions: {
            chartArea: { width: '95%' },
            hAxis: { ticks: tickDates },
            seriesType: 'bars',
          },
          chartView: {
            columns: [0, 2, 3],
          },
        }
      },
      state: { range: { start: startDate, end: endDate }}
    });
    var chart = new google.visualization.ChartWrapper({
      chartType: 'ComboChart',
      containerId: 'gesuido-syunyu-syusyutu-chart',
      options: Object.assign({}, chartOptions, {seriesType: "bars"}),
      view: { columns: [chartViewColumn0, 1, 2, 3] }
    });
    const data = new google.visualization.DataTable();
    data.addColumn('date', '年月');
    data.addColumn({ type: 'string', role: 'annotation' });
    data.addColumn('number', '下水道特会・収入');
    data.addColumn('number', '下水道特会・支出');
    data.addRows([
      [new Date(2019, 4, 0), "平成31年4月", 1.749, 3.495],
      [new Date(2019, 5, 0), null, 2.2, 1.043],
      [new Date(2019, 6, 0), null, 2.236, 0.6382],
      [new Date(2019, 7, 0), null, 1.843, 6.203],
      [new Date(2019, 8, 0), null, 8.839, 1.038],
      [new Date(2019, 9, 0), null, 1.685, 4.667],
      [new Date(2019, 10, 0), null, 1.97, 2.896],
      [new Date(2019, 11, 0), null, 1.756, 0.8465],
      [new Date(2019, 12, 0), null, 1.823, 0.6599],
      [new Date(2020, 1, 0), null, 1.752, 3.868],
      [new Date(2020, 2, 0), null, 1.946, 1.335],
      [new Date(2020, 3, 0), null, 9.713, 10.61],
      [new Date(2020, 4, 0), "令和2年4月", 1.84, 3.174],
      [new Date(2020, 5, 0), null, 5.184, 0.9301],
      [new Date(2020, 6, 0), null, 2.054, 1.265],
      [new Date(2020, 7, 0), null, 7.663, 3.611],
      [new Date(2020, 8, 0), null, 1.782, 0.955],      
      [new Date(2020, 9, 0), null, 1.721, 3.077],      
      [new Date(2020, 10, 0), null, 2.048, 3.425],
      [new Date(2020, 11, 0), null, 1.644, 1.736],      
      [new Date(2020, 12, 0), null, 1.897, 0.5877],
      [new Date(2021, 1, 0), null, 1.644, 3.068],
      [new Date(2021, 2, 0), null, 2.063, 2.1],
      [new Date(2021, 3, 0), null, 9.622, 8.064],
    ]);
    customFormatter.format(data, 0);
    dashboard.bind(control, chart);
    dashboard.draw(data);
  }
</script>

## 3. 収入と支出の累計差
各会計について、月末残高の収入累計から支出累計を引いた値をグラフにしました。この額がマイナスの場合、月末時点で、他の会計や基金から資金融通が必要になっていることを示します。また逆に大きくプラスが続いているようだと、予定していた市民サービスが消化できていない可能性もあります。

### 3.1. 一般会計（累計収入 - 累計支出）

現状で特記することはありません。

<div id="ippan-ruikei-sa-dashboard">
  <div id="ippan-ruikei-sa-chart" class="reigetu-chart"></div>
  <div id="ippan-ruikei-sa-control" class="reigetu-control"></div>
</div>

<script type="text/javascript">
  google.charts.setOnLoadCallback(drawChart7);
  function drawChart7() {
    var dashboard = new google.visualization.Dashboard(document.getElementById('ippan-ruikei-sa-dashboard'));
    var control = new google.visualization.ControlWrapper({
      controlType: 'ChartRangeFilter',
      containerId: 'ippan-ruikei-sa-control',
      options: {
        filterColumnIndex: 0,
        ui: {
          chartType: 'ComboChart',
          chartOptions: {
            chartArea: { width: '95%' },
            hAxis: { ticks: tickDates },
            seriesType: 'bars',
          },
          chartView: {
            columns: [0, 2],
          },
        }
      },
      state: { range: { start: startDate, end: endDate }}
    });
    var chart = new google.visualization.ChartWrapper({
      chartType: 'ComboChart',
      containerId: 'ippan-ruikei-sa-chart',
      options: Object.assign({}, chartOptions, {seriesType: "bars"}),
      view: { columns: [chartViewColumn0, 1, 2] }
    });
    const data = new google.visualization.DataTable();
    data.addColumn('date', '年月');
    data.addColumn({ type: 'string', role: 'annotation' });
    data.addColumn('number', '一般会計');
    data.addRows([
      [new Date(2019, 4, 0), "平成31年4月", -14.46],
      [new Date(2019, 5, 0), null, 0.2748],
      [new Date(2019, 6, 0), null, 52.73],
      [new Date(2019, 7, 0), null, 39.15],
      [new Date(2019, 8, 0), null, 38.6],
      [new Date(2019, 9, 0), null, 47.24],
      [new Date(2019, 10, 0), null, 10.94],
      [new Date(2019, 11, 0), null, 15.03],
      [new Date(2019, 12, 0), null, -13.59],
      [new Date(2020, 1, 0), null, -5.57],
      [new Date(2020, 2, 0), null, -27.45],
      [new Date(2020, 3, 0), null, 49.47],
      [new Date(2020, 4, 0), "令和2年4月", -17.12],
      [new Date(2020, 5, 0), null, 89.97],
      [new Date(2020, 6, 0), null, 96.56],
      [new Date(2020, 7, 0), null, 42.1],
      [new Date(2020, 8, 0), null, 59.18],
      [new Date(2020, 9, 0), null, 63.6],
      [new Date(2020, 10, 0), null, 25.07],
      [new Date(2020, 11, 0), null, 15.95],
      [new Date(2020, 12, 0), null, 3.912],
      [new Date(2021, 1, 0), null, 6.95],
      [new Date(2021, 2, 0), null, -14.5],
      [new Date(2021, 3, 0), null, 67.39],
    ]);
    customFormatter.format(data, 0);
    dashboard.bind(control, chart);
    dashboard.draw(data);
  }
</script>

### 3.2. その他会計（累計収入 - 累計支出）

現状で特記することはありません。

<div id="ruikei-sa-dashboard">
  <div id="ruikei-sa-chart" class="reigetu-chart"></div>
  <div id="ruikei-sa-control" class="reigetu-control"></div>
</div>

<script type="text/javascript">
  google.charts.setOnLoadCallback(drawChart8);
  function drawChart8() {
    var dashboard = new google.visualization.Dashboard(document.getElementById('ruikei-sa-dashboard'));
    var control = new google.visualization.ControlWrapper({
      controlType: 'ChartRangeFilter',
      containerId: 'ruikei-sa-control',
      options: {
        filterColumnIndex: 0,
        ui: {
          chartType: 'ComboChart',
          chartOptions: {
            chartArea: { width: '95%' },
            hAxis: { ticks: tickDates },
            seriesType: 'bars',
          },
          chartView: {
            columns: [0, 2, 3, 4, 5],
          },
        }
      },
      state: { range: { start: startDate, end: endDate }}
    });
    var chart = new google.visualization.ChartWrapper({
      chartType: 'ComboChart',
      containerId: 'ruikei-sa-chart',
      options: Object.assign({}, chartOptions, {seriesType: "bars"}),
      view: { columns: [chartViewColumn0, 1, 2, 3, 4, 5] }
    });
    const data = new google.visualization.DataTable();
    data.addColumn('date', '年月');
    data.addColumn({ type: 'string', role: 'annotation' });
    data.addColumn('number', '国保特会');
    data.addColumn('number', '後期高医特会');
    data.addColumn('number', '介護保険特会');
    data.addColumn('number', '下水道事業会計');
    data.addRows([
      [new Date(2019, 4, 0), "平成31年4月", 0.3907, 0.4886, -0.9602, 2.656],
      [new Date(2019, 5, 0), null, 0.5097, 0.4794, 0.9055, 3.813],
      [new Date(2019, 6, 0), null, 1.864, 1.134, -0.7962, 5.41],
      [new Date(2019, 7, 0), null, 5.066, 1.423, 7.523, 1.051],
      [new Date(2019, 8, 0), null, 2.96, 1.275, 3.836, 8.852],
      [new Date(2019, 9, 0), null, 10.61, 2.051, 4.053, 5.871],
      [new Date(2019, 10, 0), null, 7.329, 1.456, 6.222, 4.946],
      [new Date(2019, 11, 0), null, 3.947, 1.472, 6.414, 5.855],
      [new Date(2019, 12, 0), null, 3.818, 0.9787, 1.778, 7.018],
      [new Date(2020, 1, 0), null, 7.485, 1.373, 6.916, 4.902],
      [new Date(2020, 2, 0), null, 3.488, 0.9937, 2.564, 5.513],
      [new Date(2020, 3, 0), null, 2.656, 0.2429, 4.693, 4.611],
      [new Date(2020, 4, 0), "令和2年4月", 0.347, 0.4533, -0.9819, 3.277],
      [new Date(2020, 5, 0), null, 0.4706, 0.3564, 0.5851, 7.531],
      [new Date(2020, 6, 0), null, 1.414, 0.9838, 4.926, 8.32],
      [new Date(2020, 7, 0), null, 15.03, 1.031, 8.587, 12.37],
      [new Date(2020, 8, 0), null, 13.19, 0.9912, 4.938, 13.2],
      [new Date(2020, 9, 0), null, 10.67, 1.7, 4.804, 11.84],
      [new Date(2020, 10, 0), null, 7.528, 0.8475, 7.94, 10.47],
      [new Date(2020, 11, 0), null, 4.795, 1.025, 7.99, 10.37],
      [new Date(2020, 12, 0), null, 10.73, 0.4986, 1.38, 11.68],
      [new Date(2021, 1, 0), null, 8.438, 0.8864, 10.07, 10.26],
      [new Date(2021, 2, 0), null, 4.536, 0.3769, 5.611, 10.22],
      [new Date(2021, 3, 0), null, 0.7234, 0.2895, 8.449, 11.78],
    ]);
    customFormatter.format(data, 0);
    dashboard.bind(control, chart);
    dashboard.draw(data);
  }
</script>

＊このうち下水道事業は公営企業会計です。

## 4. 基金残高

基金残高はいろいろと変化しました。

オリ・パラ夢未来基金は、端数をそろえるためでしょうか、2,000円積立られています。

このグラフは、マウスホイールを動かすことで拡大・縮小できます。

<div id="kikin-dashboard">
  <div id="kikin-chart" class="reigetu-chart"></div>
  <div id="kikin-control" class="reigetu-control"></div>
</div>

<script type="text/javascript">
  google.charts.setOnLoadCallback(drawChart9);
  function drawChart9() {
    var dashboard = new google.visualization.Dashboard(document.getElementById('kikin-dashboard'));
    var control = new google.visualization.ControlWrapper({
      controlType: 'ChartRangeFilter',
      containerId: 'kikin-control',
      options: {
        filterColumnIndex: 0,
        ui: {
          chartType: 'ColumnChart',
          chartOptions: {
            chartArea: { width: '95%' },
            hAxis: { ticks: tickDates },
            seriesType: 'bars',
            isStacked: true,
          },
          chartView: {
            columns: [0, 2, 3, 4, 5],
          },
        }
      },
      state: { range: { start: startDate, end: endDate }}
    });
    var chart = new google.visualization.ChartWrapper({
      chartType: 'ColumnChart',
      containerId: 'kikin-chart',
      options: Object.assign({}, chartOptions, { seriesType: "bars", isStacked: true, explorer: { axis: 'vertical', keepInBounds: true, maxZoomIn: 20.0, maxZoomOut: 1} }),
      view: { columns: [chartViewColumn0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19] }
    });
    const data = new google.visualization.DataTable();
    data.addColumn('date', '年月');
    data.addColumn({ type: 'string', role: 'annotation' });
    data.addColumn('number', '都市計画事業基金');
    data.addColumn('number', '財政調整基金');
    data.addColumn('number', '公共施設基金');
    data.addColumn('number', '下水道基金');
    data.addColumn('number', '介護給付費等準備基金');
    data.addColumn('number', '職員退職手当基金');
    data.addColumn('number', 'ごみ減量・リサイクル推進基金');
    data.addColumn('number', '国民健康保険事業運営基金');
    data.addColumn('number', '国際平和友好交流基金');
    data.addColumn('number', '緑化基金');
    data.addColumn('number', '健康福祉基金');
    data.addColumn('number', '土地開発基金');
    data.addColumn('number', '東京オリパラ子ども夢・未来基金');
    data.addColumn('number', '育英基金');
    data.addColumn('number', '職員研修基金');
    data.addColumn('number', '文化振興基金');
    data.addColumn('number', '減債基金');
    data.addColumn('number', '森林環境譲与税基金');
    data.addRows([
      [new Date(2019, 4, 0), "平成31年4月", 39.21, 30.17, 22.19, 13.57, 11.88, 7.667, 3.931, 3.516, 1.072, 0.946, 0.674, 0.2196, 0.5, 0.3665, 0.3305, 0.2542, 0.048, 0],
      [new Date(2019, 5, 0), null, 39.21, 30.17, 22.19, 13.57, 11.88, 7.667, 3.931, 3.516, 1.072, 0.946, 0.674, 0.2196, 0.5, 0.3665, 0.3305, 0.2542, 0.048, 0],
      [new Date(2019, 6, 0), null, 39.21, 30.17, 22.19, 13.57, 11.88, 7.667, 3.931, 3.516, 1.072, 0.946, 0.674, 0.2196, 0.5, 0.3665, 0.3305, 0.2542, 0.048, 0],
      [new Date(2019, 7, 0), null, 39.21, 30.17, 22.19, 13.57, 11.88, 7.667, 3.931, 3.516, 1.072, 0.946, 0.674, 0.2196, 0.5, 0.3665, 0.3305, 0.2542, 0.048, 0],
      [new Date(2019, 8, 0), null, 39.21, 30.17, 22.19, 13.57, 11.88, 7.667, 3.931, 3.516, 1.072, 0.946, 0.674, 0.2196, 0.5, 0.3665, 0.3305, 0.2542, 0.048, 0],
      [new Date(2019, 9, 0), null, 39.21, 30.17, 22.19, 13.57, 11.88, 7.667, 3.931, 3.516, 1.072, 0.946, 0.674, 0.2196, 0.5, 0.3665, 0.3305, 0.2542, 0.048, 0],
      [new Date(2019, 10, 0), null, 39.21, 30.17, 22.19, 13.57, 11.88, 7.667, 3.931, 3.516, 1.072, 0.946, 0.674, 0.2196, 0.5, 0.3665, 0.3305, 0.2542, 0.048, 0],
      [new Date(2019, 11, 0), null, 39.21, 30.17, 22.19, 13.57, 11.88, 7.667, 3.931, 3.516, 1.072, 0.946, 0.674, 0.2196, 0.5, 0.3665, 0.3305, 0.2542, 0.048, 0],
      [new Date(2019, 12, 0), null, 39.21, 30.17, 22.19, 13.57, 11.88, 7.667, 3.931, 3.516, 1.072, 0.946, 0.674, 0.2196, 0.5, 0.3665, 0.3305, 0.2542, 0.048, 0],
      [new Date(2020, 1, 0), null, 39.21, 30.17, 22.19, 13.57, 11.88, 7.667, 3.931, 3.516, 1.072, 0.946, 0.674, 0.2196, 0.5, 0.3665, 0.3305, 0.2542, 0.048, 0],
      [new Date(2020, 2, 0), null, 39.21, 30.17, 22.19, 13.57, 11.88, 7.667, 3.931, 3.516, 1.072, 0.946, 0.674, 0.6996, 0.5, 0.3665, 0.3305, 0.2542, 0.048, 0],
      [new Date(2020, 3, 0), null, 47.44, 29.01, 20.59, 16.07, 11.37, 6.502, 3.469, 4.016, 1.043, 0.8845, 0.6044, 0.6996, 0.5281, 0.3724, 0.3279, 0.2235, 0.04801, 0],
      [new Date(2020, 4, 0), "令和2年4月", 47.44, 29.01, 20.59, 16.07, 11.37, 6.502, 3.469, 4.016, 1.043, 0.8845, 0.6044, 0.6996, 0.5281, 0.3724, 0.3279, 0.2235, 0.04801, 0],
      [new Date(2020, 5, 0), null, 47.44, 29.01, 20.59, 16.07, 11.37, 6.502, 3.469, 4.016, 1.043, 0.8845, 0.6044, 0.6996, 0.5281, 0.3724, 0.3279, 0.2235, 0.04801, 0],
      [new Date(2020, 6, 0), null, 47.44, 29.01, 20.59, 16.07, 11.37, 6.502, 3.469, 4.016, 1.043, 0.8845, 0.6044, 0.6996, 0.5281, 0.3724, 0.3279, 0.2235, 0.04801, 0],
      [new Date(2020, 7, 0), null, 47.44, 29.01, 20.59, 16.07, 11.37, 6.502, 3.469, 4.016, 1.043, 0.8845, 0.6044, 0.6996, 0.5281, 0.3724, 0.3279, 0.2235, 0.04801, 0],
      [new Date(2020, 8, 0), null, 47.44, 29.01, 20.59, 16.07, 11.37, 6.502, 3.469, 4.016, 1.043, 0.8845, 0.6044, 0.6996, 0.5281, 0.3724, 0.3279, 0.2235, 0.04801, 0],
      [new Date(2020, 9, 0), null, 47.44, 29.01, 20.59, 16.07, 11.37, 6.502, 3.469, 4.016, 1.043, 0.8845, 0.6044, 0.6996, 0.5281, 0.3724, 0.3279, 0.2235, 0.04801, 0],
      [new Date(2020, 10, 0), null, 47.44, 29.01, 20.59, 16.07, 11.37, 6.502, 3.469, 4.016, 1.043, 0.8845, 0.6044, 0.6996, 0.5281, 0.3724, 0.3279, 0.2235, 0.04801, 0],
      [new Date(2020, 11, 0), null, 47.44, 29.01, 20.59, 16.07, 11.37, 6.502, 3.469, 4.016, 1.043, 0.8845, 0.6044, 0.6996, 0.5281, 0.3724, 0.3279, 0.2235, 0.04801, 0],
      [new Date(2020, 12, 0), null, 47.44, 29.01, 20.59, 16.07, 11.37, 6.502, 3.469, 4.016, 1.043, 0.8845, 0.6044, 0.6996, 0.5281, 0.3724, 0.3279, 0.2235, 0.04801, 0],
      [new Date(2021, 1, 0), null, 47.44, 29.01, 20.59, 16.07, 11.37, 6.502, 3.469, 4.016, 1.043, 0.8845, 0.6044, 0.6996, 0.5281, 0.3724, 0.3279, 0.2235, 0.04801, 0],
      [new Date(2021, 2, 0), null, 47.44, 29.01, 20.59, 16.07, 11.37, 6.502, 3.469, 4.016, 1.043, 0.8845, 0.6044, 0.6996, 0.5281, 0.3724, 0.3279, 0.2235, 0.04801, 0],
      [new Date(2021, 3, 0), null, 55.4, 28.38, 18.09, 17.07, 9.947, 5.463, 2.316, 4.016, 0.8644, 1.37, 0.4264, 0.6996, 0.5281, 0.375, 0.2984, 0.1408, 0.04802, 0],
    ]);
    customFormatter.format(data, 0);
    dashboard.bind(control, chart);
    dashboard.draw(data);
  }
</script>


## 5. 一般会計への資金融通

基金から一般会計への資金融通状況です。

このグラフは、マウスホイールを動かすことで拡大・縮小できます。

<div id="shikin-dashboard">
  <div id="shikin-chart" class="reigetu-chart"></div>
  <div id="shikin-control" class="reigetu-control"></div>
</div>

<script type="text/javascript">
  google.charts.setOnLoadCallback(drawChart9);
  function drawChart9() {
    var dashboard = new google.visualization.Dashboard(document.getElementById('shikin-dashboard'));
    var control = new google.visualization.ControlWrapper({
      controlType: 'ChartRangeFilter',
      containerId: 'shikin-control',
      options: {
        filterColumnIndex: 0,
        ui: {
          chartType: 'ColumnChart',
          chartOptions: {
            chartArea: { width: '95%' },
            hAxis: { ticks: tickDates },
            seriesType: 'bars',
            isStacked: true,
          },
          chartView: {
            columns: [0, 2, 3, 4],
          },
        }
      },
      state: { range: { start: startDate, end: endDate }}
    });
    var chart = new google.visualization.ChartWrapper({
      chartType: 'ColumnChart',
      containerId: 'shikin-chart',
      options: Object.assign({}, chartOptions, { seriesType: "bars", isStacked: true, explorer: { axis: 'vertical', keepInBounds: true, maxZoomIn: 20.0, maxZoomOut: 1} }),
      view: { columns: [chartViewColumn0, 1, 2, 3, 4] }
    });
    const data = new google.visualization.DataTable();
    data.addColumn('date', '年月');
    data.addColumn({ type: 'string', role: 'annotation' });
    data.addColumn('number', '財政調整基金');
    data.addColumn('number', '都市計画事業基金');
    data.addColumn('number', '公共施設基金');
    data.addRows([
      [new Date(2019, 4, 0), "平成31年4月", 30, 5, 0],
      [new Date(2019, 5, 0), null, 30, 15, 0],
      [new Date(2019, 6, 0), null, 0, 0, 0],
      [new Date(2019, 7, 0), null, 0, 0, 0],
      [new Date(2019, 8, 0), null, 0, 0, 0],
      [new Date(2019, 9, 0), null, 0, 0, 0],
      [new Date(2019, 10, 0), null, 15, 0, 0],
      [new Date(2019, 11, 0), null, 15, 0, 0],
      [new Date(2019, 12, 0), null, 28, 0, 20],
      [new Date(2020, 1, 0), null, 28, 0, 20],
      [new Date(2020, 2, 0), null, 28, 0, 30],
      [new Date(2020, 3, 0), null, 0, 0, 0],
      [new Date(2020, 4, 0), "令和2年4月", 29, 0, 20],
      [new Date(2020, 5, 0), null, 29, 0, 20],
      [new Date(2020, 6, 0), null, 10, 0, 0],
      [new Date(2020, 7, 0), null, 10, 0, 0],
      [new Date(2020, 8, 0), null, 10, 0, 0],
      [new Date(2020, 9, 0), null, 10, 0, 0],
      [new Date(2020, 10, 0), null, 0, 0, 0],
      [new Date(2020, 11, 0), null, 0, 0, 0],
      [new Date(2020, 12, 0), null, 29, 0, 0],
      [new Date(2021, 1, 0), null, 29, 0, 0],
      [new Date(2021, 2, 0), null, 29, 17, 5],
      [new Date(2021, 3, 0), null, 0, 0, 0],
    ]);
    customFormatter.format(data, 0);
    dashboard.bind(control, chart);
    dashboard.draw(data);
  }
</script>
