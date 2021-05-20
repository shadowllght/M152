<template>
<div class="content">

    <ul>
        <li v-for="schoolGrade in schoolGrades">Fach: {{schoolGrade.name}} <br> Noten: {{schoolGrade.grades}} <br> Durchschnitt: {{gradeAverage(schoolGrade.grades)}}</li>
    </ul>
    <div>
        Gesamtdurchschnitt: {{overallAverage()}}<br>
        Maluspunkte: {{minusPoints()}}
    </div>

</div>
</template>

<script>
 export default {
     name: 'App',
     data: function () {
         return {
             schoolGrades: [{
                     name: "Mathematik",
                     grades: [5, 4.7, 3.5, 4.1]
                 },
                 {
                     name: "Geschichte",
                     grades: [5.5, 4.9, 5.75]
                 },
                 {
                     name: "Physik",
                     grades: [2, 2.7, 4.3]
                 },
                 {
                     name: "Deutsch",
                     grades: [4.25, 4.1, 3.5]
                 },
             ],
             newschoolGrade: '',
         }
     },
     methods: {
         gradeAverage: function (grades) {
             var sum = 0;
             for (var grade of grades) {
                 sum += grade;
             }
             return Math.round((sum / grades.length).toFixed(2) * 2) / 2;
         },
         overallAverage: function (schoolGrades) {
           var totalSum=0;
          for(var schoolGrade in schoolGrades){
            for(var grade of grades){
              totalSum+=grade;
            }
          }
          return totalSum/13;

         },
         minusPoints: function (grades) {
             
          
         },
     },
     computed: {

     }
 }
</script>

<style>
.content {
    width: 800px;
    margin: 0 auto;
}
</style>
