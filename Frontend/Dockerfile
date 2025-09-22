FROM node:20-alpine

WORKDIR /usr/src/app

# Copiamos solo los manifests primero
COPY package*.json ./

# Instalamos dependencias
RUN if [ -f package-lock.json ]; then npm ci; else npm install; fi

# Copiamos el resto del código (ya sin node_modules gracias al .dockerignore)
COPY . .

EXPOSE 5173
CMD ["npm", "run", "dev", "--", "--host"]
