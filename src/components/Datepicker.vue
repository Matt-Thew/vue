<template>
    <div class="container">
        <div class="row">
            <div class="col-md-3">
                <date-picker v-model="dateFrom" :config="options"></date-picker>
            </div>
            <div class="col-md-3">
                <date-picker v-model="dateTo" :config="options"></date-picker>
            </div>
        </div>
    </div>
</template>

<script>
    // Import required dependencies 
    import 'bootstrap/dist/css/bootstrap.css';
    // Import this component
    import datePicker from 'vue-bootstrap-datetimepicker';
    // Import date picker css
    import 'pc-bootstrap4-datetimepicker/build/css/bootstrap-datetimepicker.css';

    export default {
        data() {
            return {
                dateFrom: new Date(),
                dateTo: new Date(),
                options: {
                    format: 'DD/MM/YYYY',
                    useCurrent: false,
                }
            }
        },
        components: {
            datePicker
        }
    }
</script>