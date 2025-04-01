# Soniditos API

API RESTful para el servicio de streaming de música Soniditos.

## Autenticación

La API utiliza autenticación por token Bearer. El token de acceso debe enviarse junto con cada solicitud en el encabezado de autorización:

```
Authorization: Bearer <Token>
```

El token se obtiene a través de la de configuración en una cuenta en https://soniditos.com/account-settings

## Recursos Principales

### Búsqueda
- `GET /search` - Buscar álbumes, artistas, playlists, canciones o usuarios

### Playlists
- `GET /playlists/{id}` - Obtener detalles de una playlist
- `POST /playlists` - Crear nueva playlist
- `PUT /playlists/{id}` - Actualizar playlist existente
- `DELETE /playlists/{id}` - Eliminar playlist
- `GET /playlists/{id}/tracks` - Listar canciones de una playlist
- `POST /playlists/{id}/tracks/add` - Agregar canciones a una playlist
- `POST /playlists/{id}/tracks/remove` - Quitar canciones de una playlist
- `POST /playlists/{id}/follow` - Seguir una playlist
- `POST /playlists/{id}/unfollow` - Dejar de seguir una playlist

### Artistas
- `GET /artists/{id}` - Obtener información de un artista
- `GET /artists/{id}/tracks` - Listar canciones del artista
- `GET /artists/{id}/albums` - Listar álbumes del artista
- `GET /artists/{id}/followers` - Listar seguidores del artista

### Álbumes
- `GET /albums/{id}` - Obtener detalles de un álbum

### Canciones
- `GET /tracks/{id}` - Obtener información de una canción
- `GET /tracks/{id}/comments` - Listar comentarios de una canción
- `GET /tracks/{id}/lyrics` - Obtener letra de una canción

### Etiquetas
- `GET /tags/{name}/tracks` - Listar canciones por etiqueta
- `GET /tags/{name}/albums` - Listar álbumes por etiqueta

### Géneros
- `GET /genres` - Listar todos los géneros disponibles

### Usuarios
- `GET /users/{id}` - Obtener perfil público de un usuario
- `GET /users/me/liked-tracks` - Listar canciones que me gustan
- `GET /users/me/liked-albums` - Listar álbumes que me gustan
- `GET /users/me/liked-artists` - Listar artistas que me gustan
- `GET /users/me/playlists` - Listar mis playlists
- `GET /users/me/followers` - Listar mis seguidores
- `GET /users/me/followed-users` - Listar usuarios que sigo

### Autenticación
- `POST /auth/register` - Registrar nueva cuenta
- `POST /auth/login` - Iniciar sesión y obtener token

## Paginación

Las respuestas paginadas incluyen:

```json
{
  "current_page": 1,
  "from": 1,
  "to": 100,
  "per_page": 25,
  "last_page": 156,
  "total": 264,
  "data": []
}
```

## Códigos de Estado

- `200` - Éxito
- `401` - No autenticado (token inválido o faltante)
- `403` - No autorizado (permisos insuficientes)
- `404` - Recurso no encontrado
- `422` - Datos inválidos

## Licencia

<p align="center">
	Repositorio generado por <a href="https://github.com/sabiopobre" target="_blank">virtu 🎣</a>
</p>

<p align="center">
	<img src="https://open.soniditos.com/cat_footer.svg" />
</p>

<p align="center">
	Copyright &copy; 2025
</p>

<p align="center">
	<a href="/LICENSE"><img src="https://img.shields.io/static/v1.svg?style=for-the-badge&label=License&message=MIT&logoColor=d9e0ee&colorA=363a4f&colorB=b7bdf8"/></a>
</p>
