# Magento2Docker
Сборка работает если в /etc/hosts добавить :
  127.0.0.1       www.magento230.docker magento230.docker
А composer запуститься , только если внутри контейнера запустить composer install  
  
# Нужно сделать  
1) Нужно еще настроить composer
2) возможно лучше создать images (apache2 +php выделить в отдельный образ)
3) настроить  Varnish
4) hosts установить через hostname
