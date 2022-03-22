<!--
Aufgabe: Ausgabe von Studenten-Daten
Erstellen Sie eine computed Data-Property ...
a. student(), welche den Vor- und Nachnamen des Studenten ausgibt.
b. anzahlModule(), welche die Anzahl der Module des Studenten ausgibt.
b. durchschnittModule(), welche den arithmetischen Durchschnitt aller abgeschlossener Module des Studenten ausgibt.
-->
<template>
  <div class="container">
    <!-- Aufgabe a.-->
    <p>Student: {{ student }}</p>
    <!-- Aufgabe b.-->
    <p>Anzahl Module: {{ anzahlModule }}</p>
    <!-- Aufgabe c.-->
    <p>Notendurchschnitt aller absolvierten Module: {{ durchschnittModule }}</p>
  </div>
</template>
<script>
export default {
  data() {
    return {
      schule: {
        beruf: {
          id: "Mediamatiker",
          jahre: 4,
          abschluss: "EFZ"
        },
        student: {
          name: {
            vorname: 'Hans',
            nachname: 'Muster'
          },
          module: [
            {
              M286: "Eigene ICT-Arbeitsinstrumente einrichten und bedienen",
              Note: 4.5,
              Semester: 1,
              abgeschlossen: true
            }, {
              M287: "Websites mit CSS gestalten",
              Note: 5,
              Semester: 2,
              abgeschlossen: true
            }, {
              M288: "Programmiertechniken im Webfrontend einsetzen",
              Note: 0,
              Semester: 3,
              abgeschlossen: false
            }
          ]
        }
      }
    }
  },
  computed: {
    student() {
      //Aufgabe a.
      return this.schule.student.vorname + ' '
          + this.schule.student.nachname;
    },
    //
    anzahlModule() {
      //Aufgabe b.
      return this.schule.student.module.length
    },
    durchschnittModule() {
      //Aufgabe c.
      let modulnoten = [];
      let sumnoten = 0;
      this.schule.student.module.filter(modul => {
        // If featured is true, return the entry Titel
        if (modul.abgeschlossen) {
          modulnoten.push(modul.Note);
        }
      });
      console.log(modulnoten);
      modulnoten.forEach(note => {
        sumnoten += note;
      });
      let avg = sumnoten/modulnoten.length
      console.log(avg);
      return avg;
    }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  padding: 30px;
  max-width: 600px;
}

input {
  padding: 10px 6px;
  margin: 20px 10px 10px 0;
}

.output {
  font-size: 16px;
  color: red;
}
</style>
