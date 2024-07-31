# DATA CLEAN RIWI TEAM 3 API

## Overview

Esta API proporciona funcionalidades para la gestión y procesamiento de archivos. Los usuarios pueden cargar archivos CSV, realizar tareas de saneamiento de datos como la eliminación de duplicados, la validación de formatos y la ordenación de columnas, y descargar los archivos procesados en formatos CSV y PDF. La API incluye registro de solicitudes para el seguimiento y autenticación mediante una clave API para un acceso seguro a los servicios.

## Features

- Carga y procesamiento de archivos CSV
- Saneamiento de datos: eliminar duplicados, validar formatos, ordenar columnas
- Generar y descargar archivos procesados en formato CSV y PDF
- Registro completo de solicitudes para el seguimiento
- Documentación de API con Swagger

## Installation

1. **Clonar el repositorio:**
    ```bash
    git clone https://github.com/your-repo/data-clean-riwi-team3-api.git
    cd data-clean-riwi-team3-api
    ```

2. **Instalar dependencias:**
    ```bash
    npm install
    ```

3. **Configurar variables de entorno:**
    Crear un archivo `.env` en el directorio raíz y agregar las variables de entorno necesarias. Ejemplo:
    ```env
    MONGODB_URI="mongodb+srv://elipeforero21:dJybd8CPBjePuhOF@assesment.yugiws4.mongodb.net/"
    API_KEY="añlsidjewefwee"
    ```

4. **Ejecutar la aplicación:**
    ```bash
    npm run start
    ```

## API Documentation

La documentación de la API está disponible en `/api/doc` una vez que la aplicación esté en funcionamiento. Puedes acceder a ella en `http://localhost:3000/api/doc`.

## Endpoints

### Cargar Archivo CSV

- **URL:** `/api/v1/file/upload`
- **Método:** `POST`
- **Descripción:** Cargar un archivo CSV y procesarlo. El archivo CSV debe tener el siguiente formato:

    ```csv
    name,lastName,age,address
    John,Doe,30,"123 Main St"
    Jane,Smith,25,"456 Maple Ave"
    ```

- **Respuestas:**
  - `201`: Archivo procesado y PDF generado
  - `400`: Solicitud incorrecta

**Ejemplo de solicitud:**

```bash
curl -X POST http://localhost:3000/api/v1/file/upload \
  -H 'Content-Type: multipart/form-data' \
  -F 'file=@/ruta/a/tu/archivo.csv'
Detailed Explanation
FileController
uploadFile: Maneja la carga del archivo, procesa el contenido, guarda los datos, genera un PDF y responde con la ruta del PDF.
FileService
getFileFromFileName: Recupera el contenido del archivo a partir del nombre del archivo.
extractContentToString: Extrae el contenido del archivo y lo convierte en una cadena de texto.
parseCsvContent: Analiza el contenido CSV en un formato estructurado.
generatePdf: Genera un PDF a partir del contenido CSV analizado.
PersonService
save: Guarda los datos analizados en la base de datos utilizando Mongoose.
Mongoose Schema
typescript
Copiar código
import * as mongoose from 'mongoose';

export const PersonSchema = new mongoose.Schema({
  name: String,
  lastName: String,
  age: Number,
  address: String,
});
Mongoose Interface
typescript
Copiar código
import { Document } from 'mongoose';

export interface Person extends Document {
  readonly name: string;
  readonly lastName: string;
  readonly age: number;
  readonly address: string;
}
Running the Application
Iniciar la aplicación:

bash
Copiar código
npm run start
Acceder a la API:
La API estará disponible en http://localhost:3000/api/v1.

Acceder a la documentación de la API:
La documentación de la API estará disponible en http://localhost:3000/api/doc.

Development
Ejecutar en modo desarrollo
Para ejecutar la aplicación en modo desarrollo, utiliza el siguiente comando:

bash
Copiar código
npm run start:dev
Testing
Para ejecutar pruebas, utiliza el siguiente comando:

bash
Copiar código
npm run test
Linting
Para revisar el código, utiliza el siguiente comando:

bash
Copiar código
npm run lint
Contributing
Las contribuciones son bienvenidas. Por favor, sigue estos pasos:

Haz un fork del repositorio
Crea una nueva rama
Realiza tus cambios
Envía un pull request
License
Este proyecto está licenciado bajo la Licencia MIT.

Contact
Para cualquier pregunta o problema, por favor contacta a [elipeforero21@gmail.com].

