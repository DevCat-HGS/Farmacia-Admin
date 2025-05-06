# Imagen base de Node.js
FROM node:16-alpine

# Directorio de trabajo en el contenedor
WORKDIR /app

# Copiar package.json y package-lock.json
COPY package*.json ./

# Instalar dependencias
RUN npm install

# Copiar el resto del código fuente
COPY . .

# Variables de entorno
ENV PORT=5000
ENV MONGO_URI=mongodb+srv://DevHaroldGS:7SKFNR6ewkN6Uam@mydatabase.mm0b2.mongodb.net/?retryWrites=true&w=majority&appName=farmacia-admin

# Exponer el puerto
EXPOSE 5000

# Comando para iniciar la aplicación
CMD ["npm", "start"]