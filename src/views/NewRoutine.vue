<template>
    <div>
      <div v-if="!hasStarted">
        <p>How many days of exercise would you like to add?</p>
        <input
            v-model="daysExercise"
            type="number"
            name="days-exercise"
            class="input"
            id="days-exercise"
            min="0"
            max="7"
        />
        <button class="btn" type="button" @click="startRoutineCreation()">Next</button>
      </div>
      <div class="routine-creation-container" v-if="hasStarted">
          <div class="exercises-container">
              <div class="exercise-single">
                  <h2>Exercise1</h2>
                  <p>description</p>
              </div>
              <div class="exercise-single">
                  <h2>Exercise2</h2>
                  <p>description</p>
              </div>
              <div class="exercise-single">
                  <h2>Exercise3</h2>
                  <p>description</p>
              </div>
              <div class="exercise-single">
                  <h2>Exercise4</h2>
                  <p>description</p>
              </div>
          </div>
          <div class="day-filler">
              <p>This is day {{currentDay}}</p>
              <div class="current-exercises-container">
                  <div v-for="exercise in currentExercises" :key="exercise.id">
                      {{ exercise }}
                  </div>
              </div>
          </div>
      </div>
    </div>
</template>

<script>
export default {
    data: () => {
        return {
            daysExercise: 0,
            routine: [],
            currentDay: null,
            currentExercises: [],
            hasStarted: false,
        };
    },
    methods: {
        startRoutineCreation() {
            if(this.daysExercise > 0) {
                let dayTemplate = {
                    day: null,
                    exercises: [],
                };
                for (let i = 0; i < this.daysExercise; i++) {
                    this.routine.push(dayTemplate);                   
                }

                this.currentDay = 0;
                this.hasStarted = true;
            }
        }
    },
};
</script>

<style lang="scss" scoped>
</style>
