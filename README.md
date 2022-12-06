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
"int main(){ 
float a; 
float b; 
float c; 
int d;
c = a+b; 
if (c>9){
   d=d+1;
} 
} "

,y se da click en el botón de analizar. Al ser una cadena válida el programa muestra una ventana con el mensaje de "cadena aceptada!" y despliega la siguiente información:
### Texto ingresado
![o1](https://user-images.githubusercontent.com/70919055/205815190-584ec1f3-1ec0-4d71-9848-430c0c20fda2.png)
### Resultado
#### Análisis léxico y semántico
![o2](https://user-images.githubusercontent.com/70919055/205815341-217923e5-16bb-4882-bf90-e936f84907b3.png)
#### Análisis LR
#### >>> Parte inicial del análisis LR
![two](https://user-images.githubusercontent.com/70919055/205820420-7990a46d-bd77-4b4a-bbd2-d6d3dc72271f.png)
#### >>> Parte final del análisis LR
![two_2](https://user-images.githubusercontent.com/70919055/205820486-bd52ad0e-34f2-49db-9b76-1dc25d72efad.png)
Se resume en 2 capturas (parte inicial y parte final) el análisis LR para compactar la presentación de este.
#### Árbol sintáctico 
![o5](https://user-images.githubusercontent.com/70919055/205815614-f23a3e16-8f6e-4180-9e48-e0802cd0bd35.png)

En la imagen del árbol sintáctico puede apreciarse el mismo, aunque al contener varios tokens, no se logra apreciar muy bien estos y sus enlaces. Para lo cual, si queremos ir navegando a lo largo del árbol tenemos que dar click en el icono de la lupa que está en la parte superior izquierda de la ventana (5ta posición de izquierda a derecha), de inmediato se activara una función para seleccionar una parte de la ventana a la cual queramos hacerle zoom. Adicionalmente podemos movernos hacia los lados dandole click al icono que tiene las flechas hacia los lados fusionadas (4ta posición de izquierda a derecha). Además de poder regresar a un punto anterior o posterior dándole click al icono de derecha e izquierda respectivamente (2da y 3ra posición de izquierda a derecha).
Como prueba de ello, navegaré sobre el árbol tal y como se muestra a continuación:
#### * Navegando sobre el árbol sintáctico 
- Parte inferior del árbol
![o6](https://user-images.githubusercontent.com/70919055/205815700-abe08da9-a2d5-4706-a5b6-020b46ebea9a.png)
![o7](https://user-images.githubusercontent.com/70919055/205815789-8fe24635-a17a-4995-9873-fc9686115719.png)
![o8](https://user-images.githubusercontent.com/70919055/205815876-01bf9b82-f977-4220-948d-bb18aea914bc.png)
- Parte media del árbol
![o9](https://user-images.githubusercontent.com/70919055/205815977-b1437a58-e062-438c-a52a-c026d51729aa.png)
![o10](https://user-images.githubusercontent.com/70919055/205816022-a5190b3b-3bf6-4305-921a-12b144693c6c.png)
![o11](https://user-images.githubusercontent.com/70919055/205816069-8cedd3c6-b009-45ae-8dbd-b82fdaf39870.png)
- Parte superior del árbol
![o12](https://user-images.githubusercontent.com/70919055/205816236-b8b52830-d261-41ec-9851-765294d7c722.png)
![o13](https://user-images.githubusercontent.com/70919055/205816360-9cea484f-1e6c-448d-b3a8-1d3ae61838c0.png)
![o14](https://user-images.githubusercontent.com/70919055/205816550-76325a2d-a1da-445f-948b-b9a0fb9628fd.png)
#### Tabla de símbolos y código intermedio
![o15](https://user-images.githubusercontent.com/70919055/205816764-d01e9464-905f-4c24-a502-6e0e50c6316d.png)


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
![three](https://user-images.githubusercontent.com/70919055/205820584-3a85891d-4637-4d82-aacc-063fda32f5d5.png)
#### >>> Parte final del análisis LR
![three_2](https://user-images.githubusercontent.com/70919055/205820663-7bfac261-2735-4a80-bd61-0357c81b976e.png)
Se resume en 2 capturas (parte inicial y parte final) el análisis LR para compactar la presentación de este.

#### Árbol sintáctico 
![pf9](https://user-images.githubusercontent.com/70919055/205795609-55fff287-9a53-4718-83c7-e85c9fdcf738.png)
En la imagen del árbol sintáctico puede apreciarse el mismo, aunque al contener varios tokens, no se logra apreciar muy bien estos y sus enlaces. Para lo cual, si queremos ir navegando a lo largo del árbol tenemos que hacer lo mismo que en segundo ejemplo, aunque para este caso no se realizará un acercamiento a las diferentes partes del árbol para que esta documentación no se haga muy extensa y sea menos tediosa, de todos modos ya en el segundo ejemplo se específico lo necesario para poder hacerlo.
#### Tabla de símbolos y código intermedio
![pf10](https://user-images.githubusercontent.com/70919055/205796414-82f51689-b739-426d-840b-3eacbe5cc5d1.png)

