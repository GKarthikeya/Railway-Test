web: /bin/sh -c "echo 'PORT is set to $PORT' && gunicorn grok.app:app --bind 0.0.0.0:${PORT:-8080} --workers 1 --timeout 120"
