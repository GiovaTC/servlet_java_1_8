# servlet_java_1_8
# 🚀 Crear un Servlet básico en Eclipse con Java JDK 1.8

Te muestro cómo crear un Servlet básico en **Eclipse** usando un proyecto *Dynamic Web Project* y desplegándolo en **Apache Tomcat**.

---

## ✅ Pasos para crear un Servlet en Eclipse

### 1. Configuración inicial
1. Abre **Eclipse IDE for Enterprise Java Developers**.  
2. Ve a **File > New > Dynamic Web Project**.  
3. Configura:  
   - **Nombre del proyecto:** `ServletDemo`  
   - **Target runtime:** Selecciona tu Apache Tomcat (ej. *Tomcat 9 o 8.5*).  
   - **Dynamic web module version:** `3.1` (compatible con JDK 1.8).  
4. Haz clic en **Finish**.  

---

### 2. Crear el Servlet
1. Haz clic derecho sobre el proyecto → **New > Servlet**.  
2. Configura:  
   - **Nombre:** `HelloServlet`  
   - **Paquete:** `com.ejemplo.servlet`  
   - **URL mapping:** `/hello`  
3. Eclipse generará una clase con el esqueleto del Servlet. Sustitúyelo por este código:

```java
package com.ejemplo.servlet;

import java.io.IOException;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

@WebServlet("/hello")
public class HelloServlet extends HttpServlet {
    private static final long serialVersionUID = 1L;

    public HelloServlet() {
        super();
    }

    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) 
            throws ServletException, IOException {
        
        response.setContentType("text/html;charset=UTF-8");
        response.getWriter().println("<html>");
        response.getWriter().println("<head><title>Servlet Demo</title></head>");
        response.getWriter().println("<body>");
        response.getWriter().println("<h1>Hola desde el Servlet con Java JDK 1.8!</h1>");
        response.getWriter().println("</body>");
        response.getWriter().println("</html>");
    }
}
3. Desplegar y ejecutar
Haz clic derecho sobre el proyecto → Run As > Run on Server.

Selecciona tu servidor Apache Tomcat configurado en Eclipse.

Abre en el navegador:

bash
Copiar código
http://localhost:8080/ServletDemo/hello
📌 Resultado esperado
Deberías ver en pantalla:

👉 Hola desde el Servlet con Java JDK 1.8!
