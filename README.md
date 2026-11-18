# Introducción a PHP 8 mediante ejemplos

📖 **Lea el tutorial: [https://stahe.github.io/ales-php8-oct-2026/](https://stahe.github.io/ales-php8-oct-2026/)**

Este curso enseña el lenguaje [PHP](https://www.php.net) 8.5 **mediante ejemplos**: más de 300 archivos PHP, comentados línea por línea, con los resultados de su ejecución reproducidos. Comienza con los fundamentos del lenguaje y avanza hasta los servicios web y una aplicación web MVC.

Se trata de una reescritura para PHP 8 del curso [Introducción a PHP 7 mediante ejemplos](https://stahe.github.io/ales-php7-juillet-2019/) (2019): mismo esquema, mismos ejemplos, mismo hilo conductor, pero con código actualizado. Entre PHP 7 y PHP 8.5, muchas funcionalidades han quedado **obsoletas** (*deprecated*): el código de este curso no utiliza **ninguna** de ellas. Todos los scripts se ejecutaron con PHP 8.5 configurado para informar de todo (`error_reporting = E_ALL`): ningún mensaje `Deprecated` aparece en sus resultados.

| Curso PHP 7 (2019) | Curso PHP 8 (2026) |
|---|---|
| PHP 7.3 | PHP 8.5 |
| NetBeans | VS Code + PHP Intelephense |
| Codeception | PHPUnit 12 |
| Postman | curl |
| SwiftMailer, hMailServer | Symfony Mailer, Mailpit |
| funciones `imap_*` (eliminadas del núcleo de PHP en 8.4) | clientes POP3/IMAP escritos con sockets |
| propiedades dinámicas, getters/setters | propiedades tipadas, `readonly`, promoción de parámetros del constructor |
| `switch`, constantes de clase | `match`, enumeraciones (`enum`) |
| `PDO::MYSQL_ATTR_*` (obsoleto en 8.5) | `PDO::connect()`, `Pdo\Mysql`, `Pdo\Pgsql` |
| `deny from all` (Apache 2.2) | un directorio `public/` y `Require all denied` (Apache 2.4) |

## Esquema del curso

| Capítulo | Contenido |
|---|---|
| Instalación | Laragon 8 (PHP 8.5, Apache, MySQL, PostgreSQL, Redis), VS Code, Composer |
| Fundamentos de PHP | variables, tipado estricto, arreglos, cadenas, funciones (argumentos con nombre, `match`, funciones flecha, operador pipe `\|>` de PHP 8.5), archivos de texto, JSON |
| Clases, interfaces | atributos tipados, promoción en el constructor, `readonly`, ganchos de propiedades y visibilidad asimétrica (PHP 8.4), enumeraciones, `#[\Override]`, `clone` con modificaciones (PHP 8.5), tipos de intersección |
| Excepciones y errores | la jerarquía `Throwable` en PHP 8, advertencias de PHP 7 convertidas en excepciones |
| Traits, aplicaciones en capas | reutilización de código; arquitectura [DAO] / [lógica de negocio] / [consola] |
| Pruebas | PHPUnit 12: proveedores de datos mediante atributos, excepciones esperadas |
| Bases de datos | PDO con MySQL 8 y PostgreSQL: sentencias preparadas, transacciones |
| Funciones de red | TCP, HTTP, SMTP, POP3, IMAP, implementados primero con sockets y luego con bibliotecas |
| Servicios web | páginas dinámicas, JSON, parámetros GET/POST, sesiones, autenticación, HTTPS |
| XML | SimpleXML y la nueva API `Dom\XMLDocument` de PHP 8.4 |

## El hilo conductor: un calculador del impuesto sobre la renta en 13 versiones

A lo largo del curso, versión tras versión, construimos un **calculador del impuesto sobre la renta**:

- **versiones 1 y 2**: un script, funciones, archivos de texto y JSON;
- **versión 3**: clases; **versión 4**: una arquitectura en capas, probada con PHPUnit;
- **versiones 5 a 7**: datos fiscales en una base de datos MySQL, luego PostgreSQL, y luego cualquiera de las dos;
- **versiones 8 a 11**: un servicio web y su cliente de consola: autenticación, sesiones, registro de eventos (logging), notificaciones por correo electrónico al administrador en caso de errores, caché Redis, respuestas en JSON y luego en XML;
- **versión 12**: una aplicación web **MVC** que devuelve respuestas en JSON, XML o HTML (Bootstrap 5), con un cliente de consola para el servicio JSON;
- **versión 13**: seguridad de los archivos de la aplicación (solo la carpeta `public/` es visible desde la web).



## Tecnologías

PHP 8.5 · Apache 2.4 · MySQL 8.4 · PostgreSQL · Redis · Composer · PHPUnit 12 · Symfony HttpFoundation 8 · Symfony HttpClient 8 · Symfony Mailer 8 · Predis 3 · zbateson/mail-mime-parser 3 · Mailpit · Bootstrap 5 · Laragon 8 · VS Code

## Requisitos previos

- Experiencia previa en programación en cualquier lenguaje.
- Windows y [Laragon](https://laragon.org) 8 (que incluye PHP 8.5, Apache, MySQL, PostgreSQL, Redis y Composer), [VS Code](https://code.visualstudio.com) y su extensión de IntelliSense para PHP. Las instrucciones de instalación se proporcionan al comienzo del curso.

## Autor

Este curso y su código fueron escritos por **Claude**, la IA de [Anthropic](https://www.anthropic.com) (octubre de 2026), a petición de Serge Tahé, a partir de su curso de PHP 7 de 2019.
