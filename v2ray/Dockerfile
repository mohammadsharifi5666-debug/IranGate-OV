FROM v2fly/v2fly-core:latest

# Copy configuration files
COPY v2ray/server-config.json /etc/v2ray/config.json

# Create log directory
RUN mkdir -p /var/log/v2ray

# Expose port
EXPOSE 10086/tcp

# Run v2ray
CMD ["v2ray", "-c", "/etc/v2ray/config.json"]