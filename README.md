Работает: 14.05.2020 arbeit  только внимательнее читать надо и main.include .. включить вывод ошибок в журнал.

$DBDebug = false; //true
$DBDebugToFile = false; // root of site
$SERVER_PORT = $_SERVER["SERVER_PORT"] = 89;  //прячем нормально 80 и 443
@set_time_limit(3600);
#@ini_set("allow_call_time_pass_reference", "on");  //php5.4 + off
@ini_set("memory_limit", "512M");   // php-fpm nginx - into config php_value

error_reporting(E_ALL);

07-Aug-2021 15:49:13 Europe/Moscow] PHP Notice:  Undefined index: ____1205930794 in /var/www/html/a1/index.php on line 55
[07-Aug-2021 15:49:13 Europe/Moscow] PHP Notice:  Trying to access array offset on value of type null in /var/www/html/a1/index.php on line 55
[07-Aug-2021 15:49:13 Europe/Moscow] PHP Fatal error:  Uncaught Error: Call to undefined function ___1444055005() in /var/www/html/a1/index.php:66
Stack trace:
#0 [internal function]: Decode->{closure}(Array)
#1 /var/www/html/a1/index.php(67): preg_replace_callback('/___1444055005\\...', Object(Closure), '<? $GLOBALS['__...')
#2 /var/www/html/a1/index.php(43): // no variables


Decode->edit_variables_function('GLOBAL_FUNCTION...')


Скрипт полуавтоматически преобразует закодированные файлы Bitrix в читабельный формат.

![Пример использования](https://github.com/santosha2003/bitrix-decoder/blob/master/preview.jpg)

# Инструкция

1. Открываем файл и копируем закодированную часть.
2. Приводим к правильному виду через http://beautifytools.com/php-beautifier.php (можно стандартными средствами IDE) / ну у меня не сработало очень часа полтора плиз вейт не дождался - поставил убунту и там в миднайт командере все поправил за это время - и копируем в файл decode_file.php
3. В подготовленом файле сверху находятся один или 2 массива и функция. Вырезаем их (all code ) и вставляем в файл variables.php. Начинаться они будут примерно так: 
  * Массив: `$GLOBALS['____153126584'] = array(base64_deco...`
  * Функция: `if (!function_exists(__NAMESPACE__.'\\___1076931394')) { function ___1076931394($_367941623) {...`
4. Название массива копируем в 'GLOBAL_VARIABLES' в index.php а названия функций в 'GLOBAL_FUNCTIONS' они обозначены тремя нижними подчеркиваниями.
5. Запускаем скрипт из консоли `php index.php`
6. Появится файл encode_file.php в нем будет читабельный код.

### Пример строки

Было:
`$_236203417 = $GLOBALS[___1076931394(0)]->Query(___1076931394(1), true);`

Стало:
`$_236203417 = $GLOBALS['DB']->Query('SELECT VALUE FROM b_option WHERE NAME='~PARAM_MAX_USERS' AND MODULE_ID='main' AND SITE_ID IS NULL', true);`

эта.. лицензия у меня есть за деньги, сайт *** а вот вирус с майнером все равно пролез. Открыл все файлы что бы видно было.
