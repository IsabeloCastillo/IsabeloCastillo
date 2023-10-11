# Bienvenid@s al Gitbhub IsabeloCastillo

### Aqui verás como trabajo mi codigo y los proyectos en los que actúo.

![](https://cdn.pixabay.com/photo/2016/10/11/21/43/geometric-1732847_1280.jpg)

import requests
import json

def mis_estadisticas_github(username):
    # URL para la API de GitHub que nos dará los datos del usuario
    url = f"https://api.github.com/users/{username}"
    
    # Realizamos la petición a la API de GitHub
    response = requests.get(url)
    
    if response.status_code == 200:
        # Parseamos la respuesta en JSON
        data = json.loads(response.text)
        
        # Imprimimos las estadísticas del usuario
        print(f"👤 Usuario: {data['login']}")
        print(f"📝 Bio: {data['bio']}")
        print(f"🏠 Ubicación: {data['location']}")
        print(f"🔗 URL: {data['html_url']}")
        print(f"👥 Seguidores: {data['followers']}")
        print(f"👣 Siguiendo: {data['following']}")
        print(f"🌟 Repositorios públicos: {data['public_repos']}")
        
    else:
        print(f"❌ Error: No se pudo recuperar la información del usuario {username}.")
        
# Probamos la función con tu nombre de usuario de GitHub
mis_estadisticas_github("https://github.com/IsabeloCastillo")

