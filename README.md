# taller-unidemencionales
EXPLICACION DEL CODIGO DE PYTHON 
num_vertices = int(input("Ingrese el número de vértices: "))
vertices = [
    tuple(map(float, input(f"Ingrese las coordenadas x, y, z del vértice {i+1}: ").split()))
    for i in range(num_vertices)
]


EXPLICACION DEL PRIMER ESTRUCTURA DEL CODIGO 
num_vertices: Se solicita al usuario que ingrese el número de vértices que tendrá el modelo 3D. Este valor se almacena como un entero.
vertices: Es una lista de tuplas que almacenará las coordenadas de cada vértice. El código usa una lista por comprensión:

Para cada vértice (el bucle for i in range(num_vertices)), el código pide al usuario que ingrese las coordenadas x, y y z del vértice.

Las coordenadas se ingresan como una cadena de texto, y luego se separan (con .split()) y se convierten a números de tipo float (con map(float, ...)) para garantizar que sean valores decimales.
La función tuple(...) se utiliza para almacenar las coordenadas de cada vértice en una tupla.

num_faces = int(input("Ingrese el número de caras: "))
faces = [
    list(map(int, input(f"Ingrese los índices de los vértices para la cara {i+1} (ejemplo: 1 2 3): ").split()))
    for i in range(num_faces)
]


SE IMPRIME LA SALIDA DE UN FORMATO OBJ 0 archivo que almacena información geométrica en 3D.
`COMO VERTICES Y CARAS:
VERTICES:PARA CADA VERTICE (for v in vertices), SE IMPRIME EN EL FORMATO "v x y z" DONDE X Y Y Z SON LAS COORDENADAS DEL VERTICE 
CARAS: PARA CADA CARA  (for f in faces), SE IMPRIME EN ELÑ FORMATO "f i j k", donde i, j, y k DONDE SON LOS IDICES DE LOS VERTICES QUE COMPONES LA CARA LA FUNCION  map(str, f) COVIERTE LOS IDICIES DE ENTEROS A CADENAS DE TEXTO Y LUEGO " ".join(...) QEU ES UN método que une los elementos de un iterable en una sola caden, DONDE HACE QUE SE UNA UN ESPACIO ENTRE ELLOS 
UN EJEMPLO COMO EJECUTAR EL CODIGO DONDE LA SALIDA DEBE SER LA SIGUENTE:
ALGO DEBE DAR HACI Salida en formato OBJ:
v 0.0 0.0 0.0
v 1.0 0.0 0.0
v 1.0 1.0 0.0
v 0.0 1.0 0.0
f 1 2 3
f 1 3 4
EL PROGRAMA PRIMERO NOS VA PERDIR EL NUMERO DE VERTICES COMO EN ESTE CASO SON 4 VERTICES 
LUEGO NOS VAN A PEDRIR LAS COODERNADAS DE LOS VERTICES SE PODRAN COLOCAR CUALQUIERAS POR EJEMPLO 
Vértice 1: 0 0 0

Vértice 2: 1 0 0

Vértice 3: 1 1 0

Vértice 4: 0 1 0
LUEGO LE PEDIRA EL NMUMERO DE CARAS POR EJEMPLO: 2 
LUEGO LE PEDIRA LOS INDICES DE LOS VERTICES DE LA CARA POR EJEMPLO 
Cara 1: 1 2 3

Cara 2: 1 3 4 
SI SE HACE CORECTAMENTE LE DEBE IMPRIMIR LO SIGUENTE:
Salida en formato OBJ:
v 0.0 0.0 0.0
v 1.0 0.0 0.0
v 1.0 1.0 0.0
ESO FUE LA EXPLICACION DEL CODIGO DE PYTHON, A CONTINUACION SE EXPLICARA EL CODIGO DE C++
const int MAX_VERTICES = 100; // Máximo de vértices permitidos
const int MAX_FACES = 50;     // Máximo de caras permitidas
const int MAX_FACE_SIZE = 10; // Máximo de vértices por cara

ESTA PRIMERA PARTE DEL CODIGO SIRVE PARA 
v 0.0 1.0 0.0
f 1 2 3
f 1 3 4
ESA ES LA EXPLICACION DEL CODIGO DE PYTHON A CONTINUACION EL DE C+
const int MAX_VERTICES = 100; // Máximo de vértices permitidos
const int MAX_FACES = 50;     // Máximo de caras permitidas
const int MAX_FACE_SIZE = 10; // Máximo de vértices por cara

ESTA PRIMERA PARTE DEL CODIGO SIRVE PARA DEFINIR LA CANTIDAD DE VERTICES, CARAS Y EL NUEMRO MAXIMO DE VERTICES POR CARA SE PUEDE INGRESAR Y EVITA QUE INGRISE UN NUMERO QUE NO PERTENEZCA AL RANGO ADECUADO 
float vertices[MAX_VERTICES][3]; // Arreglo de vértices
int faces[MAX_FACES][MAX_FACE_SIZE]; // Arreglo de caras
int face_sizes[MAX_FACES]; // Cantidad de vértices en cada cara

vertices[MAX_VERTICES][3]:ES UNA MATRIX PARA ALM,ACENAR COORDENADAS DE CADA VERTTICE EN EL ESPACION 3D

faces[MAX_FACES][MAX_FACE_SIZE]: EL MENU DE SIZE ES:cuenta el número de elementos de un array o matriz, CON LO QUE AYUDA A Es una matriz para almacenar las caras. Cada fila de este arreglo contiene los índices de los vértices que componen una cara.

face_sizes[MAX_FACES]: EL MENU DE MAX ES :devuelve el valor más grande de un iterable o de una entrada dada, CON LO QUE AYUDA Es un arreglo que almacena el número de vértices en cada cara. Esto se utiliza para saber cuántos vértices componen una cara antes de imprimirla.

LA SIGUENTE PARTE DEL CODIGO DE C++

int num_vertices = 0, num_faces = 0;

Estas variables almacenan el número de vértices y el número de caras ingresados por el usuario. Se inicializan en 0.

cout << "Ingrese el número de vértices: ";
cin >> num_vertices;

if (num_vertices > MAX_VERTICES || num_vertices <= 0) {
    cout << "Número de vértices fuera de rango.\n";
    return 1;
}

for (int i = 0; i < num_vertices; i++) {
    cout << "Ingrese las coordenadas x, y, z del vértice " << (i + 1) << ": ";
    cin >> vertices[i][0] >> vertices[i][1] >> vertices[i][2];
}

EN ESTE PUNTO DEL CODIOG SE LE PIDE AL USUARIO QUE INGRESE EL NUMERO DE VERTICES PERO TIENE QUE ESTAR EN EL RANGO QUE ESTA PERMITIDO SINO TERMINARA CON UN MENSAJE DE ERROR Y NO SE PODRA EJECUTAR EL CODIGO
Luego, para cada vértice (en un bucle de 0 a num_vertices - 1), se piden las coordenadas 
𝑥x, 𝑦y y𝑧z del vértice, y se almacenan en el arreglo vertices.

cout << "Ingrese el número de caras: ";
cin >> num_faces;

if (num_faces > MAX_FACES || num_faces <= 0) {
    cout << "Número de caras fuera de rango.\n";
    return 1;
}

for (int i = 0; i < num_faces; i++) {
    cout << "Ingrese la cantidad de vértices de la cara " << (i + 1) << " (máximo " << MAX_FACE_SIZE << "): ";
    cin >> face_sizes[i];

    if (face_sizes[i] > MAX_FACE_SIZE || face_sizes[i] <= 0) {
        cout << "Cantidad de vértices no válida.\n";
        return 1;
    }

    cout << "Ingrese los índices de los vértices de la cara (ejemplo: 1 2 3): ";
    for (int j = 0; j < face_sizes[i]; j++) {
        cin >> faces[i][j];

        if (faces[i][j] < 1 || faces[i][j] > num_vertices) {
            cout << "Error: Índice fuera de rango. Debe estar entre 1 y " << num_vertices << ".\n";
            return 1;
        }
    }
}
PRIMERO SE SOLICITARA EL NUMERO DE CARAS DEBE SATAR DENTRO DE LA CONDICION Y DEL RANGO PERMITIDO SINO ESTA EN EL RANGO PERMITIDO SE IMPRIMIRA ERROR 

Luego, para cada cara (en un bucle de 0 a num_faces - 1): 
SE SOLICITARAN LA CANTIDAD DE VERTICES QUE COMPONEN LA FIGURA SINO CUMPLE LA CONDICION  (mayor que 0 y menor o igual a MAX_FACE_SIZE) AL FINALO DEL CONDIGO SE IMPRIMIRA EL CODIGO ERROR PORQUE NO SE CUMPLE LA CONDICION 
LUEG0 SE PIDEN LOS IDICES DE LOS VERTICES QUE CONFORMAN LA CARA SI  los índices estén dentro del rango de los vértices válidos (es decir, deben ser números entre 1 y num_vertices) SE TERMINARA EL PROGRAMA 

LUEGO POR CASI ULTIMO 
cout << "\nSalida en formato OBJ:\n";

// Imprimir vértices
for (int i = 0; i < num_vertices; i++) {
    cout << "v " << vertices[i][0] << " " << vertices[i][1] << " " << vertices[i][2] << endl;
}

// Imprimir caras
for (int i = 0; i < num_faces; i++) {
    cout << "f";
    for (int j = 0; j < face_sizes[i]; j++) {
        cout << " " << faces[i][j];
    }
    cout << endl;
}
EN ESTE APARTADO SE DEBEN IMRPRIMIR LOS VERTICES Y LAS CARAS 

POR ULTIMO TERMINAREMOS CON EL :
return 0;

UN EJEMPLO DE COMO EJECUTARLO COGEREMOS EL MISMO EJEMPLEMPLO DE PYTHON 
SI INGRESAMOS LOS MISMO DIJITOS QUE SON:

Número de vértices: 4

Vértices: (0, 0, 0), (1, 0, 0), (1, 1, 0), (0, 1, 0)

Número de caras: 2

Caras: Cara 1 con vértices 1 2 3, Cara 2 con vértices 1 3 4

POR LO GENERAL EL RPOGRAMA DEBE IMPRIMIR LO SIGUENTE: 

Salida en formato OBJ:   OBJ(archivo que almacena información geométrica en 3D)
v 0 0 0
v 1 0 0
v 1 1 0
v 0 1 0
f 1 2 3
f 1 3 4
ESE DEBE SER LA RESPUESTA SI SE SIGUE CORECTAMENTE LOS PASOS 


