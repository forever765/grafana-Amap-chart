# ���㣺����Amap����ͨMongoDB����Դ��չʾ�й���ͼ
* grafana�汾 v6.2.5
* 20191206����
* ���ܰ�����������ӭ����֧�֣�лл


# 1. ��װ
ֱ�ӽ�������Ƶ�grafanĿ¼�£�Ĭ��Ŀ¼Ϊ/var/lib/grafana/plugins/

# 2. ����grafana
service grafana restart

# 3. ��ΪMongoDB�洢��γ�ȱȽϹ㷺��ѡ��MongoDB����Դ����дSQL
* ����MongoDB����Դ������ã���ο�https://github.com/JamesOsgood/mongodb-grafana
* db.escrowCarInfo.aggregate ( [ 
* { "$match" :   {"point":{"$ne":null, "$exists":true},"overview.soc":{"$ne":null, "$exists":true},"use_nature":{"$ne":1}}  },                  
* {"$project" :   {"����":"$cityName","���ݺ�":"$vin","����":"$modelName","��ɫ":"$carColor","ʹ������":"$use_nature","����":"$licenseNo","�����":"$mileage", "point":"$point", "����":"$overview.soc", "�ϱ�ʱ��":"$pointTime",  "_id" : 0} } ,
* { "$limit":500000},
* { "$skip":2}
* ])
* ע������һ��Ҫѡ��table


# 4. demoͼƬ
* ����, ��������amap key
![Image text](https://raw.githubusercontent.com/ocpeng/grafana-amap-chart/master/grafana-amap-chart/demo/01.png)
* Ч��չʾ
![Image text](https://raw.githubusercontent.com/ocpeng/grafana-amap-chart/master/grafana-amap-chart/demo/02.png)
* ���ܰ�����������ӭ����֧�֣�лл
![Image text](https://raw.githubusercontent.com/ocpeng/grafana-amap-chart/master/grafana-amap-chart/demo/03.png)
