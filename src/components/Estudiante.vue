<template>
<head>
  <meta charset="UTF-8">
  <meta name="viewport"
        content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">

  <title>Estudiante</title>
  <meta name="description" content="Consultar todo sobre estudiante">
  <meta name="author" content="Kenlly Chacon">
  <meta name="keywords" content="estudiante, consultar, eliminar, actualizar, eliminar">
  <meta name="google-site-verification" content="">
  <meta name="googlebot" content="">
</head>

<body>
<header>
  <h1>ESTUDIANTE</h1>
  <h3>Consultar estudiante por Id</h3>
</header>

<section>
  <label id="id_consulta" for="id_consulta_input">Id</label>
  <input id="id_consulta_input" type="text" v-model="text">
  <button @click="consultar">Consultar</button>

  <p>Id: {{id}}</p>
  <p>Nombre: {{nombre}}</p>
  <p>Apellido: {{apellido}}</p>
  <p>Fecha de nacimiento: {{fechaNacimiento}}</p>
  <p>Salario: {{salario}}</p>

</section>

<footer>
  Derechos Reservados 2023-2024
</footer>
</body>
</template>

<script>
export default {
  name: "Estudiante",
  data(){
    return{
      text: null,
      id: null,
      nombre: null,
      apellido: null,
      fechaNacimiento: null,
      salario: null,
    }
  },
  methods:{
    async consultar() {
      const data = await fetch(`http://localhost:8081/API/Matricula/V1/estudiantes/${this.text}`).then(r => r.json())
      console.log(data)
      const {id,nombre,apellido,fechaNacimiento,salario} = data
      this.id = id
      this.nombre = nombre
      this.apellido = apellido
      this.fechaNacimiento = fechaNacimiento
      this.salario = salario
    }
  },
}
</script>

<style scoped>

header,nav,section,footer,aside,article{
  display: block;
}

p{
  width: 100%;
  text-align: center;
  display: block;
  margin: 0 auto;
  font-size: 25px;
  padding: 7px;
  border-radius: 10px;
}

section input,label{
  text-align: center;
  display: block;
  width: 25%;
  margin: 0 auto;
  font-size: 25px;
  padding: 7px;
  border-radius: 10px;
}

h1,h2{
  margin: 25px;
  text-align: center;
}

footer{
  font-size: 18px;
  margin: 25px auto;
  clear: both;
}

img {
  width: 300px;
  height: 350px;
  margin: 15px;
}

button{
  transition-duration: 0.4s;
  padding:15px;
  margin: 25px auto;
  display: block;
  text-align: center;
  font-size: 16px;
  border-radius: 10px;
  width: 25%;
  background-color: #3E4251;
  cursor: pointer;
  color: white;
}

body{
  background-color: #1B1F27;
}

button:hover {
  background-color: #1F2E3C; /* Green */
  color: white;
}

</style>