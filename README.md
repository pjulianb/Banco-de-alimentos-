# Banco-de-alimentos-
INTERFAZ: Formulario limpio con logo
USUARIO: *Ingresa credenciales*
BOTÓN "Iniciar Sesión" → Navega a HOME
BOTÓN "Registrarse" → Navega a REGISTER

INTERFAZ: Formulario de registro
USUARIO: *Completa datos personales*
BOTÓN "Registrarse" → Guarda datos → Navega a HOME
BOTÓN "Volver" → Regresa a LOGIN

INTERFAZ: Dashboard con opciones
BOTÓN "Agregar Alimento" → Navega a ADD_FOOD
BOTÓN "Ver Todos los Alimentos" → Navega a ALIMENTOS  
BOTÓN "Mis Donaciones" → Navega a MIS_DONACIONES
BOTÓN "Mis Solicitudes" → Navega a MIS_SOLICITUDES

INTERFAZ: Formulario de alimento
USUARIO: *Llena datos del alimento*
- Nombre, Cantidad, Tipo, Donante, Fecha caducidad
BOTÓN "Guardar" → AlimentoViewModel.agregarAlimento()
→ Navega de regreso a HOME

INTERFAZ: Lista de alimentos con estadísticas
- Muestra contador total de alimentos
- Muestra total de unidades disponibles
BOTÓN "Editar" en cada alimento → Navega a EDIT_FOOD/{id}
BOTÓN "Eliminar" → AlimentoViewModel.eliminarAlimento()
BOTÓN "Volver" → Regresa a HOME

INTERFAZ: Vista detallada del alimento
- Muestra información completa del alimento
- Permite acciones específicas según el estado

- INTERFAZ: Lista filtrada de donaciones del usuario
- Estadísticas: Total donado, Entregados
BOTÓN "Agregar Donación" (FAB) → Navega a ADD_FOOD
BOTÓN "Editar" → Navega a EDIT_FOOD

INTERFAZ: Gestión de solicitudes
- Estadísticas: Total, Pendientes, Aprobadas
BOTÓN "Nueva Solicitud" (FAB) → Navega a nueva solicitud
BOTÓN "Cancelar" → SolicitudViewModel.cancelarSolicitud()
BOTÓN "Detalles" → Navega a detalles de solicitud

LOGIN ←→ REGISTER
    ↓
   HOME
    ↓
ADD_FOOD → (Guardar) → HOME
ALIMENTOS → EDIT_FOOD/{id} → ALIMENTOS  
ALIMENTOS → FOOD_DETAIL/{id}
MIS_DONACIONES → ADD_FOOD
MIS_DONACIONES → EDIT_FOOD/{id}
MIS_SOLICITUDES → NUEVA_SOLICITUD

VIEWMODELS:
- AlimentoViewModel: Gestiona alimentos (agregar, editar, eliminar)
- SolicitudViewModel: Gestiona solicitudes

ESTADO:
- alimentos.collectAsState() → Actualización automática de UI
- Parámetros de navegación: alimentoId, foodId en URLs
