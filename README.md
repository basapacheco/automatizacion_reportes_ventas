# 📝 Automatización de Reportes de Ventas

Este proyecto es un sistema diseñado para automatizar la generación y el envío de reportes de ventas semanales. El sistema facilita la comunicación de los resultados de ventas de manera eficiente y oportuna, enviando automáticamente los reportes a la dirección cada semana.

## 📋 Descripción

El sistema automatiza todo el proceso de obtención de datos, análisis, visualización y envío de reportes. Se conecta a una hoja de cálculo de Google Sheets para obtener los datos de ventas, realiza análisis y visualización de los datos usando Python, y finalmente, envía los reportes por correo electrónico.

## 🛠 Herramientas Utilizadas

- **Python**: Pandas, Matplotlib, smtplib
- **Google Sheets API**: Para interactuar con hojas de cálculo de Google
- **Jupyter Notebook**: Para el desarrollo y pruebas
- **Cron**: Para automatizar la ejecución semanal del script en MacOS

## ⚙️ Configuración del Entorno

### 1. Clonar el Repositorio

```bash
git clone https://github.com/tu_usuario/automatizacion_reportes_ventas.git
cd automatizacion_reportes_ventas
```

### 2. Crear y Activar un Entorno Virtual

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Instalar las Dependencias

```bash
pip install -r requirements.txt
```

### 4. Configurar la API de Google Sheets

1. Crea un proyecto en Google Cloud Console y habilita la API de Google Sheets.
2. Configura la autenticación y descarga las credenciales OAuth2 en formato JSON.
3. Guarda el archivo de credenciales en la carpeta principal del proyecto (asegúrate de que esté en `.gitignore`).

### 5. Añadir las Credenciales de Google Sheets

Crea un archivo `config.json` en la carpeta principal del proyecto para almacenar las credenciales:

```json
{
  "google_sheets": {
    "credentials_file": "path_to_credentials.json",
    "spreadsheet_name": "Nombre_de_la_Hoja"
  },
  "email": {
    "sender_email": "tu_email@gmail.com",
    "receiver_email": "destinatario@example.com",
    "smtp_server": "smtp.gmail.com",
    "smtp_port": 587,
    "password": "tu_contraseña"
  }
}
```

## 🚀 Uso del Proyecto

### 1. Ejecutar el Análisis y Generar el Reporte

```bash
python src/generate_report.py
```

Este script realizará los siguientes pasos:
- Conectarse a Google Sheets y obtener los datos de ventas.
- Procesar los datos usando Pandas para calcular las métricas clave.
- Generar gráficos de ventas semanales usando Matplotlib.
- Enviar un correo electrónico con el gráfico adjunto como reporte semanal.

### 2. Automatización del Envío Semanal del Reporte

Para automatizar el envío semanal del reporte, configura una tarea cron en MacOS:

1. Abre el archivo crontab en la terminal:
   ```bash
   crontab -e
   ```

2. Añade la siguiente línea para ejecutar el script todos los lunes a las 8:00 AM:
   ```bash
   0 8 * * 1 /usr/bin/python3 /path/to/your_script.py
   ```

## 📝 Licencia

Este proyecto está licenciado bajo la Licencia MIT. Ver el archivo [LICENSE](LICENSE) para más detalles.

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Siéntete libre de abrir issues o enviar pull requests.

## 📧 Contacto

Para cualquier consulta o sugerencia, puedes contactar a [tu_email@gmail.com](mailto:tu_email@gmail.com).