# Vagrant

Этот проект настраивает виртуальную машину Vagrant с Ubuntu 20.04, устанавливает Docker и Docker Compose с помощью Ansible, и конфигурирует стек мониторинга Prometheus и Grafana. Настройка включает установку Node Exporter на ВМ и настройку Prometheus для сбора метрик с Node Exporter. Grafana предварительно настроена для использования Prometheus в качестве источника данных и включает предустановленный дашборд для визуализации собранных метрик.

## Предварительные условия

- Vagrant (https://developer.hashicorp.com/vagrant/install)
- VirtualBox (https://www.virtualbox.org/wiki/Downloads) или другой провайдер, совместимый с Vagrant)

## Инструкции по установке и запуску

1. **Клонируйте репозиторий**

   git clone https://github.com/Pomarus/vagrant
   
   cd vagrant

3. **Запустите Vagrant**
   
   vagrant up

   ```

   Эта команда выполнит следующие действия:
   - Создаст и запустит виртуальную машину с Ubuntu 20.04.
   - Выполнит playbook Ansible для установки Docker, Docker Compose и Node Exporter.
   - Настроит Docker Compose для запуска контейнеров Prometheus и Grafana.

4. Откройте Grafana в браузере
   
   После успешного выполнения команды vagrant up, откройте браузер и перейдите по адресу:
   
   http://localhost:3000
   

6. Авторизация в Grafana
   
   Войдите в Grafana используя стандартные учетные данные:
   
   - Логин: admin
   - Пароль: admin

8. Просмотр дашборда
   
   Перейдите на вкладку "Dashboards" и откройте его.

## Примечания

- Убедитесь, что порт 3000 (для Grafana) свободны на вашей машине.
- После завершения работы с проектом вы можете остановить и удалить виртуальную машину с помощью команд:

  vagrant halt
  
  vagrant destroy

- Dashboard может появиться не сразу, а через несколько секунд после запуска контейнера
