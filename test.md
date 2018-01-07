только создал учетную запись и сразу нашел кучу ошибок
похоже, что эта CRM очень сырая для использования


Правое верхнее меню.
Administrator»Профиль
Вкладка ВНЕШНИЕ УЧЕТНЫЕ ЗАПИСИ
рямо под ней светятся 2 ошибки.
Notice: Undefined index: eapm in /var/www/html/include/SubPanel/SubPanelDefinitions.php on line 748
Notice: Undefined index: eapm in /var/www/html/include/SubPanel/SubPanelDefinitions.php on line 751


При нажатии на кнопку создать роль в верху страницы светится ошибка
 Deprecated: Non-static method ACLRole::getRoleActions() should not be called statically, assuming $this from incompatible context in /var/www/html/modules/ACLRoles/EditView.php on line 78

При создании роли дублированием или при нажатии кнопки редактировать роль ошибка такая.
 Deprecated: Non-static method ACLRole::getRoleActions() should not be called statically, assuming $this from incompatible context in /var/www/html/modules/ACLRoles/EditView.php on line 65

После сохранения роли в верху страницы светится ошибка
 Deprecated: Non-static method ACLRole::getRoleActions() should not be called statically, assuming $this from incompatible context in /var/www/html/modules/ACLRoles/DetailView.php on line 60

В таблице со списком ролей столбик РОЛИ носит название Проектная задача.


В разделе 
 Strict Standards: Declaration of PopupSmarty::setup() should be compatible with ListViewDisplay::setup($seed, $file, $where, $params = Array, $offset = 0, $limit = -1, $filter_fields = Array, $id_field = 'id', $id = NULL) in /var/www/html/include/Popups/PopupSmarty.php on line 46

 Strict Standards: Declaration of PopupSmarty::setup() should be compatible with ListViewDisplay::setup($seed, $file, $where, $params = Array, $offset = 0, $limit = -1, $filter_fields = Array, $id_field = 'id', $id = NULL) in /var/www/html/include/Popups/PopupSmarty.php on line 46

Раздел обновления
В верхней части страницы Проверка системы
Notice: Undefined index: LBL_CURRENT_PHP_VERSION in /var/www/html/modules/UpgradeWizard/uw_utils.php on line 1119
Notice: Undefined index: warn_found in /var/www/html/modules/UpgradeWizard/systemCheck.php on line 191

В верхней части страницы Загрузка пакета обновления 
 Strict Standards: Declaration of ListViewPackages::setup() should be compatible with ListViewDisplay::setup($seed, $file, $where, $params = Array, $offset = 0, $limit = -1, $filter_fields = Array, $id_field = 'id', $id = NULL) in /var/www/html/ModuleInstall/PackageManager/ListViewPackages.php on line 42



Настройки портала
В верхней части страницы
Notice: Undefined index: distribution_options in /var/www/html/modules/Administration/AOPAdmin.php on line 130
Notice: Undefined index: case_status_changes in /var/www/html/modules/Administration/AOPAdmin.php on line 173