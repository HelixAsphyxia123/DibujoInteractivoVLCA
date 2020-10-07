# DibujoInteractivoVLCA
Desarrollar un programa que implemente una aplicación con GUI de dibujo interactivo.  La aplicación puede dibujar lineas, óvalos y rectángulos, pudiendo seleccionar colores y poder dibujar figuras rellenas.  Debe existir un botón para deshacer la última figura que se haya dibujado. Un botón para borrar todas las figuras del dibujo. Un botón para seleccionar el color. Un cuadro combinado para seleccionar la figura a dibujar.  Una casilla de verificación que especifique si una figura debe estar rellena o sin relleno.
En este ejercicio, implementará una aplicación de GUI que utiliza la jerarquía MiFigura del ejercicio 10.2 del
ejemplo práctico de GUI, para crear una aplicación de dibujo interactiva. Debe crear dos clases para la GUI y proporcionar una clase de prueba para iniciar la aplicación. Las clases de la jerarquía MiFigura no requieren modifi caciones
adicionales.
La primera clase a crear es una subclase de JPanel llamada PanelDibujo, la cual representa el área en la cual el
usuario dibuja las fi guras. La clase PanelDibujo debe tener las siguientes variables de instancia:
 a) Un arreglo llamado figuras de tipo MiFigura, que almacene todas las fi guras que dibuje el usuario.
 b) Una variable entera llamada cuentaFiguras, que cuente el número de fi guras en el arreglo.
 c) Una variable entera llamada tipoFigura, que determine el tipo de la fi gura a dibujar.
 d) Un objeto MiFigura llamado figuraActual, que represente la fi gura actual que está dibujando el usuario.
 e) Un objeto Color llamado colorActual, que represente el color del dibujo actual.
 f) Una variable bolean llamada figuraRellena, que determine si se va a dibujar una fi gura rellena.
 g) Un objeto JLabel llamado etiquetaEstado, que represente a la barra de estado. Esta barra deberá mostrar
las coordenadas de la posición actual del ratón.
La clase PanelDibujo también debe declarar los siguientes métodos:
 a) El método sobrescrito paintComponent, que dibuja las fi guras en el arreglo. Use la variable de instancia
cuentaFiguras para determinar cuántas fi guras hay que dibujar. El método paintComponent también
debe llamar al método draw de figuraActual, siempre y cuando figuraActual no sea null.
 b) Métodos establecer para tipoFigura, colorActual y figuraRellena.
 c) El método borrarUltimaFigura debe borrar la última fi gura dibujada, decrementando la variable de instancia cuentaFiguras. Asegúrese de que cuentaFiguras nunca sea menor que cero.
 d) El método borrarDibujo debe eliminar todas las fi guras en el dibujo actual, estableciendo cuentaFiguras
en cero.
Los métodos borrarUltimaFigura y borrarDibujo deben llamar al método repaint (heredado de Jpanel) para actualizar el dibujo en el objeto PanelDibujo, indicando que el sistema nunca debe llamar al método paintComponent.
La clase PanelDibujo también debe proporcionar el manejo de eventos, para permitir al usuario dibujar con el
ratón. Cree una clase interna individual que extienda a MouseAdapter e implemente MouseMotionListener para
manejar todos los eventos de ratón en una clase.
En la clase interna, sobrescriba el método mousePressed de manera que asigne a figuraActual una nueva fi gura
del tipo especifi cado por tipoFigura, y que inicialice ambos puntos con la posición del ratón. A continuación, sobrescriba el método mouseReleased para terminar de dibujar la fi gura actual y colocarla en el arreglo. Establezca el segundo
punto de figuraActual con la posición actual del ratón y agregue figuraActual al arreglo. La variable de instancia
cuentaFiguras determina el índice de inserción. Establezca figuraActual a null y llame al método repaint para
actualizar el dibujo con la nueva fi gura. 
Sobrescriba el método mouseMoved para establecer el texto de etiquetaEstado, de manera que muestre las coordenadas del ratón; esto actualizará la etiqueta con las coordenadas cada vez que el usuario mueva (pero no arrastre) el
ratón dentro del objeto PanelDibujo. A continuación, sobrescriba el método mouseDragged de manera que establezca
el segundo punto de figuraActual con la posición actual del ratón y llame al método repaint. Esto permitirá al usuario ver la fi gura mientras arrastra el ratón. Además, actualice el objeto JLabel en mouseDragged con la posición actual
del ratón.
Cree un constructor para PanelDibujo que tenga un solo parámetro JLabel. En el constructor, inicialice
etiquetaEstado con el valor que se pasa al parámetro. Además, inicialice el arreglo figuras con 100 entradas, cuentaFiguras con 0, tipoFigura con el valor que represente a una línea, figuraActual con null y colorActual con
Color.BLACK. El constructor deberá entonces establecer el color de fondo del objeto PanelDibujo a Color.WHITE. y
registrar a MouseListener y MouseMotionListener, de manera que el objeto JPanel maneje los eventos de ratón en
forma apropiada.
A continuación, cree una subclase de JFrame llamada MarcoDibujo, que proporcione una GUI que permita al
usuario controlar varios aspectos del dibujo. Para el esquema del objeto MarcoDibujo, recomendamos BorderLayout,
con los componentes en la región NORTH, el panel de dibujo principal en la región CENTER y una barra de estado en
la región SOUTH, como en la fi gura 11.49. En el panel superior, cree los componentes que se listan a continuación. El
manejador de eventos de cada componente deberá llamar al método apropiado en la clase PanelDibujo.
 a) Un botón para deshacer la última fi gura que se haya dibujado.
 b) Un botón para borrar todas las fi guras del dibujo.
 c) Un cuadro combinado para seleccionar el color de los 13 colores predefi nidos.
 d) Un cuadro combinado para seleccionar la fi gura a dibujar.
 e) Una casilla de verifi cación que especifi que si una fi gura debe estar rellena o sin relleno.
Declare y cree los componentes de la interfaz en el constructor de MarcoDibujo. Necesitará crear la barra de estado
JLabel antes de crear el objeto PanelDibujo, de manera que pueda pasar el objeto JLabel como argumento para el
constructor de PanelDibujo. Por último, cree una clase de prueba para inicializar y mostrar el objeto Marco-Dibujo
para ejecutar la aplicación.
