
Zatree for zabbix 2.2.x ��װ
==================================

1�������ļ�

git clone https://github.com/spide4k/zatree.git zatree

2����������ļ�

����zabbix webĿ¼λ����/var/www/zabbix,����zabbixĿ¼

ZABBIX_PATH=/var/www/zabbix

��������ļ���Ŀ¼

cp -rf zatree/zabbix-2.2.x $ZABBIX_PATH/zatree

cd $ZABBIX_PATH/zatree/addfile

cp -f CLineGraphDraw_Zabbix.php CGraphDraw_Zabbix.php CImageTextTable_Zabbix.php $ZABBIX_PATH/include/classes/graphdraw/

cp -f zabbix.php zabbix_chart.php $ZABBIX_PATH/

cp -f CItemValue.php $ZABBIX_PATH/api/classes/

cp -f menu.inc.php $ZABBIX_PATH/include/

cp -f main.js $ZABBIX_PATH/js/

cp -f API.php $ZABBIX_PATH/include/classes/api/


3��֧��web interface,�޸������ļ�

vi $ZABBIX_PATH/zatree/zabbix_config.php

'user'=>'xxx', //web��½���û���

'passowrd'=>'xxx', //web��½������



����
==================================

QQ����Ⱥ��216490997

��������
==================================

1������Ŵ�

���Դ�php����ʾ���󣬿���ʲôԭ��

vi /etc/php.ini

display_errors = On

����web server,Ȼ����web��־

2��Fatal error: Call to undefined function json_encode() in /var/www/html/zabbix/zatree/ZabbixApiAbstract.class.php on line 220

��Ҫphp encode֧��

yum install php-pecl-json

�����������������У��Ҳ���php-pecl-json�����������������

yum install php-pear

pecl install json

echo "extension=json.so" > /etc/php.d/json.ini

3������Ҳ���ʾһ��2��ͼ��˵����ֱ��ʲ��������ϰ���㻻�������������޸�graph.php�ļ����е�widthֵ

    181 <img  src="<?php echo $small_graph; ?>" width="357" height="211" style="float:left;padding-top:4px;padding-left:4px;"  /> </a>

4:�����´���

Warning: array_key_exists() expects parameter 2 to be array, null given in zatree/ZabbixApiAbstract.class.php on line 255

Notice: Trying to get property of non-object in zatree/ZabbixApiAbstract.class.php on line 262

Warning: Invalid argument supplied for foreach() in zatree/graph.php online 130

�ڴ�������޸�php.ini������СΪXXX
memory_limit = XXXM

5:�Ƿ�֧����������ؼ��֣�

֧�֣��ؼ����ö��ŷָ�

6:����ѡ��Ĳ�ֵ��ʲô��˼��

��һ��ʱ������ֵ��ȥ��Сֵ�õ�һ�������Ȼ�����������������ѡ���һ��ʱ���ڵ�ͻ�������鿴�ǳ�����

7: ����������������ip��������������ʾ����������� �༭zabbix_ajax.php 

   43�д���ע��44�򿪣���֧��ip����43�д����44��ע�ͣ�֧��ip����
          43  $new_list[ip2long($each_host->host)]=$each_host;
          44  //$new_list[] = $each_host;

8: ���zabbix��2.2.1�汾���п��ܻᱨ

Call to undefined method CMacrosResolverHelper::resolveItemNames() in zabbix/include/classes/api/CLineGraphDraw_Zabbix.php on line 107
�������������zabbix > 2.2.1



����֧��
==================================

http://weibo.com/spider4k

http://weibo.com/chinahanna

http://weibo.com/678236656


С����
==================================

��������zatree��������а���, <a href="http://me.alipay.com/spider4k">�������</a>���Զ����߽���С����

ף������
