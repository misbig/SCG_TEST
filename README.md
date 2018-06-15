

__________               __      _________ __                
\______   \ ____   ____ |  | __ /   _____//  |______ _______ 
 |       _//  _ \_/ ___\|  |/ / \_____  \\   __\__  \\_  __ \
 |    |   (  <_> )  \___|    <  /        \|  |  / __ \|  | \/
 |____|_  /\____/ \___  >__|_ \/_______  /|__| (____  /__|   
        \/            \/     \/        \/           \/       
    ----------------------------------------------------------------- 

Hi there! Welcome to easy PHP framework for beginners!

Good for beginner who have no idea about PHP framework, let start from easy code here.

To get you started, let download all files and test run with Apache or try on Clound9(c9.io).

1) Start from ./module/Application/config/module.config.php

2) For serious configuration, you have to change DB configuration like below
'Db' => array(
        'driver' => 'Pdo',
        'dsn' => 'mysql:dbname=dbname;host=db host',   
        'driver_options' => array( 
            PDO::MYSQL_ATTR_INIT_COMMAND => 'SET NAMES \'UTF8\''
        ),
        'username' => 'username',
        'password' => 'password', 
    ),

3) Make sure your DB is correct and have "users" table and contain field id, name and last_update

4) Check router from router array.

5) Add controller like below
'controllers' => array(
        'invokables' => array(
            //add controller
            'Application\Controller\Index' => 'Application\Controller\IndexController',
            //'Application\Controller\Xxx' => 'Application\Controller\XxxController',
        ),
    ),
    
6) Every Action have to add view like below
#index
'application/index/index' => __DIR__ . '/../view/index/index.phtml',
'application/index/user' => __DIR__ . '/../view/index/user.phtml',


Ex1)
Start from IndexController ./module/Application/src/Application/Controller/IndexController.php

Ex2)
How to use multiple languages
Check ./module/Application/src/Application/language/
let use .po and .mo
like below

msgid "title"
msgstr "TH ZF3"

and try <?=$this->translate('title');?>

* All views here /module/Application/view/

URL will be like this https://www.xxxx.com/[language]/[Action]/ :: https://www.xxxx.com/user/th/
For router you can change later, but for the beginner let follow this structure first.

Ex3)
Check another Action on IndexController(How to add data - edit - view - delete)

Happy coding!
SCG CTO,
Tonytoons


## Documentation

ZF1 https://docs.zendframework.com/tutorials/
Po2Mo https://po2mo.net/
Bootstrap http://getbootstrap.com/getting-started/ for css framework!

git clone git@bitbucket.org:Tonytoons/zf3-starter-kit.git


#Upgrade to php7.1 on C9. #follow below.
PHP 7.1
sudo add-apt-repository ppa:ondrej/php -y
sudo apt-get update -y
 
sudo apt-get install php7.1-curl php7.1-cli php7.1-dev php7.1-gd php7.1-intl php7.1-mcrypt php7.1-json php7.1-mysql php7.1-opcache php7.1-bcmath php7.1-mbstring php7.1-soap php7.1-xml php7.1-zip -y
 
sudo mv /etc/apache2/envvars /etc/apache2/envvars.bak
sudo apt-get remove libapache2-mod-php5 -y
sudo apt-get install libapache2-mod-php7.1 -y
sudo cp /etc/apache2/envvars.bak /etc/apache2/envvars
 
sudo a2dismod php5
sudo a2enmod php7.1

sudo apt-get purge php*

sudo apt-get install php7.1-mysql php7.1-curl php7.1-json php7.1-cgi  php7.1 libapache2-mod-php7.1

sudo apt-get install php7.1-mbstring
sudo apt-get autoremove
sudo service apache2 restart
sudo apt-get install php7.1-simplexml
 
sudo service apache2
sudo service apache2 restart
