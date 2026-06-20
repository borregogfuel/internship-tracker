# Internship Tracker

Plataforma para rastrear internships disponibles, con enfoque en programas early como Duolingo Thrive, Microsoft Explore, Google STEP, Meta University y Uber STAR.

## Por qué

Estos programas suelen abrir aplicaciones antes que el resto de los internships de verano, y muchas veces no aparecen en los repositorios públicos de GitHub hasta que alguien hace un pull request. La idea es enterarme apenas abran, antes que la mayoría.

Es un proyecto personal — uso inicial para mí, estudiante de 2do semestre buscando opciones para Summer 2027. Si funciona bien, lo voy a abrir a la comunidad del Tec de Monterrey.

También es mi proyecto de práctica como próximo AWS Builder Group Campus Captain de mi campus, así que está construido 100% en AWS.

## Cómo funciona

Dos fuentes de datos:

1. **Repositorio de GitHub** (SimplifyJobs/Summer2026-Internships) — una Lambda revisa el README cada hora y detecta internships nuevos o cambios de status.
2. **Portales directos de empresas** — una segunda Lambda vigila páginas de careers de empresas específicas que no aparecen en el repo público.

Cuando se detecta algo nuevo, se manda una alerta por email.

## Stack

- Frontend: React + Vite + TypeScript + Tailwind
- Backend: AWS Lambda + API Gateway
- Base de datos: DynamoDB
- Scheduling: EventBridge
- Notificaciones: SNS + SES
- Hosting: S3 + CloudFront
- Infraestructura: AWS CDK (TypeScript)
- CI/CD: GitHub Actions

Cada servicio de AWS se construye primero a mano en la consola para entender cómo funciona, y luego se recrea con CDK para que quede versionado.

## Estado

En construcción. Por ahora es uso personal, sin frontend todavía.