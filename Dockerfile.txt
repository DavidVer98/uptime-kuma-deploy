FROM louislam/uptime-kuma:1

# Configurar el puerto
EXPOSE 3001

# Crear y configurar el directorio de datos
RUN mkdir -p /app/data && \
    chown -R 1000:1000 /app/data

# Volumen para datos persistentes
VOLUME ["/app/data"]

# Comando de inicio
CMD ["node", "server/server.js"]