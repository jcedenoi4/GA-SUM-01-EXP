# GA-SUM-01-EXP · EXP-1: Spotify como sistema distribuido en la nube

Exposición del primer corte de **Aplicaciones Distribuidas (ISR-701)**.
Universidad Técnica Estatal de Quevedo · Facultad de Ciencias de la Computación · Carrera de Software · séptimo nivel, paralelo B.
Docente: Gleiston Guerrero Ulloa, PhD.

**Sistema analizado:** Spotify.

**Video del ensayo (máximo 12 minutos):** https://youtu.be/yxKQQ6LOazk (cada integrante grabó su parte por separado y luego se unieron en un solo video).

## Equipo y apartados

| Integrante | Apartados | Archivos principales |
|---|---|---|
| Apunte Pazmiño Washington German | 1. Presentación del sistema · 2. Arquitectura | `secciones/01_presentacion.tex`, `secciones/02_arquitectura.tex`, `notas/apartados/presentacion_arquitectura.tex`, `diagramas/arquitectura_spotify.drawio` |
| Cedeño Intriago Jilmar Jesus | 3. Transparencias · 5. Modelos de comunicación | `secciones/03_transparencias.tex`, `secciones/05_modelos_comunicacion.tex` |
| Mendoza Villarroel Elian Jossue | 4. CAP y PACELC · 7. Comparación | `secciones/04_cap_pacelc.tex`, `secciones/07_comparacion.tex`, `notas/apartados/cap_comparacion.tex` |
| Muñoz Vera Melanie Michelle | 6. Tolerancia a fallos · 8. PFC y conclusiones | `secciones/06_tolerancia_fallos.tex`, `secciones/08_pfc_conclusiones.tex`, `diagramas/analisis_causas_raiz.drawio` |

## Qué se necesita para compilar

- Una distribución de LaTeX con `pdflatex` y `biber`: [MiKTeX](https://miktex.org) en Windows (activar «instalar paquetes faltantes automáticamente») o TeX Live en Linux y macOS.
- Paquetes que usa el proyecto: `beamer`, `babel` (español), `biblatex` con el estilo `ieee` (paquete `biblatex-ieee`), `csquotes`, `booktabs`, `graphicx` y `lmodern`.

Para comprobar que todo está instalado:

```
pdflatex --version
biber --version
```

## Cómo compilar las diapositivas

Desde la carpeta raíz del repositorio, en este orden:

```
pdflatex presentacion
biber presentacion
pdflatex presentacion
pdflatex presentacion
```

El resultado es `presentacion.pdf`. `biber` arma la lista de referencias desde `referencias.bib`; las dos últimas pasadas de `pdflatex` ponen los números de las citas.

Si falta el archivo de alguna sección, la compilación sigue y deja el aviso `Falta el archivo secciones/...` en `presentacion.log`. Antes de la entrega final no debe quedar ningún aviso de ese tipo.

## Cómo compilar las notas

`notas/notas.tex` se compila también desde la carpeta raíz, porque las rutas de los apartados, de la bibliografía y de la foto del boceto parten de ahí:

```
pdflatex notas/notas.tex
biber notas
pdflatex notas/notas.tex
pdflatex notas/notas.tex
```

El resultado es `notas.pdf`, en la carpeta raíz.

## Estructura del repositorio

```
GA-SUM-01-EXP/
├── presentacion.tex      Archivo principal de las diapositivas: solo une las secciones
├── referencias.bib       Bibliografía común (biblatex, estilo IEEE)
├── secciones/            Una sección por apartado (NN_nombre.tex)
├── notas/
│   ├── notas.tex         Archivo principal de las notas técnicas
│   └── apartados/        Notas de cada integrante
├── diagramas/            Diagramas editables de draw.io (.drawio)
├── figuras/              Imágenes exportadas (.png) que usan las diapositivas
├── evidencias/           Capturas de lectura y foto del boceto a mano
└── README.md             Este archivo
```

Reglas para los archivos:

- Cada diagrama tiene su editable en `diagramas/` y su PNG exportado en `figuras/` con el mismo nombre.
- Nombres de archivo sin espacios ni tildes. Capturas de lectura: `evidencias/lectura_FUENTE_pPAGINA.png`.
- Los archivos de compilación (`.aux`, `.bbl`, `.log`, etc.) no se suben: el `.gitignore` ya los ignora.

## Cómo trabajamos con Git

- Cada integrante trabaja en su rama (por ejemplo, `washington-apunte`) y pasa su trabajo a `main` con un Pull Request.
- Antes de cada commit se compila la presentación y se revisa que no haya errores.
- Se agregan solo los archivos propios, por su nombre (sin `git add .`), con un mensaje que diga qué se hizo y dónde.
- No se usa `git push --force` ni `git reset --hard`, y las ramas no se borran al fusionar.

## Uso de inteligencia artificial

Cada archivo indica en su comentario inicial si se usó asistencia de IA y para qué. El detalle va en la declaración de IA del equipo.