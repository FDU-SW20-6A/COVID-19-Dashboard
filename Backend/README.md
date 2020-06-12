# covid19_be

official back-end repo

## ��Ŀ���з���

�Ⱦ���������װDjango��ܣ�Python 3.x��django-cors-headers��djangorestframework��validators��

### ��װ����

```bash
#Windows:
pip3 install django              #django��װ����
pip3 install django-cors-headers #django-cors-headers��װ����
pip3 install djangorestframework #django rest framework��װ����
pip3 install validators          #validators��װ����

#Mac(δ����):
sudo easy_install pip            #��װpip������Ѱ�װ��������
pip3 install django              #django��װ����
pip3 install django-cors-headers #django-cors-headers��װ����
pip3 install djangorestframework #django rest framework��װ����
pip3 install validators          #validators��װ����
```

### ���з���

```bash
covid19_be>$ python3 manage.py runserver <�˿���># ���Ŀǰʹ�ö˿�8001
```

������`http://localhost:<�˿���>`���ɡ�<br>
����ǰ�����޺�ģʽ������npm��

### �޸ı������ݿ�ķ���

����django���������˿���Ϊ8001��������http://localhost:8001/admin/������superuser���˻������롣

ע��superuser�ķ���Ϊ��

```bash
covid19_be>$ python3 manage.py createsuperuser
```

���������û��������䣨��Ϊ�գ������뼴�ɡ�

#### �鿴Ԫ��

ѡ�����Ӧ�õ�ģ�ͣ������ӦԪ�飬���ɲ鿴Ԫ����Ϣ��

#### �޸�Ԫ��

ѡ�����Ӧ�õ�ģ�ͣ������ӦԪ�飬�޸Ķ�Ӧ��Ϣ����`SAVE`��ť��������޸ġ�

#### ���Ԫ��

ѡ�����Ӧ��ģ�ͺ󣬵��ҳ�����Ͻ�`add`��ť���ɽ�����ӽ��档

#### ɾ��Ԫ��

ѡ�����Ӧ�õ�ģ�ͣ������ӦԪ�飬�޸Ķ�Ӧ��Ϣ����`DELETE`��ť�������ɾ����

�����Ҫ����ɾ��Ԫ�飬������ѡ�����Ӧ�õ�ģ�ͺ�ѡ��Ԫ�����ĸ�ѡ���������˵���ѡ��`Delete selected`ѡ����`GO`��ť�����������ɾ����

## ��������

### ·��

covid19_be/nearby

### ��ɽ���

����ɡ�

ǰ�������������ɡ�����һЩ��ѧ���󣨵�ͼ��Ϣ�����ʱ����ʾ����

### ���÷���

���磺��γ����Ϊ`(30.05,120.66)`��ǰ�����ȵ��øߵµ�ͼAPI��֪�õص�λ�������У����д���Ϊ330600�����û���ѯ��������ʱ��ǰ�������URLΪ

```
/nearby/?lat=30.05&lon=120.66&citycode=330600
```

��˷���һ��json�ַ�����

```json
{
    "mapCenter": {"longitude": 120.66, "latitude": 30.05}, 
    "address": "������", 
    "markers": [
        {
            "position": {"longitude": 120.988632, "latitude": 30.154519}, 
            "title": "�����´�"
        },
        {
            "position": {"longitude": 120.994444, "latitude": 30.148293}, 
            "title": "������·"
        }, 
        {
            "position": {"longitude": 120.379159, "latitude": 30.284556}, 
            "title": "�ζ����������"
        }, 
        {
            "position": {"longitude": 120.389487, "latitude": 30.300031},
            "title": "��ʫ�����ʽ���"
        }, 
        {
            "position": {"longitude": 120.31792, "latitude": 30.295629},
            "title": "�߸�С��"
        }, 
        {
            "position": {"longitude": 121.130834, "latitude": 30.048196}, 
            "title": "�����԰(����·)"
        },
        {
            "position": {"longitude": 121.147633, "latitude": 30.026232}, 
            "title": "���ٹ��ʳ�"
        }, 
        {
            "position": {"longitude": 121.133954, "latitude": 30.178446}, 
            "title": "ƽ������"
        }, 
        {
            "position": {"longitude": 121.10753, "latitude": 30.245701},
            "title": "�����"
        },
        {
            "position": {"longitude": 120.814055, "latitude": 30.468319},
            "title": "���Ѵ�"
        }
    ], 
    "city": "������",
    "totalCase": "42", 
    "currentCase": "0", 
    "nearDis": 33.68,
    "nearLoc": "�����´�",
    "case1": 0,
    "case3": 0, 
    "case5": 0
}
```

����ÿ���ֶεĺ������������API�ĵ���

https://mubu.com/doc/506MXg39K3t

### marker�����޸ķ���

��covid19_be/nearby/views.py�У���41�����������`markersNum`��ĿǰֵΪ10���޸ĸñ�����ֵ���Կ���ǰ����ʾmarker��������

## ����API

### �ĵ�

https://share.mubu.com/doc/2kTqfaDApY7

https://share.mubu.com/doc/2YKmJ6mXsh7

## ע���¼

### ·��

covid19_be/login

### ��ɽ���

���RESTful�ӿڵ�ע���¼������д�á�ǰ�����������ɡ�

�޸�������ʼ���֤��ע�ᡢ�������룩�Ľӿ���д�á�ǰ�����������ɡ�

ע���¼���ֵĵ�Ԫ��������ɡ�

### ���÷���

#### ��¼

URL��http://localhost:8001/user/login/

http������POST

Ŀǰǰ��fakeAccountLogin�������õ���ͨ��POST����json���������¼ʱ������û���������ֱ�Ϊadmin��ant.design����ǰ�˷��͵�json����Ϊ��

```json
{
    "userName":"admin",                 
    "password":"ant.design",
    "type":"account"
}
```

ǰ�˽��յķ���ֵͬ��Ϊjson��ʽ������¼�ɹ�ʱ���������£�

```json
{
    "status":"ok",                      /*״̬��ok��error���֣���Ӧ��¼�ɹ����¼ʧ�ܡ�*/
    "type":"",                          /*��״̬Ϊerrorʱ��type�ֶ���ʾ������Ϣ����״̬Ϊokʱ��type�ֶ�Ϊaccount*/
    "currentAuthority":"user"/"admin"   /*��ǰ�û�Ȩ�ޣ����ƺ�����Ϊuser,admin,guest���֡�*/
}
```

����currentAuthority�²���Ȩ���йء�

#### ע��

URL��http://localhost:8001/user/register/

http������POST

ǰ����Ҫ�ṩjson��ʽ�Ĳ�������ʽ���£�

```json
{
    "username":"",           /*�û���*/
    "password1":"",          /*����*/
    "password2":"",          /*�ظ����룬�������벻һ�·���ע��ʧ��*/
    "email":"",              /*���䣬һ������ֻ��ע��һ���˺ţ����ڿɼ���������֤���ܣ�*/
    "authority":"",          /*�û�Ȩ�ޣ�Ŀǰ����ǰ�˴��룬��Ϊadmin��user����Ȩ�ޣ�*/
}
```

**ע�⣺**ע��ʱ�ṩ������**����Ϊ��**��

��˷��ص�json����Ϊ��

```json
{
    "status":"ok/error",     /*״̬��ok��error���֣���Ӧע��ɹ���ע��ʧ��*/
    "type":"",               /*��״̬Ϊerrorʱ��type�ֶ���ʾ������Ϣ����״̬Ϊokʱ��type�ֶ�Ϊregister*/
}
```

��˻�����һ����֤�룬������˺Ű󶨵����䷢��һ�������֤���ӵ��ʼ����û�������Ӻ󼴿������֤��

#### �ǳ�

URL��http://localhost:8001/user/logout/

http������POST

ǰ���ڵ��øýӿ�ʱ���û�Ӧ�����ڵ�¼״̬�������û���¼ʱ��cookies������ˡ�

��˷��ص�json������ʽΪ��

```json
{
    "status":"ok/error",     /*״̬��ok��error���֣���Ӧ�ǳ��ɹ���ǳ�ʧ��*/
    "type":"",               /*��״̬Ϊerrorʱ��type�ֶ���ʾ������Ϣ����״̬Ϊokʱ��type�ֶ�Ϊlogout*/
}
```

#### �޸�����

URL��http://localhost:8001/user/change/

http������POST

ǰ����Ҫ�ṩ��json������ʽΪ��

```json
{
    "oldpsw":"",		/*���û��������룬������֤���*/
    "newpsw":"",		/*�޸ĺ��������*/
}
```

ǰ���ڵ��øýӿ�ʱ���û�Ӧ�����ڵ�¼״̬�������û���¼ʱ��cookies������ˡ�

**ע�⣺**�޸�����ʱ�ṩ��������**����Ϊ��**��

��˷��ص�json������ʽΪ��

```json
{
    "status":"ok/error",     /*״̬��ok��error���֣���Ӧ�޸ĳɹ����޸�ʧ��*/
    "type":"",               /*��״̬Ϊerrorʱ��type�ֶ���ʾ������Ϣ����״̬Ϊokʱ��type�ֶ�ΪchangePassword*/
}
```

#### ��������

URL��http://localhost:8001/user/reset/

http������POST

ǰ����Ҫ�ṩ��json������ʽΪ��

```json
{
    "username":"",		/*����������˺��û���*/
}
```

��˷��ص�json������ʽΪ��

```json
{
    "status":"ok/error",	/*״̬��ok��error���֣���Ӧ���óɹ�������ʧ��*/
    "type":"",			    /*��״̬Ϊerrorʱ��type�ֶ���ʾ������Ϣ����״̬Ϊokʱ��type�ֶ�ΪresetPassword*/
}
```

��˻Ὣ���˺ŵ���������Ϊ���ֵ��������˺Ű󶨵����䷢��һ��������������ʼ���

## ��������/�����ܱ�

### ·��

covid19_be/login

### ��ɽ���

���RESTful�ӿڵ���Ӷ��ġ��鿴���ġ�ɾ�����Ľӿ���д�á�ǰ�����������ɡ�

��������ܱ��Ľӿ���д�á�ǰ�����������ɡ�

�������ĺ������ܱ��ĵ�Ԫ��������ɡ�

### ����ļ���ַ

���������ļ���covid19_be/login/data/AMap_adcode.csv

### ���÷���

#### �鿴����

URL��http://localhost:8001/user/subscribe/get/

http������GET

ǰ���ڵ��øýӿ�ʱ���û�Ӧ�����ڵ�¼״̬�������û���¼ʱ��cookies������ˡ�

��˷��ص�json����Ϊ��

```json
{
    "status":"ok/error",                /*��״̬Ϊerrorʱ��content�ֶ�*/
    "type":"",                          /*��״̬Ϊerrorʱ��type�ֶ���ʾ������Ϣ����״̬Ϊokʱ��type�ֶ�Ϊsubscribe*/
    "content":[{"name":"","adcode":"",}]/*���ض��ĵ����б��ֶηֱ�Ϊ���ƺ͵�������*/
}
```

#### �޸Ķ���

URL��http://localhost:8001/user/subscribe/post/

http������POST

ǰ����Ҫ�ṩ��json������ʽΪ��

```json
{
    "content":["110101",]/*���û��µĶ��ĵ��������б�*/
}
```

ǰ���ڵ��øýӿ�ʱ���û�Ӧ�����ڵ�¼״̬�������û���¼ʱ��cookies������ˡ�

��˷��ص�json����Ϊ��

```json
{
    "status":"ok/error",                /*��״̬Ϊerrorʱ��content�ֶ�*/
    "type":"",                          /*��״̬Ϊerrorʱ��type�ֶ���ʾ������Ϣ����״̬Ϊokʱ��type�ֶ�Ϊsubscribe*/
    "content":[{"name":"","adcode":"",}]/*���ض��ĵ����б��ֶηֱ�Ϊ���ƺ͵�������*/
}
```

#### �����ܱ�

URL��http://localhost:8001/user/weekly/get/

http������GET

ǰ���ڵ��øýӿ�ʱ���û�Ӧ�����ڵ�¼״̬�������û���¼ʱ��cookies������ˡ�

��˷��ص�json��������ǰ��Ҫ���д���˴�ʡ�ԡ�