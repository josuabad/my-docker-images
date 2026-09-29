## ¿Cómo adjuntar un volumen previamente creado?

Para crear un volumen:

```bash
docker volume create nombre_de_tu_volumen
```

Contenido del Compose para estos casos:

```YAML
services:
  python-app:
    image: python:3.12-slim
    # container_name: python3.14_env
    working_dir: /workspace
    volumes:
      - .:/workspace
      - pip_cache:/usr/local/lib/python3.12/site-packages
    tty: true # Mantener el contenedor vivo sin fallar

    # command: ["tail", "-f", "/dev/null"]

    # deploy:
    #   resources:
    #     limits:
    #       cpus: "6.0"
    #       memory: 12G

volumes:
  pip_cache:
    external: true

```
