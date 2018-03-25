# yii2-docker-basic
Nginx + PHP-FPM + MySQL docker-compose layout for yii2 basic template

**Docker setup*
1. Clone this repo into `docker` folder inside your yii2 project root
2. `cd docker`
3. `docker-compose build`
4. `docker-compose up -d`

**Yii2 setup**
1. Update yii2 config with new dbhost (which is `db`).  
    ```
    ...
    'components' => [
        'db' => [
            'class' => 'yii\db\Connection',
            'dsn' => 'mysql:host=db;dbname=dbname',
            'username' => 'username',
            'password' => 'password',
            'charset' => 'utf8',
        ],
        ...
    ```  
    
    You can check other DB credentials in `docker-compose.yml`

2. Open shell to `php` container via `docker-compose exec php bash`
    1. Install composer and dependencies from `composer.json`
    2. Apply migrations
    
3. Test your application by going to `http:\\localhost\`