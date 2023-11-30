# arduino
#include <Protothreads.h>

PT_THREAD(miTarea(struct pt *pt)) {
  PT_BEGIN(pt);

  // Código de inicio de la tarea

  while (1) {
    // Código que se ejecuta concurrentemente

    PT_WAIT_UNTIL(pt, condicion);  // Bloquea la tarea hasta que se cumpla la condición
  }

  PT_END(pt);
}

void loop() {
  static struct pt tarea1, tarea2;
  
  // Inicialización de las protothreads
  PT_INIT(&tarea1);
  PT_INIT(&tarea2);

  // Ejecución concurrente de las tareas
  miTarea(&tarea1);
  miTarea(&tarea2);
}
