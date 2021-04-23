# laraauth (Tutorial)

Hello Everyone Today I am going to teach to how to do user authentication in laravel 8. in laravel 8 has been relesed and have major diffrence from previous laravel version 7 and 6. in laravel 7 and 6 we do use command "composer require laravel/ui"
but in laravel 8 had major changes in structure and many things introduce newly and many configuration has be done to not minding boilerplate for you application, one of that is Jetstream. Jetstream is laravel amazing design scaffolding. it's major change from standard Auth UI

so without westing more time in theory let's do some practical

1st Step create laravel project

-create laravel project by following command

composer create-project laravel/laravel laraauth

or you can create project with Jetstream by following command

Laravel new projectapp --jet

2nd Step: Database create and connect with laravel

let's goto phpmyadmin and create one data base for project aith name laraauth and add it to out .env file

image load phpmyadmin.png

.env file will be look like this

DB_CONNECTION=mysql
DB_HOST=localhost
DB_PORT=3306
DB_DATABASE=laraauth
DB_USERNAME=root
DB_PASSWORD=123456

next step is to migrate database, before that we need to handle one bug, max string length in AppServiceProvider.php file

add Schema::defaultstringLength(191); link in boot function

and use Illuminate\Support\Facades\Schema; at top

the file will be look like as follow

image AppServiceProvider.png

3rd step: migrate database
hit the php artisan migrate command and migrate database

image migratedatabase.png

4th step -install jetstream
now a time let's install jetstream into out project

composer require laravel/jetstream

image Jetstreaminstall.png

its advice to install jetstream in fresh project, with jetstream we need to install one of two stack to install layouts, login , register and dashboard route and templates. so let's install jetstream stacks

5th step - install stack

Jetstream have two stack livewire and inertia, here we will install livewire because its install everything what we needed. I will write one blog about comparesion and individual example for livewire and inertia

let's install livewire by following command

php artisan jetstream:install livewire

image livewire.png

let's migrate latest created migrations

php artisan migrate

image newmigrateafterlivewireinstall.png

6th step: build css and js of project and first run out application

let's imstall node packages and build css and js file for project by following commands

npm install
npm run dev

it's all set let run server by

php artisan serve

image firstlookofapp.png

lets setup temp mail setver in mail trail

click on user google account or user github account
image mailtrapsignin.png

select latavel 7+
image mailtrap_configurations.png

copy configurations

MAIL_MAILER=smtp
MAIL_HOST=smtp.mailtrap.io
MAIL_PORT=2525
MAIL_USERNAME=f915874e988c27
MAIL_PASSWORD=fcc1115d20f98f
MAIL_ENCRYPTION=tls

now lets register with new user

image register2.png

after register you will redirect to dashboard

image dashboard.png

let's check other functionalities

check forgot password

image forgotpassword.png

let's check mail in mailtrap

image resetpasswordlinkmail.png

click on reset password button

image resetpassword.png

password has been reset now let's login

image login.png

and it's all work fine

if you have any query you can ask me on any of my social media handle or you can mail me on learning@dreamseekerinfotech.com
