# Proyecto Final (Compilador)
Este proyecto fue realizado en el lenguage de programación Python, utilizando la versión 3.10 y empleando el entorno de Visual Studio Code para su desarrollo. No obstante, se trabajó a modo de consola e interfaz (utilizando la librería de Pyside2 del entorno QT), realizando esta compactación hibrida para un mejor manejo de la información procesada.

## Instalación
### 1ra forma.
Dar clic en Code, luego en Donwload ZIP y después de que termine la descarga, descomprimirlo.

### 2da forma.
Crear una carpeta, ingresar a git bash y ejecutar el siguiente comando:  git clone https://github.com/OTG-16/Proyecto_Final_ST2.git

### Nota
Es importante resaltar que en este proyecto se utilizan herramientas que deben ser instaladas previamente para el correcto funcionamiento de este analizador. Entre ellas están las siguientes:

- IDE QT Creator
- Librería Pyside2 (Se podría consultar el siguiente video para su instalación https://www.youtube.com/watch?v=INSimE1tW34&list=PLNN_J-C1-lZvgVgnoYXeZo49Boz6CDGTf&index=4 y este otro como introducción para su manejo https://www.youtube.com/watch?v=T0qJdF1fMqo&list=PLNN_J-C1-lZvgVgnoYXeZo49Boz6CDGTf&index=5&t=1533s)
- Librería Colorama (Utlizar en el cmd el comando: pip install colorama)
- Librería Matplotlib (Utlizar en el cmd el comando: pip install matplotlib)
- Librería Networkx (Utlizar en el cmd el comando: pip install networkx)

## Probando el programa
En un principio, al momento de correr el programa este muestra lo siguiente:
#### Interfaz principal
![c1](https://user-images.githubusercontent.com/70919055/191636160-03a7d676-64d0-44b7-be3e-5f74b06b9f8a.PNG)

Puede apreciarse una interfaz. Al lado izquierdo se cuenta con un cuadro de texto (ignorar el de la derecha) para ingresar la información a analizar. En la parte de a medias se tiene un botón, este se usa para comenzar el análisis léxico, sintáctico y semántico. Además, si la cadena es válida permite mostrar la tabla de símbolos y el código intermedio correspondiente. 
- ### Primer ejemplo

Ahora bien, se ingresa en el cuadro correspondiente, el texto 

"int a;
int suma(int a, int b){
return a+b;
}

int main(){
float a;
int b;
int c;
c = a+b;
c = suma(8.5,9.9);
}"

,como primer ejemplo y se da click en el botón de analizar. Al ser una cadena inválida semánticamente el programa muestra una ventana con el mensaje del error, tal como se muestra a continuación:
#### Texto ingresado
![E2](https://user-images.githubusercontent.com/70919055/201827451-47eddeaf-47dd-4d5e-84f3-eda1ec214058.png)
#### Resultado
![E2_2](https://user-images.githubusercontent.com/70919055/201827502-a5e0b5a4-76a3-463d-801a-0a8ed5cb78f8.png)
- ### Segundo ejemplo
No obstante, como segunda ejemplo se ingresa en el cuadro correspondiente, el texto
"int a;

int suma(int a, int b){
return a+b;
}

int main(){
float a;
int b;
int c;
c = a+b;
c = suma(8,9);
}"

,y se da click en el botón de analizar. Al ser una cadena válida el programa muestra una ventana con el mensaje de "cadena aceptada!" y despliega la siguiente información:
### Texto ingresado
![T1](https://user-images.githubusercontent.com/70919055/202300882-19939662-ce3c-4942-b0dc-60ca9f9251b7.png)
### Resultado
#### Análisis léxico y semántico
![T2](https://user-images.githubusercontent.com/70919055/202301005-e376d756-6298-447e-9eb1-a0a675e0f6ba.png)
#### Análisis LR
#### >>> Parte inicial del análisis LR
![pf2](https://user-images.githubusercontent.com/70919055/205792177-d28419fd-79cd-476a-a4bc-43d98a26ce8e.png)
#### >>> Parte final del análisis LR
![pf3](https://user-images.githubusercontent.com/70919055/205792367-57ae6e53-d6a5-42c7-8b12-cb02d3ae2c93.png)

Se resume en 2 capturas (parte inicial y parte final) el análisis LR para compactar la presentación de este.
#### Árbol sintáctico 
![T3](https://user-images.githubusercontent.com/70919055/202301132-332ccf0d-1f98-4db7-8fc1-dfa078de5d88.png)

En la imagen del árbol sintáctico puede apreciarse el mismo, aunque al contener varios tokens, no se logra apreciar muy bien estos y sus enlaces. Para lo cual, si queremos ir navegando a lo largo del árbol tenemos que dar click en el icono de la lupa que está en la parte superior izquierda de la ventana (5ta posición de izquierda a derecha), de inmediato se activara una función para seleccionar una parte de la ventana a la cual queramos hacerle zoom. Adicionalmente podemos movernos hacia los lados dandole click al icono que tiene las flechas hacia los lados fusionadas (4ta posición de izquierda a derecha). Además de poder regresar a un punto anterior o posterior dándole click al icono de derecha e izquierda respectivamente (2da y 3ra posición de izquierda a derecha).
Como prueba de ello, navegaré sobre el árbol tal y como se muestra a continuación:
#### * Navegando sobre el árbol sintáctico 
- Parte inferior del árbol
![t4](https://user-images.githubusercontent.com/70919055/202308795-aafb443f-0ded-4119-9be7-be496ecf2547.png)
![t4_2](https://user-images.githubusercontent.com/70919055/202308902-68b5b939-7d32-4372-97ae-07d8bb729dc4.png)
![t4_3](https://user-images.githubusercontent.com/70919055/202308941-2c31f58e-c3cd-48d7-ba8d-2feef874a268.png)
- Parte media del árbol
![t5](https://user-images.githubusercontent.com/70919055/202309071-3d8598e2-00d1-4d46-8233-27c98c19fda9.png)
![t5_2](https://user-images.githubusercontent.com/70919055/202309169-49f85a0b-4ec3-4b0a-8e9c-43762b722ce4.png)
![t5_3](https://user-images.githubusercontent.com/70919055/202309216-694108c3-3c13-47a9-9c9a-afaaba3b0512.png)
- Parte superior del árbol
![t6](https://user-images.githubusercontent.com/70919055/202309610-297cac3a-dee4-46fb-8d10-7175a590469f.png)
![t6_2](https://user-images.githubusercontent.com/70919055/202309670-d26465bb-fff4-457d-9e98-f7cb80a6aa4c.png)
![t6__3](https://user-images.githubusercontent.com/70919055/202309732-fa1f6030-5724-4e4a-8f59-e12b76eeddf4.png)
#### Tabla de símbolos y código intermedio
![pf](https://user-images.githubusercontent.com/70919055/205786649-4be5a561-fbf5-4b65-b1bc-c96ad6509912.png)

- ### Tercer ejemplo
Finalmente, como tercer ejemplo se ingresa en el cuadro correspondiente, el texto

"int main(){
    string s;
    int i;
    s = "hola mundo";
    s = "Oscar Torres García";
    i=0;
    if (i<9){
            i = i+1;
    }
    s = "ya sali del bucle";
    return 0;
}"

,y se da click en el botón de analizar. Al ser una cadena válida el programa muestra una ventana con el mensaje de "cadena aceptada!" y despliega la siguiente información:
### Texto ingresado
![pfn](https://user-images.githubusercontent.com/70919055/205797987-b86c6992-0a51-48aa-a203-bb9f6377bcb4.png)
### Resultado
#### Análisis léxico y semántico
![pf4](https://user-images.githubusercontent.com/70919055/205793756-3f2911af-3185-4d47-82b5-b456c207bb09.png)
#### Análisis LR
#### >>> Parte inicial del análisis LR 
![pf7](https://user-images.githubusercontent.com/70919055/205795101-88076af1-d476-4112-a953-ca75a79d9109.png)
#### >>> Parte final del análisis LR
![pf8](https://user-images.githubusercontent.com/70919055/205795281-467cadb2-4d4a-40c0-935b-980989dab37c.png)
Se resume en 2 capturas (parte inicial y parte final) el análisis LR para compactar la presentación de este.

#### Árbol sintáctico 
![pf9](https://user-images.githubusercontent.com/70919055/205795609-55fff287-9a53-4718-83c7-e85c9fdcf738.png)
En la imagen del árbol sintáctico puede apreciarse el mismo, aunque al contener varios tokens, no se logra apreciar muy bien estos y sus enlaces. Para lo cual, si queremos ir navegando a lo largo del árbol tenemos que hacer lo mismo que en segundo ejemplo, aunque para este caso no se realizará un acercamiento a las diferentes partes del árbol para que esta documentación no se haga muy extensa y sea menos tediosa, de todos modos ya en el segundo ejemplo se específico lo necesario para poder hacerlo.
#### Tabla de símbolos y código intermedio
![pf10](https://user-images.githubusercontent.com/70919055/205796414-82f51689-b739-426d-840b-3eacbe5cc5d1.png)
