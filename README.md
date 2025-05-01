# uml-diagrama-gestion-radios-empresas
diagrama de clases basado en modelo relacional 
title Diagrama de Clases basado en el Modelo Relacional - Gestión de Radios y Publicidad

'Definicion de clases

class EmpresaMedios {
   +NIF: String
   +nombre: String
   +director: String
   +direccionPostal: String
}

class Cadena {
  +idCadena: int
  +nombre: String
  +directorCadena: String
}

class Emisora  {
   +NIF: String
   +nombre: String
   +direccionPolstal: String
   +director: String
   +bandaHertziana: String
   +provincia: String
}

class Programa {
  +idPrograma: int
  +nombrePrograma: String
  +responsable: String
  +horaInicio: Time
  +diaSemana: String
  +duracionMinutos: int
}

class Publicidad {
  +idPublicidad: int
  +duracionSegundosPorSemana: int
  +precioPorSegundo: decimal
  +costoTotal: decimal
}

class Patrocinador {
  +numeroContrato: int
  +nombre: String
  +duracionContrato: int
  +importeTotalContrato: decimal
}

' Relaciones

EmpresaMedios "1" --"0...*" Cadena : controla >
cadena "1" -- "1" Emisora : sede central >
cadena "1" -- "0...*" Emisora : agrupa >
Emisora "1" -- "0..." Programa : transmite >
cadena "1" -- "0...*" Programa : transmite >
Programa "1" -- "0...*" Publicidad : contiene >
Publicidad "1" -- "1" Patrocinador : contratada por >
