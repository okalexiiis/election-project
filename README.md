Project Manager CLI

Gestor de proyectos local y remoto para desarrolladores.
Permite listar, crear, abrir, clonar, sincronizar y gestionar proyectos de manera eficiente desde la terminal, integrando GitHub y workflows con tmux.

🔹 Características principales

Gestión de proyectos locales en $PROJECTS_DIR.

Integración con GitHub para clonar repositorios, crear repos remotos y manejar repos privados.

Automatización de workflows y plantillas por proyecto.

Integración con editores (VSCode, Neovim) y terminal multiplexer (tmux).

Backups y sincronización entre máquinas.

CLI interactiva con subcomandos y flags avanzados.

🔹 Instalación
Requisitos

Git

Bash (o Go si usas versión compilada)

Opcional: VSCode / Neovim / tmux

Instalar desde código
git clone https://github.com/okalexiiis/project-manager-cli.git ~/Projects/project-manager-cli
cd ~/Projects/project-manager-cli
chmod +x tool.sh
sudo ln -s ~/Projects/project-manager-cli/tool.sh /usr/local/bin/proj


Ahora puedes ejecutar:

proj --help

🔹 Uso
1️⃣ Listar proyectos
proj list               # Lista proyectos locales
proj list --repos       # Lista repositorios de GitHub
proj list --filter <texto>  # Filtra proyectos por nombre

2️⃣ Crear proyectos
proj new <nombre>            # Crear proyecto local vacío
proj new <nombre> -g         # Inicializar git repo
proj new <nombre> -t node    # Crear proyecto con plantilla Node
proj new <nombre> --repo     # Crear repo local y remoto en GitHub

3️⃣ Clonar repositorios
proj clone <nombre>          # Clona repo de GitHub usando tu usuario
proj clone <url> --ssh       # Clona repo con SSH
proj clone <nombre> -u otro  # Clonar repo de otro usuario
proj clone <nombre> --dir ~/OtrosProyectos  # Cambiar directorio destino

4️⃣ Abrir proyectos
proj open <nombre>           # Abrir proyecto en editor por defecto
proj open <nombre> --tmux    # Abrir proyecto en sesión tmux
proj open <nombre> --code    # Abrir en VSCode
proj open <nombre> --nvim    # Abrir en Neovim

5️⃣ Eliminar proyectos
proj delete <nombre>         # Eliminar proyecto local
proj delete <nombre> --backup  # Hacer backup antes de eliminar
proj delete <nombre> --force   # Eliminar sin confirmación

6️⃣ Backup
proj backup <nombre>        # Backup de proyecto individual
proj backup --all           # Backup de todos los proyectos
proj backup <nombre> --zip  # Guardar backup en ZIP
proj backup <nombre> --dir ~/Backups  # Carpeta destino

7️⃣ Sincronización con GitHub
proj sync <nombre>          # Ejecuta git pull
proj sync --all             # Actualiza todos los proyectos con repos remotos
proj push <nombre>          # Empuja cambios al repo remoto
proj push <nombre> --branch dev  # Empuja cambios a branch específica

8️⃣ Configuración
proj config set editor code        # Configurar editor por defecto
proj config set projects_dir ~/Proyectos  # Cambiar directorio base
proj config get editor             # Mostrar configuración
proj config list                   # Listar todas las configuraciones

🔹 Integración avanzada

Tmux: abrir sesiones por proyecto, layouts predefinidos, scripts automáticos.

GitHub API: listar repositorios, manejar issues y pull requests, crear repos remotos.

Templates y workflows: crear proyectos con estructura predefinida y comandos automáticos.

🔹 Futuras mejoras

CLI interactiva con menú TUI.

Historial de acciones (clones, backups, aperturas).

Sincronización en la nube (S3, Google Drive, Nextcloud).

Plugins y scripts personalizados por proyecto.

🔹 Contribución

Fork del repositorio

Crear tu branch: git checkout -b feature/nueva-funcionalidad

Commit de cambios: git commit -am 'Agrega nueva funcionalidad'

Push a branch: git push origin feature/nueva-funcionalidad

Crear Pull Request
