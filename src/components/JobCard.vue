<template>
    <div>
        <b-card v-b-hover="hoverHandler" :class="'mb-3 rounded-0 '+hoverClass">
            <b-row>
                <div class="col-1">
                    <b-card-img :src="require(`../assets/${company.logo}`)"></b-card-img>
                </div>
                <div class="col-11">
                    <b-row>
                        <div class="col-12">
                            <b-row style="cursor: pointer;">
                                <b-card-title class="text-start col-12 ps-3 pt-2">{{ company.jobTitle }}</b-card-title>
                            </b-row>
                        </div>
                        <div class="col-12">
                            <b-row>
                                <div class="col-12">
                                    <b-card-text style="font-size: 0.9em;" class="row">
                                        <div class="col-2 text-start">
                                            <div class="text-truncate">
                                                <b-img src="../assets/building.svg" class="col-3 p-2"></b-img>
                                                <span class="col-9 p-0 text-nowrap">{{ company.name }}</span>
                                            </div>
                                        </div>
                                        <div class="col-2 text-start">
                                            <div class="text-truncate">
                                                <b-img src="../assets/geo.svg" class="col-3 p-2"></b-img>
                                                <span class="col-9 p-0 text-nowrap">{{ company.location }}</span>
                                            </div>
                                        </div>
                                        <div class="col-2">
                                            <div class="text-truncate">
                                                <b-img src="../assets/cash.svg" class="col-3 p-2"></b-img>
                                                <span class="col-9 p-0 text-nowrap">{{ company.salary }}</span>
                                            </div>
                                        </div>
                                        <div class="col-2">
                                            <div class="text-truncate">
                                                <b-img src="../assets/people.svg" class="col-3 p-2"></b-img>
                                                <span class="col-9 p-0 text-nowrap">{{ company.vacancies }} vacante{{
                                                        company.vacancies === 1 ? '' : 's'
                                                }} </span>
                                            </div>
                                        </div>
                                        <div class="col-2">
                                            <div class="text-truncate">
                                                <b-img src="../assets/calendar.svg" class="col-3 p-2"></b-img>
                                                <span class="col-9 p-0 text-nowrap">{{ company.publicationDate | humanFormat }}</span>
                                            </div>
                                        </div>
                                        <div class="col-2">
                                            <b-row>
                                                <div class="col p-2">
                                                    <b-img v-b-tooltip.hover title="Cursos de ingles"
                                                        src="../assets/global.svg" class="col-4">
                                                    </b-img>
                                                </div>
                                                <div class="col p-2">
                                                    <b-img v-b-tooltip.hover title="Trabajo remoto"
                                                        src="../assets/geo.svg" class="col-4">
                                                    </b-img>
                                                </div>
                                                <div class="col p-2">
                                                    <b-img v-b-tooltip.hover title="Horarios flexibles"
                                                        src="../assets/watch.svg" class="col-4">
                                                    </b-img>
                                                </div>
                                            </b-row>
                                        </div>
                                    </b-card-text>
                                </div>
                            </b-row>
                        </div>
                    </b-row>
                </div>
            </b-row>
        </b-card>
    </div>
</template>

<script>
import moment from 'moment';

export default {
    name: 'JobCard',
    props: {
        company: Object
    },
    data(){
        return {
            hoverClass: ''
        }
    },
    methods: {
        hoverHandler(isHovered) {
            if (isHovered) {
                this.hoverClass = 'shadow'
            } else {
                this.hoverClass = ''
            }
        }
    },
    filters: {
        humanFormat: function (value) {
            return moment(value).format("YYYY-MM-DD")
        }
    }
}
</script>