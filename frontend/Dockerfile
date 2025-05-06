# Etapa de construcción
FROM node:16-alpine as build

# Directorio de trabajo
WORKDIR /app

# Copiar package.json y package-lock.json
COPY package*.json ./

# Instalar dependencias
RUN npm install

# Copiar el código fuente
COPY . .

# Construir la aplicación
RUN npm run build

# Etapa de producción
FROM nginx:alpine

# Copiar los archivos de construcción al directorio de nginx
COPY --from=build /app/build /usr/share/nginx/html

# Exponer el puerto 4000
EXPOSE 4000

# Iniciar nginx
CMD ["nginx", "-g", "daemon off;"]