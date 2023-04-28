#include <iostream>
#include <iomanip>

using namespace std;

int main() {

    // Configuración de las dimensiones del borde de página
    const int ROWS = 23;
    const int COLS = 100;

    // Configuración de los colores para los bordes
    const char GREEN_BORDER = 'G';
    const char YELLOW_BORDER = 'Y';

    // Configuración de la información a mostrar en el interior del borde
    string institution = "Institución Educativa Física Cumbayá";
    string course = "Aplicaciones Informáticas";
    string subject = "Programación y Base de Datos";
    string class_info = "Primero Paralelo \"E\"";
    string project = "Tema Proyecto Integrado";
    string student = "Estudiante Aracely Cabascango";
    string year = "Año Lectivo 2022-2023";

    // Configuración de los caracteres para el borde superior e inferior
    char horizontal_border = '-';
    char vertical_border = '|';

    // Configuración de la posición inicial para la información a mostrar en el interior del borde
    int row_position = (ROWS - 7) / 2; // se divide por 2 para centrar la información verticalmente

    // Configuración del borde superior
    for (int i = 0; i < COLS; i++) {
        if (i == 0 || i == COLS - 1) {
            cout << "+"; // Esquina superior izquierda o derecha
        } else if (i % 4 == 0) {
            cout << GREEN_BORDER; // Caracter verde cada 4 columnas
        } else if (i % 4 == 2) {
            cout << YELLOW_BORDER; // Caracter amarillo cada 4 columnas (desplazado 2)
        } else {
            cout << horizontal_border; // Caracter horizontal
        }
    }
    cout << endl;

    // Configuración del borde izquierdo y derecho y de la información a mostrar en el interior del borde
    for (int i = 0; i < ROWS; i++) {
        for (int j = 0; j < COLS; j++) {
            if (j == 0 || j == COLS - 1) {
                cout << vertical_border; // Borde izquierdo o derecho
            } else if (i == row_position) {
                if (j == (COLS - institution.length()) / 2) {
                    cout << institution; // Información de la institución centrada
                    j += institution.length() - 1;
                } else if (j == (COLS - course.length()) / 2) {
                    cout << course; // Información del curso centrada
                    j += course.length() - 1;
                } else if (j == (COLS - subject.length()) / 2) {
                    cout << subject; // Información de la asignatura centrada
                    j += subject.length() - 1;
                } else if (j == (COLS - class_info.length()) / 2) {
                    cout << class_info; // Información del grupo centrada
                    j += class_info.length() - 1;
                } else if (j == (COLS - project.length()) /

