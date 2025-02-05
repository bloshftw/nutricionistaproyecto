Tecnologias utilizadas para este proyecto:
-Xampp
-Mysql
-Java / Java swing


Estructura basica de la base de datos:
-paciente (Información de cada paciente)

id_paciente (PK)
nombre
apellido
edad
peso_actual
peso_objetivo
altura
tasa_metabolica
objetivo (Ej: "Aumentar peso", "Disminuir peso")
alimento (Listado de alimentos disponibles)

id_alimento (PK)
nombre
categoria (Ej: "Desayuno", "Almuerzo", "Cena", "Snack")
calorias_por_porcion
proteinas
carbohidratos
grasas
dieta (Una dieta asignada a un paciente)

id_dieta (PK)
id_paciente (FK)
fecha_inicio
fecha_fin
estado (Ej: "Activa", "Finalizada")
menu_diario (Un menú diario dentro de una dieta)

id_menu_diario (PK)
id_dieta (FK)
dia (Ej: "Lunes", "Martes", etc.)
renglon_menu (Cada alimento en un menú diario)

id_renglon_menu (PK)
id_menu_diario (FK)
id_alimento (FK)
cantidad_porciones

Esta estructura hace que cada dieta esté compuesta por varios menús diarios, y cada menú diario tenga varios renglones de menú con diferentes alimentos y sus porciones.

CLASES: 
Propuesta de Clases:

Modelo (Datos y lógica de negocio)
Paciente
Alimento
Dieta
MenuDiario
RenglonMenu

Vista (Interfaz gráfica en Swing)
PrincipalVista (Menú principal)
FormularioVista (Pantalla para ingresar datos del paciente)
AlimentoVista (Pantalla para agregar/modificar alimentos)
DietaVista (Pantalla donde se asignan dietas)
MenuDiarioVista (Pantalla donde se muestran y editan los menús diarios)

BaseDeDatos (Para manejar conexiones SQL)
Controlador (Comunicación entre Vista y Modelo)
PacienteControlador
AlimentoControlador
DietaControlador
MenuDiarioControlador


VISTAS Y FUNCIONES DE LA APLICACION:

Vista Pacientes:
-Agregar Paciente
-Modificar Paciente
-Eliminar Paciente

Vista Dieta:
-Crear dieta / Incluye funciones como crear dietas manualmente, y una opcion para suugerir una dieta automaticamente basada en los datos del paciente, con un resumen del paciente a crear la dieta.
-Modificar dieta:Se selecciona un paciente, y se pueden modificar renglones especificos de cada paciente, como almuerzo / desayuno, y modificar los alimentos que tiene.
-Eliminar dieta: Se selecciona un paciente con una dieta asignada, y permite eliminarla por completo.
-Ver dietas: Se pueden ver todas las dietas asignadas a un paciente.

Vista Alimentos:
-Crear Alimentos: Permite crear un nuevo alimento con todos sus atributos y almacenarlo en la base de datos.
-Modificar alimentos: Permite modificar nombre/calorias/etc, y reescribirlo en la base de datos.
-Eliminar alimentos: Permite eliminar uno o varios elementos de la base de datos.
-Lista: Permite ver todos los alimentos en la base de datos.
