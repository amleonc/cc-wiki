<%*
const name = await tp.system.prompt("Nombre de la asignatura", "")
const code = await tp.system.prompt("Código", "")
const component = await tp.system.suggester(["Fundamentación", "Disciplinar", "Libre elección"], ["Fundamentación", "Disciplinar", "Libre elección"], false, "Componente")
const semester = await tp.system.suggester(["1", "2", "3", "4", "5", "6", "7", "8", "9"], [1,2,3,4,5,6,7,8,9], false, "¿En qué semestre se recomienda tomarla?")
const credits = await tp.system.prompt("Número de créditos", "")
const weeklyHours = await tp.system.prompt("Horas presenciales por semana", "")
const autonomousHours = await tp.system.prompt("Horas trabajo autónomo por semana", "")
const mandatory = await tp.system.suggester(["Sí", "No"], [true, false], false, "¿Es obligatoria?")
const mandatoryText = mandatory ? "Sí" : "No";
const validable = await tp.system.suggester(["Sí", "No"], [true, false], false, "¿Es validable?")
const validableText = validable ? "Sí" : "No";
-%>
---
name: <% name %>
code: <% code %>
component: <% component %>
semester: <% semester %>
credits: <% credits %>
weeklyHours: <% weeklyHours %>
autonomousHours: <% autonomousHours %>
mandatory: <% mandatory %>
validable: <% validable %>
<% "tag" %>: unal,curriculum
---

### Código
<% code %>

### Nombre
<% name %>

### Características

|                    |                      |
| ------------------ | -------------------- |
| **Componente**         | <%component%>        |
| **Semestre**           | <%semester%>         |
| **Créditos**           | <%credits%>          |
| **Intensidad horaria** | <%weeklyHours%> h     |
| **Trabajo autónomo**   | <%autonomousHours%> h |
| **Obligatoria**        | <%mandatoryText%>        |
| **Validable**          | <%validableText%>        |


### Descripción



### Contenido

