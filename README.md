
# Inicio Rapido API Beta de Asistentes de OpenAI v2

Una plantilla de inicio rápido utilizando la [API de Asistentes de OpenAI](https://platform.openai.com/docs/assistants/overview) con [Next.js](https://nextjs.org/docs).
<br/>
<br/>
![OpenAI Assistants API Quickstart](https://github.com/openai/openai-assistants-quickstart/assets/27232/755e85e9-3ea4-421f-b202-3b0c435ea270)
## Configuración Rápida

### 1. Clonar repositorio

```shell
git clone https://github.com/israelgo93/asistente-openai-v2.git
cd asistente-openai-v2
```

### 2. Establece tu [clave API de OpenAI](https://platform.openai.com/api-keys)

```shell
export OPENAI_API_KEY="sk_..."
```

(o en `.env.example` y renómbralo a `.env`).

### 3. Instalar dependencias

```shell
npm install
```

### 4. Ejecutar

```shell
npm run dev
```

### 5. Navega a [http://localhost:3000](http://localhost:3000).

## Despliegue

Puedes desplegar este proyecto en Vercel o en cualquier otra plataforma que soporte Next.js.

## Visión General

Este proyecto tiene como objetivo servir de plantilla para utilizar la API de Asistentes en Next.js con transmisión, uso de herramientas (intérprete de código y búsqueda de archivos), y llamadas a funciones. Aunque hay varias páginas para demostrar cada una de estas capacidades, todas utilizan el mismo asistente subyacente con todas las capacidades activadas.

La lógica principal para el chat se encontrará en el componente `Chat` en `app/components/chat.tsx`.

### Páginas

- Ejemplo Básico de Chat: [http://localhost:3000/examples/basic-chat](http://localhost:3000/examples/basic-chat)
- Ejemplo de Llamadas a Funciones: [http://localhost:3000/examples/function-calling](http://localhost:3000/examples/function-calling)
- Ejemplo de Búsqueda de Archivos: [http://localhost:3000/examples/file-search](http://localhost:3000/examples/file-search)
- Ejemplo Completo: [http://localhost:3000/examples/all](http://localhost:3000/examples/all)

### Componentes Principales

- `app/components/chat.tsx` - maneja la renderización del chat, transmisión, y reenvío de llamadas a funciones
- `app/components/file-viewer.tsx` - maneja la subida, obtención y eliminación de archivos para búsqueda de archivos

### Puntos de Acceso

- `api/assistants` - `POST`: crear asistente (solo se usa al inicio)
- `api/assistants/threads` - `POST`: crear nuevo hilo
- `api/assistants/threads/[threadId]/messages` - `POST`: enviar mensaje al asistente
- `api/assistants/threads/[threadId]/actions` - `POST`: informar al asistente del resultado de una función que decidió llamar
- `api/assistants/files` - `GET`/`POST`/`DELETE`: buscar, subir y eliminar archivos de asistente para búsqueda de archivos
