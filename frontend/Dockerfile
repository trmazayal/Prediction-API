FROM nginx:1.18-alpine AS frontend
FROM tiangolo/uvicorn-gunicorn-fastapi:python3.7

COPY --from=frontend /usr/share/nginx/html /app/frontend
RUN pip install -U pip aiofiles python-multipart jinja2
COPY /frontend /app
