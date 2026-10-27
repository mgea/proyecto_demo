# proyecto_demo
demo Proyecto comunicacion audiovisual interactivo usando IA 



Contiene 

* proyecto 
* profile card (about)













## Prompt 

Actua como experto en diseño web y crea una webapp con estilo para proyecto de documental interactivo llamado "Hijos del Sacromonte" que consiste en rescatar la historia de  figuras destacadas del flamenco en Granada. La página contiene un header con  logotipo y enlaces a Inicio, proyecto, Acerca de  , y tiene la posibilidad de activar/desactivar música de fondo. Contiene un hero Section donde aparecerá una informacion sobre el proyecto y una imagen de fondo o al lado que se integra con un pequeño efecto parallax. EL texto debe tener buen contraste con imagen de fondo. A continuacion tendríamos un carrusel de fotografias de los artistas que tendrán efecto hover (de  B/N a color y efecto zoom) con el nombre en la parte inferior y que al pulsarlas se abre en la parte inferior un panel con contenido relacionado con ese artista: video_IA (un video en formato vertical de youtube que debe ir incrustado ) y que se lanza automaticamente al abrir ese panel aunque tiene controles para pausar/volver a ver , entrevista (video en formato 9:6 de youtube que tambien debe ir incrustado con sus controles). Se debería evitar que ambos videos se viesen simultaneamente, por lo que cuando se active uno, automatiamente se pause el otro. Debajo aparecerán varios recursos (array variable) que serán como cards dispuestas en formato bento y que contienen: img: imagen, descripción: información del recurso y link: al recurso. Generalmente podrán ser noticias, enlaces a sonidos, etc. Finalmente hay un apartado de "Proyecto" donde se explica el proceso de ideación y contexto histórico, enlaces a recursos externos y finalizando con informacion del "Autor" y enlace a su página web/porfolio que se obtiene del fichero JSON. Hay un footer con datos sobre: 
Investigación y Comunicación Multimedia, Trabajo realizado por el periodista peruano Marco Gonzales Cadillo. Curso: *Bases Teóricas y Metodológicas para la Investigación en Medios Audiovisuales en la Era Digital.* Máster en Nuevos Medios Interactivos y Periodismo Multimedia · Universidad de Granada. 

**Igualación de Altura de Vídeos (IA y Entrevista)**: Ambos contenedores de reproductor en el panel del artista tienen ahora una altura idéntica e inmersiva (`aspect-ratio: 16/9` o min-height equilibrado con `height: 100%`) para evitar desbalances visuales en el panel.

La galeria de imagenes de artistas se pueda mover para izda o dcha la galería con el ratón, si no se hace nada, sigue pasando hacia izda: 

* **Draggable & Auto Infinite Carousel (100vw x 100vh)**: Drag with mouse/touch to slide left or right in real-time, wheel scroll support, seamless infinite loop via JavaScript `requestAnimationFrame`, automatic smooth leftward resumption after user interaction, grayscale to color + zoom hover effect, and robust SVG fallbacks for all images.
* **Exclusive Dual YouTube Players**: Vertical 9:16 AI portrait and 16:9 documentary interview embed with YouTube IFrame API automatic mutual pausing.
* **Bento Grid Layouts**: Dynamic Bento Grid for artist news/resources and general historical context.
* **Interactive Web Audio Ambient Music**: Integrated sound generator with visual equalizer state.

* **Dynamic JSON Upload**: Fully compatible with your specified `autoload.json` structure with graceful fallback defaults.

* **Carga Automática de `autoload.json`**: Al iniciar la aplicación web se realiza un `fetch('./autoload.json')`. Si el archivo existe en el directorio actual, se carga dinámicamente de forma automática. De lo contrario, se cargan los datos locales por defecto.

* **Hero Parallax & Complete Academic Footer**: Official credits for UGR, Marco Gonzales Cadillo, and course details.

Toda esa informacion dinámica se almacena en un fichero llamado "contenido.json" que se carga dinámicamente (Dynamic JSON Data Loading) al iniciar la aplicación, si no existe, habrá datos por defecto y un botón para cargar fichero json valido en header. Tambien la musica de fondo se puede modificar dinámicamente en fichero JSON. La estrcutura es la siguiente 

```
{
  "bailaores": [
    {
      "id": "mariquilla",
      "nombre": "Mariquilla",
      "rol": "Maestra & Bailaora de Leyenda",
      "descripcion": "María Guardia Gómez, conocida históricamente como Mariquilla, es una de las grandes bailaores de Granada. Hija de la cantaora y bailaora María, desde su cuna en el Sacromonte hasta las giras internacionales, Mariquilla encarna la elegancia, el temperamento sobrio y la maestría en el braceo que definió la escuela flamenca granadina.",
      "wixUrl": "https://hijosdelsacromonte.wixsite.com/hijos-del-sacromonte/blank",
      "iaVideo": "https://www.youtube.com/embed/JU5ME6Q5xRU",
      "entrevista": "https://www.youtube.com/embed/oLf7NE8LTdo",
      "imagen": "./img/mariquilla.jpg",
      "noticias": [
        {
          "titulo": "Mariquilla recibe el homenaje a toda una vida dedicada al baile flamenco",
          "medio": "Diario de Granada",
          "url": "https://hijosdelsacromonte.wixsite.com/hijos-del-sacromonte/blank",
          "imagen": "https://images.unsplash.com/photo-1514525253161-7a46d19cd819?q=80&w=400&auto=format&fit=crop",
          "fecha": "2024"
        },
        {
          "titulo": "La cuna del flamenco granadino y la estirpe de María Guardia Gómez",
          "medio": "Revista Flamenca",
          "url": "https://hijosdelsacromonte.wixsite.com/hijos-del-sacromonte/blank",
          "imagen": "https://images.unsplash.com/photo-1508700115892-45ecd05ae2ad?q=80&w=400&auto=format&fit=crop",
          "fecha": "2023"
        }
      ],
      "redesSociales": {
        "youtube": "https://www.youtube.com/watch?v=oLf7NE8LTdo",
        "instagram": "https://instagram.com",
        "facebook": "https://facebook.com"
      }
    },
    {
      "id": "canastera",
      "nombre": "María la Canastera",
      "rol": "Matriarca & Leyenda de la Cueva",
      "descripcion": "María Cortés Heredia, 'María la Canastera', es el alma inmortal del Sacromonte. Su cueva fue epicentro cultural internacional por donde desfilaron artistas, diplomáticos y amantes del arte para presenciar la zambra pura y el legado viviente del pueblo gitano.",
      "wixUrl": "https://hijosdelsacromonte.wixsite.com/hijos-del-sacromonte/blank-1",
      "iaVideo": "https://www.youtube.com/embed/JU5ME6Q5xRU",
      "entrevista": "https://www.youtube.com/embed/oLf7NE8LTdo",
      "imagen": "./img/canastera.jpg",
      "noticias": [
        {
          "titulo": "La Cueva de María la Canastera: Bien de Interés Cultural en Granada",
          "medio": "Granada Hoy",
          "url": "https://hijosdelsacromonte.wixsite.com/hijos-del-sacromonte/blank-1",
          "imagen": "https://images.unsplash.com/photo-1543857778-c4a1a3e0b2eb?q=80&w=400&auto=format&fit=crop",
          "fecha": "2024"
        }
      ],
      "redesSociales": {
        "youtube": "https://www.youtube.com/watch?v=oLf7NE8LTdo",
        "facebook": "https://facebook.com"
      }
    },
    {
      "id": "manolete",
      "nombre": "Manolete",
      "rol": "Maestro del Baile Masculino",
      "descripcion": "Manuel Santiago Maya, conocido universalmente como 'Manolete'. Referente indiscutible del baile flamenco masculino por la sobriedad de sus pases, el señorío en escena y la elegancia rítmica transmitida directamente de la casta sacromontana.",
      "wixUrl": "https://hijosdelsacromonte.wixsite.com/hijos-del-sacromonte/blank-2",
      "iaVideo": "https://www.youtube.com/embed/JU5ME6Q5xRU",
      "entrevista": "https://www.youtube.com/embed/oLf7NE8LTdo",
      "imagen": "./img/manolete.jpg",
      "noticias": [
        {
          "titulo": "El legado inalcanzable de Manolete en la Escuela de Baile del Sacromonte",
          "medio": "El País - Cultura",
          "url": "https://hijosdelsacromonte.wixsite.com/hijos-del-sacromonte/blank-2",
          "imagen": "https://images.unsplash.com/photo-1547153760-18fc86324498?q=80&w=400&auto=format&fit=crop",
          "fecha": "2023"
        }
      ],
      "redesSociales": {
        "youtube": "https://www.youtube.com/watch?v=oLf7NE8LTdo",
        "instagram": "https://instagram.com"
      }
    },
    {
      "id": "antonia",
      "nombre": "Antonia la Gallina",
      "rol": "Bailaora Festera de Racial Pureza",
      "descripcion": "Antonia 'La Gallina' encarna el genio festero, la visceralidad y el compás espontáneo de la zambra gitana. Su estampa bailaora es un pilar fundamental en la memoria oral de las familias del Sacromonte.",
      "wixUrl": "https://hijosdelsacromonte.wixsite.com/hijos-del-sacromonte/blank-3",
      "iaVideo": "https://www.youtube.com/embed/JU5ME6Q5xRU",
      "entrevista": "https://www.youtube.com/embed/oLf7NE8LTdo",
      "imagen": "./img/gallina.jpg",
      "noticias": [
        {
          "titulo": "La farsa y la zambra: el compás único de Antonia la Gallina",
          "medio": "Cultura Andaluza",
          "url": "https://hijosdelsacromonte.wixsite.com/hijos-del-sacromonte/blank-3",
          "imagen": "https://images.unsplash.com/photo-1533105079780-92b9be482077?q=80&w=400&auto=format&fit=crop",
          "fecha": "2022"
        }
      ],
      "redesSociales": {
        "youtube": "https://www.youtube.com/watch?v=oLf7NE8LTdo"
      }
    },
    {
      "id": "director",
      "nombre": "José Sánchez-Montes",
      "rol": "Director y Documentalista",
      "descripcion": "Cineasta y creador audiovisual. José Sánchez-Montes ha dedicado años a investigar y capturar en celuloide la memoria viva de los maestros flamencos en su célebre documental 'Sacromonte. Los sabios de la tribu', haciendo posible la divulgación interactiva de este patrimonio.",
      "wixUrl": "https://hijosdelsacromonte.wixsite.com/hijos-del-sacromonte/blank-4",
      "iaVideo": "https://www.youtube.com/embed/JU5ME6Q5xRU",
      "entrevista": "https://www.youtube.com/embed/oLf7NE8LTdo",
      "imagen": "./img/joseSanchezMontes.jpg",
      "noticias": [
        {
          "titulo": "Sánchez-Montes rescata el archivo inédito de las zambras en el cine",
          "medio": "Fotogramas",
          "url": "https://hijosdelsacromonte.wixsite.com/hijos-del-sacromonte/blank-4",
          "imagen": "https://images.unsplash.com/photo-1485846234645-a62644f84728?q=80&w=400&auto=format&fit=crop",
          "fecha": "2024"
        }
      ],
      "redesSociales": {
        "youtube": "https://www.youtube.com/watch?v=oLf7NE8LTdo",
        "instagram": "https://instagram.com"
      }
    }
  ],
  "proyecto": {
    "descripcion": "Proyecto de recuperación de la memoria",
    "recursos": [
      {
        "titulo": "El flamenco",
        "descripcion": "página oficial",
        "url": "https://www.flamencogranada.org/",
        "imagen": "https://images.unsplash.com/photo-1547153760-18fc86324498?q=80&w=400&auto=format&fit=crop"
      }
    ]
  },
  "autor": {
    "nombre": "Marco González",
    "titulo": "Investigación y Comunicación Multimedia",
    "descripcion": "Trabajo desarrollado por el periodista peruano Marco Gonzales Cadillo en el marco del curso 'Bases Teóricas y Metodológicas para la Investigación en Medios Audiovisuales en la Era Digital' del Máster en Nuevos Medios Interactivos y Periodismo Multimedia de la Universidad de Granada.",
    "img": "./img/Marco.png",
    "recursos": [
      {
        "id": "portfolio",
        "url": "https://www.flamencogranada.org/",
        "imagen": "https://images.unsplash.com/photo-1547153760-18fc86324498?q=80&w=400&auto=format&fit=crop"
      },
      {
        "id": "instagram",
        "url": "https://instagram.com/marco",
        "imagen": "https://images.unsplash.com/photo-1547153760-18fc86324498?q=80&w=400&auto=format&fit=crop"
      }
    ]
  },

  "configuracion": {
    "sonido": "./snd/flamenco.mp3"
  }


}

```



