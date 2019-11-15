# darknet_http_server
http server for YOLO darknet

clone this under darknet folder.


`sudo apt-get install libopencv-dev  libopencv-dev`
`pip3 install ...`


* daemons
  >cam_daemon.py 文件读取config.json文件cameras信息，上传摄像头获取图片

* templates
  >header.html 基础页面，所有页面继承于此
  >index.html 主页，展示各个相机实时图片，对图片解析出人物、包裹数量
                   显示最近20分钟各分钟数量表格
                   显示当前展示图片创建时间期限，以及设备是否在线
  >stats.html 显示最近一周人数的热力图
  >devices.html 上下分别展示摄像头设备于当前服务器的相关信息
  >settings.html 一个周热力图的样式

* upload
  >存放上传图片

* app.py
  >服务主程序，后端接口写于此

* gen_stats.py
  >对产生的实时数据进行处理，生成分钟、小时整点数据存放于数据库中

* 程序运行
  run.sh
  python3 cam_daemon.py
  python3 gen_stats.py
  三个服务需要同时启动运行