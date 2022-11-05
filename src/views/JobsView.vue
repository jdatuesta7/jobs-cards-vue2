<template>
  <div class="about">
    <h1>Empleos</h1>
    <b-container>
      <b-card-group deck>
        <JobCard :company="company" v-for="(company, index) in companies" :key="index"></JobCard>
      </b-card-group>
    </b-container>
  </div>
</template>

<script>
import JobCard from '@/components/JobCard.vue'

export default {
  name: 'JobsView',
  components: {
    JobCard
  },
  data() {
    return {
      companies: [
        {
          jobTitle: 'Desarrollador .NET',
          name: 'Peaku Inc.',
          location: 'Medellín',
          salary: '$ 7M - 10M COP',
          vacancies: 1,
          publicationDate: '2022-11-09T18:30:00.000Z',
          logo: 'company.svg'
        },
        {
          jobTitle: 'Desarrollador Power BI',
          name: 'VICHARA TECH',
          location: 'Remoto',
          salary: '$ 7M - 9M COP',
          vacancies: 2,
          publicationDate: '2022-10-09T18:30:00.000Z',
          logo: 'peaku.png'
        },
        {
          jobTitle: 'Asistente administrativo y contable',
          name: 'Cualquiera',
          location: 'No disponible',
          salary: '$ 2M - 3.6M COP',
          vacancies: 1,
          publicationDate: '2022-09-09T18:30:00.000Z',
          logo: 'company.svg'
        },
        {
          jobTitle: 'Lider técnico',
          name: 'VETTICA',
          location: 'Híbrido - mix rem...',
          salary: '$ 8M COP',
          vacancies: 1,
          publicationDate: '2022-11-03T18:30:00.000Z',
          logo: 'company.svg'
        },
        {
          jobTitle: 'Desarrollador back-end de Node.js',
          name: 'Bankuish',
          location: 'Remoto',
          salary: '$ 40K - 70K USD',
          vacancies: 1,
          publicationDate: '2022-10-28T18:30:00.000Z',
          logo: 'bankuish.png'
        }
      ]
    }
  },
  methods: {
  }
}
</script>
