<div>
<img src="https://img.shields.io/badge/Ubuntu-A34F26?style=for-the-badge&logo=ubuntu&logoColor=white" alt=""/>
<img src="https://img.shields.io/badge/PHP-C34F26?style=for-the-badge&logo=php&logoColor=white" alt=""/>
<img src="https://img.shields.io/badge/Markdown-E34F26?style=for-the-badge&logo=markdown&logoColor=white" alt=""/>
<img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt=""/>
<img src="https://img.shields.io/badge/CSS3-E34F26?style=for-the-badge&logo=css3&logoColor=white" alt=""/>	
<img src="https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white" alt=""/>
<img src="https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white" alt=""/>
<img src="http://img.shields.io/badge/-PHPStorm-181717?style=for-the-badge&logo=phpstorm&logoColor=white" alt=""/>	
<img src="https://img.shields.io/badge/Debian-A81D33?style=for-the-badge&logo=debian&logoColor=white" alt=""/>	
<img src="https://img.shields.io/badge/Notion-000000?style=for-the-badge&logo=notion&logoColor=white" alt=""/>
<img src="https://img.shields.io/badge/R-276DC3?style=for-the-badge&logo=r&logoColor=white" alt=""/>
</div>
<div>
<img src="https://img.shields.io/badge/R-Studio-blue" alt=""/>
</div>

#### ETAPAS DE CRIAÇÃO DO PROJETO - INTEGRAÇÃO GITHUB/IDE

Crie o repositório do projeto no GitHub;

    test_project
Utilize um terminal para acessar via SSH o servidor remoto;

    dev@dev:~$ sudo ssh -22 luciolemos@88.198.104.148
    [sudo] password for dev: ****
    luciolemos@88.198.104.148's password: ****
Clone diretamente na raiz `/var/www`do servidor, utilizando a opção SSH;
    luciolemos@cloud18344:~$ cd /var/www
    luciolemos@cloud18344:/var/www$ sudo git clone [git@github.com:luciolemos/test_project.git]
Observe o proprietário do diretório criado em /var/www. O Composer oferece restrições quanto a trabalhar com o root.

    luciolemos@cloud18344:/var/www$ ls -l
    total 44
    drwxr-xr-x  9 luciolemos            luciolemos            4096 Mar 27 07:11 crud
    drwxr-xr-x  8 luciolemos            luciolemos            4096 Nov 12 16:39 estagio_project
    drwxr-xr-x  2 root                  root                  4096 May 21  2024 exemplo_php
    drwxr-xr-x 12 luciolemos            luciolemos            4096 Oct 10 13:19 fsphp
    drwxr-xr-x  3 luciolemos            luciolemos            4096 Sep  4  2024 gateway
    drwxr-xr-x  2 root                  root                  4096 May 14  2024 html
    drwxrwxrwx  3 estagiario-verde-leao estagiario-verde-leao 4096 Feb  8 15:40 idg
    drwxr-xr-x  9 luciolemos            luciolemos            4096 Jul  9  2024 myapp
    drwxr-xr-x  4 luciolemos            luciolemos            4096 Jul 25  2024 new_crud
    drwxr-xr-x  7 root                  root                  4096 May 20  2024 php
    drwxr-xr-x  3 root                  root                  4096 Mar 28 21:07 test_project
Antes de instalar o composer é necessário alterar o proprietário e o grupo de todos os arquivos e diretórios dentro de /var/www/test_project para o usuário atual.

    luciolemos@cloud18344:/var/www/test_project$ sudo chown -R $USER:$USER /var/www/test_project
Agora observe o proprietário do diretório do projeto:

    total 44
    drwxr-xr-x  9 luciolemos            luciolemos            4096 Mar 27 07:11 crud
    drwxr-xr-x  8 luciolemos            luciolemos            4096 Nov 12 16:39 estagio_project
    drwxr-xr-x  2 root                  root                  4096 May 21  2024 exemplo_php
    drwxr-xr-x 12 luciolemos            luciolemos            4096 Oct 10 13:19 fsphp
    drwxr-xr-x  3 luciolemos            luciolemos            4096 Sep  4  2024 gateway
    drwxr-xr-x  2 root                  root                  4096 May 14  2024 html
    drwxrwxrwx  3 estagiario-verde-leao estagiario-verde-leao 4096 Feb  8 15:40 idg
    drwxr-xr-x  9 luciolemos            luciolemos            4096 Jul  9  2024 myapp
    drwxr-xr-x  4 luciolemos            luciolemos            4096 Jul 25  2024 new_crud
    drwxr-xr-x  7 root                  root                  4096 May 20  2024 php
    drwxr-xr-x  5 luciolemos            luciolemos            4096 Mar 28 21:14 test_project
Agora sim podemos proceder a instalação do Composer no projeto `Composer init`;

    luciolemos@cloud18344:/var/www$ cd test_project
    luciolemos@cloud18344:/var/www/test_project$ composer init
    ********
    Generated autoload files
    PSR-4 autoloading configured. Use "namespace Luciolemos\TestProject;" in src/
    Include the Composer autoloader with: require 'vendor/autoload.php';
No PhpStorm crie um projeto utilizando a opção `Create New Project from Existing Files` do menu File. Será criado em 
um diretório local o projeto test_project a partir dos arquivos existentes no servidor remoto. Utilize a opção `Web server
is on remote host files are accesseble via FTP/SFTP/FTPS` do PhpStorm.
