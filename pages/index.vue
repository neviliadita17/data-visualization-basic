<template>
    <div class="grid grid-cols-2 gap-2">
        <div class="bg-gray-200 rounded-md shadow-md">
            <highchart :options="chartOptions"/>
        </div>
        <div class="bg-gray-200 rounded-md shadow-md">
            <highchart :options="chartColumnOptions"/>
        </div>

        <div class="bg-gray-200 rounded-md shadow-md">
            <highchart 
                :options="chartColumnStackOptions" 
                :modules="['exporting', 'export-data']"/>
        </div>
        <div class="bg-gray-200 rounded-md shadow-md">
            <highchart :options="piechartOptions"/>
        </div>
    </div>
</template>

<script>
export default {
    data () {
        return {
            chartOptions: {
                chart: {
                    type: 'areaspline',
                },
                title: {
                    text: 'Statistik Data Penduduk'
                },
                subtitle: {
                    text: 'Data Penduduk tahun 2020-2024'
                },
                legend: {
                    align: 'center',
                    verticalAlign: 'bottom',
                    layout: 'horizontal'
                },
                tooltip: {
                    // enabled: false 
                    // format -----------
                    // format: '<b> Tahun {x} </b> <br /> Jumlah Penduduk: {series.name} {point.y}'

                    // formatter ------------
                    // formatter: function() {
                    //     return `<b> Tahun ${this.x} </b> <br /> Jumlah Penduduk ${this.series.name}: ${this.point.y}`
                    // }

                    // formatter untuk shared tooltip------------
                    // split: true,
                    shared: true,
                    formatter: function() {
                        // console.log(this.points)
                        return [`<b>Tahun ${this.x}</b> </br>`].concat(
                            this.points ? this.points.map(point => {
                                return `Jumlah ${point.series.name}: ${point.y} <br />`
                            }) : []
                        )
                        return 'something'
                    }

                },
                // plotOptions: {
                //     spline: {
                //         dataLabels: {
                //         enabled: false
                //         }
                //     }
                // },
                xAxis: {
                    categories: [2020, 2021, 2022, 2023, 2024]
                },
                yAxis: {
                    title: {
                        text: 'Jumlah Penduduk'
                    }
                },
                series: [
                    {
                        name: 'Pria',
                        data: [21534, 32465, 33530, 42330, 63590]
                    },
                    {
                        name: 'Wanita',
                        data: [32597, 39435, 43520, 52530, 73290]
                    },

                ]
            },
            chartColumnOptions: {
                chart: {
                    type: 'bar',
                },
                title: {
                    text: 'Statistik Data Penduduk'
                },
                subtitle: {
                    text: 'Data Penduduk tahun 2020-2024'
                },
                legend: {
                    align: 'center',
                    verticalAlign: 'bottom',
                    layout: 'horizontal'
                },
                tooltip: {
                    // enabled: false 
                    // format -----------
                    // format: '<b> Tahun {x} </b> <br /> Jumlah Penduduk: {series.name} {point.y}'

                    // formatter ------------
                    // formatter: function() {
                    //     return `<b> Tahun ${this.x} </b> <br /> Jumlah Penduduk ${this.series.name}: ${this.point.y}`
                    // }

                    // formatter untuk shared tooltip------------
                    // split: true,
                    shared: true,
                    formatter: function() {
                        // console.log(this.points)
                        return [`<b>Tahun ${this.x}</b> </br>`].concat(
                            this.points ? this.points.map(point => {
                                return `Jumlah ${point.series.name}: ${point.y} <br />`
                            }) : []
                        )
                        return 'something'
                    }

                },
                plotOptions: {
                    bar: {
                        stacking: 'normal',
                        dataLabels: {
                            enabled: true
                        }
                    }
                },
                xAxis: {
                    categories: [2020, 2021, 2022, 2023, 2024]
                },
                yAxis: {
                    title: {
                        text: 'Jumlah Penduduk'
                    }
                },
                series: [
                    {
                        name: 'Pria',
                        data: [21534, 32465, 33530, 42330, 63590]
                    },
                    {
                        name: 'Wanita',
                        data: [32597, 39435, 43520, 52530, 73290]
                    },

                ]
            },
            chartColumnStackOptions: {
                chart: {
                    type: 'column',
                },
                // credits: {
                //     enabled: true
                // },
                title: {
                    text: 'Statistik Data Penduduk'
                },
                subtitle: {
                    text: 'Data Penduduk tahun 2020-2024'
                },
                legend: {
                    align: 'center',
                    verticalAlign: 'bottom',
                    layout: 'horizontal'
                },
                tooltip: {
                    // enabled: false 
                    // format -----------
                    // format: '<b> Tahun {x} </b> <br /> Jumlah Penduduk: {series.name} {point.y}'

                    // formatter ------------
                    // formatter: function() {
                    //     return `<b> Tahun ${this.x} </b> <br /> Jumlah Penduduk ${this.series.name}: ${this.point.y}`
                    // }

                    // formatter untuk shared tooltip------------
                    // split: true,
                    shared: true,
                    formatter: function() {
                        // console.log(this.points)
                        return [`<b>Tahun ${this.x}</b> </br>`].concat(
                            this.points ? this.points.map(point => {
                                return `Jumlah ${point.series.name}: ${point.y} <br />`
                            }) : []
                        )
                        return 'something'
                    }

                },
                plotOptions: {
                    column: {
                        stacking: 'normal',
                        // dataLabels: {
                        //     enabled: true
                        // }
                    }
                },
                xAxis: {
                    categories: [2020, 2021, 2022, 2023, 2024]
                },
                yAxis: {
                    title: {
                        text: 'Jumlah Penduduk'
                    }
                },
                series: [
                    {
                        name: 'Pria',
                        data: [21534, 32465, 33530, 42330, 63590]
                    },
                    {
                        name: 'Wanita',
                        data: [32597, 39435, 43520, 52530, 73290]
                    },

                ]
            },
            piechartOptions: {
                chart: {
                    type: 'pie',
                    backgroundColor: "#FFDD95"
                }, 
                title: {
                    text: 'Perbandingan Pria dan Wanita',
                    style: {
                        color: '#000',
                        fontSize: '20px', 
                        textTransform: 'uppercase'
                    }
                },
                subtitle: {
                    text: 'Jumlah data Pria dan Wanita'
                },
                plotOptions: {
                    pie: {
                        innerSize: '30%',
                        allowPointSelect: true,
                        dataLabels: {
                            enabled: true,
                            distance: -60,
                            format: '{point.name}</br> {point.y}'
                        }
                    }
                },
                series: [
                    {
                        name: 'Jumlah',
                        data: [
                            {
                                name: 'Pria',
                                y: 45672
                            },
                            {
                                name: 'Wanita',
                                y: 55672
                            }
                        ]
                    }
                ]
            }
        }
    }
}
</script>